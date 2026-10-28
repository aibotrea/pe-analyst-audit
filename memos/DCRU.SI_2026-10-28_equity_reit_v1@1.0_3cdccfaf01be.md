# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-10-28_equity_reit_v1@1.0_3cdccfaf01be`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centers
**As of**: 2026-10-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers a high trailing USD yield of about 8.2% on a USD 0.44 price. That is roughly 4 points above the 4.05% T-bill, and the sponsor is Digital Realty. DPU has been flat (FY2025 3.60 US cents, 1HFY2026 unchanged), so most of the expected return is income rather than growth. The 25% realised volatility and the concentrated, small data-centre portfolio limit the margin of safety. The OU Monte Carlo gives a 12-month PGain of 65.8% with a mean return of 6.9%. The numeric chain supports a base score of 3, and I reduced it by one step for asset concentration, giving a score of 2 (Low). The beta of 0.31 against IASP.L is weak (correlation 0.15) and carries currency-basis noise, so the CAPM alpha of 5.7% should be treated cautiously.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1701
- P-gain: 0.6580
- CAPM alpha: 0.0565
- Beta: 0.3087
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - Higher-for-longer USD rates and refinancing at 3.5%+ cut DPU by about 10%. A major data-centre tenant does not renew or re-leases at lower rents. Data-centre cap rates widen by 50bps. Valuation markdowns raise gearing, and the sector de-rates as AI-driven demand or power-supply concerns weigh on sentiment. Equity-market stress adds to the unit-price decline.
- **base**: E(R)=0.0700
  - Central case as built in the chain: 8.2% yield, flat DPU, about 1.2% multiple drag, stable occupancy, and refinancing absorbed through capital recycling.
- **bull**: E(R)=0.2200
  - Capital recycling is accretive and DPU grows 3-4%. Rate cuts compress yields, and the unit price re-rates toward NAV with about 8-10% multiple expansion. Sponsor Digital Realty supports the pipeline and leasing demand stays strong.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `price` = 0.44 (Cat A) — Latest close on 2026-10-28 from get_price (USD-denominated SGX listing).
- `distribution_yield` = 0.082 (Cat A) — FY2025 DPU of 3.60 US cents (reported by Yahoo Finance Singapore, 2026-02-03) divided by the USD 0.44 close. News also reports 1HFY2026 DPU unchanged year on year (2026-07-28). I could not read the DPU figures in the stored filing bodies, so I took them from news headlines.
- `dpu_growth_12m` = 0.0 (Cat C) — Assumes flat DPU. 1HFY2026 DPU was unchanged and the REIT is recycling capital (The Edge, 2026-09-17). Contractual escalators are offset by refinancing at higher cost, including the JPY 5bn 3.47% notes due 2031 priced on 2026-10-27 (DCRU 2026-10-27 ANNC). Sensitivity is tested in the bear and bull scenarios.
- `multiple_change` = -0.012 (Cat C) — Assumes modest unit-price drag. Yield sits about 4 percentage points above the 4.05% T-bill, but beta is low, the sector carries headwinds, and total return has been volatile. This is a judgement, not an observed figure.
- `expected_return_build` = 0.07 (Cat B) — E(R) = 8.2% yield + 0.0% DPU growth - 1.2% multiple change, rounded to 7.0%. Passed to the Monte Carlo as base_return.
- `risk_free_rate` = 0.0405 (Cat A) — FRED DTB3 3-month T-bill, observed 2026-10-27 via get_tbill_rate. The unit is USD, which matches the REIT's reporting currency.
- `expected_market_return` = -0.047068 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (lookback 1260). The result is GBP-based and negative, so CAPM required return is depressed.
- `leverage_data_gap` = not_verified (Cat C) — The stored filing bodies for the 3Q2026 business update were PDF attachments, and no gearing figure was extracted. I assume aggregate leverage is below the 50% SG regulatory cap, based on prior public disclosures. This must be verified against the 3Q26 update.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_value` = 0.3087 (Cat B) — 252-day regression against IASP.L. Correlation is only 0.15, so the beta is statistically weak and mostly reflects noise.

## Key Risks
- Refinancing and interest-cost risk: debt is being refinanced at higher fixed rates (JPY notes at 3.47%), which could erode DPU while USD rates stay elevated.
- Asset and tenant concentration: a small portfolio with large exposure to a few data-centre tenants and the sponsor ecosystem means one lease event could move DPU.
- Data not verified: gearing, DPU coverage and WALE could not be extracted from the 3Q26 filing PDFs, and the SGX announcement API returned a 403 error. Leverage and coverage gates are therefore marked info, not pass.
- Beta and market-return noise: IASP.L is GBP-denominated, correlation is only 0.15, and the 5-year benchmark return is negative, so CAPM alpha is unreliable.
- Sector and valuation risk: data-centre valuations and AI-demand or power-supply sentiment could drive cap-rate expansion and unit-price de-rating.

## Invalidation Condition
Exit if aggregate leverage rises above about 45% or interest coverage falls toward the regulatory minimum, or if DPU is cut by more than 10% from the 3.60 US cent FY2025 level. Also exit if a top-3 tenant fails to renew or goes into distress, or if portfolio occupancy drops materially below recent levels for two consecutive quarterly updates.
