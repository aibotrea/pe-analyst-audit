# Specialist Memo — VCX.AX

**Memo ID**: `VCX.AX_2026-11-24_equity_reit_v1@1.0_a387d2efb0fc`
**Ticker**: VCX.AX (Vicinity Centres)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-11-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Vicinity owns a portfolio of premium Australian shopping centres. News coverage points to improving occupancy and leasing spreads, supporting an estimated forward yield of about 6.6% plus 2-3% growth. The OU Monte Carlo gives a 12-month simulated return of about 7.9% on a 15% standard deviation, for a PGain of 70% and a CAPM alpha of about 9.9% (inflated by the negative IASP.L trailing return, with currency-basis noise). The numeric chain supports a conviction of 4. I cut it one step to 3 because DPS, coverage and gearing could not be checked against issuer filings, and because the David Jones administration adds retail-tenant risk.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1495
- P-gain: 0.7021
- CAPM alpha: 0.0993
- Beta: 0.7050
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation-style pathway: Australian rates rise further and cap rates widen by about 50bps. Retailer failures following David Jones push occupancy down and cut FFO growth to zero. Distribution coverage drops below 1.0x AFFO, the distribution is cut, and the multiple contracts by around 10%.
- **base**: E(R)=0.0800
  - Central case as built in the chain: 6.6% yield, 2.5% DPU growth, about 1% multiple contraction. Occupancy is stable, leasing spreads stay positive, gearing stays in the low 30% range and cap rates are flat.
- **bull**: E(R)=0.2000
  - RBA easing compresses cap rates by about 25bps. David Jones space is re-let quickly at higher rents and DPU growth reaches 4-5%. Asset recycling and development add to NAV, and the multiple expands about 4%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `share_price` = 2.47 (Cat A) — Latest close of AUD 2.47 on 2026-11-24 from get_price.
- `distribution_yield` = 0.066 (Cat B) — Approximate forward distribution yield of about 16.3-16.5 cents per security divided by the AUD 2.47 price. The FY26 DPS comes from my recall of the FY25 payout and the FY26 result headline. The stored ASX filing bodies for VCX returned text from unrelated issuers, so the figure could not be checked against an issuer filing. Treated as a derived estimate.
- `dpu_growth` = 0.025 (Cat C) — Assumes 2.5% FFO/DPU growth. This reflects contractual rent escalators of roughly 3-4%, positive leasing spreads and improving occupancy reported in news coverage, less drag from the David Jones administration and higher funding costs. Tested in the bear and bull scenarios.
- `multiple_change` = -0.011 (Cat C) — Assumes about 1.1% of multiple contraction. This allows for a still-elevated AUD rate environment (US 3M T-bill 4.18%) and retail tenant risk after the David Jones administration. Tested in the bear and bull scenarios.
- `expected_return_build` = 0.08 (Cat C) — E(R) is 6.6% yield plus 2.5% growth minus 1.1% multiple change, rounded to 8.0%. The result depends on the unverified yield and the two Category C components.
- `risk_free_rate` = 0.0418 (Cat A) — FRED DTB3 3-month T-bill at 4.18% on 2026-11-23. This is a USD rate used as the platform-standard Rf, not an AUD rate.
- `expected_market_return` = -0.04487 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (1260 trading days) from calculate_benchmark_return. It is GBP-denominated and includes FX noise. The negative figure makes CAPM alpha look large.
- `leverage_gearing` = unverified (Cat C) — No gearing figure could be sourced from the tools. Vicinity has historically run gearing in the low 30% range, inside the AU convention of below 40%. This is an assumption and not a filed figure.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Distribution, AFFO coverage and gearing figures could not be sourced from a filed document. The stored VCX filing bodies contained unrelated issuers' content, so the memo relies on recalled and news-derived figures.
- Retail tenant failures following the David Jones administration could lower occupancy, raise incentives and slow rent growth.
- Higher-for-longer Australian rates could widen cap rates and compress the multiple. The bear scenario includes a stagflation pathway.
- Beta of 0.705 has a correlation of only 0.38 with IASP.L, and the benchmark is GBP-denominated. The negative 5-year benchmark return inflates CAPM alpha, so alpha is a weak supporting input.
- Macro signals other than the T-bill rate (FEDFUNDS, T10Y2Y, credit spreads) were not used. Rf is a USD rate applied to an AUD asset.
- Calibration is a directional signal, not a formal point-in-time backtest.

## Invalidation Condition
Exit if Vicinity cuts its distribution, or if AFFO coverage falls below 1.0x for two consecutive reporting periods. Also exit if portfolio occupancy drops materially below about 98% (reported near 99%) alongside negative leasing spreads, or if balance sheet gearing rises above 40%, the AU convention cap. Any of these would show the retail-recovery thesis is failing.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
