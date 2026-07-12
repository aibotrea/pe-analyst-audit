# METHODOLOGY.md

Authoritative source for all investment rules. Committed to
`aibotrea/pe-analyst-audit` before any position is logged.

Rules are not amended retrospectively. Changes are logged as new commits
to this file with rationale in the commit message. All prior versions
remain in Git history. The committed version of this file at the time a
position is logged is the methodology under which that position is
governed.

**Provenance.** This repository begins with this commit. An earlier build
of the platform ran a preparatory track from June 2026 under a prior
methodology. That record was retired before any quarterly publication and
its repository is archived and no longer public. No position, decision,
or outcome from that period carries into the record published here, and
no performance figure published here draws on it. The track record begins
at the first position logged under this document.

---

## 1  Platform Identity and Scope

### 1.1  Purpose

The PE Analyst Platform produces investment analysis on public REITs in
the APAC region and operates two parallel simulated portfolios on that
analysis. Both portfolios are auditable in public via the audit
repository and Substack publication. The platform is a personal
research and capability project; it does not place live trades, does not
hold client capital, and is not regulated.

### 1.2  Universe

In scope: equity REITs listed on the Singapore Exchange (SGX), Tokyo
Stock Exchange (TSE), Hong Kong Stock Exchange (HKEX), and Australian
Securities Exchange (ASX). Australian stapled securities are treated as
a distinct instrument type within the equity REIT scope.

Out of scope: REIT credit and bonds (insufficient publicly traded APAC
instruments with free price data); private real estate; non-REIT listed
property companies.

Universe membership is determined by structural filters applied to a
candidate set sourced from each exchange's REIT listing:

