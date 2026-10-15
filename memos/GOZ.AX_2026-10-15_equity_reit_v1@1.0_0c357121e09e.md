# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-10-15_equity_reit_v1@1.0_0c357121e09e`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Office/Industrial
**As of**: 2026-10-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
GOZ offers an approximately 8% distribution yield from a diversified Australian office and industrial portfolio, with a major sponsor (Growthpoint Properties Ltd) as its largest holder. Expected 12-month total return is about 6.5%, only modestly above the 4.1% T-bill rate, with 20% annual volatility. The OU Monte Carlo gives a PGain of 68%. CAPM alpha is positive at 7.8%, but it rests on a negative IASP.L market return and a currency-basis beta of 0.60 (low correlation of 0.35), so it should be discounted. Gearing near 41% sits marginally above the Australian convention, and office valuation pressure caps conviction at Low with a one-step gate override.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1355
- P-gain: 0.6827
- CAPM alpha: 0.0784
- Beta: 0.6014
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Office capitalisation rates widen by 50bps or more and valuations fall. Gearing moves above 43% and approaches covenant headroom limits. Refinancing costs rise in a higher-for-longer or stagflation rate path. DPU is cut and the yield multiple de-rates by 3-4%. Distribution coverage falls below 1.0x AFFO.
- **base**: E(R)=0.0650
  - Central case as built in the chain. Yield is about 8%, DPU growth is -0.5%, the multiple de-rates by 1%, office valuations are broadly stable and gearing stays around 41%.
- **bull**: E(R)=0.1700
  - RBA easing and lower bond yields compress cap rates by 25bps. Office leasing spreads improve and industrial rents grow. Disposals reduce gearing below 38%, and the yield multiple re-rates upward by 3-4%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 1.935 (Cat A) — Latest close of AUD 1.935 on 2026-10-15 from get_price.
- `distribution_yield` = 0.08 (Cat B) — About 8% forward distribution yield. It is taken from secondary news coverage (Kalkine and Simply Wall Street, Jun-Sep 2026) and cross-checked against the current price. The issuer's FY26 DPS was not verified from a primary filing.
- `dpu_growth` = -0.005 (Cat C) — Assumes roughly flat to slightly negative distribution and NAV growth. Office valuation pressure and higher interest costs offset leasing resilience and industrial rental growth. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.01 (Cat C) — Assumes modest yield-multiple de-rating over 12 months. Rates stay elevated (US 3M T-bill 4.10%) and office cap rates are not yet clearly stabilised.
- `expected_return` = 0.065 (Cat C) — Yield 8.0% plus growth -0.5% plus multiple change -1.0% equals 6.5% total return over 12 months.
- `gearing` = 0.41 (Cat B) — About 41% gearing from secondary news coverage (Kalkine, Jun 2026). It is not verified against a primary filing. The Australian convention is below 40%, so this is marginally above it.
- `filing_body_gap` = disclosed (Cat B) — The stored GOZ.AX filing bodies returned content belonging to unrelated issuers (BCAL, Objective Corp, Evion, Latrobe, Spectur and others). None were used. GOZ ASX headlines show an FY26 Sustainability Report, AGM notice and board changes, with no price-sensitive items. AFFO coverage, WALE and tenant data could not be verified from primary documents.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month US T-bill of 4.10% on 2026-10-14. It is a USD rate used as the CAPM risk-free input per methodology.
- `expected_market_return` = -0.0495 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (1260 trading days). It is GBP-denominated and is affected by currency basis.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. This is a currency-basis caveat.

## Key Risks
- Office cap-rate expansion and further valuation write-downs would pressure NAV and gearing, which is already around 41% against the sub-40% Australian convention.
- Higher-for-longer rates raise refinancing and interest costs and could erode distribution coverage, which was not verified against AFFO from a primary filing.
- Data limitations: stored filing bodies were mismatched to other issuers, and yield and gearing rely on secondary news. Beta and market return use a GBP-denominated benchmark with only 0.35 correlation, so CAPM alpha is noisy. IASP.L has a negative 5-year return, so the alpha comparison is unusually flattering.
- Tenant concentration and lease expiry risk in office assets, including government and corporate tenants, could not be verified from primary documents.
- Calibration is a directional signal, not a formal vintage-disciplined backtest.

## Invalidation Condition
Exit if reported gearing rises above 43% or interest cover falls toward covenant limits, if FY27 distribution coverage falls below 1.0x AFFO or the DPU is cut, or if office portfolio valuations decline by more than 5% in a half-year revaluation with occupancy falling below 93% (WALE shortening materially). Exit as well if Growthpoint Properties Ltd materially reduces its stake or support for GOZ.
