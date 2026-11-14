# Specialist Memo — CQE.AX

**Memo ID**: `CQE.AX_2026-11-14_equity_reit_v1@1.0_9854d5dba776`
**Ticker**: CQE.AX (Charter Hall Social Infrastructure REIT)
**Market**: Australia
**Sector**: Social Infrastructure (Childcare/Community)
**As of**: 2026-11-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CQE is an Australian social infrastructure REIT, mainly childcare and community assets, sponsored by Charter Hall. It offers a roughly 6.3% yield backed by long leases and rent escalators, which is about 2.2 points above the 4.14% T-bill rate. The OU Monte Carlo gives a simulated 12-month return of 7.7% with a standard deviation of 16.5%, so PGain is 68%. Beta is 0.67 against IASP.L, with the currency-basis caveat applying, and CAPM alpha is flattered by the benchmark's negative 5-year return. Conviction is moderate because the return is mostly yield, volatility is high at 24%, and issuer fundamentals could not be verified from filings.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1646
- P-gain: 0.6806
- CAPM alpha: 0.0931
- Beta: 0.6683
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0900
  - A higher-for-longer rate or stagflation path pushes cap rates out by 50bps and valuations down about 8-10%. Refinancing costs squeeze distributable income and growth falls to zero. Childcare rent reviews and occupancy soften, and the price-to-NTA discount widens.
- **base**: E(R)=0.0780
  - Central case as built: 6.3% yield, 1.5% income growth, flat cap rates and a stable price-to-NTA multiple. Distribution coverage holds at or above 1.0x.
- **bull**: E(R)=0.2000
  - Rate cuts compress cap rates by 25bps and the discount to NTA narrows. Rent escalators and accretive recycling lift income growth to about 3.5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 2.62 (Cat A) — Latest close of AUD 2.62 on 2026-11-13 from get_price.
- `distribution_yield` = 0.063 (Cat B) — Forward distribution yield estimate of about 6.3%. It is derived from a third-party report (Kalkine, July 2026) quoting a 6.48% yield, adjusted down slightly for the current price. The issuer DPU was not verified from a filing, because the stored filing bodies returned for CQE.AX were unrelated issuers' documents and were ignored.
- `distributable_income_growth` = 0.015 (Cat C) — Assumed 1.5% annual growth in distributions. It rests on contracted and CPI-linked rent escalators on long-lease social infrastructure assets, partly offset by higher refinancing costs. It is not tied to consensus, so it is tested in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes flat price-to-NTA and cap rates over 12 months. No re-rating is assumed, and the bear and bull cases flex this.
- `expected_return_build` = 0.078 (Cat B) — E(R) = yield 6.3% + growth 1.5% + multiple change 0.0% = 7.8%.
- `risk_free_rate` = 0.0414 (Cat A) — FRED DTB3 3-month T-bill at 4.14% on 2026-11-12, from get_tbill_rate. This is a USD rate used as the platform's standard Rf.
- `expected_market_return` = -0.043142 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (1260-day lookback). It is GBP-denominated and absorbs FX co-movement. The negative figure makes CAPM required return low (-1.5%), which flatters alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `fundamental_data_gap` = disclosed (Cat C) — Gearing, AFFO coverage, WALE, occupancy and tenant concentration could not be verified from the stored filings or search results. The gate assessments use general knowledge of the Charter Hall-sponsored portfolio (childcare, Goodstart concentration, gearing historically around 30%) and are marked 'info', not 'pass'.

## Key Risks
- Higher-for-longer rates or a stagflation path could widen cap rates and the NTA discount, and raise refinancing costs for a leveraged REIT.
- Tenant and asset-class concentration in childcare, with policy risk from government subsidy and regulation and exposure to a few large operators.
- Issuer gearing, AFFO coverage, WALE and DPU could not be verified from filings, and gate assessments rely on general knowledge.
- The IASP.L benchmark is GBP-denominated, so beta (correlation only 0.33) and market return carry heavy FX noise, and the negative Rm inflates CAPM alpha.
- Realised volatility of 24% is well above what the yield alone justifies, and the AUD/USD basis between the T-bill Rf and AUD returns adds error.

## Invalidation Condition
Exit if reported gearing rises above 40% or distribution coverage falls below 1.0x AFFO for two consecutive reporting periods. Exit too if a DPU cut is announced, if occupancy or WALE deteriorates materially, or if Charter Hall reduces its sponsor support. A sustained cap-rate expansion of 50bps or more that pushes the price-to-NTA discount beyond 20% would also invalidate the thesis.
