# METHODOLOGY.md

## PE Analyst Platform — Investment Methodology

This document defines the rules, universe, quantitative framework, and scoring
methodology for the PE Analyst Platform's twin-track investment system. It is
committed to this public repository before any position is logged.

**Rules cannot be amended retrospectively.** Any changes to this methodology
are logged as a new commit with rationale. The original rules remain visible
in the Git history. This document exists so that anyone reviewing the track
record can verify the rules were defined before outcomes were known.

---

## 1. Twin-Track System

### 1.1 Portfolio A — Fully Automated

All position decisions are made by the GP agent. No human review of investment
rationale. No overrides permitted. The GP agent learns exclusively from its
own prediction accuracy versus market outcomes. It never has access to IC
rationale feedback from Track B.

### 1.2 Portfolio B — Human Overlay

The same specialist agents produce the same analysis. The human (acting as
Investment Committee) receives agent output as an IC pre-read, challenges
the thesis, and approves, modifies, or rejects. Override reasons are logged
at entry time — never retrospectively.

### 1.3 Reviewer Agent

The reviewer agent operates on both tracks as a document quality gate. It
checks: memo completeness, structure, data citations, analytical clarity.
It does not assess investment rationale. It retrieves from the
ic_feedback_corpus (ChromaDB) to calibrate quality standards over time.

### 1.4 Segregation Principle

Track A's GP agent has no access to Track B's IC rationale feedback. This
is enforced structurally via separate data stores (gp_predictions vs
ic_feedback_corpus in ChromaDB), not by procedural guidelines. The reviewer
agent's document quality feedback benefits both tracks — this is not a
segregation violation because it concerns output format, not investment
substance.

---

## 2. Universe

### 2.1 Markets

- Japan (TSE-listed J-REITs)
- Singapore (SGX-listed S-REITs)
- Hong Kong (HKEX-listed HK-REITs)
- Australia (ASX-listed A-REITs)

### 2.2 Instrument Types

- Listed REITs (equity)
- Listed REIT bonds and credit instruments (where available and liquid)

### 2.3 Inclusion Criteria

To be finalised in Phase 1 when the universe is constructed. Criteria will
include:

- Minimum market capitalisation (threshold TBC)
- Minimum average daily trading volume (threshold TBC)
- Must be classified as a REIT or REIT-equivalent structure under local
  regulation (MAS for Singapore, SFC for Hong Kong, J-REIT Act for Japan,
  ASIC for Australia)
- Minimum 12 months trading history

### 2.4 Exclusion Criteria

- Suspended securities
- REITs under active takeover or delisting proceedings
- Instruments with insufficient liquidity for the simulated position size

### 2.5 Universe Maintenance

The universe is fixed for the duration of the experiment. New listings that
meet inclusion criteria are added at the next quarterly review. Delistings
are removed and positions are exited at the last available price. Expansion
to new markets or asset classes is a separate future experiment.

The specific ticker list is committed as a separate file (universe.csv)
when Phase 1 completes.

---

## 3. Quantitative Framework

The conviction scoring system combines three quantitative layers. The LLM
reasons about what to analyse and interprets results. It does not generate
probability numbers from its own judgment. Quantitative models produce the
numbers.

### 3.1 Monte Carlo Simulation

For each investment thesis, the specialist agents define input variables
with probability distributions rather than single point estimates:

**Equity inputs:** rental growth rate, vacancy rate, cap rate movement,
DPU growth trajectory, lease renewal probability, sponsor support
assumptions, FX movement.

**Credit inputs:** refinancing cost, interest rate trajectory, covenant
headroom under stress, rating migration probability, recovery rate
assumptions.

Each input is assigned a distribution (normal, triangular, or uniform as
appropriate) with defined parameters. The simulation runs 10,000 scenarios
over the investment horizon. The output is a distribution of returns
producing:

- **E(R):** expected return (mean of the simulated distribution)
- **St.Dev:** standard deviation of the simulated returns
- **Distribution shape:** skewness and tail characteristics

The input assumptions for every position are logged in the memo and are
reproducible. Anyone can re-run the simulation with the same inputs and
verify the outputs.

