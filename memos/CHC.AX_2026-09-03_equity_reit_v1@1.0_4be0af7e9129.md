# Specialist Memo — CHC.AX

**Memo ID**: `CHC.AX_2026-09-03_equity_reit_v1@1.0_4be0af7e9129`
**Ticker**: CHC.AX (Charter Hall Group)
**Market**: Australia
**Sector**: Diversified REIT / Integrated Property Manager
**As of**: 2026-09-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Charter Hall Group (CHC.AX) is an integrated Australian property fund manager and co-investor that suffered a sharp ~19% drawdown in August 2026, falling from AUD 23.4 to AUD 18.70. At current prices the distribution yield is modest (~2.3%), well below the 3.78% risk-free rate, leaving limited carry compensation for equity risk. Annualised historical volatility of 28.2% and an OU Monte Carlo PGain of only 58.7% support a low conviction rating. The integrated manager model — where earnings are leveraged to AUM flows and fee income rather than pure contractual rent — introduces an additional layer of earnings volatility not present in pure-play REITs, warranting a one-step gate override to conviction 2.

## Quantitative Chain

- E(R): 0.0430
- Std dev: 0.1918
- P-gain: 0.5869
- CAPM alpha: 0.0783
- Beta: 0.8695
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2000
  - AUM declines materially as institutional investors redeem from Charter Hall-managed vehicles; DPU cut of 20-25%; gearing rises above 38% LVR; further cap rate expansion of 50bps compresses NAV; RBA holds rates elevated suppressing property valuations; price falls toward AUD 14-15 range. This scenario also captures a macro rate-shock pathway where the RBA unexpectedly hikes, further pressuring Australian property valuations and fee income.
- **base**: E(R)=0.0430
  - Central case as built in quantitative chain: distribution yield ~2.3%, zero DPU growth, +2% multiple partial reversion. AUM broadly stable, RBA holds or cuts once, occupancy across managed portfolios remains 93-95%. Share price drifts modestly higher from August 2026 lows.
- **bull**: E(R)=0.2200
  - RBA cuts rates 50-75bps over 12 months, compressing cap rates and lifting property valuations; AUM inflows resume as institutional appetite for Australian commercial property recovers; Charter Hall announces accretive development pipeline completions; DPU upgrades ~10%; share price recovers toward AUD 22-23. Full mean reversion to pre-selloff levels.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.023 (Cat C) — Estimated trailing distribution yield of ~2.3% based on AUD 18.70 closing price as of 2026-09-03 and Charter Hall's historical DPU of approximately 42-44 cents per security. Exact FY2026 DPU not confirmed in available filings (ASX body capture returned mismatched pipeline content); yield estimated from public price history and prior-year distributions. Sensitivity: a 10% DPU cut would reduce yield to ~2.1%.
- `dpu_growth_3yr` = 0.0 (Cat C) — Zero DPU growth assumed over the 12-month horizon. Charter Hall's fee income is AUM-driven; the ~19% share price decline in August 2026 signals market concern about AUM compression and earnings pressure. No confirmed growth catalyst visible in available ASX announcements. Sensitivity tested in scenario analysis.
- `multiple_reversion` = 0.02 (Cat C) — Modest +2.0% positive contribution from partial mean reversion following the August 2026 drawdown (peak ~AUD 23.4 on 2026-07-28 to trough ~AUD 18.61 on 2026-09-03, approximately -20%). A partial reversion to fair value is assumed under the base case but carries high uncertainty given the severity and speed of the decline.
- `gearing_estimate` = within_convention (Cat C) — Charter Hall Group historically reports balance sheet gearing below the AU convention of <40% LVR. Exact FY2026 figures not confirmed from available stored filings (bodies mismatched in pipeline). Assumed compliant with the <40% convention pending FY26 annual report confirmation.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. This is the currency and iasp basis risk inherent in the IASP.L benchmark. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- AUM compression risk: Charter Hall's fee income is directly leveraged to assets under management; institutional redemptions or valuation writedowns could trigger significant earnings downgrades beyond what is priced in.
- Distribution yield below risk-free rate: At ~2.3% yield vs 3.78% T-bill, there is negative carry; any further price decline eliminates the total return case.
- RBA rate environment: Elevated Australian rates suppress property valuations and widen cap rates, pressuring both NAV and the competitiveness of distribution yield.
- Elevated volatility (28.2% annualised): Reflects market uncertainty about fair value post-drawdown; momentum is negative and the selloff may not be complete.
- Filing data gap: Available ASX stored filings returned mismatched bodies (pipeline issue); exact FY2026 DPU, AFFO coverage, and gearing figures could not be confirmed and represent a key information risk to this analysis.

## Invalidation Condition
Exit if Charter Hall announces FY2026 or interim DPU below AUD 0.38 per security (more than 10% cut to estimated base), or if disclosed balance sheet LVR exceeds 40%, or if AUM under management declines more than 10% in a single reporting period, or if the share price closes below AUD 16.00 for three consecutive sessions signalling further structural de-rating beyond the August 2026 drawdown.
