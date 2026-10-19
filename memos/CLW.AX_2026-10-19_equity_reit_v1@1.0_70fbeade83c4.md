# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-10-19_equity_reit_v1@1.0_70fbeade83c4`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified/Long-Lease Net Lease
**As of**: 2026-10-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CLW offers defensive, long-lease AUD net-lease exposure, with about 9-year WALE and near-full occupancy as reported in news coverage. It is sponsored by Charter Hall, a large sponsor and manager. The estimated forward distribution yield of about 7.4% is about 3.3pts above the 4.08% T-bill, and the OU Monte Carlo gives a 12-month simulated return of 7.2% with PGain of about 73%. The numeric chain alone supports conviction 4 (alpha of 9.0% is inflated by the negative IASP.L 5-year return, and beta carries currency-basis noise). I applied a one-step gate override to 3 because DPU coverage, gearing and the DPU level could not be verified from primary filings and the price has fallen about 9% since August, which suggests the market is pricing refinancing or valuation risk.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1202
- P-gain: 0.7267
- CAPM alpha: 0.0898
- Beta: 0.6349
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Stagflation or higher-for-longer rates push AU/US yields up and long-WALE cap rates out by 40-50bps. About $2B of debt refinances at materially higher margins, so DPU is cut by about 5% and the yield falls to about 7%. The multiple de-rates by 10-12%, and coverage drops below 1.0x AFFO.
- **base**: E(R)=0.0730
  - Central case as built in the chain: yield about 7.4%, DPU growth about 1%, cap rates broadly flat with a small valuation drag of about 1%, occupancy near 99%+ and WALE around 9 years.
- **bull**: E(R)=0.1800
  - Rate cuts and falling bond yields compress cap rates by 25bps, which re-rates the units about 7-8% toward NTA. DPU grows about 3% from CPI-linked rent reviews and successful capital recycling, and the refinancing is completed on favourable terms.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `price` = 3.25 (Cat A) — CLW.AX closing price AUD 3.25 on 2026-10-19 (get_price). The price is down about 9% from roughly 3.56 on 2026-08-21 (stored prices).
- `distribution_yield` = 0.074 (Cat B) — Estimated forward cash distribution yield of about 24c per unit on AUD 3.25. The DPU level is my estimate from FY26 results coverage and the Kalkine/Investing.com headlines (FY26 about 2% growth). I could not verify it against a primary filing. The stored ASX filing bodies returned for CLW.AX in this run were for unrelated issuers and were not used. Treat the yield as an approximation.
- `dpu_growth` = 0.01 (Cat C) — Assumed 1% annual DPU/earnings growth from contracted fixed and CPI-linked rent reviews on a roughly 9-year WALE, partly offset by higher refinancing costs on the roughly $2B of debt being refinanced. Sensitivity: each 1pt of growth moves E(R) by 1pt. This is shown in the bear and bull cases.
- `multiple_change` = -0.011 (Cat C) — Assumed modest 12-month net valuation/multiple drag of about -1.1% to reflect cap-rate/NTA pressure on long-WALE assets while the 3M T-bill is 4.08%. Sensitivity: a 25bp cap rate move is roughly a 4-5% NAV change at mid-30s gearing, which is covered by the bear and bull cases.
- `expected_return_build` = 0.073 (Cat B) — E(R) = yield 7.4% + growth 1.0% + multiple change -1.1% = 7.3%. This is a total-return estimate, not a published figure.
- `rf_source` = 0.0408 (Cat A) — 3-month T-bill (DTB3) 4.08% observed 2026-10-16. The risk-free rate is USD-based while the asset is AUD-denominated, so there is a rate-basis mismatch.
- `expected_market_return` = -0.0499 (Cat B) — IASP.L trailing 5.17-year annualised log return (1260-day lookback) from calculate_benchmark_return. The negative market return inflates CAPM alpha. Alpha is a supporting input only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_quality` = 0.635 (Cat B) — 252-day beta 0.635 with correlation 0.42 and 257 observations. This is a low-fit estimate.
- `portfolio_facts` = WALE about 9 years; occupancy about 99.9%; portfolio about $6.1B (Cat B) — Taken from Kalkine news headlines dated 2026-09-28 and 2026-10-15 (AGM coverage). I could not verify these against the filings, because the stored filing bodies were mismatched. Gearing was not retrieved.

## Key Risks
- Refinancing and interest-cost risk: about $2B of debt is being refinanced, and higher-for-longer rates could compress AFFO coverage and cut DPU.
- Cap rate expansion and NTA write-downs on long-WALE assets if bond yields rise. The price is already down about 9% from August.
- Data gap: the stored ASX filing bodies were for unrelated issuers, so the DPU level, gearing, AFFO coverage and WALE are unverified, and gearing was not retrieved. Gates marked 'info' are provisional.
- Concentration in a few long-lease tenants and sector exposures (e.g. telco, government, grocery/pubs, and the like), and reliance on sponsor-managed asset recycling that could destroy NAV if executed at discounts.
- Currency-basis and benchmark noise: beta has a low correlation (0.42) to a GBP-denominated benchmark, the negative 5-year benchmark return inflates alpha, and the USD T-bill rate is used as Rf for an AUD asset. This is a directional signal, not a formal backtest.

## Invalidation Condition
Exit if CLW announces a DPU cut or FY27 guidance below the roughly 24c run-rate, or if AFFO coverage falls below 1.0x for two consecutive periods. Also exit if reported gearing rises above about 40% or the refinancing of the roughly $2B debt is completed at margins that materially erode earnings. Further triggers are portfolio occupancy falling below 97% or a major tenant default or lease non-renewal, and a sustained NTA decline of more than 10% from valuation write-downs. A closing price below roughly AUD 2.90 with no company-specific explanation would force a thesis review.
