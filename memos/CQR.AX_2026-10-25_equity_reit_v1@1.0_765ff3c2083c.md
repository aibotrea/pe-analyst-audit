# Specialist Memo — CQR.AX

**Memo ID**: `CQR.AX_2026-10-25_equity_reit_v1@1.0_765ff3c2083c`
**Ticker**: CQR.AX (Charter Hall Retail REIT)
**Market**: Australia
**Sector**: Retail (Convenience/Necessity-based)
**As of**: 2026-10-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CQR is an Australian necessity-based and convenience retail REIT with a sponsor, Charter Hall, that has an established platform. Press-reported occupancy near 99% supports the income stream. At AUD 3.58, after a roughly 10% drawdown since late August, the estimated forward yield of about 7.2% is about 3.2 percentage points above the 4.04% T-bill. The OU Monte Carlo gives a 12-month expected return of 8.6% with a standard deviation of 13.5% and a PGain of 73.9%. The numeric chain scores conviction 4, and I applied a one-step downward override to 3. The reasons are that issuer gearing and AFFO coverage could not be verified from filings, and the recent price momentum is negative. Alpha of 10.4% is inflated by the negative IASP.L 5-year return, and beta of 0.66 carries currency-basis noise.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.1350
- P-gain: 0.7389
- CAPM alpha: 0.1037
- Beta: 0.6585
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0900
  - Softer trading, which the press flagged in Sep 2026, becomes a sustained slowdown in necessity retail. Higher-for-longer rates or a stagflation-type shock push cap rates out by 25-50bps, with a roughly 7% valuation hit. DPU growth is flat to slightly negative, AFFO coverage falls toward 1.0x, and the multiple de-rates a further 10%.
- **base**: E(R)=0.0870
  - Central case as built in the chain: yield of about 7.2%, DPU growth of 1.5%, occupancy stable near 99%, cap rates and multiple flat.
- **bull**: E(R)=0.2000
  - Rate relief and stabilising retail sales lead to partial mean reversion of the recent drawdown, a multiple re-rating of about 6-7%. DPU growth reaches about 3.5% on rent reviews and accretive recycling, with yield stable near 7%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 3.58 (Cat A) — CQR.AX last close AUD 3.58 on 2026-10-23 (get_price). The stored price series fell from about 3.95 in late Aug to about 3.5 in Oct.
- `distribution_yield` = 0.072 (Cat B) — Estimated forward distribution yield. It assumes DPU of about 26c, which is back-solved from a press-cited 6.55% yield on an earlier, higher price (Kalkine, Jul 2026) and then applied to the current AUD 3.58 price. The company's FY26 distribution announcement body was not retrievable. The stored filing bodies for CQR.AX were mismatched, with text from unrelated issuers.
- `dpu_growth` = 0.015 (Cat C) — Assumed 1.5% organic distribution growth from fixed rent escalators on necessity-based retail, below the press-reported FY26 distribution growth and FY27 guidance. This is a model assumption; sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes no re-rating or de-rating of the price-to-distribution multiple over 12 months. The recent price drawdown could continue or mean-revert.
- `expected_return_build` = 0.087 (Cat C) — E(R) = 7.2% yield + 1.5% growth + 0.0% multiple change = 8.7%.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill at 4.04% on 2026-10-22 (get_tbill_rate). This is a USD rate used as the model's risk-free proxy for an AUD asset.
- `occupancy` = 0.991 (Cat B) — Press-reported portfolio occupancy of about 99.1% (Kalkine, 2026-09-29). This is secondary-source data and was not verified against an issuer filing.
- `expected_market_return` = -0.0463 (Cat B) — IASP.L trailing 5.17-year annualised log return, via calculate_benchmark_return (1260-day lookback). The benchmark is GBP-denominated, so the figure absorbs FX effects. The negative market return mechanically inflates CAPM alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_data_gap` = disclosed (Cat B) — get_stored_filings for CQR.AX returned bodies from unrelated issuers (Lac Gold, Argo, Alara, Civmec, CBA and others). No issuer-sourced gearing, AFFO coverage or WALE could be extracted. Gate assessments rely on headline and press data and are flagged as unverified.

## Key Risks
- Rate and cap-rate risk: higher-for-longer rates or a stagflation-type shock could widen cap rates, compress valuations and de-rate the yield multiple. The recent drawdown from about 3.95 to about 3.5 suggests the market is already pricing some of this.
- Fundamental data gap: stored filing bodies for CQR.AX were mismatched. Gearing, AFFO coverage, WALE and DPU are not verified against issuer documents, and the 7.2% yield is back-solved from press figures. Press commentary in Sep 2026 flagged softer trading.
- Consumer and retail exposure: weaker retail sales or tenant stress at major supermarket and specialty tenants would pressure rent growth and distribution coverage.
- Benchmark and macro-input noise: beta (0.66, correlation 0.39) and Rm (-4.6%) use a GBP-denominated benchmark, so CAPM alpha is unreliable. The risk-free rate is a USD T-bill used for an AUD asset.
- Methodology limitation: the chain is a directional signal rather than a formal backtest. E(R) growth and multiple inputs are Category C assumptions.

## Invalidation Condition
Exit if reported AFFO coverage of the distribution falls below 1.0x for two consecutive half-year periods, if portfolio occupancy drops below 97% from the roughly 99% reported, or if gearing rises above the 40% Australian convention. Exit also if the Charter Hall sponsor reduces its stake or cuts its support, or if the units fall more than 15% below the 3.58 reference price without any improvement in fundamentals.
