# Specialist Memo — CMW.AX

**Memo ID**: `CMW.AX_2026-07-14_equity_reit_v1@1.0_8cbd82b0ba74`
**Ticker**: CMW.AX (Cromwell Property Group)
**Market**: Australia
**Sector**: Diversified Office/Commercial
**As of**: 2026-07-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Cromwell Property Group (CMW.AX) is an internally managed Australian diversified REIT with significant exposure to domestic and European office assets, currently trading at AUD 0.42 — a deep discount to estimated NTA reflecting persistent office-sector headwinds, elevated gearing (~44%, above the AU <40% convention), and uncertain distribution coverage following asset recycling. The estimated distribution yield of ~9.5% is superficially attractive but is undermined by gearing risk, opaque DPU coverage, and ongoing disposal-driven income erosion. The OU Monte Carlo produces a simulated 12-month return of 5.9% with a high standard deviation of 20.9%, yielding a PGain of 61.1% — marginally above neutral but insufficient to support meaningful conviction given structural balance sheet constraints. After applying two downward gate overrides for leverage breach and sponsor/pipeline quality concerns, conviction is reduced to 1 (Speculative), capping position at 1.0%.

## Quantitative Chain

- E(R): 0.0600
- Std dev: 0.2089
- P-gain: 0.6113
- CAPM alpha: 0.0738
- Beta: 0.6786
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2200
  - Gearing breaches 45% covenant threshold forcing distressed asset sales at cap rate expansion of 75bps; DPU cut by 30%; occupancy in Australian office portfolio falls below 85%; RBA holds rates elevated crimping the yield spread; European portfolio disposal proceeds disappoint. This scenario also captures a broader office sector repricing event driven by structural vacancy acceleration.
- **base**: E(R)=0.0600
  - Central case: estimated annual DPU of ~4.0c (yield ~9.5%) at AUD 0.42; DPU growth of -1.5% reflecting reduced European income; mild -2.0% multiple contraction from persistent NTA discount; gearing flat at ~44%; Brisbane office venture stabilises incrementally.
- **bull**: E(R)=0.2500
  - European asset disposals completed above book value, reducing gearing below 38% and triggering capital return or DPU uplift; RBA cuts rates by 75bps compressing cap rates and re-rating office REITs; occupancy improves to 92%+ on lease-up; discount to NTA narrows materially driving price rerating toward AUD 0.52-0.55.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=fail [override_applied=-1]
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.095 (Cat B) — Estimated annual DPU of ~AUD 0.040 per unit at current price of AUD 0.420. Distribution announcement filings (CMW.AX 2026-06-16 and 2026-03-26) body capture failed (ASX Phase 01 v3.3 §4 limitation). Estimate derived from known quarterly distribution cadence and post-restructuring payout guidance. Category B due to body unavailability; confirmed DPU figure not retrievable from stored filings.
- `dpu_growth_3yr` = -0.015 (Cat C) — Negative DPU growth assumed reflecting ongoing asset disposal programme (Chatswood JV exit July 2026, Brisbane office venture), reduced income from European portfolio wind-down, and elevated gearing constraining distribution capacity. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.02 (Cat C) — Mild negative multiple change assumed. Cromwell trades at a structural discount to NTA reflecting office-sector headwinds and leverage overhang. Spread compression unlikely in the near term given elevated Australian base rates and persistent office vacancy. Sensitivity tested in scenario analysis.
- `gearing_estimate` = 0.44 (Cat B) — Gearing estimated at ~44% based on publicly known FY25 levels. HY26 Results Presentation (CMW.AX 2026-02-25 PERIODIC REPORTS) body unavailable. Exceeds Australian REIT convention of <40%; treated as a qualitative gate failure on leverage. Disclosed as Category B due to body unavailability.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.
- `risk_free_rate_source` = 0.0376 (Cat A) — 3-Month US Treasury Bill rate (DTB3) as at 2026-07-13: 3.76%. Used as proxy risk-free rate per platform methodology.
- `benchmark_return` = -0.0381 (Cat B) — IASP.L (FTSE EPRA/NAREIT Asia Developed, GBP-denominated) trailing 5-year annualised log return of -3.81% over 1,304 observations. Reflects broad APAC REIT sector headwinds over the measurement window. Currency-basis caveat applies.

## Key Risks
- Gearing at ~44% exceeds Australian REIT convention of <40%, limiting refinancing flexibility and constraining DPU; any cap rate expansion could trigger covenant breaches or forced asset sales at discounts.
- Structural office vacancy acceleration in Australia and Europe — work-from-home normalisation, lease expiry concentration, and tenant downsizing pressure occupancy and rent reversion.
- Distribution coverage opaque: HY26 Results Presentation and distribution announcement filing bodies unavailable, preventing verification of AFFO payout ratio; DPU sustainability cannot be independently confirmed from stored filings.
- Interest rate risk: RBA higher-for-longer policy compresses the yield spread over risk-free assets and elevates refinancing costs for a heavily leveraged balance sheet.
- European portfolio execution risk: asset disposals (Chatswood JV exit, Brisbane venture) must be completed at or above book values to prevent NTA dilution; market liquidity for secondary office assets in Europe remains thin.

## Invalidation Condition
Exit the position if gearing is confirmed above 45% in any subsequent half-year report or if DPU is cut by more than 20% from the trailing annualised level (below approximately 3.2c per annum), or if occupancy across the Australian office portfolio falls below 85% for two consecutive reporting periods, signalling structural demand deterioration beyond base case assumptions.
