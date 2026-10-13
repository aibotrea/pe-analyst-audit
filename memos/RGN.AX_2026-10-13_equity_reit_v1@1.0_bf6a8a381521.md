# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-10-13_equity_reit_v1@1.0_bf6a8a381521`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail (Neighbourhood/Convenience Shopping Centres)
**As of**: 2026-10-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Region Group offers defensive, non-discretionary neighbourhood retail exposure with FY27 guidance of ~3% growth and an active buy-back. An estimated ~5.9% yield plus ~3% growth gives a 12-month expected return of about 7.8%. The OU Monte Carlo gives a PGain of about 78% with 10% simulated volatility. Beta of 0.46 versus IASP.L is low, and the currency-basis caveat applies. The numeric chain supports a conviction of 4, but I applied a one-step downward gate override. The distribution and gearing inputs could not be verified from primary filings, the yield spread to the 4.06% T-bill is thin, and the CAPM alpha is flattered by a negative IASP.L 5-year return.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1015
- P-gain: 0.7776
- CAPM alpha: 0.0790
- Beta: 0.4589
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Stagflation-style pathway: RBA and long-end yields rise further and AUD 3M/10Y rates stay elevated. Neighbourhood retail cap rates expand ~40bps, FFO growth stalls at 0-1%, distribution coverage slips toward 1.0x AFFO, and gearing drifts above 35% as valuations soften.
- **base**: E(R)=0.0780
  - Central case as built in the chain: ~5.9% yield, ~3% FFO/DPU growth in line with FY27 guidance, stable occupancy, and ~1pp of multiple drag from a flat-to-higher rate backdrop.
- **bull**: E(R)=0.1900
  - Rates ease and cap rates compress ~25bps. Leasing spreads and occupancy improve, FFO growth reaches 4-5%, and buy-backs at a discount to NTA add accretion, so the stock re-rates toward NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 2.2 (Cat A) — RGN.AX latest close AUD 2.20 on 2026-10-13 (get_price).
- `distribution_yield` = 0.059 (Cat C) — Approx. forward distribution of ~13.0 cps on AUD 2.20 price. The cps figure is a recollection of FY25/FY26 payout levels and was NOT verified. The stored filing bodies returned for RGN.AX were off-topic (other issuers' announcements) and were ignored. Sensitivity: +/-0.5c DPS moves yield by about +/-0.23pp.
- `dpu_growth_12m` = 0.03 (Cat B) — FY27 FFO/distribution growth of ~3% per a Kalkine headline on RGN FY26 results (2026-08-18). The headline was not verified against the primary results filing. Sensitivity is tested in the bear and bull scenarios.
- `multiple_change` = -0.011 (Cat C) — Assumed modest cap-rate/multiple drag. 3M T-bill is 4.06% and the yield spread to the risk-free rate is thin. Sum of components: 5.9% + 3.0% - 1.1% = 7.8%.
- `risk_free_rate` = 0.0406 (Cat A) — FRED DTB3 3-month US T-bill 4.06% on 2026-10-09 (get_tbill_rate). It is a USD rate used as the platform Rf, not an AUD rate.
- `expected_market_return` = -0.050045 (Cat B) — IASP.L trailing 5.17y annualised log return from calculate_benchmark_return (1260-day lookback). GBP-denominated, so it absorbs FX noise. The negative Rm inflates CAPM alpha mechanically.
- `gearing_assumption` = 0.31 (Cat C) — Assumed look-through gearing of ~30-32%, inside the Australian <40% convention. It was not verified from a filing and is a model assumption. Ongoing on-market buy-backs (ASX Appendix 3E updates, Sept 2026) suggest balance-sheet capacity.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer rates (RBA and US T-bill at 4.06%) compress the yield spread and widen cap rates, hurting valuations and funding costs
- Key distribution, gearing and coverage inputs are unverified: stored ASX filing bodies were off-topic and ASX body capture is not usable, so AFFO coverage and gearing are Category C assumptions
- Expected market return from IASP.L is negative (-5.0% over 5y) and GBP-denominated, so CAPM alpha is inflated and carries currency-basis noise; beta correlation is only 0.36
- Consumer spending slowdown or tenant failures at neighbourhood centres, and refinancing at higher hedged debt costs, could erode FFO growth below the ~3% guidance
- Directional calibration only; no vintage discipline, and the 12-month OU Monte Carlo relies on trailing 252-day volatility

## Invalidation Condition
Exit if reported distribution coverage falls below 1.0x AFFO for two consecutive half-year periods, if look-through gearing rises above 38-40% or the portfolio occupancy falls materially below the ~98% area, or if FY27 FFO growth guidance is cut to zero or negative. Also exit if the price falls more than 15% on cap-rate expansion without a matching NTA reset, since that would break the yield-plus-growth thesis.
