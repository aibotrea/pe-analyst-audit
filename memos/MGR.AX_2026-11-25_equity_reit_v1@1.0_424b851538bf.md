# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-11-25_equity_reit_v1@1.0_424b851538bf`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified (Office/Industrial/Residential Development)
**As of**: 2026-11-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mirvac is a diversified Australian REIT with low gearing (about 24%) and an internalised management model. FY26 operating profit grew about 7%, and the shares have de-rated about 22% over the past year, which gives a roughly 5.5% yield and a balance sheet able to fund buy-backs. The OU Monte Carlo gives a 12-month expected return of about 7.9% with a standard deviation of 16.1%, which implies a PGain of 68.9%. Beta of 0.76 against IASP.L carries the currency-basis caveat, and the large negative IASP.L 5-year return inflates CAPM alpha, so I weight PGain over alpha. Moderate conviction (3/5) fits a positive but not compelling risk-adjusted return, with development and office exposure and AUD rate sensitivity as the main uncertainties.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1607
- P-gain: 0.6890
- CAPM alpha: 0.1032
- Beta: 0.7619
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - A stagflation-style rate shock lifts Australian bond yields and widens cap rates by 50bps or more. Office valuations are written down and residential development margins and settlements weaken. Distribution growth is zero or negative and the stock de-rates further. AUD weakness adds currency-basis drag.
- **base**: E(R)=0.0800
  - Central case as built in the chain: 5.5% yield, 3% growth, flat multiple. Gearing stays near 24%, office and industrial occupancy is stable, and development settlements proceed on schedule.
- **bull**: E(R)=0.2200
  - RBA easing and lower bond yields drive cap rate compression and a re-rating toward NTA. Residential and build-to-rent pipeline delivery is strong, earnings growth reaches 6-7%, and the ongoing buy-back is accretive.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 1.92 (Cat A) — MGR.AX closing price on 2026-11-25 from get_price (AUD).
- `distribution_yield` = 0.055 (Cat B) — Estimated forward DPS of about AUD 0.106 divided by AUD 1.92 price. The DPS figure is my recollection of FY26 guidance and was not verified against a filing. The stored filing bodies returned for MGR were off-topic, so I did not use them.
- `dpu_growth` = 0.03 (Cat C) — Assumed 3% growth in distributions and earnings. Supported by FY26 operating profit growth of about 7% (Kalkine, 2026-08-19) but moderated for development and residential earnings volatility. Tested in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating or de-rating assumed. Shares fell about 22% over the past year (Kalkine, 2026-10-04), so upside from multiple recovery is possible but is not underwritten.
- `gearing` = 0.241 (Cat B) — FY26 gearing of 24.1% as reported in news coverage of the FY26 result (Kalkine, 2026-08-19). I did not verify it against the issuer filing.
- `risk_free_rate_source` = 0.0418 (Cat A) — FRED DTB3 3-month T-bill at 4.18% on 2026-11-24 via get_tbill_rate. This is a USD rate used as the risk-free proxy for an AUD asset.
- `expected_market_return` = -0.0435 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260-day lookback). Currency-basis noise applies. This is a negative CAPM market return, which inflates alpha mechanically.
- `expected_return_build` = 0.08 (Cat C) — E(R) = 5.5% yield + 3.0% growth + 0% multiple change, rounded to 8.0%. Tested in the three scenarios.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer rates or a stagflation shock widening cap rates and compressing office and diversified asset valuations
- Residential development earnings volatility, including settlement delays and margin pressure, affecting the earnings that support the distribution
- Key figures (DPS, gearing, coverage) are unverified secondary-source or recalled figures, and the stored filing bodies were off-topic, so fundamentals are less certain than the quantitative chain
- Currency-basis noise in beta and the market return: IASP.L is GBP-denominated and has a negative 5-year return, which mechanically inflates CAPM alpha and uses a USD T-bill as Rf for an AUD asset
- Moderate beta correlation (0.37) with the benchmark means the beta estimate is statistically weak

## Invalidation Condition
Exit if gearing rises above 35% or distribution coverage falls below 1.0x operating earnings for two consecutive half-year reporting periods. Also exit if office or industrial occupancy drops materially below recent levels, or if cap-rate expansion of 50bps or more drives material NTA write-downs and a cut to DPS guidance.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
