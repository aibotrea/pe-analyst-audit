# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-10-20_equity_reit_v1@1.0_3b679cd8f650`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail (Supermarket-anchored neighbourhood/convenience)
**As of**: 2026-10-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
RGN offers supermarket-anchored neighbourhood retail exposure in Australia, a defensive subsector with a stable non-discretionary tenant base. FY27 FFO growth guidance of about 3% plus a roughly 6% estimated yield gives a base 12-month E(R) near 8%, against a 4.1% T-bill. The OU Monte Carlo (sigma 15%) gives a simulated return of 7.95% with 10.2% std dev and a PGain of 78%, which would be an above-average conviction of 4. I cut that by one step to 3 because gearing, AFFO coverage and DPS were not verified from primary filings. The benchmark's negative 5-year return also makes the 8.2% CAPM alpha look better than it is. Beta of 0.46 versus IASP.L is subject to the currency-basis caveat.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1019
- P-gain: 0.7823
- CAPM alpha: 0.0817
- Beta: 0.4599
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Stagflation or higher-for-longer rate pathway: AU and US yields rise further and retail REIT yields widen by 40-50bps, a roughly -8% re-rating. Distribution growth stalls near 0% as supermarket-anchored rent growth slows and cost of debt resets higher. AFFO coverage slips toward 1.0x and gearing drifts above the 40% AU convention.
- **base**: E(R)=0.0800
  - Central case as built in chain: yield about 6.0%, FFO and distribution growth about 3% in line with FY27 guidance, cap rates broadly flat with a slight -1% multiple drag, and occupancy stable to slightly higher.
- **bull**: E(R)=0.1900
  - Rate cuts compress yields, giving a +5% re-rating from the discounted price after the post-result sell-off. FFO growth of 4-5% from rent reviews and accretive recycling, supported by the active buy-back narrowing the NAV discount.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `last_price` = 2.19 (Cat A) — RGN.AX closing price AUD 2.19 on 2026-10-20 (get_price). The price is down from about AUD 2.42 in late July 2026. Most of the fall came around the 18 Aug 2026 FY26 result.
- `distribution_yield` = 0.06 (Cat B) — Estimated forward cash distribution yield of about 6.0% on the AUD 2.19 price. The tools did not return an issuer-published FY26 DPS figure, so this is my estimate from the REIT's historical payout of roughly 85-100% of AFFO and an FFO yield near 8%. It is not verified against the FY26 results filing. Sensitivity: each 0.5% change in yield moves E(R) by 0.5%.
- `dpu_growth` = 0.03 (Cat B) — FY27 FFO growth guidance of about 3%, as reported in Kalkine headlines on the FY26 results of 18 Aug 2026 (Region Group FY26 Results: FFO Growth, Higher Occupancy and 3% FY27 Guidance). Secondary-source headline only. The issuer document was not retrievable. Assumed to pass through to distributions.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% drag from modest yield or cap-rate softness. Rf is 4.1% and the benchmark has fallen steadily since July 2026, so rates remain a headwind for valuation multiples. Sensitivity: the bear case assumes a -8% re-rating, the bull case +5%.
- `expected_return_build` = 0.08 (Cat C) — E(R) = yield 6.0% + growth 3.0% + multiple change -1.0% = 8.0%. This is a 12-month total return assumption.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month T-bill rate of 4.10% on 2026-10-19 (get_tbill_rate). It is a US rate used as the platform's standard Rf, not an AUD rate.
- `expected_market_return` = -0.051776 (Cat B) — IASP.L trailing 1260-trading-day annualised log return (calculate_benchmark_return). The benchmark is GBP-denominated, so the figure includes FX effects. The negative market return mechanically inflates CAPM alpha, so alpha is only a weak supporting input.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_data_gap` = disclosed (Cat B) — The stored RGN.AX filing bodies (ASX, 2026-09 to 2026-10) contained other issuers' documents (prospectus, Appendix 3B, Vanguard ETF notice) and no RGN financial data. Under the filing rules, ASX body capture is also parked. Gearing, AFFO coverage, occupancy, WALE and NTA were therefore not verified from primary filings. Headline items such as the on-market buy-back notices of 2026-09-06/07 are used only for context.

## Key Risks
- Higher-for-longer rates: the stock fell about 10% from late July to October 2026 as yields stayed elevated, and a further rise in AU or US yields would widen cap rates and compress valuations.
- Unverified fundamentals: stored filing bodies were mismatched, so DPS, AFFO coverage, gearing (AU convention below 40%), occupancy and WALE are not confirmed from RGN's primary filings. The yield input is my estimate (Category B).
- Currency-basis noise: beta (0.46) and benchmark return are measured against GBP-denominated IASP.L, correlation is only 0.36, and CAPM alpha is inflated by the negative benchmark return.
- Retail-specific risk: supermarket-anchor concentration, consumer spending weakness, and refinancing costs on maturing debt could limit FFO growth below the 3% guidance.
- Calibration limitation: this is a directional signal rather than a formal backtest, since vintage discipline arrives in Phase 5. Some macro series beyond DTB3 were not used.

## Invalidation Condition
Exit if RGN reports AFFO distribution coverage below 1.0x for two consecutive halves, or gearing moves above 40% without a credible deleveraging plan. Also exit if portfolio occupancy falls below about 97% alongside negative like-for-like net property income growth, or if FY27 FFO guidance of about 3% growth is cut to flat or negative. Any of these would mean the base-case E(R) of roughly 8% no longer holds.