#### 3.1.2 Input Classification

Every Monte Carlo input is classified into one of three categories. The
classification is disclosed in each memo so that anyone reviewing the
analysis can assess the reliability of the simulation outputs.

##### Category A — Observed Data

Inputs derived directly from public disclosures or market data with no
modelling assumptions. These are verifiable by any third party.

- DPU history and declared distributions (REIT filings)
- Reported occupancy rates (REIT filings and quarterly updates)
- Lease expiry profiles as disclosed (annual reports)
- Gearing and LTV ratios (mandatory disclosure, all four markets)
- Debt maturity profiles and coupon rates (annual reports)
- Interest coverage ratios (calculable from reported financials)
- Historical price data and beta (yfinance)
- Risk-free rate (FRED DTB3)
- Central bank policy rates (MAS, BoJ, HKMA, RBA)
- FX spot rates (yfinance)
- Current credit ratings (public, from rating agencies)
- Cap rates implied from reported NOI and property valuations (annual reports)

#### Category B — Derived Estimates

Inputs calculated from observed data using defined, reproducible methods.
The derivation method is disclosed in the memo.

- Rental reversion estimates (calculated from disclosed passing rents
  and available market rent comparables)
- Covenant headroom under stress (covenants from filings, stress
  assumptions defined by the analyst and disclosed)
- Unencumbered asset ratios (calculable from balance sheet data)
- Beta estimation period and method (e.g. 2-year weekly returns
  regressed against benchmark)
- Vacancy rate trends (extrapolated from historical reported data
  using disclosed method)
- Rental growth trajectory (extrapolated from historical data or
  derived from REIT management guidance in public presentations)
- Implied default probability (derived from financial metrics using
  disclosed model, e.g. Altman Z-score adapted for REITs)

##### Category C — Model Assumptions

Inputs that require judgment and cannot be derived mechanically from
public data. These are the primary source of model uncertainty. Each
Category C input must state:

