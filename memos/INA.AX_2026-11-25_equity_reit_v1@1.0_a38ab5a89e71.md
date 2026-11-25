# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-11-25_equity_reit_v1@1.0_a38ab5a89e71`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential/Lifestyle Communities
**As of**: 2026-11-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
INA.AX has rerated about 40% since late August 2026 and the ASX headline of 2026-11-25 points to a non-exclusive sale process. Price is therefore driven by event risk more than by fundamentals. The fundamental E(R) of about 4% is roughly in line with the 4.18% T-bill rate, and the 36% annualised volatility gives a 12-month OU Monte Carlo PGain of only 56%. Beta of 0.58 versus IASP.L has a correlation of 0.19 and carries a currency-basis caveat, so the positive CAPM alpha of 4.8% is weak support. The model returns a base conviction of 3, which I cut by one step to 2 because gearing, coverage and sponsor data could not be verified from filings. That leaves a small position sized for a binary outcome.

## Quantitative Chain

- E(R): 0.0400
- Std dev: 0.2462
- P-gain: 0.5627
- CAPM alpha: 0.0476
- Beta: 0.5795
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2500
  - The non-exclusive sale process ends with no binding offer and the takeover premium unwinds, taking the price back toward the 3.7 to 4.0 range from late August and September. Growth in distributable earnings slows to about 2% on weaker settlements and housing-market softness. Higher rates add 25bps or more to cap rates. Gearing rises above the 40% convention for Australia. A stagflation-type rate shock would add to the decline.
- **base**: E(R)=0.0400
  - Central case as built in the chain. Yield is about 2.2%, distributable earnings growth is 5% and the multiple contracts by 3%. No takeover premium is priced, and the price stays in a 4.7 to 5.4 range.
- **bull**: E(R)=0.2500
  - The process produces a binding scheme or takeover offer at a premium to 5.12, or earnings growth of 8% or more coincides with multiple expansion as lifestyle-community assets rerate on strong private-market transaction evidence.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 5.12 (Cat A) — ASX closing price on 2026-11-25 from get_price. The price is up about 40% from the late-August 2026 weekly close of 3.65.
- `distribution_yield` = 0.022 (Cat B) — Approximate trailing distribution of about 11 cents per security divided by the 5.12 price. This is my recollection of published FY25 figures. It could not be verified because the stored filing bodies for INA.AX were mismatched to other issuers, so it is treated as an estimate.
- `distributable_earnings_growth` = 0.05 (Cat C) — Assumed 12-month growth in distributable earnings per security. It comes from rental growth in the lifestyle communities and the development settlement pipeline, with no consensus data available. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.03 (Cat C) — Assumed 3% multiple contraction. The price rerated sharply in late October and November, coinciding with the 'Ingenia's Non-exclusive Process' letter to shareholders (ASX, 2026-11-25). I assume partial mean reversion if the process produces no binding offer. If a bid emerges, the sign could flip.
- `expected_return_build` = 0.04 (Cat C) — E(R) is about 2.2% yield plus 5% growth minus 3% multiple change, rounded to 4.0%. The model does not price a takeover premium.
- `risk_free_rate_note` = 0.0418 (Cat A) — FRED DTB3 3-month US T-bill on 2026-11-24, from get_tbill_rate. It is a USD rate used as the model's standard risk-free input, not an AUD rate.
- `filing_data_gap` = disclosed (Cat B) — INA.AX stored filings from 2026-11-18 to 2026-11-25 returned bodies belonging to other issuers (IG6, KOA, SBZ, NST and others), so none were used. Only the headlines were used. The ASX headline 'Letter to Shareholders, Ingenia's Non-exclusive Process' (2026-11-25, Takeover/Scheme Announcements) is the only INA-specific event. Gearing, coverage and AFFO figures could not be verified from filings.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_quality` = 0.5795 (Cat B) — 252-day beta versus IASP.L with correlation of only 0.185 over 258 observations. Low explanatory power makes beta and the CAPM alpha unreliable.
- `expected_market_return` = -0.0435 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return. It is GBP-denominated and the figure is negative. Currency basis noise applies.

## Key Risks
- Event risk: if the non-exclusive sale process lapses with no bid, the price could fall back toward 3.7 to 4.0, a drop of 20% or more. A bid at a premium would produce a gain that the model does not capture.
- Data gap: the stored filings for INA.AX were mismatched to other issuers, so gearing, AFFO coverage, development settlement volumes and the distribution figure are unverified. Gate statuses are 'info' for that reason.
- Rates and valuation: higher-for-longer Australian rates and cap rate expansion would hurt lifestyle-community valuations and development margins. The risk-free rate is a USD T-bill and the benchmark return of -4.4% is GBP-denominated, so CAPM inputs carry currency noise.
- Beta quality: the 0.19 correlation to IASP.L makes beta and alpha statistically weak. Volatility of 36% is high for a REIT and widens the OU simulation distribution (std dev of 24.6%).
- Calibration limitation: this is a live analysis with a Phase 2 directional signal, not a formal backtest. Macro series beyond DTB3 (FEDFUNDS, T10Y2Y, credit spreads) were not used.

## Invalidation Condition
Exit if the non-exclusive sale process is terminated or lapses with no binding offer and the price closes below about 4.50, or if reported gearing rises above 40% or distribution cover falls below 1.0x. Also exit if later filings show that development settlements or lifestyle-community rental growth are materially weaker than the assumed 5% distributable earnings growth. Any of these would invalidate the thesis that E(R) is at least equal to the risk-free rate.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
