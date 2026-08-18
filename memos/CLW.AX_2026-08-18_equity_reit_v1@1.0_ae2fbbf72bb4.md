# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-08-18_equity_reit_v1@1.0_ae2fbbf72bb4`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified
**As of**: 2026-08-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Charter Hall Long WALE REIT offers a defensive, income-oriented exposure to Australian long-duration real estate underpinned by government and essential-services tenants with characteristically long lease profiles (WALE typically 10+ years). A trailing distribution yield of approximately 6.8% at the current price of AUD 3.59 provides meaningful income above the 3.72% US T-bill risk-free proxy. FY2026 results confirmed modest 2% DPU growth and the successful completion of a $2B debt refinancing, de-risking near-term refinancing exposure. The OU Monte Carlo returns a 12-month simulated return of 8.2% with a PGain of 76.3%; however, the gearing level approaching the 40% Australian convention ceiling and the NTA discount signal a market environment that is not yet fully supportive of re-rating. Conviction is set at Moderate (3/5) with a one-step gate override applied for leverage, warranting a 5% maximum position size.

## Quantitative Chain

- E(R): 0.0830
- Std dev: 0.1152
- P-gain: 0.7630
- CAPM alpha: 0.0961
- Beta: 0.6156
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher-for-longer or re-tightens, driving cap-rate expansion of 30-50bps across CLW's long-WALE industrial and social-infrastructure assets. NTA discount widens materially; distribution coverage falls below 1.0x AFFO if variable-rate debt costs exceed hedges post-refinancing; DPU cut of 5-10%. Gearing breaches 40% convention, triggering asset disposals at unfavourable prices. Multiple contraction of -200bps assumed.
- **base**: E(R)=0.0830
  - Central case: 2% DPU growth sustained per FY2026 actuals, gearing stable at ~38% post-$2B refinancing, occupancy near 100% on long government-linked leases, modest -0.5% multiple contraction. Distribution yield of ~6.8% dominates total return. No material asset revaluations.
- **bull**: E(R)=0.2000
  - RBA begins rate-cutting cycle in H1 CY2027, compressing cap rates and closing the NTA discount (positive re-rating of +5-8%). Charter Hall sponsor injects accretive pipeline assets at favourable yields. DPU growth accelerates to 3-4% on CPI-linked rent escalators. Gearing falls to ~34% via asset revaluations, improving balance-sheet headroom.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.068 (Cat A) — Trailing distribution yield derived from current market price AUD 3.59 (as of 2026-08-18) and estimated FY2026 DPU of approximately AUD 0.245 (implied by FY2026 full-year results announcement on 2026-08-12 indicating 2% DPU growth from prior-year base of ~AUD 0.24). Yield = 0.245 / 3.59 = ~6.8%. The closing price is Category A; the DPU figure is an analyst estimate pending full filing body extraction (bodies cross-contaminated in stored pipeline; see key_risks).
- `dpu_growth` = 0.02 (Cat B) — FY2026 DPU growth of 2% sourced from Investing.com earnings call transcript and GuruFocus highlights published 2026-08-12 to 2026-08-13, referencing Charter Hall Long WALE REIT FY2026 full year results (ASX filing 2026-08-12, PERIODIC REPORTS, price_sensitive=True). Derived estimate with disclosed source; classified Category B.
- `multiple_change` = -0.005 (Cat C) — Assumed modest -0.5% multiple contraction over 12 months. CLW is reported trading below NTA (Simply Wall St, 2026-08-14) amid higher-for-longer rate environment in Australia. RBA policy rate unavailable from APAC rates store at as_of date. Assumption is that any NTA discount re-rating is offset by residual cap-rate pressure, leaving a small net negative. Sensitivity tested: bull case assumes flat multiples; bear case assumes -2% contraction.
- `gearing_estimate` = 0.38 (Cat B) — CLW gearing estimated at ~38% LVR based on FY2026 full-year results (ASX filing 2026-08-12) and news referencing a $2B debt refinancing completed in H2 FY2026 (Investing.com, 2026-08-13). Australian A-REIT convention cap is ~40%. Estimate is Category B — filing body text unavailable for precise extraction due to ASX body pipeline cross-contamination.
- `wale_profile` = long (Cat B) — CLW's defining characteristic is its long weighted-average lease expiry (WALE), typically reported at 10+ years with government, social-infrastructure and industrial tenants. Classified Category B as no specific WALE figure could be extracted from available filing bodies (cross-contamination in stored pipeline). Consistent with historical reporting and REIT mandate name.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces measurement noise in the computed beta of 0.616. Treated as Category B input. CAPM alpha inherits the same noise and should not be interpreted as a precise excess-return estimate.

## Key Risks
- Higher-for-longer RBA policy rates compressing the property yield spread and delaying NTA discount closure; risk is amplified by CLW's long-duration asset profile, which is more rate-sensitive than shorter-WALE peers.
- Gearing near the ~40% Australian A-REIT convention ceiling limits balance-sheet flexibility; any adverse asset revaluation could push leverage above the threshold, requiring equity issuance or asset sales at potentially distressed prices.
- Filing body cross-contamination in the stored ASX pipeline meant that DPU, NTA, gearing and WALE figures could not be confirmed from primary source documents; key assumptions are therefore reliant on news headlines and analyst summaries (Category B/C), introducing estimation risk.
- Benchmark (IASP.L) 5-year annualised return is -4.5%, reflecting a structurally weak APAC REIT environment; beta of 0.62 means CLW is partially exposed to the same headwinds; CAPM alpha (positive at 9.6%) inherits currency-basis noise from AUD/GBP cross-movement.
- Backtest calibration limitation: Phase 2 calibration is a directional signal only; vintage discipline not yet in place (Phase 5). Conviction score should be treated as indicative, not a formally backtested signal.

## Invalidation Condition
Exit the position if CLW reports gearing above 40% LVR for two consecutive semi-annual periods without a credible de-leveraging plan, or if DPU is cut by more than 5% in any reporting period, or if Charter Hall Group (the sponsor) materially reduces its ownership stake in CLW below 10% or publicly signals withdrawal of pipeline support, or if occupancy on the government-linked lease portfolio falls below 97% for two consecutive periods.
