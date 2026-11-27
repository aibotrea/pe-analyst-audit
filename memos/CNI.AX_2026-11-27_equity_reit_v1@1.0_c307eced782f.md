# Specialist Memo — CNI.AX

**Memo ID**: `CNI.AX_2026-11-27_equity_reit_v1@1.0_c307eced782f`
**Ticker**: CNI.AX (Centuria Capital Group)
**Market**: Australia
**Sector**: Diversified (Property Funds Management / Office & Industrial)
**As of**: 2026-11-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CNI is an ASX-listed property funds manager with co-investments across office, industrial and other sectors. It trades at AUD 1.16 after a roughly 41% fall over 12 months, which leaves an estimated forward yield of about 7.3%, subject to verification of guidance. The AGM reportedly reaffirmed FY27 guidance and completed the CEO transition. The OU Monte Carlo gives an expected return of 7.2% against a 25.7% standard deviation, so PGain is only 61% and conviction is capped at 3 (Moderate). Beta of 0.43 has low correlation (0.13) to IASP.L, so it is a weak guide to risk, and the currency-basis caveat applies. Positive CAPM alpha of 6.8% is flattered by the negative trailing benchmark return. Sizing should stay modest given the high volatility, the earnings cyclicality of funds management and the unverified balance-sheet gates.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.2569
- P-gain: 0.6101
- CAPM alpha: 0.0676
- Beta: 0.4330
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2500
  - Higher-for-longer rates, or a stagflation-style shock, push office and industrial cap rates out by 50bps or more. Transaction and performance fees dry up, and co-investment balance-sheet values are marked down. Management cuts or resets the distribution, funds-management earnings fall short of guidance, and the stock extends its 12-month de-rating.
- **base**: E(R)=0.0720
  - Central case as built in the chain: roughly 7.3% distribution yield maintained on reaffirmed guidance, 1% growth, and a 1% multiple drag. Cap rates are broadly flat and AUM grows modestly. Volatility stays elevated near 38%.
- **bull**: E(R)=0.3000
  - Rate cuts compress cap rates and transaction activity recovers, lifting fee income and performance fees. AUM growth and new fund launches beat expectations. The distribution is secure and the stock re-rates toward its early-2026 levels of about AUD 1.6 to 1.9, adding about 15% of multiple expansion on top of yield and growth.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 1.16 (Cat A) — Latest ASX close on 2026-11-27 (AUD 1.16) from get_price. The price is down about 41% from roughly AUD 1.97 in Dec-2025, based on monthly history.
- `distribution_yield` = 0.073 (Cat B) — Estimated forward distribution of roughly 8.5 cents per security divided by the AUD 1.16 price. This is my recollection of management's FY26 guidance, not verified against a filing retrieved in this run. News headlines say FY27 guidance was reaffirmed at the 2026 AGM, but the figure is not confirmed. A distribution reset would change this input directly.
- `dpu_growth` = 0.01 (Cat C) — Assumed 1% distribution growth. CNI is a fund manager with a co-investment balance sheet, so earnings depend on AUM growth, performance fees and transaction fees, which are cyclical. This is below the headline AUM-expansion narrative. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% drag from multiple contraction. Sector rate anxiety, a persistently weak 12-month price trend, and heavy volume (price falling on rising volume) suggest the market is still repricing the stock. No re-rating is assumed.
- `expected_return_build` = 0.073 (Cat B) — E(R) = yield 7.3% (B) + growth 1.0% (C) + multiple change -1.0% (C) = 7.3%.
- `risk_free_rate` = 0.0416 (Cat A) — DTB3 3-month T-bill at 4.16% (observed 2026-11-25) from get_tbill_rate. This is a USD rate, used per the platform methodology. It is not an AUD risk-free rate.
- `expected_market_return` = -0.0421 (Cat B) — Trailing annualised log return of IASP.L over 1260 trading days (about 5.2 years of observations) from calculate_benchmark_return. It is GBP-denominated and absorbs FX co-movement. A negative Rm makes CAPM required return very low (0.54%), which flatters alpha.
- `historical_volatility` = 0.378 (Cat B) — 252-day annualised volatility from stored prices (262 observations). It is very high for a REIT-like instrument and reflects the equity-market sensitivity of a funds manager.
- `filing_body_gap` = disclosed (Cat B) — The 8 most recent stored CNI.AX filing rows had bodies belonging to unrelated issuers (Light & Wonder, ReNerve, Parbo, Objective Corp, Norwest, Citi and ECS) or boilerplate, so no CNI facts were taken from them. Gearing, WALE, occupancy and coverage were not verifiable from retrieved filings. The qualitative gates are therefore marked info rather than pass.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Distribution and guidance risk: the yield estimate rests on unverified FY26/FY27 guidance, and fee earnings could miss it. A reset would hit both income and the multiple.
- Rate and cap-rate risk: sector rate anxiety has driven the de-rating. Further cap-rate expansion would mark down co-investment values and suppress transaction and performance fees.
- High volatility (37.8%) and a persistent downtrend, with price falling on rising volume. The 12-month standard deviation of about 26% means a wide outcome range, and PGain is only about 61%.
- Data gaps: stored filing bodies for CNI.AX were mismatched to other issuers, so gearing, coverage, WALE and concentration could not be verified. The qualitative gates are info rather than pass and could warrant a downward override once verified.
- Benchmark and risk-free inputs are noisy: IASP.L is GBP-denominated with correlation of only 0.13, Rf is a USD T-bill rather than an AUD rate, and the negative trailing Rm flatters CAPM alpha.

## Invalidation Condition
Exit if management cuts or resets the FY27 distribution guidance below roughly 8 cents per security, or if look-through gearing or the funds-management earnings base deteriorates materially, for example funds-under-management outflows or performance-fee earnings falling well short of guidance. Also exit if the price breaks below the AUD 1.00 to 1.03 October 2026 low on rising volume, or if a filing-verified review shows distribution coverage below 1.0x of operating earnings for two consecutive half-year periods.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
