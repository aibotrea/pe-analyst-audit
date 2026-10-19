# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-10-19_equity_reit_v1@1.0_7f6e6b45e6aa`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics (incl. Data Centres)
**As of**: 2026-10-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is a high-quality global industrial and data-centre developer-manager. Its returns come mainly from earnings growth and development, because the roughly 1.1% distribution yield is small. The 12-month OU Monte Carlo gives a 6.9% simulated return, a 19.8% standard deviation and a PGain of 63.6%. Alpha of +9.7% is flattered by the negative IASP.L five-year return and the weak beta fit (currency-basis caveat). That gives Moderate conviction, with no gate-driven downgrade because the available evidence did not show a failure.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1982
- P-gain: 0.6363
- CAPM alpha: 0.0974
- Beta: 0.7515
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or rate-shock path: AUD and US yields rise further, cap rates expand about 50bps, and the data-centre premium de-rates by 15-20% on AI capex digestion or hyperscaler pull-back. Development earnings slip, and earnings growth falls to about 0-2% with multiple compression of 15% or more.
- **base**: E(R)=0.0700
  - Central case as built: about 1.1% distribution yield, 8% earnings growth from the development pipeline and data-centre power conversion, and 2% multiple compression.
- **bull**: E(R)=0.2200
  - Faster data-centre power energisation and development starts lift earnings growth to 12-14%. Rate relief supports a multiple re-rating of about +6-8%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 26.28 (Cat A) — GMG.AX latest close 2026-10-19 via get_price, in AUD.
- `distribution_yield` = 0.0114 (Cat B) — Assumes a flat distribution of about 30 cents per security, based on my recollection of Goodman's published FY25 payout and guidance, divided by the 26.28 close. I could not verify the FY26 DPS from the tools. The stored GMG.AX filings returned in this run contained other issuers' content (Brambles, MC Mining, Podium Minerals and others), so no filing body was used. The low yield reflects Goodman's low-payout, reinvestment model.
- `earnings_growth_12m` = 0.08 (Cat C) — Assumed 12-month growth in operating earnings per security (the value driver, since the payout is small). It rests on development work-in-progress, data-centre power and campus conversion, and rental growth. It is not tied to a consensus figure I could verify. Sensitivity is shown in the bear and bull scenarios (roughly -10% to +20%).
- `multiple_change` = -0.02 (Cat C) — Assumed modest multiple compression of 2% from higher-for-longer rates (US 3M T-bill at 4.08%) and the elevated AI/data-centre premium already in the price. Sensitivity is covered by the bear and bull scenarios.
- `expected_return_build` = 0.07 (Cat C) — E(R) is about 1.1% yield plus 8% growth minus 2% multiple change, rounded to 7.0%. It carries the Category C assumptions above.
- `risk_free_rate` = 0.0408 (Cat A) — FRED DTB3 3-month T-bill, 4.08% on 2026-10-16. This is a USD rate used as the platform's standard Rf for an AUD asset, which is a currency mismatch.
- `expected_market_return` = -0.0499 (Cat B) — IASP.L trailing 5.17-year annualised log return of -4.99% from calculate_benchmark_return. It is GBP-denominated and absorbs FX co-movement. A negative Rm makes CAPM required return negative, which inflates alpha mechanically.
- `historical_volatility` = 0.2916 (Cat B) — 252-day annualised volatility from stored prices, 262 observations.
- `leverage_gearing` = low (roughly 10% look-through, unverified) (Cat C) — Goodman's gearing has historically been in the low teens or below, well inside the AU <40% convention. I could not verify the current figure from the retrieved filings, so this is an assumption.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_value` = 0.7515 (Cat B) — 252-day beta vs IASP.L, 257 observations, correlation only 0.30, so the fit is weak and the beta estimate is noisy.

## Key Risks
- Data-centre and AI-capex cyclicality: the valuation depends on hyperscaler demand and power availability, and de-rating risk is high at about 29% annualised volatility.
- Higher-for-longer rates (US 3M T-bill at 4.08%) compress the multiple and cap rates, and development-margin earnings are sensitive to funding costs.
- Data gap: stored GMG.AX filing bodies returned other issuers' content, so the DPS, gearing, WALE and occupancy figures were not verified from filings and rest on assumptions (Categories B and C).
- Alpha is inflated by the negative IASP.L five-year return (-4.99%) and a beta with only 0.30 correlation. The GBP currency basis adds noise to both beta and Rm, and Rf is a USD rate applied to an AUD asset.
- Distribution coverage is not meaningful for a low-payout developer-manager, and the weak yield gives little income cushion against price falls.

## Invalidation Condition
Exit if Goodman's operating earnings per security growth guidance is cut below about 5%, or reported look-through gearing rises above roughly 20%. Also exit if data-centre pre-commitments or power energisation timelines slip materially for two consecutive reporting periods, or if the price falls through the bear-case level with hyperscaler capex cuts confirmed.
