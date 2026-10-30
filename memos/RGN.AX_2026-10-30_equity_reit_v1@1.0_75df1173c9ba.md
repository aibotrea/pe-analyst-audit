# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-10-30_equity_reit_v1@1.0_75df1173c9ba`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail (Neighbourhood/Convenience Shopping Centres)
**As of**: 2026-10-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Region Group is an Australian neighbourhood and grocery-anchored retail REIT. Its defensive tenancy base supports an estimated 5% yield and about 3% FFO growth guidance for FY27, which together give an E(R) of about 8%. The OU Monte Carlo gives a simulated return of 7.95% with a 10.3% standard deviation, so PGain is 78%. Beta of 0.47 versus IASP.L (currency-basis caveat applies) and alpha of 8.1% are flattered by the negative trailing benchmark return and should not be over-weighted. The numeric chain supports conviction of 4, and I reduced it one step to 3 because fundamentals (gearing, AFFO coverage, occupancy) were not verified from primary filings.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1028
- P-gain: 0.7804
- CAPM alpha: 0.0813
- Beta: 0.4720
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Stagflation or higher-for-longer rate pathway: AUD bond yields rise and cap rates expand about 25-50bps. Specialty and neighbourhood retail sales soften, FFO growth stalls at 0% and AFFO coverage falls below 1.0x. The P/FFO multiple de-rates about 10%, partly offset by a roughly 5% yield.
- **base**: E(R)=0.0800
  - Central case as built in the chain: about 5.0% distribution yield, about 3% FFO and DPU growth in line with FY27 guidance, flat cap rates and a flat multiple. Occupancy is stable and the buy-back continues.
- **bull**: E(R)=0.1900
  - RBA easing compresses cap rates by about 25bps and the P/FFO multiple re-rates about 5-6%. FFO growth reaches 4-5% on strong comparable NOI and accretive buy-backs or capital recycling, with the discount to NTA narrowing.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 2.31 (Cat A) — RGN.AX latest close 2026-10-30 in AUD from get_price.
- `distribution_yield` = 0.05 (Cat B) — Estimated forward distribution yield of about 5.0% on the AUD 2.31 price. It assumes a payout of roughly 85-90% of FFO. I could not retrieve the FY26 DPS from a primary filing, because the stored filing bodies returned for RGN.AX were mismatched documents from other issuers and were ignored. Treat the yield as an approximation to be verified against the FY26 results release.
- `ffo_dpu_growth` = 0.03 (Cat B) — FY27 FFO growth guidance of about 3%, from news headlines on the FY26 results (Kalkine, 2026-08-18: 'FFO Growth, Higher Occupancy and 3% FY27 Guidance'). Used as the growth proxy, assuming DPU grows in line with FFO. The underlying release was not read directly.
- `multiple_change` = 0.0 (Cat C) — Assumes flat cap rates and a flat P/FFO multiple over 12 months. The company is running an on-market buy-back (ASX notices 2026-10-26 to 2026-10-30), which supports the unit price but is not counted as upside. Sensitivity of roughly +/-25bps of cap rate is covered in the bear and bull scenarios.
- `expected_return_build` = 0.08 (Cat B) — E(R) = yield 5.0% + growth 3.0% + multiple change 0.0% = 8.0%.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill rate of 4.00% on 2026-10-29. It is a USD rate, used as the platform's standard risk-free input, so there is a USD/AUD basis mismatch.
- `expected_market_return` = -0.047539 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (1260-day lookback). It is negative and GBP-denominated, which makes CAPM alpha mechanically favourable.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `fundamentals_data_gap` = disclosed (Cat C) — Gearing, AFFO coverage, occupancy, WALE and sponsor or manager details were not verified from filings for this memo. Gate assessments rely on prior knowledge of RGN (gearing historically low-to-mid 30% range, internally managed, grocery-anchored portfolio). A one-step conservative conviction reduction is applied for this gap.

## Key Risks
- Higher-for-longer AUD rates or rising bond yields could expand cap rates and compress the REIT's valuation spread to the risk-free rate.
- Fundamentals were not verified from primary filings: stored RGN filing bodies were mismatched documents from other issuers, so the yield, growth, gearing and coverage inputs rest on news headlines and prior knowledge.
- Beta and CAPM alpha are distorted by the GBP-denominated IASP.L benchmark (correlation 0.37) and a negative 5-year benchmark return. Alpha is likely overstated, and the USD T-bill is used as the risk-free rate for an AUD asset.
- Consumer spending weakness and retailer insolvencies could hit specialty tenant income and occupancy.
- The expected-return build rests on a flat-multiple assumption (Category C) and on headline 3% guidance, so a miss on either would remove most of the modelled return.

## Invalidation Condition
Exit if RGN reports AFFO distribution coverage below 1.0x for two consecutive half-year periods, or if gearing rises above the roughly 40% Australian convention. Also exit if portfolio occupancy falls materially below 97% alongside negative comparable NOI growth, or if cap rates expand more than 50bps without offsetting FFO growth. A fall in the PGain-implied return below zero would also invalidate the thesis.
