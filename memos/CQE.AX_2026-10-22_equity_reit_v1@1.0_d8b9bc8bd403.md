# Specialist Memo — CQE.AX

**Memo ID**: `CQE.AX_2026-10-22_equity_reit_v1@1.0_d8b9bc8bd403`
**Ticker**: CQE.AX (Charter Hall Social Infrastructure REIT)
**Market**: Australia
**Sector**: Social Infrastructure (Childcare/Community)
**As of**: 2026-10-22
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CQE offers AUD social infrastructure exposure (childcare and community assets) with long leases and a yield of about 6.5%, backed by the Charter Hall sponsor platform. A 12-month E(R) of 9.0% (yield plus modest growth, no re-rating) gives an OU Monte Carlo PGain of 70.8% on a simulated standard deviation of 16.3%. The numeric chain supports a score of 4. CAPM alpha of 11% is inflated by the negative IASP.L 5-year return and by the currency-basis noise in a beta of 0.67 (correlation 0.32). Fundamentals could not be verified from primary filings, so conviction is cut one step to 3.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1633
- P-gain: 0.7077
- CAPM alpha: 0.1108
- Beta: 0.6694
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - A stagflation or higher-for-longer rate path pushes AU valuation yields out 50bps and compresses the multiple by about 8%. DPU growth falls to 0% on refinancing costs and slower childcare rent reviews, and coverage falls below 1.0x. Gearing drifts toward the top of the 30-40% range.
- **base**: E(R)=0.0900
  - Central case as built in the chain: yield about 6.5%, DPU growth about 2.5% from rent reviews, no multiple change, and stable occupancy and gearing.
- **bull**: E(R)=0.2000
  - RBA easing and lower bond yields drive a 5-8% re-rating toward NAV. DPU growth rises to about 4% on accretive acquisitions and developments from the Charter Hall pipeline, with occupancy and WALE holding.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.065 (Cat A) — Trailing distribution yield of about 6.5%, based on a 6.48% yield reported by Kalkine (2026-07-20) and the last close of AUD 2.37 (2026-10-22). The figure comes from secondary news, not a primary filing. The stored CQE filing bodies were mismatched with other issuers and were ignored.
- `dpu_growth` = 0.025 (Cat C) — Assumed forward distribution growth of about 2.5%. It rests on fixed and CPI-linked rent reviews on long-lease childcare and community assets, less funding-cost drag from refinancing. The FY27 guidance was not verified against a primary filing. Sensitivity is covered in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in the yield or price-to-NAV multiple over 12 months. Units have lagged over the past year, so re-rating is possible in either direction. It is neutral in the base case and tested in the bear and bull cases.
- `expected_return_build` = 0.09 (Cat B) — E(R) is about 6.5% yield + 2.5% growth + 0% multiple change, which gives 9.0%. This is a derived estimate.
- `risk_free_rate` = 0.0407 (Cat A) — FRED DTB3 3-month US T-bill rate, 4.07% on 2026-10-21. The rate is USD-based, so it does not match the AUD cash rate.
- `expected_market_return` = -0.0511 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return. It is GBP-denominated and absorbs FX co-movement. The negative figure mechanically inflates CAPM alpha.
- `historical_volatility` = 0.2402 (Cat B) — 252-day annualised volatility from stored AUD prices (262 observations).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gate_data_gap` = disclosed (Cat C) — Gearing, AFFO coverage, occupancy and WALE could not be sourced from primary filings. Stored filing bodies were off-topic, and ASX body capture is parked. A one-step conservative override is applied on distribution_coverage for this data gap.

## Key Risks
- Rates risk: higher-for-longer Australian bond yields could widen valuation yields and compress NAV and unit price, and refinancing would raise interest costs and cut DPU growth.
- Data gap: gearing, AFFO coverage, occupancy, WALE and tenant concentration were not verified from primary filings (stored bodies were off-topic and ASX body capture is parked). The yield comes from secondary news.
- Sector and policy risk: childcare operator credit, government funding or subsidy changes, and a lower-yield operator mix could affect rent collection and re-leasing.
- Benchmark noise: IASP.L is GBP-denominated, the beta correlation is only 0.32, and the negative 5-year market return mechanically inflates CAPM alpha. Rf is a USD T-bill rate used for an AUD asset.
- Volatility and mean reversion: realised volatility of 24% and units that have lagged over the past year point to a wide outcome range, and the OU Monte Carlo assumes mean reversion.

## Invalidation Condition
Exit if aggregate gearing rises above 40% or interest cover falls below 2.0x, if distribution coverage falls below 1.0x AFFO for two consecutive reporting periods, if portfolio occupancy drops below 95% or WALE shortens materially, or if Charter Hall reduces its sponsor support. Also exit if the DPU is cut and the 12-month PGain falls below 55%.
