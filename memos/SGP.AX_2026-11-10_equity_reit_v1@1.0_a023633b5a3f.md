# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-11-10_equity_reit_v1@1.0_a023633b5a3f`
**Ticker**: SGP.AX (Stockland)
**Market**: Australia
**Sector**: Diversified (Residential/Retail Town Centres/Logistics)
**As of**: 2026-11-10
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Stockland is a low-geared (about 22.7%) Australian diversified REIT and residential developer. FY27 FFO guidance of 38-39c supports a forward distribution yield of about 6% with comfortable coverage of about 1.4x. Together with 3% growth and a small multiple give-back after the recent rally, this gives an E(R) of about 8%. The OU Monte Carlo gives a 12-month simulated return of 7.9% with a 20.5% standard deviation, so PGain is 65% and conviction is moderate. Beta of about 1.0 versus IASP.L is Category B because of the currency basis. The 30% historical volatility and the cyclical residential earnings limit sizing to 5%.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.2049
- P-gain: 0.6502
- CAPM alpha: 0.1255
- Beta: 0.9973
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or rate-shock pathway: RBA tightening and higher bond yields push cap rates out by 25-50bps and compress the multiple by about 10%. Residential settlements and pre-sales slow, FFO falls short of the 38c low end of guidance, and the distribution is held flat.
- **base**: E(R)=0.0800
  - Central case as built: roughly 6% yield, 3% growth with FY27 FFO guidance of 38-39c met, 1% multiple contraction after the recent rally, gearing stays low and cap rates are flat.
- **bull**: E(R)=0.2200
  - FFO beats guidance on record residential settlements, data-centre and logistics development earnings come through, gearing stays near 23% with capital recycling or buybacks, and the multiple expands about 5% as AU rates ease.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 4.55 (Cat A) — SGP.AX latest close on 2026-11-10 (AUD 4.55) from get_price. The stock rallied from about 4.06 in mid-October, so the starting multiple is elevated.
- `distribution_yield` = 0.06 (Cat B) — Approximate forward distribution of about 27-28c per security over a 4.55 price. The figure is an estimate. The FY26 DPS was not retrieved directly from a filing, because ASX body capture is unavailable and the recent announcements were only governance notices.
- `ffo_guidance_fy27` = 38-39c (Cat A) — FY27 FFO guidance of 38-39c per security, per Kalkine news coverage of the FY26 result dated 2026-08-19. This is secondary-source news, not a primary filing. The implied FFO yield is about 8.5% and the implied payout is about 70%, so coverage is roughly 1.4x.
- `gearing` = 0.227 (Cat A) — Reported gearing of 22.7% at FY26, per Kalkine news dated 2026-08-19. This is well below the AU convention of 40%. It is secondary-sourced and should be verified against the primary filing.
- `dpu_growth` = 0.03 (Cat C) — Forward distribution and earnings growth assumption of 3%, based on FY27 FFO guidance, residential settlement momentum and the data-centre/logistics pipeline. Residential earnings are cyclical. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% multiple contraction over 12 months after the recent price re-rating of roughly 12% in 6 weeks and the FY26 result rally. Sensitivity is about +/-5% in the scenarios.
- `expected_return_build` = 0.08 (Cat B) — E(R) = yield 6.0% + growth 3.0% + multiple change -1.0% = 8.0%.
- `risk_free_rate` = 0.0406 (Cat A) — FRED DTB3 3-month T-bill rate of 4.06% on 2026-11-09. It is a USD rate used as the risk-free proxy, which is a mismatch with an AUD-denominated asset.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `expected_market_return` = -0.0457 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (GBP-denominated). It absorbs FX noise and makes CAPM alpha mechanically large, because Rm is below Rf. Alpha should be read with caution.

## Key Risks
- Residential and development earnings cyclicality: settlement or pre-sales slowdown, or higher mortgage rates, would hit FFO, which relies on residential for a large share of earnings.
- Rate and cap-rate risk: RBA tightening or higher bond yields would expand cap rates and compress the multiple. The stock has re-rated sharply and is exposed to mean reversion.
- High realised volatility (30% annualised) with only 0.39 correlation to IASP.L. Beta and CAPM alpha are noisy because of the AUD/GBP currency basis. The negative IASP.L 5-year return inflates alpha.
- Data limitations: FY26 DPS, gearing and FFO guidance rest on secondary news sources, because ASX filing bodies are unavailable and recent announcements were governance notices only. The risk-free rate is a USD T-bill proxy for an AUD asset.
- Execution risk on the data-centre and logistics development pipeline, plus capital allocation and recycling risk.

## Invalidation Condition
Exit if FFO guidance of 38-39c per security is cut or missed at the half-year result, if distribution coverage falls below 1.0x, or if gearing rises above 35% on development spending. Also exit if residential settlements and pre-sales fall materially for two consecutive reporting periods, or if the price loses the 4.00 level on a sustained rise in Australian bond yields.
