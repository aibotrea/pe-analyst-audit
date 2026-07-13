# Specialist Memo — CMW.AX

**Memo ID**: `CMW.AX_2026-07-13_equity_reit_v1@1.0_b326567526c3`
**Ticker**: CMW.AX (Cromwell Property Group)
**Market**: Australia
**Sector**: Office/Diversified
**As of**: 2026-07-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Cromwell Property Group offers a high nominal distribution yield of approximately 8.5% at the current AUD 0.425 price, providing a meaningful income cushion for long-only investors. The OU Monte Carlo (sigma 30.7%, base 8.5%) returns a PGain of 65.6% and CAPM alpha of 10.0%, reflecting the low or negative expected APAC REIT market return. However, estimated gearing of ~46% materially exceeds the Australian REIT convention of 40%, introducing refinancing risk and limiting capital management flexibility, which triggers a mandatory downward gate override to conviction 2. The July 2026 Brisbane office venture and recent institutional accumulation by MUFG and another substantial holder are positive signals, but office sector headwinds and limited filing body transparency constrain confidence. At conviction 2, a maximum position of 3% is warranted pending confirmation of a credible deleveraging pathway and DPU coverage above 1.0x.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.2089
- P-gain: 0.6562
- CAPM alpha: 0.1003
- Beta: 0.6712
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Gearing remains elevated at 47-50% with no deleveraging pathway; office occupancy falls below 90% in Brisbane/Sydney assets; DPU cut of 15-20% as coverage drops below 1.0x AFFO; further cap rate expansion of 25-50bps driven by higher-for-longer RBA rates; AUD weakness compounds AUD/GBP FX basis on benchmark. Stagflation or sustained rate shock scenario would represent the severe end of this range.
- **base**: E(R)=0.0840
  - Central case as modelled in the quantitative chain: distribution yield ~8.5%, flat DPU growth, flat cap rates, gearing stable at ~46%. Brisbane office venture modestly accretive over 12 months. RBA holds rates broadly steady. IASP.L benchmark return remains negative, providing low hurdle for relative alpha.
- **bull**: E(R)=0.2200
  - Successful execution of Brisbane office venture drives NTA accretion; RBA rate cuts compress cap rates by 25bps, supporting 5-8% multiple re-rating toward NTA; DPU maintained or lifted 5%; two new substantial holder notices (MUFG, May 2026; second party, May 2026) signal institutional re-accumulation. Gearing path below 42% unlocks refinancing at lower spreads.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.085 (Cat A) — Estimated trailing distribution yield based on CMW's two quarterly distribution announcements on ASX (June 2026 and March 2026; filing bodies unavailable under Phase 01 v3.3 §4). CMW price AUD 0.425 as of 2026-07-13 (Category A closing price). Annualised DPU estimated at ~3.6 cpu derived from recurring quarterly distributions visible in ASX headlines. Yield = ~8.5% used conservatively; rounded to 8.5% to account for body capture gap. Disclosed limitation: exact DPU amount not confirmed from filing body.
- `dpu_growth_rate` = 0.0 (Cat C) — Flat DPU growth assumed over 12-month horizon. CMW has faced persistent office sector headwinds, elevated gearing, and a history of distribution cuts. The July 2026 Brisbane office venture launch is incrementally positive but insufficient to justify positive DPU growth at this stage. Sensitivity: bear case uses -10% DPU reduction; bull case uses +5% DPU growth. Basis: publicly available news (Morningstar 2026-07-02 noting CMW 'in better shape than most other small office REITs'), combined with sector context.
- `multiple_change` = 0.0 (Cat C) — Zero multiple expansion/contraction assumed in base case. CMW trades at a significant discount to NTA (historically 30-40%). Morningstar note (2026-07-02) implies relative stabilisation but not re-rating. Bull case captures modest re-rating of +5%; bear case captures further de-rating of -8%.
- `gearing_estimate` = 0.46 (Cat B) — Gearing estimated at approximately 46% based on CMW's HY26 Results Announcement headline (2026-02-25, body unavailable). Historically CMW has operated at 45-50% look-through gearing. This exceeds the Australian REIT convention of <40%, triggering a qualitative gate override. Exact figure unconfirmed due to ASX filing body unavailability — treated as Category B estimate with disclosed uncertainty.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Elevated gearing (~46% estimated) exceeds Australian REIT convention of <40%; refinancing at higher spreads in a persistent high-rate environment could force distribution cuts or asset sales at depressed valuations.
- Office sector structural vacancy risk: CMW's portfolio is concentrated in Australian office (Brisbane, Sydney) and European assets, both facing secular demand headwinds from hybrid work adoption.
- ASX filing body capture failure (Phase 01 v3.3 §4) means exact DPU quantum, NTA, gearing, and AFFO coverage are unconfirmed — key_assumptions rely on headline data and prior public disclosures, introducing estimation risk.
- AUD/GBP currency basis distorts the IASP.L beta computation; actual co-movement with APAC property markets may differ from the reported beta of 0.67.
- Backtest/calibration limitation: Phase 2 calibration is directional only; vintage discipline arrives in Phase 5. Conviction score should be treated as directional, not precise.

## Invalidation Condition
Exit position if CMW announces a distribution cut exceeding 10% versus the trailing annualised DPU, or if reported gearing rises above 50% for two consecutive reporting periods, or if office occupancy across the Australian portfolio falls below 88%, or if any unscheduled ASX announcement reveals a covenant breach or requirement for emergency equity capital raising at a discount greater than 10% to prevailing NTA.
