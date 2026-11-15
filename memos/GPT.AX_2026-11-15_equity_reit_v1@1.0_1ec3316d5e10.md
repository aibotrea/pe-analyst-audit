# Specialist Memo — GPT.AX

**Memo ID**: `GPT.AX_2026-11-15_equity_reit_v1@1.0_1ec3316d5e10`
**Ticker**: GPT.AX (GPT Group)
**Market**: Australia
**Sector**: Diversified (Office/Retail/Logistics)
**As of**: 2026-11-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
GPT is a diversified Australian REIT (office, retail, logistics) with an assumed forward distribution yield of about 5.1% and a mid-single-digit total-return profile. The Group expanded its value-add Partnership on 2026-09-13. The OU Monte Carlo gives a 12-month expected return of about 7.0% with a standard deviation of 14.9%, which implies a PGain of 68%. Beta of 0.77 against IASP.L carries a currency-basis caveat. The positive CAPM alpha is flattered by the negative trailing benchmark return, so it is a supporting input only. Moderate conviction fits a decent but not compelling risk-adjusted return, with fundamentals not independently verified.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1493
- P-gain: 0.6812
- CAPM alpha: 0.0950
- Beta: 0.7736
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - A higher-for-longer or stagflation-style rate shock lifts Australian bond yields. Cap rates expand by 50bps, office valuations fall, and P/NTA de-rates by about 10%. Distribution growth is 0% and gearing rises toward 35%. Retail and logistics earnings soften.
- **base**: E(R)=0.0710
  - Central case as built in the chain: yield about 5.1%, growth about 2%, flat multiple and flat cap rates. Gearing stays near 30% and the value-add partnership contributes modestly.
- **bull**: E(R)=0.2000
  - RBA easing and falling bond yields compress cap rates by about 25bps. P/NTA re-rates by about 7%. Office leasing recovers, development and partnership pipeline completes accretively, and distribution growth reaches about 4%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 5.1 (Cat A) — GPT.AX last close AUD 5.10 on 2026-11-13 (get_price).
- `distribution_yield` = 0.051 (Cat C) — Assumes a forward DPS of about AUD 0.26 (roughly 26 cps) against a AUD 5.10 price. The stored filing bodies for GPT.AX returned content from unrelated issuers, so the DPS could not be verified from an issuer document. The figure is recalled from prior published guidance. Sensitivity: each ±1c of DPS moves yield by about ±0.2pp.
- `dpu_growth` = 0.02 (Cat C) — Assumed 2% annual distribution and NTA growth from rental reversion and development and value-add partnership contribution, partly offset by higher funding costs. This is below any unverified consensus. It is tested in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes a flat P/NTA multiple and flat cap rates over 12 months. No valuation re-rating is underwritten.
- `expected_return_build` = 0.071 (Cat C) — E(R) = 5.1% yield + 2.0% growth + 0.0% multiple change = 7.1%. The yield is Category C because it could not be verified. The growth and multiple components are Category C. Total return is a model assumption.
- `historical_volatility` = 0.2196 (Cat B) — 252-day annualised volatility from stored prices (262 observations).
- `risk_free_rate` = 0.0414 (Cat A) — FRED DTB3 3-month T-bill 4.14% observed 2026-11-12. It is a USD rate used as the platform's standard Rf for AUD assets, so there is a currency mismatch.
- `expected_market_return` = -0.0431 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (1305 observations). It is GBP-denominated and negative, so it inflates CAPM alpha. Alpha should be read with caution.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `leverage_assumption` = 0.3 (Cat C) — Assumed look-through gearing near 30%, which is within the Australian convention of below 40%. This was not verified from a filing body, because the GPT.AX stored filing bodies were mismatched with other issuers. The 2026 interim result and September-quarter 2026 operating update were identified by headline only.

## Key Risks
- Fundamental inputs (DPS, gearing, AFFO coverage, occupancy) could not be verified. The stored filing bodies for GPT.AX contained other issuers' documents, so the yield and growth components are Category C.
- Higher-for-longer Australian rates or a stagflation scenario would widen cap rates and compress P/NTA, especially in the office portfolio.
- The CAPM alpha of 9.5% is inflated by the negative IASP.L trailing 5-year return (-4.3%, GBP basis). The Rf is a USD T-bill applied to an AUD asset. Currency-basis noise affects both beta and market return.
- The 2026 interim result and the September-quarter 2026 operating update were not readable, so recent leasing, occupancy and guidance changes are unknown. Development and partnership execution risk applies.
- Macro signals beyond DTB3 were not analysed. The 21.96% volatility is high for a REIT and the correlation to the benchmark is only 0.41, so beta is a noisy estimate.

## Invalidation Condition
Exit if reported distribution coverage by AFFO falls below 1.0x or FY27 distribution guidance is cut. Also exit if look-through gearing rises above 40% or portfolio occupancy drops materially (below about 93%) for two consecutive reporting periods. A sustained 50bps or larger rise in Australian cap rates or independent valuation write-downs of more than 5% would also invalidate the thesis.