- The specific assumption (e.g. "rental growth of 3% p.a. for years 1–3")
- The basis for the assumption (e.g. "5-year historical average for
  Singapore CBD office was 2.8%; URA planning pipeline suggests
  tightening supply")
- The sensitivity: what happens to PGain if this assumption is wrong
  by +/- one standard deviation

Category C inputs include:

- Forward rental growth rate distributions
- Future vacancy rate distributions
- Cap rate movement assumptions
- Sponsor support probability
- Recovery rate assumptions in default scenarios
- Rating migration probability distributions
- Development pipeline cost variance
- FX movement distributions beyond spot

##### Classification Rules

- Every Monte Carlo input in every memo is tagged as A, B, or C
- Category A inputs are not debatable — they are what the filings say
- Category B inputs are reproducible — anyone applying the same method
  to the same observed data should reach the same number
- Category C inputs are where analytical judgment lives — and where
  Track A and Track B may legitimately diverge
- A memo with a high proportion of Category C inputs should carry
  lower conviction than one driven primarily by Category A and B
  inputs, all else being equal. This is captured in the qualitative
  gates (Section 4.2).

### 3.2 PGain — Probability of Positive Return

PGain is the probability that the investment returns more than the capital
invested. It is calculated from the Monte Carlo outputs assuming a normal
distribution of returns:


Z-Score = -E(R) / St.Dev
PGain   = 1 - Φ(Z-Score)


Where Φ is the cumulative normal distribution function.

PGain captures a question distinct from expected return: how likely is it
that capital is returned? A high E(R) with high volatility can have a lower
PGain than a modest E(R) with low volatility. This metric penalises
uncertainty regardless of upside potential.

**PGain is the primary input to the conviction scoring table.**

Example: E(R) = 21%, St.Dev = 20%.
Z-Score = -0.21 / 0.20 = -1.05.
PGain = 85.3%.

### 3.3 CAPM — Required Return Benchmark

The Capital Asset Pricing Model provides the minimum return the market
demands for bearing systematic risk:


Required Return = Rf + β × (Rm - Rf)


Where:
- Rf = risk-free rate (3-month US T-bill, FRED series DTB3)
- β = beta of the REIT relative to the benchmark index
- Rm = expected return of the benchmark (FTSE EPRA/NAREIT Asia Developed)

**CAPM alpha** = E(R) from Monte Carlo minus CAPM required return.

A positive CAPM alpha indicates the expected return exceeds what the market
demands for the risk. A negative CAPM alpha does not automatically disqualify
a position but is flagged in the memo and may reduce conviction.

### 3.4 How the Three Layers Interact

1. Specialist agents define input assumptions and run Monte Carlo. Each input is classified as Category A, B, or C
2. Monte Carlo produces E(R) and St.Dev
3. PGain is calculated from E(R) and St.Dev
4. CAPM required return is calculated from the risk-free rate and REIT beta
5. CAPM alpha = E(R) minus required return
6. PGain maps to the conviction table (Section 4)
7. Qualitative gates can override conviction downward but never upward
8. All inputs, intermediate calculations, and outputs are logged in the memo

---

## 4. Conviction Scoring and Position Sizing

### 4.1 Conviction Table

PGain is the quantitative input. Qualitative gates can reduce conviction
below the PGain-implied level but cannot increase it. The quantitative
floor holds.

| Conviction | PGain Range | Qualitative Gate | Max Position Size |
|---|---|---|---|
| 5 — High | > 85% | AND no unmodelled binary risks AND CAPM alpha > 0 | 12% |
| 4 — Above average | 70–85% | AND at least one confirming qualitative factor | 8% |
| 3 — Moderate | 55–70% | OR PGain > 70% with material unmodelled risk | 5% |
| 2 — Low | 40–55% | Timing or magnitude uncertain | 3% |
| 1 — Speculative | < 40% | Logged for tracking only | 1% |

### 4.2 Qualitative Gates

Qualitative gates capture risks that the Monte Carlo simulation cannot
model. These include:

- **Binary event risk:** regulatory changes, major tenant default,
  government policy shifts that are not continuous variables
- **Unmodelled correlation:** REIT exposure to a factor not captured in
  the simulation inputs
- **Data quality concern:** key input assumption relies on stale, incomplete,
  or unreliable data
- **Liquidity risk:** the position size relative to average daily volume
  creates execution risk beyond the 25bps cost assumption
- **Input quality concern:** memo relies heavily on Category C assumptions
  with limited Category A/B anchoring

A qualitative gate can only push conviction downward. For example:
Monte Carlo produces PGain of 80% (implying conviction 4), but a pending
regulatory review creates binary risk the model cannot capture. Conviction
is reduced to 3. The memo must state which gate was applied and why.

### 4.3 Conviction Overrides (Track B Only)

In Track B, the human may override the conviction score in either direction
as part of the IC process. The override reason is logged at entry time.
Track A uses the conviction score as computed — no human override is
permitted.

---

## 5. Portfolio Rules

### 5.1 Capital and Constraints

- Simulated capital: USD 10,000,000 per portfolio
- Maximum single position: 12% of portfolio
- Maximum single-country exposure: 35% of portfolio
- Transaction costs: 25bps on entry + 25bps on exit, applied
  programmatically, never waived
- FX conversion: spot rate on entry date via yfinance
- Idle capital: earns 3-month US T-bill rate (FRED series DTB3)
- Both portfolios start on the same date — the date the first position
  is committed

### 5.2 Execution and Price Capture

Positions are not executed through a brokerage. Both tracks are simulated
using market prices from yfinance at the point of decision. Transaction
costs are applied programmatically. This ensures clean separation between
tracks and removes brokerage account management as a variable.

**Track A (automated):** entry price is the yfinance market price at the
timestamp when the GP agent commits its position decision. The agent must
capture and log the price in the same atomic operation as the decision —
no delay between decision and price capture.

**Track B (human overlay):** entry price is the yfinance market price at
the timestamp when the human logs the position approval or override. The
price is captured at the moment of logging, not at the time the GP agent
generated the original recommendation.

**Exit prices** follow the same logic: the yfinance market price at the
timestamp when the exit decision is logged for the relevant track.

**Price source:** yfinance delayed prices are used. Real-time execution is
not claimed. All prices are reproducible — yfinance historical data can be
independently verified against the logged timestamps.

### 5.3 Track B Remote Notification and Response

Track B requires timely human decision-making on GP agent recommendations.
The platform must provide remote notification and response capability so
that IC decisions are not delayed by physical location.

#### Notification

When the GP agent generates a recommendation, the platform delivers a
notification to the human via OpenClaw messaging channels (configured in
Phase 4). The notification includes: ticker, direction, conviction score,
PGain, key thesis summary, and a link to the full Memo A. The human can
review and respond from any location via Tailscale VPN connection to the
OpenClaw dashboard.

#### Maximum Response Window

The human must log an IC decision (approve, override, or reject) within
24 hours of the GP agent's recommendation timestamp. If no decision is
logged within 24 hours:

- The recommendation is recorded as "IC timeout — not entered"
- No position is opened in Track B for this recommendation
- Track A is unaffected — the GP agent enters its position at the
  original decision timestamp regardless of Track B response timing
- IC timeouts are tracked and reported in quarterly reviews as a
  measure of Track B operational discipline

The 24-hour window balances two concerns: giving the human adequate time
to review the analysis (particularly across time zones and working hours),
while preventing stale recommendations from being entered at prices that
no longer reflect the original thesis conditions.

#### Price Staleness Gate

If the market price of the instrument has moved more than 3% between the
GP agent's recommendation timestamp and the human's approval timestamp,
the position is flagged as "price-stale" in the position record. The
human must confirm entry despite the price movement. The flag is:

- Logged in the position record for transparency
- Included in quarterly review analysis — do price-stale entries
  perform differently from timely entries?
- Not an automatic block — the human may still enter if the thesis
  remains valid at the new price level

The 3% threshold is an initial setting. It may be adjusted after the
first two quarterly reviews based on observed APAC REIT volatility
patterns, with the adjustment logged as a new commit to METHODOLOGY.md.

### 5.4 IBKR Proof of Concept

A standalone technical validation demonstrating the platform can connect to
Interactive Brokers via IB Gateway and execute a paper trade is conducted in
Phase 1. This proof of concept is separate from the portfolio system and
does not generate tracked positions. It exists to validate the technical
capability for potential future migration to live execution.

---

## 6. Benchmark

- **Index:** FTSE EPRA/NAREIT Asia Developed Index
- **Data source candidate:** IFAPAC.L via yfinance (to be confirmed when
  data pipeline is built in Phase 1)
- Performance is measured net of transaction costs against this benchmark
- CAPM beta for individual REITs is calculated relative to this benchmark

---

## 7. Publication Rules

### 7.1 Publish-Before-Log Rule

No position is logged until its paired twin memos (Memo A + Memo B) are
committed and pushed to GitHub. The publication timestamp must precede the
position entry timestamp. This is non-negotiable.

### 7.2 Twin Memo Format

Each investment thesis produces two memos committed to GitHub before any
position is logged:

**Memo A:** unedited GP agent output in IC pre-read format. Contains:
thesis, key data, Monte Carlo inputs and outputs, PGain, CAPM comparison,
conviction score, invalidation signal, position sizing recommendation.

**Memo B:** human overlay. Contains: where you agree with Memo A, where
you diverge and why, context the platform lacks, your conviction score
(which may differ from Memo A for Track B).

**Comparison section:** scores both memos on: analytical rigour, data
breadth, contextual judgment, tail risk identification, quantitative
model appropriateness.

### 7.3 Substack Publication

Both memos published together as a single Substack post with GitHub commit
hashes embedded. Research log framing, not tech commentary. Target audience:
~200–300 APAC RE practitioners. Free for year one.

---

## 8. Override Rules (Track B)

### 8.1 Permitted Actions

Any GP agent signal may be overridden: approved as-is, approved with
modified conviction/sizing, or rejected entirely.

### 8.2 Logging Requirements

Override reason must be logged at entry time as part of the position record.
Retrospective override reasons are prohibited — if the reason was not logged
at entry, it does not exist for evaluation purposes.

### 8.3 Override Categories

Each override is categorised at entry time:

- **Timing disagreement:** agree with thesis direction but disagree on entry timing
- **Conviction adjustment:** agree with thesis but assess probability differently
- **Additional context:** information available to the human that the platform lacks
- **Risk not captured:** tail risk or binary event the quantitative model does not address
- **Thesis rejection:** fundamental disagreement with the investment thesis

### 8.4 Override Analysis

Quarterly reviews analyse which override categories added value and which
detracted. This analysis is published honestly — including cases where
human judgment was wrong.

---

## 9. Scoring Methodology

### 9.1 Quarterly Reviews

All closed positions are scored at each quarterly review.

### 9.2 Thesis Outcome

Each closed position receives one of three outcomes:

- **Confirmed:** the thesis played out as described in the memo
- **Invalidated:** the invalidation signal was triggered or the thesis
  was proven incorrect by events
- **Inconclusive:** the position was exited for reasons unrelated to the
  original thesis (e.g. portfolio rebalancing, universe change)

### 9.3 Return Measurement

- Gross return: entry price to exit price
- Net return: gross return minus transaction costs (25bps entry + 25bps exit)
- Returns calculated in local currency and in USD

### 9.4 Track Comparison

- Portfolio A return vs benchmark (net of costs)
- Portfolio B return vs benchmark (net of costs)
- Portfolio A vs Portfolio B (the human value-add or value-detract)

### 9.5 Override Analysis

For Track B only: which overrides added value (improved return vs Track A
position on the same thesis) and which detracted. Broken down by override
category from Section 8.3.

### 9.6 Quantitative Model Assessment

- PGain calibration: were the confidence scores well-calibrated? Did
  positions with PGain of 80% actually return positive ~80% of the time?
- Monte Carlo accuracy: how did realised returns compare to the simulated
  distribution? Were inputs reasonable in hindsight?
- CAPM alpha realisation: did positions with positive CAPM alpha
  outperform those without?

### 9.7 GP Agent Prediction Scoring

Track A only. Measures the accuracy of the GP agent's conviction scores
against actual outcomes. Identifies systematic biases: does the agent
consistently overestimate or underestimate confidence in specific markets,
sectors, or conditions?

---

## 10. Audit Trail Integrity

- All position records are committed to this Git repository
  (github.com/aibotrea/pe-analyst-audit)
- GitHub branch protection is enabled: force push is blocked at the
  remote level
- The following are permanently prohibited:
  - `git commit --amend` (rewrites history)
  - `git rebase` (rewrites history)
  - `git push --force` (destroys public timestamp anchor)
- Errors in position entries are corrected by a new commit, never by
  altering the original
- Git commit timestamps are cryptographically immutable
- The combination of GitHub branch protection and the publish-before-log
  rule ensures that the public record cannot be altered after the fact

---

## Appendix A: Implementation Notes

### A.1 Monte Carlo Implementation

Simulation module implemented in Python using scipy and numpy. 10,000
iterations per position. Input distributions and parameters are logged
with each memo. The module is called as a shared function by both
specialist agents.

### A.2 PGain Implementation

python
from scipy.stats import norm

def calculate_pgain(expected_return: float, std_dev: float) -> float:
    """Probability of positive return assuming normal distribution."""
    if std_dev <= 0:
        return 1.0 if expected_return > 0 else 0.0
    z_score = -expected_return / std_dev
    return 1 - norm.cdf(z_score)


### A.3 CAPM Implementation

python
def calculate_capm_return(risk_free: float, beta: float,
                          market_return: float) -> float:
    """CAPM required return."""
    return risk_free + beta * (market_return - risk_free)


### A.4 Data Sources

- Price data: yfinance
- Risk-free rate: FRED series DTB3
- Benchmark: FTSE EPRA/NAREIT Asia Developed (IFAPAC.L candidate)
- Filings: EDGAR, SGX, HKEX, EDINET, ASX
- Macro: FRED, MAS, BoJ, HKMA, RBA

---

*This document is a draft. It will be finalised and committed before the
first position is logged in Phase 4. The draft is maintained in the
working directory and is not yet part of the immutable audit trail.*