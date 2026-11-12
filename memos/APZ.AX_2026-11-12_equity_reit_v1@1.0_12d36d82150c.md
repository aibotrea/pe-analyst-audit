# Specialist Memo — APZ.AX

**Memo ID**: `APZ.AX_2026-11-12_equity_reit_v1@1.0_12d36d82150c`
**Ticker**: APZ.AX (Aspen Group)
**Market**: Australia
**Sector**: Residential/Land Lease & Holiday Parks
**As of**: 2026-11-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Aspen Group offers exposure to Australian land lease communities and holiday parks. Recent headlines point to a roughly 10% distribution rise and active capital recycling through a holiday park sale and an Adelaide purchase. The OU Monte Carlo gives a 12-month expected return of about 6.9% against a 22.5% standard deviation, so PGain is only 62%. Beta of 0.84 against IASP.L carries the currency-basis caveat and a weak 0.30 correlation. Conviction is cut one step to 2 (Low) because the yield, coverage and gearing inputs could not be verified from retrieved filings, and 33% realised volatility is high for a REIT.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.2251
- P-gain: 0.6203
- CAPM alpha: 0.0998
- Beta: 0.8414
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - Stagflation or higher-for-longer rate pathway: RBA and US rates stay elevated, and cap rates expand by 50bps or more. Land lease and holiday park valuations soften and the disposal/acquisition recycling is dilutive. Distribution growth stalls at 0%, distribution coverage falls below 1.0x, and the multiple contracts 10%+, in line with the 33% realised volatility.
- **base**: E(R)=0.0700
  - Central case as built in the chain: 4.5% yield, 3% growth, and a -0.5% multiple change. Gearing stays under 40%, and the holiday park sale and Adelaide purchase complete without NAV dilution.
- **bull**: E(R)=0.2600
  - Distribution growth sustains near the headline 10% rise, and the holiday park sale crystallises gains above book value. Recycling into Adelaide is accretive, rate cuts compress cap rates, and the multiple re-rates 8-10%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 5.08 (Cat A) — APZ.AX closing price AUD 5.08 on 2026-11-12 (get_price).
- `distribution_yield` = 0.045 (Cat C) — Forward distribution yield assumption of about 4.5%. I could not verify the published FY26 DPS from the retrieved filings, because the stored filing bodies returned for this ticker were unrelated third-party notices. The assumption rests only on the news headline of a ~10% distribution rise (Kalkine, 2026-10-23). Sensitivity: each 1pt of yield error moves E(R) by 1pt.
- `dpu_growth` = 0.03 (Cat C) — Distribution/earnings growth assumption of 3%. This is a haircut to the ~10% FY26 distribution rise headline, allowing for normalisation and for the holiday park disposal and Adelaide acquisition headline (Kalkine, 2026-10-23), whose terms were not retrieved.
- `multiple_change` = -0.005 (Cat C) — Small multiple contraction assumption of -0.5%. The price recovered from a low near 4.25 (2026-10-01) to 5.08, and the 12-month volatility of 33% is high for a REIT.
- `expected_return_build` = 0.07 (Cat C) — E(R) = 4.5% yield + 3.0% growth - 0.5% multiple change = 7.0%.
- `risk_free_rate` = 0.0412 (Cat A) — FRED DTB3 3-month US T-bill rate 4.12% on 2026-11-10 (get_tbill_rate). This is a USD rate used as the platform risk-free proxy for an AUD-denominated asset.
- `expected_market_return` = -0.0432 (Cat B) — IASP.L trailing 5.18-year annualised log return of -4.32% (calculate_benchmark_return). GBP-denominated, so it absorbs FX co-movement.
- `historical_volatility` = 0.3312 (Cat A) — Annualised volatility from 252 days of stored prices (262 observations).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_quality` = 0.8414 (Cat B) — Beta 0.84 on 258 observations, but correlation with IASP.L is only 0.30, so the estimate is statistically weak. The CAPM alpha of ~10% is inflated by the negative trailing benchmark return and should be treated with caution.
- `gearing_assumption` = unverified (Cat C) — Gearing and distribution coverage were not confirmed from retrieved filings. The assumption is that gearing stays below the 40% Australian convention and that coverage by operating earnings is at least 1.0x. This is flagged as a data gap.

## Key Risks
- Distribution yield, coverage and gearing could not be verified from retrieved filings, which returned unrelated third-party notices. E(R) rests on Category C assumptions.
- High realised volatility of 33% and a wide MC standard deviation of 22.5% make the return distribution very wide, with PGain at only about 62%.
- Higher-for-longer rates or stagflation could expand cap rates and compress land lease and holiday park valuations.
- Execution risk on the holiday park sale and Adelaide acquisition, including dilution and funding terms that were not retrieved.
- Beta and market return are measured against a GBP benchmark with a correlation of 0.30, so CAPM alpha is unreliable. The risk-free rate is a USD T-bill used as a proxy for an AUD asset.

## Invalidation Condition
Exit if reported distribution coverage by operating earnings falls below 1.0x, or gearing rises above the roughly 40% Australian convention, or the holiday park sale and Adelaide acquisition prove NAV-dilutive. Also exit if the unit price breaks decisively below the October 2026 low near A$4.25 on deteriorating fundamentals, or if the next results show that the ~10% distribution rise is not sustainable.
