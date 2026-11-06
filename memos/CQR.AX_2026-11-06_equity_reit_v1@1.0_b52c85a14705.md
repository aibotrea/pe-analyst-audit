# Specialist Memo — CQR.AX

**Memo ID**: `CQR.AX_2026-11-06_equity_reit_v1@1.0_b52c85a14705`
**Ticker**: CQR.AX (Charter Hall Retail REIT)
**Market**: Australia
**Sector**: Retail (Convenience/Net Lease)
**As of**: 2026-11-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CQR is an Australian convenience and net-lease retail REIT with a sponsor-backed (Charter Hall) platform. News points to higher FY27 guidance. The estimated yield of about 6.5% plus modest growth gives an 8% E(R), a 4-point spread over the 4.0% T-bill rate. The OU Monte Carlo gives a 12-month PGain of about 72%, supporting a base conviction of 4. Fundamentals (DPU, gearing, coverage) could not be verified from a retrieved filing, and recent news flags softer trading. I therefore applied a one-step downward override on distribution coverage to give a final conviction of 3. Beta of 0.64 is against a GBP benchmark, so the currency-basis caveat applies.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1365
- P-gain: 0.7195
- CAPM alpha: 0.0947
- Beta: 0.6352
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Softer convenience-retail trading and weaker specialty sales push occupancy and rental growth down. Distribution coverage falls below 1.0x. Cap rates widen by 25-50bps under a stagflation or higher-for-longer rate path. Yield multiple de-rates by about 10%.
- **base**: E(R)=0.0800
  - Central case as built in the chain: 6.5% yield, 2% growth in line with FY27 guidance, about 0.5% de-rating and stable occupancy and gearing.
- **bull**: E(R)=0.2000
  - Australian rates ease and cap rates compress by 25bps. FY27 guidance is beaten on net-lease income growth, and accretive recycling lifts earnings growth to about 4%. The yield multiple expands by about 5-6%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 3.94 (Cat A) — CQR.AX closing price on 2026-11-06 (AUD) from get_price.
- `distribution_yield` = 0.065 (Cat B) — Approximate trailing distribution per security (~25.5c) divided by the A$3.94 price. I could not verify the DPU from a retrieved filing. The stored CQR filing bodies were mislabelled and came from unrelated issuers, so I ignored them. News flags FY27 guidance as higher, but I did not see the figures. Treat the yield as an estimate.
- `dpu_growth` = 0.02 (Cat C) — Assumed distribution/earnings growth of about 2%. This rests on news headlines of higher FY27 guidance, convenience-retail rental growth and net-lease income. It sits below the likely guided growth to allow for softer-trading commentary. Tested in the bear and bull scenarios.
- `multiple_change` = -0.005 (Cat C) — Assumed small yield-multiple de-rating of about 0.5%. Reasons: Rf is 4.0%, which limits the REIT yield spread, and the price has recovered from about A$3.34 in early October to A$3.94. It is only an assumption and carries no valuation work.
- `expected_return_build` = 0.08 (Cat B) — E(R) = 6.5% yield + 2.0% growth - 0.5% multiple change = 8.0%. The components are classified B, C and C respectively.
- `historical_volatility` = 0.2009 (Cat A) — 252-day annualised volatility from stored prices (262 observations). The stored series shows an odd discontinuity around 2026-09-23, which may reflect price adjustment.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill rate of 4.0% on 2026-11-05, which is a USD rate applied to an AUD asset.
- `expected_market_return` = -0.0461 (Cat B) — IASP.L trailing 5.18-year annualised log return computed by calculate_benchmark_return. It is GBP-denominated and absorbs FX noise. It is negative, which inflates CAPM alpha mechanically.
- `gearing_assumption` = 0.33 (Cat C) — Gearing of roughly 30-35%, inside the AU convention of under 40%. This is not verified from a filing in this run and relies on prior knowledge of the REIT's reported range.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer Australian rates compressing the yield spread to the 4.0% risk-free rate and widening cap rates.
- Softer retail trading or specialty tenant stress could cut occupancy, rental growth and distribution coverage. News flags the convenience strategy as under review.
- Fundamental data could not be verified: the stored filings were mislabelled or off-topic, so DPU, gearing, coverage and WALE are estimates.
- CAPM alpha is inflated by the negative IASP.L 5-year return, and beta of 0.64 with correlation of about 0.38 carries currency-basis noise (AUD vs GBP). The stored price series also shows a discontinuity in late September.
- Calibration is directional only and not a formal backtest, and the USD T-bill is used as Rf for an AUD asset.

## Invalidation Condition
Exit if reported distribution coverage by operating earnings falls below 1.0x for two consecutive reporting periods, if gearing rises above 40% or interest cover weakens materially, if portfolio occupancy drops below about 97% with negative like-for-like rental growth, or if the Charter Hall sponsor cuts its support. Exit also if the OU-based 12-month PGain falls below 55% on a refreshed run.