- Market capitalisation ≥ USD 300 million (FX-converted at the
  assessment date's spot rate)
- Average daily traded value ≥ USD 750,000 (60-day trailing)
- Trading history ≥ 200 trading days

The filters define the universe; the universe is therefore expected to
change over time as instruments cross thresholds. The universe table in
SQLite is the canonical source of truth.

Universe maintenance: monthly drift check (Airflow `universe_maintenance`
DAG, 06:00 SGT on the 1st of each month). The drift check compares
yfinance metadata to the universe table and logs differences to
`universe_drift_log`. Additions and removals to the universe table
between rebuilds are recorded with `added_date` and `removed_date`;
backtests respect `removed_date` so universe state at any historical
`as_of` is recoverable.

Delisting handling: when a ticker is removed from an exchange (suspension
that becomes permanent, takeover completion, voluntary delisting), the
position is exited at the last available market price on that ticker.
The universe row is marked with `removed_date` set to the delisting
date.

### 1.3  Reporting Currency and Capital Base

Each track operates a simulated capital base of USD 10,000,000. All
performance, exposure, and risk metrics are computed in USD. Foreign
currency exposures are translated at the spot rate from the price
server's `get_fx_rate` at the relevant decision or report timestamp.
Historical valuation and attribution read point-in-time rates from the
`fx_history` table through the same interface, so a USD figure computed
for a past date uses the rate that prevailed on that date, not today's.
Distribution income is the single exception: its USD value is fixed at
the rate prevailing when it was posted and is never re-marked (§8.6).

Idle (uninvested) capital accrues daily at the FRED 3-month Treasury
Bill rate (series `DTB3`). The daily rate is `dtb3_annual / 365`,
matching FRED's published bond-equivalent yield convention. Accrual is
applied on each calendar day at the prior business day's published
DTB3.

Idle balance at any `as_of` is computed as:

```
idle = capital_base
        + realised_pnl_lifetime
        + accrued_cash_interest
        + distributions_lifetime
        − Σ value_usd_at_entry over open legs
```

Distributions (§8.6) are received as cash and are not reinvested, so they
enter the idle base and accrue DTB3 from the date of receipt onward.

The market-value term that appears in NAV (§8.5) cancels with the
invested-at-market subtraction in this identity, so idle is independent
of current prices. Every term above is either a constant or a booked USD
cash amount. Historical reconstruction of idle at any `as_of` is therefore
exact without historical price data.

### 1.4  Transaction Costs

25 basis points each way (entry and exit), applied without exception or
waiver, on the local-currency notional value of each trade. Costs are
deducted from cash at the moment of execution and recorded on the
position leg.

---

## 2  Twin-Track System

Two parallel portfolios run on identical inputs and inherit the same
universe, methodology, and reviewed memos. Their decision-making
mechanism differs.

| Aspect | Track A (Portfolio A) | Track B (Portfolio B) |
|---|---|---|
| Decision maker | GP agent — single LLM batch call per cycle | IC (operator) — per memo, with optional LLM challenge mode |
| Memo-flow actions | accept_as_proposed, accept_with_downgrade, reject | + no_action_timeout (Track B only) |
| Rebalance-flow actions | hold, partial_dispose, complete_dispose | + hold_inaction (Track B only) |
| Memo timeout | None | 7 days → no_action_timeout |
| Rebalance window | None (single batch) | 24 hours per position → hold_inaction |
| Vector log collection | gp_predictions | ic_feedback_corpus |
| Learning loop | Outcome-only (predictions vs realised) | Rationale + outcome |
| Override discretion | None | Permitted; logged at entry; auditable |

Track A is fully autonomous. Track B requires operator input on every
position decision and applies operator judgement that may differ from
the reviewed memo's implied action.

The two tracks operate independently in time. Track A's GP batch runs
on its weekly schedule regardless of Track B's queue state or operator
response timing. A Track B memo expiry or a Track B rebalance-window
timeout has no effect on the Track A position book.

### 2.1  Segregation

Track A and Track B share data sources, universe, framework,
reviewer-approved specialist memos, execution layer, and portfolio
accounting. They do not share decision logs.

Reviewer approval is a structural and quality gate — it validates
schema, gate identity, scenario monotonicity, thesis substance, risk
completeness, and invalidation specificity. The Layer 2 (semantic)
reviewer additionally retrieves prior IC feedback for the relevant
market from `ic_feedback_corpus` and includes it as context, so quality
standards calibrate against accumulated IC override patterns over time.
Reviewer approval is not an investment recommendation; investment
judgement is the responsibility of the GP (Track A) and IC (Track B).

Architectural segregation is enforced two ways:

1. Static AST analysis. Track A code (`agents/gp/`) may not import from
   `agents/ic/*` or `memo_queue/*`. Track B code (`agents/ic/`) may not
   import from `agents/gp/*`. Both may import shared modules
   (`decisions`, `execution`, `portfolio`, `llm`, `quant`, `review`,
   `mcp_servers`, `orchestrator`).

2. Runtime instrumentation. A Track A decision log call must increment
   `gp_predictions` count and not `ic_feedback_corpus`. A Track B
   decision log call must do the reverse.

Both checks are part of the platform's continuous integrity suite and
must pass before any deployment that touches the decision path.

### 2.2  Override Discipline

Track B is the only track that may diverge from a reviewed memo's
implied action. Divergence is captured in the decision record at the
moment of entry — `executed_size_pct`, `reason_class`, `reason_text`,
and `binding_constraint` together describe the override. The decision
record is committed to the audit repository alongside the memo it
overrides. Overrides cannot be re-classified or re-explained after the
fact.

Track A does not override. The GP system prompt is the canonical
mandate; the LLM's structured output is parsed and validated against the
schema; any decision that does not match the schema is recorded as a
batch failure for later review and the next batch proceeds.

---

## 3  Quantitative Framework

Three layers computed in deterministic order on every memo.

### 3.1  Monte Carlo Simulation (Ornstein-Uhlenbeck)

Only the Ornstein-Uhlenbeck process is used for memo Monte Carlo.

10,000 iterations per seed; 5 seeds; results averaged across seeds.
Cross-seed mean range is reported alongside the result for stability
diagnosis.

Process: detrended Ornstein-Uhlenbeck on residuals.

```
dx_t = -theta * x_t * dt + sigma * dW_t
final return = base_return * horizon_years + x_T
```

`base_return` supplies the drift; OU adds mean-reverting noise around
zero. Theta is estimated from historical price data where the estimator
returns a stable value; where estimation is unreliable or data is
insufficient, theta defaults to `1.0 / horizon_years` and the use of
the default is recorded on the memo.

Rationale: REIT total returns exhibit mean reversion at investment-
relevant horizons (occupancy mean-reverts; cap-rate moves are bounded by
underlying rent; distributions stabilise around AFFO). A normal random
walk produces horizon variance that grows linearly; the OU asymptote at
`sigma² / (2 * theta)` captures the bounded nature of REIT total-return
dispersion.

Self-audit: the closed-form variance `(sigma² / (2 * theta)) *
(1 - exp(-2 * theta * T))` is computed alongside the simulation. The
simulated standard deviation must fall within 5% of the closed-form
value or the simulation is flagged.

Outputs: simulated mean return, standard deviation, empirical PGain
(fraction of paths with positive return), the closed-form standard
deviation (for self-audit), the cross-seed mean range (for stability
assessment), and the theta value used.

### 3.2  PGain

PGain is the probability of positive return over the simulation horizon.

```
PGain = 1 - Φ(-E(R) / σ)
```

computed from the simulated mean return and standard deviation. PGain
is the platform's primary conviction metric and maps to the conviction
table (§4.1).

Worked example: `E(R) = 21%`, `σ = 20%`. `Z = -0.21 / 0.20 = -1.05`.
`PGain = 1 - Φ(-1.05) ≈ 0.853`. A high `E(R)` with high volatility
can have a lower PGain than a modest `E(R)` with low volatility; PGain
penalises uncertainty regardless of upside potential.

### 3.3  CAPM

`required_return = Rf + β(Rm - Rf)`; `alpha = E(R) - required_return`.

`Rf` is the current FRED DTB3 rate. `Rm` is the trailing benchmark
return computed by the returns module's `calculate_benchmark_return`
over a 1260-trading-day (5-year) trailing window. `β` is the OLS slope
of the ticker's local-currency daily returns regressed against the
benchmark's GBP-denominated daily returns over a 252-trading-day
(approximately 12-month) trailing window (see §3.4 caveat).

CAPM output is supporting context, not the primary conviction driver.
PGain governs sizing; CAPM informs the narrative case.

### 3.4  Benchmark Beta and Currency-Basis Caveat

The platform benchmark is **IASP.L** (iShares Asia Property Yield UCITS
ETF, LSE-listed, GBP-denominated).

IASP.L is the platform's only benchmark. APAC REITs trade in local
currencies (SGD, JPY, HKD, AUD). When the returns module regresses a
REIT's local-currency closes against IASP.L's GBP-denominated closes,
the computed beta absorbs both property co-movement and FX co-movement.
CAPM alpha derived from this beta inherits the FX noise.

Treatment:

- Beta is classified as **Category B** (derived estimate; methodology
  disclosed). The memo schema rejects memos that omit the currency-
  basis caveat from `key_assumptions`.
- The beta regression runs on the raw GBp price series. It is neither
  FX-adjusted nor distribution-adjusted, and the platform does not
  construct per-market REIT benchmarks. The single-benchmark choice is
  retained for consistency and for the Substack reader's audit
  experience.
- *Future enhancement.* If calibration review establishes that this
  currency-basis noise materially drives mis-calibration, an
  FX-adjusted benchmark or per-market benchmark composition will be
  considered.

**Scope.** This section governs the beta factor only. The same ETF is
also the platform's performance benchmark, where it *is* restated to USD
and *is* measured on a total-return basis. The two uses apply different
transforms to the same underlying series, and the caveat above does not
carry across to the published performance comparison. See §8.7.

### 3.5  Input Classification

Every memo input is classified. Pydantic memo schema rejects memos that
omit classification.

| Category | Definition | Examples |
|---|---|---|
| A | Observed public data | Closing price, published DPU, filed leverage ratio |
| B | Derived estimates with disclosed methodology | Beta vs benchmark, NAV from DCF, forward DPU forecast |
| C | Model assumptions requiring disclosed basis and sensitivity | Terminal cap rate, discount rate, growth rate beyond consensus |

Category A inputs are not debatable — they are what the filings or the
market say. Category B inputs are reproducible — anyone applying the
same method to the same observed data should reach the same number.
Category C inputs are where analytical judgement lives.

Each Category C input must state, in the memo:

- The specific assumption (e.g. "rental growth of 3% p.a. for years 1-3")
- The basis for the assumption (e.g. "5-year historical average for
  Singapore CBD office is 2.8%; URA planning pipeline suggests
  tightening supply")
- The sensitivity (e.g. "PGain falls from 0.78 to 0.62 if growth is 1%
  for the first three years")

A memo with a high proportion of Category C inputs should carry lower
conviction, captured via the qualitative gates (§3.6).

*Future enhancement.* The current memo schema validates the
classification field on each input but does not enforce per-Cat-C
sensitivity disclosure. Schema-level enforcement of the
assumption / basis / sensitivity triplet is a planned tightening.

### 3.6  Qualitative Gates

Qualitative gates supplement the quantitative chain. Each gate carries
a `status`, an `override` integer in `[-2, 0]` (downward only), and a
`rationale`. Gate identity is checked against
`analysis/equity_reit_framework.json` — a gate id that is not in the
framework registry is rejected at the mechanical reviewer.

Cumulative override floor is `-4` across all gates; per-gate maximum is
`-2`. Override is downward only — gates can reduce conviction below the
quantitatively-implied score, never raise it above.

---

## 4  Conviction and Sizing

### 4.1  Conviction Score to Target Weight

| Conviction score | Target ticker weight |
|---|---|
| 1 | 1% |
| 2 | 3% |
| 3 | 5% |
| 4 | 8% |
| 5 | 12% |

This mapping is implemented in `quant/scoring.py::get_conviction()` and
referenced (not redefined) by every consumer in the platform.

### 4.2  PGain Floors per Conviction Score

PGain must meet a minimum threshold to support each conviction score:

| Conviction score | PGain floor |
|---|---|
| 5 | ≥ 0.85 |
| 4 | ≥ 0.70 |
| 3 | ≥ 0.55 |
| 2 | ≥ 0.40 |
| 1 | (no floor) |

PGain below 0.40 yields a conviction of 1 by floor, regardless of other
inputs.

### 4.3  Conviction Semantics

Memo conviction expresses a standalone view of instrument merit on
quantitative inputs after qualitative gate overrides. The
conviction-implied target ticker weight is the post-decision target,
not a transaction delta. The GP or IC reconciles the implied target
with the current portfolio state, and the execution layer computes the
implied transaction:

- target > current → acquire delta
- target < current → trim delta
- target = current → no-op

---

## 5  Hard Caps and Floors

Caps are enforced at the input layer. The effective ceiling for a
candidate position is computed at every action prompt as the minimum of
the four binding caps applied to the current portfolio snapshot. The
operator (Track B) and the GP system prompt (Track A) cannot size above
the ceiling. The decision schema additionally records observed
concentration as data — caps are hard at the input layer; the schema
captures shape; periodic calibration reviews analyse any retrospective
breach patterns.

| Constraint | Limit | Source |
|---|---|---|
| Single position | 12% (= conviction-5 ceiling) | `portfolio/cap_arithmetic.py::SINGLE_POSITION_CAP_PCT` |
| Country exposure | 35% | `COUNTRY_CAP_PCT` |
| Sector exposure | 30% | `SECTOR_CAP_PCT` |
| Total invested | 95% (cash floor 5% implied) | `TOTAL_INVESTED_CAP_PCT` |
| Min position | 1% (= conviction-1 floor) | `MIN_POSITION_PCT` |

When a memo's conviction-implied target exceeds the effective ceiling,
the GP or IC has four options:

1. **Downgrade.** Size at or below the ceiling. `accept_with_downgrade`
   with `reason_class = downgrade_concentration` and `binding_constraint`
   naming the binding cap.
2. **Reject.** `reason_class` in the reject family.
3. **Make room.** Trim other holdings to lift the ceiling, then accept
   at conviction-implied target. `dispose_list` entries carry
   `reason_class = make_room`. Track B only — the GP equivalent is the
   Phase A → Phase B → Phase C iterative subtractive flow within the
   batch evaluator.
4. **Defer.** Track B may return the memo to the queue. Track A's batch
   does not defer; it produces a decision per memo or records a
   validation failure.

Below the conviction-1 floor (1%), the action is `reject_capacity`.

---

## 6  Decision Vocabulary

The decision schema is the single source of truth tying GP, IC,
rebalance, execution, and quarterly review scoring together. Every
decision across both tracks is recorded as a `DecisionRecord` and
persisted to the `decisions` SQLite table.

### 6.1  Flow Contexts

| Flow context | Track | Source | Notes |
|---|---|---|---|
| memo_triggered_a | A | Specialist memo (reviewer-approved) | Single GP batch over pending memos |
| memo_triggered_b | B | Specialist memo (reviewer-approved) | Per-memo IC decision via queue |
| rebalance_a | A | Weekly Track A rebalance batch | Sunday 19:00 SGT cycle |
| rebalance_b | B | Per-position 24h Track B window | Operator decides each via IC CLI |
| cap_resolution_a | A | GP subtractive iteration during batch | Trim other holdings to clear caps for new accepts |

### 6.2  Actions

| Action | Memo flow | Rebalance flow | Track restriction | executed_size_pct |
|---|---|---|---|---|
| accept_as_proposed | Yes | No | Both | = conviction_implied_pct |
| accept_with_downgrade | Yes | No | Both | < conviction_implied_pct |
| reject | Yes | No | Both | None (no transaction) |
| no_action_timeout | Yes | No | Track B only | None (memo expired) |
| hold | No | Yes | Both | None (position unchanged) |
| hold_inaction | No | Yes | Track B only | None (rebalance window passed) |
| partial_dispose | No | Yes | Both | New target weight, < current |
| complete_dispose | No | Yes | Both | 0.0 (full exit) |

`executed_size_pct` is the post-decision target ticker weight, not the
transaction size.

### 6.3  Reason Classes

Reason class is required on every decision. The vocabulary is fixed:

| Reason class | Used with |
|---|---|
| accept_routine | accept_as_proposed (standard accept within caps) |
| accept_caveated | accept_as_proposed (accept with explicit caveats) |
| downgrade_concentration | accept_with_downgrade (cap-driven; `binding_constraint` required) |
| downgrade_judgement | accept_with_downgrade (judgement-driven; `binding_constraint` must be null) |
| reject_thesis_disagreement | reject |
| reject_better_alternative | reject |
| reject_capacity | reject (below conviction-1 floor after ceiling) |
| reject_other | reject |
| invalidation_triggered | partial_dispose, complete_dispose (rebalance) |
| thesis_decay | partial_dispose, complete_dispose (rebalance) |
| make_room | dispose_list entries on accept_as_proposed / accept_with_downgrade (IC only) |
| hold_thesis_intact | hold (rebalance) |
| cap_resolution | cap_resolution_a dispose_list entries |

`binding_constraint` is required only when `reason_class =
downgrade_concentration` (names the binding cap) or
`flow_context = cap_resolution_a` (names the cap the dispose was
intended to resolve). For `downgrade_judgement` it must be null.

### 6.4  Dispose List Semantics

- Allowed on `accept_as_proposed` and `accept_with_downgrade` (make-
  room trims that ride alongside a new acquisition; IC only). Each
  entry must use `reason_class = make_room` and cannot reference the
  memo ticker.
- Required exactly one entry on `partial_dispose` and `complete_dispose`.
  The entry ticker must match the decision ticker and the entry mode
  must match the action.
- Empty for all other actions.

### 6.5  Reason Text Minimum

Memo-flow decisions: reason_text ≥ 50 characters.
Dispose-entry reason_text: ≥ 30 characters.

### 6.6  Stable Identifiers

| Identifier | Format |
|---|---|
| memo_id | `{ticker}_{as_of}_{framework_version}_{md5(content)[:12]}` |
| decision_id | `{track}_{flow_context}_{ticker_safe}_{ts}_{hash[:8]}` |
| cycle_id | `A_cycle_{decided_at_iso}_{md5(memo_ids)[:8]}` (Track A batch only) |

Re-running on identical inputs produces identical IDs. ChromaDB upsert
is idempotent on these IDs. Track B records and rebalance records
carry `cycle_id = null` (schema-enforced).

### 6.7  Framework Version

Every memo carries `framework_version` (e.g. `equity_reit_v1@1.0`)
populated from `analysis/framework.py::get_framework_version()`. The
field name in the memo JSON is `framework_slug`. Decisions also carry
the framework version under which the memo was produced.

---

## 7  Memo Generation Cadence

### 7.1  Trigger Model

Memos are generated on an event-driven basis with time-based ceilings
and a daily cap. Memo generation is not on a fixed batch schedule —
memos enqueue individually as generated.

Triggers (priority order):

1. Filing-event arrival for a held position → ticker queued for the
   next morning's specialist batch.
2. Held position with no memo refresh in the last **21 days** → forced
   refresh queued.
3. Filing-event arrival for an unheld universe ticker → queued.
4. Unheld universe ticker with no memo refresh in the last **90 days**
   → forced refresh queued.

### 7.2  Daily Generation Cap

A maximum of **5 memos per day** is generated. When the cap binds,
prioritisation follows the trigger order above. Surplus rolls to the
following day. The 21-day held ceiling ensures the rebalance flows
always operate on a recent thesis view.

### 7.3  Memo Distribution

Each generated memo passes the two-layer reviewer (mechanical then
semantic). Reviewer-approved memos are written to the `analyst_outputs`
ChromaDB collection and automatically enqueued to the Track B memo
queue. Track A's GP batch evaluator reads reviewer-approved memos from
`analyst_outputs` (cross-referenced against the `decisions` table to
exclude already-decided memos) on each cycle.

### 7.4  Memo Expiry (Track B)

A Track B memo enqueued for IC review expires 7 calendar days from
enqueue. Unprocessed expired memos generate a `no_action_timeout`
decision in the Track B log via the queue sweep (daily, 08:00 SGT).

---

## 8  Execution, Position Accounting, and Performance Measurement

### 8.1  Multi-Leg Position Model

A position in a ticker on a track is composed of one or more **legs**.
Each leg corresponds to one acquisition decision and records its own
entry date, entry price, units, cost basis, decision id, and status
(open / closed). The composite uniqueness is `(track, ticker,
entry_date, decision_id)`.

Multiple legs exist when a ticker is acquired more than once on the
same track — for example, an initial conviction-3 acquisition followed
by an upgrade to conviction-4 that triggers an additional acquire delta.
Per-leg cost basis is preserved through partial trims.

### 8.2  Disposal — FIFO

Disposals draw down legs in first-in-first-out order across the legs
open at the time of disposal. A `partial_dispose` that fits inside the
first leg leaves later legs untouched. A larger partial closes earlier
legs in their entirety and reduces a later leg by the remainder. A
`complete_dispose` closes all legs of the ticker on that track.

Realised P&L is recorded **per leg**, not at ticker level. This is the
cost-basis-preserving accounting required for honest attribution.

`realised_pnl_usd` accumulates over the life of the leg. It is null until
the leg's first disposal; each partial trim adds that trim's realised
P&L; the final close adds the closing P&L. The leg's cost basis
(`value_usd_at_entry`) is pro-rated down at each partial trim, so the
units still held carry their proportionate share of the original cost.

A leg that is still **open** can therefore already carry realised P&L,
booked on earlier trims. Any NAV or attribution computation that sums
realised P&L must include open legs. Filtering to closed legs alone
silently drops the entire trim book, and the resulting error is
directional — it flatters a track that trims into strength and penalises
one that does not.

### 8.3  Board-Lot Rounding

Acquisitions and disposals round share counts to each market's minimum
trading lot. Lot sizes are stored as a per-ticker `board_lot` column on
the universe table, with the per-market default as a fallback for any
unspecified ticker:

| Market | Default lot |
|---|---|
| Singapore | 100 |
| HongKong | 1000 |
| Japan | 100 |
| Australia | 1 |

### 8.4  Price Capture

| Track | Execution price |
|---|---|
| A | Quote at GP decision timestamp via `get_execution_price` (atomic) |
| B | Quote at IC approval timestamp via `get_execution_price` (atomic) |

Track B remote operators decide within a 24-hour window per memo or
rebalance position; the price is captured at the operator's actual
decision timestamp, not the window-open time.

A 3% price staleness gate applies to Track B: if the quote at decision
time differs from the quote at memo-generation time by more than 3%,
the operator is alerted and the memo's quantitative inputs are
re-evaluated before execution.

### 8.5  NAV Computation

```
NAV = capital_base
    + realised_pnl_lifetime
    + unrealised_pnl
    + accrued_cash_interest
    + distributions_lifetime
```

`realised_pnl_lifetime` sums `realised_pnl_usd` across **all** legs, open
and closed (§8.2).

`accrued_cash_interest` accrues daily on idle USD at the simple-interest
daily rate (§1.3). Inter-day compounding arises implicitly through the
NAV→idle path: NAV includes prior accrued interest, so each day's idle
USD opens at a slightly higher base. Accrual is applied on each calendar
day, including weekends and holidays, at the prior business day's
published DTB3 rate.

`unrealised_pnl` is computed at the close of each business day for
reporting and rebalance purposes.

`distributions_lifetime` is the gross USD value of every distribution
received, fixed at posting FX (§8.6). It is a term **distinct** from
`accrued_cash_interest`: the former is income received from the holdings,
the latter is interest earned on idle cash — including on distribution
cash, once received.

---

### 8.6  Distribution Accounting

APAC REITs distribute a large share of their total return as income. A
price-only book would understate the return of the strategy it claims to
measure, so distributions are booked explicitly.

**Entitlement.** A distribution is booked to a leg if the leg was held on
the distribution's **ex-date**. Units held on the ex-date determine the
entitlement; units acquired after it do not participate.

**Amount.** Distributions are booked **gross**. Withholding tax is not
modelled. Several APAC jurisdictions levy withholding on REIT
distributions paid to a non-resident holder, so the income recorded here
is larger than the income a real non-resident investor would net. This is
a disclosed simplification, not an oversight: it applies uniformly across
the universe and across both tracks, and it is stated here so that no
published return figure is read as a post-tax figure.

**Currency.** The USD value of a distribution is computed at the spot rate
prevailing when it is posted, stored, and **never re-marked**. A
distribution received is cash received; its USD value does not float with
subsequent FX movement. This is why §1.3's point-in-time FX convention
carries an explicit exception.

**Treatment after receipt.** Distributions are **not reinvested**. They are
received as cash and held as idle capital, where they accrue DTB3 under
§1.3 like any other idle USD. The platform does not model a dividend
reinvestment plan.

**Reporting.** `distributions_lifetime` is a distinct NAV term (§8.5) and
is not folded into realised P&L. Income return and price return are
therefore separable at every point in the record.

---

### 8.7  Performance Measurement and Benchmark Basis

The performance benchmark is IASP.L, the same ETF used for the beta factor
in §3.4 — but the two uses are not the same measurement, and §3.4's
currency caveat does not carry across to this section.

**Total return, not price.** IASP.L is a distributing ETF. Measuring it on
raw closing prices would understate its return and flatter the tracks by
construction. The benchmark is therefore made total-return by the same
operation applied to the book: an explicit ledger of the benchmark's
distributions, added to its price level.

The platform does **not** use a vendor-adjusted (back-adjusted) close for
this purpose. An adjusted-close series is a *reinvested* total-return
series — it compounds income back into the price. The book does not
reinvest (§8.6); it holds distributions as idle cash. An adjusted-close
benchmark would therefore compound income that the book leaves flat, and
the comparison would be dishonest in a way that grows with time. An
explicit ledger is also inspectable against the ETF's published payment
record, and it is stable: back-adjusted prices are rewritten by the vendor
every time a new distribution is declared, which would silently rewrite
the platform's own history.

**Symmetry of income booking.** Benchmark distributions are booked on the
identical convention to the book's own: ex-date entitlement, gross, USD
value fixed at posting FX and never re-marked. Both ledgers begin empty at
inception and post forward.

**Dual currency basis.** The benchmark is quoted in GBp; the tracks are
USD. Two figures are published side by side for every period:

- `benchmark_twr_gbp` — the benchmark's return in its native currency.
- `benchmark_twr_usd` — the benchmark restated to USD at point-in-time
  rates (§1.3), which is the like-for-like comparison against a USD book.

The **difference between the two active-return figures is the currency
contribution**, isolated and reported rather than disclaimed. Neither is
suppressed: the native-currency figure is what the instrument did, and the
USD figure is what a USD investor would have experienced.

**The currency term is noisy over short windows.** An endpoint-to-endpoint
return measured over a few weeks can have its FX component change sign on
a shift of a day or two in the start date. Over such windows the currency
contribution is noise, not signal. It is published anyway, with this
caveat attached, on the same principle that governs every thin-sample
metric on this platform (§13.7): the figure is illustrative until the
window is long enough to support inference, and the reader is told which
it is. Suppression would be the greater dishonesty.

**Known divergence: idle cash.** The book earns DTB3 on distribution cash
once received (§1.3, §8.6). The benchmark's distribution income is held
flat and earns nothing. The two sides are therefore **symmetric on
booking** and **asymmetric on treatment after receipt**. This is a
persistent, one-directional tailwind to both tracks, equal to DTB3 on
accumulated distribution cash. It is immaterial over short windows and
grows with the length of the record.

It is disclosed rather than corrected. Accruing interest on a
notional index's income would be inventing a cash-management policy the
index does not have. The asymmetry is intrinsic to comparing a
cash-managed book against an index level, and it is named here so that a
reader assessing the multi-year record knows to discount for it.

**Reporting horizons.** Two windows are reported:

- **Year to date**, clamped to inception. A window that opens before the
  first position was taken reports from inception, not from the calendar
  boundary — otherwise "year to date" is lifetime wearing a shorter label.
  The clamp self-disables from the second year onward.
- **Since inception**, from the first position to the reporting date.

In the first partial year the two are identical by construction. That is
informative, not an error.

**Absent must be visibly absent.** A performance figure that cannot be
computed is reported as `n/a`. It is never rendered as zero. A hardcoded
zero is indistinguishable from a real flat return, and on a platform whose
entire premise is auditability, a plausible false number is worse than a
visible gap. This rule binds every published figure without exception.

---

## 9  Rebalance Cadence

### 9.1  Track A Weekly Rebalance

Track A weekly rebalance runs **Sunday 19:00 SGT** via the
`rebalance_track_a` Airflow DAG. The GP evaluates the open Track A
position book in one batch. Per ticker, the GP issues `hold`,
`partial_dispose`, or `complete_dispose` with the relevant rebalance
reason class (`hold_thesis_intact`, `invalidation_triggered`,
`thesis_decay`). All decisions log to `decisions` and `gp_predictions`
through the Track A two-sink write.

### 9.2  Track B Weekly Rebalance

Track B opens a 24-hour rebalance window per open Track B position at
**Sunday 19:00 SGT**. Operators decide each via the IC CLI within the
window. Windows that expire without a decision sweep to `hold_inaction`
via the `rebalance_b_sweep` DAG (**daily 20:00 SGT**), which records the
hold_inaction decision and links the window to it.

### 9.3  Memo-Queue Sweep

The 7-day memo expiry sweep runs **daily at 08:00 SGT**. Expired memos
generate `no_action_timeout` decisions in the Track B log.

---

## 10  Notification Policy

### 10.1  Track B Operational Notifications (OpenClaw to phone)

- Memo expiry warning: **48 hours** before expiry, then **24 hours**
  before expiry.
- Rebalance window warning: **24 hours** before expiry, then **6 hours**
  before expiry.

No enqueue notification. No cap-breach notification (caps are
structural; no breach is reachable). No Track A operational
notifications.

### 10.2  Email Notifications (immediate)

- HK filing staleness reminder (Monday 09:00 SGT, weekly).
- SGX 403 token expiry (auth-token preflight failure).
- Airflow DAG failure (any DAG, both tracks, ingestion, sweeps,
  rebalance).
- Atomicity reconciliation finds orphan rows.
- Publish-before-log enforcement blocks a log call (methodology
  violation attempt).
- Restic backup failure.

### 10.3  Weekly Status Reports (Sunday 09:00 SGT)

Three separate reports, each addressing one domain. Each report is sent
as an email; Track A and Track B reports additionally trigger a
portfolio-only headline notification via OpenClaw to phone.

| Report | OpenClaw headline (phone) | Email content |
|---|---|---|
| Track A weekly status | Positions count, NAV, total invested %, idle cash %, country exposure, sector exposure | Full position list with weight, conviction, days held; exposures vs caps (observational); year-to-date and since-inception TWR against the benchmark on both currency bases (§8.7); week's GP decisions summary |
| Track B weekly status | Same metrics + queue pending count | Same as Track A + week's IC decisions summary + queue ageing |
| Platform technical | None — email only | DAG run summary, ingestion freshness per source, atomicity reconciliation result, Restic backup status, SQLite integrity check, disk usage, ChromaDB collection counts |

OpenClaw headlines contain zero technical or DAG content.

Return figures follow §8.7: windows are clamped to inception, and any
figure that cannot be computed is reported as `n/a`, never as zero.
Before the first position is taken, the reports state that there is no
track record rather than reporting a return on a synthetic base.

---

## 11  Publication Discipline

### 11.1  Audit Repository

`github.com/aibotrea/pe-analyst-audit` (public). Branch protection
active: force push blocked, deletions blocked, no PR requirement (the
agent commits directly to `main`). Errors are corrected by new commits;
history is never rewritten.

Repository structure:

```
METHODOLOGY.md              this file
README.md                   repository title
memos/                      Specialist memo history (twin format: A and B)
outcomes/                   Quarterly scoring with attribution
portfolio_a/                Track A position memos and outcomes
portfolio_b/                Track B position memos with override metadata
```

### 11.2  Twin Memo Format

Every position decision results in a twin memo pair:

- One memo for Track A, recording the GP decision and the underlying
  specialist memo.
- One memo for Track B, recording the IC decision (override or
  acceptance) and the underlying specialist memo.

Both memos in a pair reference the same source specialist memo by
`memo_id`. The pair is committed to `~/pe-analyst-audit/memos/` in a
single commit per position event.

### 11.3  Publish-Before-Log Rule

The twin memo pair must be committed and pushed to the audit repo on
GitHub **before** any position is logged to the `decisions` table or
written to `gp_predictions` / `ic_feedback_corpus`. This rule is
enforced programmatically:

- A pre-log check confirms the twin memo pair exists on `origin/main`
  and the commit is reachable from the audit repo's HEAD before the
  decision is permitted to write.
- If the check fails, the log call raises and the failure is emailed
  (§10.2).
- No exception. No retroactive logging is permitted.

`METHODOLOGY.md` must be committed to `origin/main` before the first
position is logged.

### 11.4  Substack Publication

Substack is the platform's public-facing publication channel. Posts are
published in the following categories:

- **Methodology launch and amendments** — published on commit of
  `METHODOLOGY.md` (initial and any subsequent amendment commit).
- **Twin memo posts** — published as positions are taken; each post
  references the audit-repo commit hash of the twin memo pair.
- **Quarterly review** — published at the close of each quarter (§13).

Every Substack post that references a position, a memo, or a
methodology rule includes the audit-repo commit hash of the referenced
artifact. The Substack post is not the authoritative record; the audit
repo commit is. The Substack post is the narrative wrapper for the
audit-repo record.

Publication is **manual**. No scheduled job publishes to Substack, and
none is planned; the operator reviews every post before it goes out. The
absence of automation here is not a gap — it is the point at which a
human is required to stand behind what is published.

Each quarterly cycle writes three artefacts to the audit repository under
`outcomes/{quarter_id}/`:

- `report.json` — machine-readable canonical record of every decision in
  the period and every computed metric.
- `report.md` — human-readable summary.
- `substack_draft.md` — operator-editable draft of the public post.

The quarterly post carries, subject to operator judgement at publication
time: the headline (total return in USD, excess return against the
benchmark on both currency bases, position count); a prose account of the
period; PGain calibration against baseline; override patterns and their
outcomes; the cap-breach summary; and a link to this methodology.

### 11.5  Methodology Amendments

This methodology is not amended retrospectively. Amendments are
committed as new commits to `METHODOLOGY.md` with rationale in the
commit message. A methodology-amendment Substack post accompanies each
amendment commit and announces the change to subscribers.

Positions logged before an amendment continue to be governed by the
version of `METHODOLOGY.md` at the time of their logging — Git history
preserves that version.

---

## 12  Override Rules

Track B overrides — divergence from a reviewed memo's implied action —
are governed by the decision schema and audit discipline.

### 12.1  Permitted Overrides

| Override type | Reason class | Mechanism |
|---|---|---|
| Downgrade size on caps | downgrade_concentration | accept_with_downgrade; binding_constraint required |
| Downgrade size on judgement | downgrade_judgement | accept_with_downgrade; binding_constraint must be null |
| Reject reviewed memo | reject_thesis_disagreement, reject_better_alternative, reject_other | reject |
| Make room and accept | make_room (on dispose entries) | accept with non-empty dispose_list |
| Defer | (no decision) | Return memo to queue |
| Allow expiry | no_action_timeout | (passive — recorded by sweep) |

### 12.2  Override Recording

The override is captured at decision-entry time in the `DecisionRecord`:

- `executed_size_pct` differs from `conviction_implied_pct` (downgrade)
  or `action != accept_as_proposed` (other overrides).
- `reason_class` names the override class.
- `reason_text` (≥ 50 chars) states the operator's reasoning.
- `binding_constraint` names the binding cap (where applicable).

The decision record is committed to the audit repository via the twin
memo pair before being logged to `decisions`.

### 12.3  Override Scoring

The quarterly review (§13) scores override outcomes — was the override
directionally correct in retrospect? Override scoring is published in
the quarterly Substack post alongside attribution. The published
analysis includes cases where the operator's judgement was wrong in
retrospect; selective publication of successful overrides only is not
permitted under §11.5.

---

## 13  Calibration and Review Cadence

### 13.1  Quarterly Review

**Quarter definition.** Quarters follow the calendar: Q1 (Jan–Mar), Q2
(Apr–Jun), Q3 (Jul–Sep), Q4 (Oct–Dec). The review fires fourteen days
after each quarter-end — late enough for filings and prices to settle,
and aligned with the reporting cadence readers already expect. The review
covers the most recently completed quarter, never the quarter in progress.

Inception is the date of the first position logged under this methodology.
A first quarter that begins mid-quarter has fewer than ninety days of data
at its first review. Thin-sample metrics are caveated, not suppressed
(§13.7).

The review covers the following.

**Per-position outcomes.** Each closed position receives one of three
outcome classifications:

- *Confirmed.* The thesis played out as described in the memo.
- *Invalidated.* The thesis invalidation signal was triggered, or the
  thesis was proven incorrect by events.
- *Inconclusive.* The position was exited for reasons unrelated to the
  original thesis (e.g. rebalance, universe change, delisting).

**Return measurement.** For each closed position and at the portfolio
level:

- Gross return (entry price to exit price).
- Net return (gross minus the 25bps entry + 25bps exit costs).
- Local-currency return.
- USD return, translated at point-in-time rates (§1.3).

**Track comparison.** Both tracks are compared against the benchmark on
the dual-basis, total-return convention of §8.7, net of costs; and against
each other, which is the measure of the operator's value-add or
value-detract.

**Quantitative model assessment.**

- PGain calibration by decile — see §13.3.
- Monte Carlo accuracy: how realised returns compared to the simulated
  distribution; whether input distributions were reasonable in hindsight.
- CAPM alpha realisation: whether positions entered with positive CAPM
  alpha outperformed those without.

**Track B operational metrics.**

- `no_action_timeout` rate — share of memos that expired in queue
  without an IC decision.
- `hold_inaction` rate — share of rebalance windows that expired
  without an IC decision.
- Price-stale entry rate — share of Track B entries where the quote at
  IC approval differed from the quote at memo generation by more than
  3% (per §8.4).
- Response time distribution — how quickly the operator typically
  responds, by hour buckets.

Outputs are written to `~/pe-analyst-audit/outcomes/{quarter_id}/` and
published per §11.4.

### 13.2  Outcome Metrics

The outcomes report scores each decision on one of three branches,
determined by the decision's action.

**Acquire decisions** (`accept_as_proposed`, `accept_with_downgrade`) are
scored from the position rows they produced:

- `total_return_usd` — dollar P&L, realised plus unrealised.
- `total_return_pct` — return on capital deployed at entry.
- `total_realised_usd` — lifetime realised P&L from `realised_pnl_usd`,
  which accumulates across trims and close (§8.2).
- `total_unrealised_usd` — mark-to-market against entry value for legs
  still open.
- `excess_vs_benchmark_pct` — return less the benchmark over the same
  holding window, on both currency bases (§8.7).
- `disposition` — one of `closed_per_thesis`, `reversed`, `forced`,
  `manual_or_legacy`, `still_open`.

**Non-acted decisions** (`reject`, `hold`, `hold_inaction`) are scored as
counterfactuals: what a position taken at `decided_at` and held to period
end would have returned, computed from price history. Excess return is
computed identically.

**Dispose decisions** (`partial_dispose`, `complete_dispose`) are not
scored separately. They return `attributed_to_acquire`: the disposal's
P&L is recognised on the leg's `realised_pnl_usd` and surfaces through the
outcome of the acquire that opened it. Scoring a disposal in its own right
would double-count it.

### 13.3  PGain Calibration Methodology

Calibration is measured through three lenses, computed in parallel against
the same paired data set.

**Brier score.** Mean squared error between predicted PGain and the binary
realised outcome (1 if the return was positive, 0 otherwise). The baseline
is 0.263, established on the Phase 02 validation set. This is the headline
number for governance review. The reported `baseline_gap` is
`brier − baseline`, so **a positive gap is worse**.

**Bucket calibration.** Predictions are partitioned into ten PGain deciles.
For each decile, the realised hit rate is compared against the bucket
midpoint:

```
calibration_gap = realised_hit_rate − bucket_midpoint
```

A **negative** gap is over-confidence: the predictions promised more than
the outcomes delivered.

**Conviction-band hit rate.** Predictions partitioned by
`conviction_implied_pct` band (1%, 3%, 5%, 8%, 12%), with the realised hit
rate reported per band.

**What is being scored.** The PGain under measurement is the
**specialist's** PGain, captured at memo creation. The join runs
`decisions.memo_id → analyst_outputs[memo_id].pgain`. The GP's stored
reasoning does not carry a PGain field; PGain originates upstream, in the
specialist's quantitative chain. This metric therefore measures the
specialist agent's probability calibration, **not the GP's**. The GP's
quality is measured separately, through override analysis (§13.4) and the
cap-breach audit (§13.5).

**Exclusions.** Decisions without a memo (rebalance, cap resolution) carry
no PGain and are skipped. Acted decisions whose position resolved with no
usable market data are skipped. Any prediction record whose `decision_id`
has no matching row in the decisions table is excluded as an orphan, and
the excluded count is reported rather than silently absorbed.

*Future enhancement.* Calibration with vintage discipline — point-in-time
macro and fundamentals locked to the historical `as_of` rather than current
values — is the natural way to distinguish regime-specific from
methodology-systemic over-confidence on a single-vintage sample. This is a
planned addition.

### 13.4  Override Analysis

Override analysis measures the divergence between the GP's autonomous
decisions (Track A) and the IC's decisions (Track B) on the same specialist
memo. Both tracks see the same memo; their independent decisions are paired
by `memo_id`.

Classifications:

- `aligned` — both tracks act, same action, same executed size.
- `pure_reject` — A accepts, B rejects.
- `size_reduction` — both accept, B chooses a smaller executed size.
- `size_increase` — both accept, B chooses a larger executed size.
- `expiration` — A acts, B does not decide within the 24-hour window.
- `pure_accept_b_only` — B acts, A did not. Anomalous; rare.

For each override, the counterfactual is computed from the Track A
position's outcome (the world in which the IC did not override) against the
Track B outcome or counterfactual (the world in which the override stood).
The delta is that override's contribution to Track B's relative performance.

Published analysis includes the cases where the operator's judgement was
wrong in retrospect. Selective publication of successful overrides is not
permitted (§11.5, §12.3).

An override class that is consistently additive — or consistently
value-destroying — across a market or sector for four consecutive quarters
is one of the triggers for an agent vintage bump (§13.6).

### 13.5  Cap-Breach Audit

Caps are hard at the input layer (§5); this audit confirms that procedural
enforcement worked, and surfaces whether the constraints bind in a way that
suggests the methodology itself warrants revision.

For the period, the audit reports:

- Total decision count.
- Count carrying a non-null `binding_constraint`.
- Frequency distribution by binding cap (`single_position_cap`,
  `country_cap`, `sector_cap`, `total_invested_cap`, `cash_floor`,
  `lot_indivisibility`).
- Severity: for each binding decision, the gap in percentage points
  between intended size (`conviction_implied_pct`) and executed size
  (`executed_size_pct`).
- `lot_indivisibility_count`, reported as a separate line. These are not
  cap breaches — they are executable-resolution constraints (§8.3), and
  conflating them with genuine capital constraints would overstate how
  often the caps bind.

### 13.6  Agent Iteration and Prompt Versioning

The platform runs five versioned LLM system prompts across four agent
roles. The Track B main decide flow is human-driven and has no LLM prompt
to version.

| Agent role | Prompt | Env var | Default |
|---|---|---|---|
| GP (per-memo) | `GP_PHASE_A_PROMPT` | `GP_PHASE_A_VERSION` | `v1` |
| GP (cap resolution) | `GP_PHASE_C_PROMPT` | `GP_PHASE_C_VERSION` | `v1` |
| Specialist (equity REIT) | `EQUITY_REIT_SYSTEM_PROMPT` | `SPECIALIST_PROMPT_VERSION` | `v1` |
| Memo reviewer | `REVIEWER_SYSTEM_PROMPT` | `REVIEWER_PROMPT_VERSION` | `v1` |
| Track A rebalance | `REBALANCE_A_SYSTEM` | `REBALANCE_PROMPT_VERSION` | `v1` |

GP Phase A and Phase C are versioned independently: a bump to one does not
require a bump to the other. Every decision logged carries the
`prompt_version` active at decision time. Track B decisions carry the
constant `ic_interface_v1` — an interface vintage, not an LLM prompt
vintage, since no LLM sits in the Track B decide loop.

Vintage bumps are at most quarterly. Each is documented with its trigger,
the change, the expected effect, and the baseline prompt version against
which the change will be measured. **Bumps are not a productivity metric.
The correct outcome of a quarter's review may be zero bumps.**

Bump triggers — any one is sufficient:

- Brier score crosses ±0.05 from the 0.263 baseline across two consecutive
  quarters.
- One IC override class is consistently additive across four consecutive
  quarters in the same market or sector.
- A cap binds in more than 80% of weeks in a single market across a
  quarter.
- A material external event: a regulatory or market-regime change
  warranting methodology revision.

A prompt change is a methodology change and is committed as such (§11.5).

### 13.7  Sample-Size Minima and Caveat Discipline

Each metric carries a `caveat` field, and a stated `n`, whenever the
sample falls below its minimum:

| Metric | Caveat threshold |
|---|---|
| Brier score | `n_predictions < 30` |
| Bucket calibration | each bucket with `n < 5` is marked |
| Override patterns | `n_overrides < 10` |
| Cap-breach patterns | `n_binding < 5` |

**The report publishes anyway, with the caveat beside the metric.**
Suppression would be paternalistic; disclosure is the discipline. The
first quarterly review may return all-caveat metrics simply because the
platform has not yet accumulated enough decisions to support inference.
The methodology position is that such metrics are *illustrative* until
their minima are cleared and *inferential* thereafter, and the public post
mirrors that language whenever a caveat fires.

This is the same principle that governs the short-window currency term in
§8.7, and it is the counterpart to the rule in §8.7 that a figure which
cannot be computed is shown as `n/a`. A metric that is weak is published
and labelled weak. A metric that is absent is published as absent. Neither
is quietly dropped, and neither is dressed up as something it is not.

### 13.8  Model Assignment Review

The platform operates `claude-sonnet-4-6` as the default model across
all agents. The `llm_complete` interface supports a per-call `model=`
override.

*Future enhancement.* A model-assignment review evaluates whether
specific agent roles benefit from an alternative model assignment.
Candidates include: semantic reviewer (single-call judgement task;
Opus reasoning advantage may apply); GP batch evaluator Phase A and
Phase C (structured-output judgement across multi-memo batches; Opus
may improve relative-weakness reasoning). The specialist (tool-use-
heavy, multi-round) is expected to remain on Sonnet for cost reasons.

The review records any assignment change as a methodology amendment
under §11.5.

---

## 14  Audit Integrity

### 14.1  Non-Negotiable Rules

- No force push to the audit repo, ever. Branch protection enforces.
- No `git commit --amend`, `git rebase`, or history rewrite, ever.
- No retroactive position logging. Publish-before-log is enforced
  programmatically; bypass is not possible without amending the
  enforcement code itself, which would be a methodology amendment
  audited under §11.5.
- No deletion of memos, decisions, or outcomes from the audit repo.
  Errors are corrected by new commits with rationale.

### 14.2  Atomicity Reconciliation

The decision log path performs sequential writes (SQLite then ChromaDB
for Track A; SQLite, ChromaDB, queue update for Track B) without
transactional rollback. If a later write fails, the system can be in
an inconsistent state until reconciliation.

A daily reconciliation report (Sunday 09:00 SGT, included in the
platform technical weekly email) detects orphan `decisions` rows
without matching ChromaDB entries, and orphan ChromaDB entries without
matching `decisions` rows. Discrepancies are emailed and logged. The
reconciliation report is the operational compensation for sequential-
write semantics.

---

## 15  Reserved

This section is reserved for future methodology additions. Anything
added here is committed as a methodology amendment under §11.5.

---

## Appendix A — Formulas and Data Sources

### A.1  PGain

```python
from scipy.stats import norm

def calculate_pgain(expected_return: float, std_dev: float) -> float:
    """Probability of positive return assuming normal distribution
    of simulated terminal returns."""
    if std_dev <= 0:
        return 1.0 if expected_return > 0 else 0.0
    z = -expected_return / std_dev
    return 1 - norm.cdf(z)
```

### A.2  CAPM Required Return

```python
def calculate_capm_return(risk_free: float, beta: float,
                          market_return: float) -> float:
    """CAPM required return = Rf + β · (Rm - Rf)."""
    return risk_free + beta * (market_return - risk_free)
```

### A.3  Primary Data Sources

| Domain | Source |
|---|---|
| Price data (REITs and benchmark) | yfinance |
| Distribution data (REITs and benchmark) | yfinance |
| FX rates (spot and history) | yfinance |
| Risk-free rate | FRED series `DTB3` (3-month US T-bill) |
| Benchmark | IASP.L (iShares Asia Property Yield UCITS ETF) |
| US macro series | FRED (`DFF`, `BAMLH0A0HYM2`, `T10Y2Y`, `DTWEXBGS`) |
| APAC central bank rates | Manual input — MAS, BoJ, HKMA, RBA |
| SGX filings | api.sgx.com (auth-token) |
| TSE filings | api.edinet-fsa.go.jp (API key) |
| HKEX filings | hkexnews.hk (manual logging) |
| ASX filings | asx.api.markitdigital.com |
| Filing body parsing | LlamaParse (`llama-cloud-services`) |

---

*FINAL — committed before first position. METHODOLOGY governs every position logged from this commit onward.*
