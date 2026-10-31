# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-10-31_equity_reit_v1@1.0_d7c897dd6f7f`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Retail/Daily Needs (Neighbourhood Retail & Large Format)
**As of**: 2026-10-31
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
HDN is a daily-needs retail REIT (supermarket-anchored neighbourhood centres and large-format retail) offering an estimated 7.3% distribution yield, roughly 330bps above the 4.0% T-bill. The OU Monte Carlo gives a 12-month simulated return of 7.2% with a standard deviation of 13.1%, a PGain of 71% and a numeric conviction of 4. Beta of 0.62 versus IASP.L is low, but the correlation is only 0.38 and the currency-basis caveat applies. Management flagged FY27 FFO pressure from financing costs, and the issuer-sourced coverage and gearing data could not be verified. Conviction is therefore lowered one step to 3 through the distribution-coverage gate.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1306
- P-gain: 0.7104
- CAPM alpha: 0.0869
- Beta: 0.6154
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Refinancing at higher margins in a higher-for-longer rate stagflation path cuts FFO and DPU by about 8-10%. Cap rates expand by about 25-50bps, driving a 5-8% valuation decline. Gearing drifts above the 40% convention and distribution cover falls below 1.0x.
- **base**: E(R)=0.0730
  - Central case as built in the chain: distribution held at the current run-rate (about 7.3% yield), zero DPU growth as indexation offsets financing cost drag, and cap rates and the NAV discount unchanged.
- **bull**: E(R)=0.1900
  - RBA easing and lower swap rates relieve financing cost pressure and DPU grows about 3%. Some of the discount to NAV closes (about 5% re-rating), helped by development completions and capital recycling.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 1.125 (Cat A) — HDN.AX closing price AUD 1.125 on 2026-10-30 (get_price).
- `distribution_yield` = 0.073 (Cat B) — Estimated forward cash distribution yield at AUD 1.125. It is derived from an approximate ~8.2 cents per unit run-rate, which is consistent with news-reported FY26 distribution maintenance and a 6.57% yield quoted in June 2026 at a higher unit price. The stored HDN filing bodies returned off-topic content from other issuers, so the DPU was not verified against an HDN filing. Treat the figure as an estimate.
- `dpu_growth` = 0.0 (Cat C) — Zero distribution growth assumed. Press coverage after the FY26 result (Aug 2026) flags FY27 FFO pressure from higher financing costs, which offsets rent indexation and development contributions. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating assumed. The AU policy rate is 4.6% (BIS, observed 2026-10-22) and the US 3M T-bill is 4.0%, so there is no basis for cap rate compression. NAV discount mean reversion is left as bull-case upside only.
- `expected_return_build` = 0.073 (Cat B) — E(R) = yield 7.3% + growth 0.0% + multiple change 0.0% = 7.3%.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill 4.0% on 2026-10-29 (get_tbill_rate).
- `expected_market_return` = -0.0475 (Cat B) — IASP.L trailing 5.17-year annualised log return of -4.75% (calculate_benchmark_return, 1260 days). It is GBP-denominated and absorbs FX co-movement. A negative market return mechanically inflates CAPM alpha, so alpha is treated as a weak supporting input.
- `au_policy_rate` = 0.046 (Cat A) — BIS RBA policy rate 4.6%, observation date 2026-10-22 (get_stored_apac_rates).
- `filing_body_gap` = disclosed (Cat B) — The eight stored HDN.AX filing rows (Annual Report 2026, FY26 results, distribution notices; filing dates Aug-Sep 2026) carried body text belonging to unrelated issuers. These bodies were ignored. Gearing, AFFO coverage, occupancy and WALE could not be sourced from issuer text, so the gates on them are marked info and conviction is cut by one step.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency noise.

## Key Risks
- FY27 FFO and DPU pressure from higher refinancing and hedging costs; the AU policy rate is 4.6% and distribution cover is unverified against issuer filings
- Cap rate expansion on neighbourhood and large-format retail valuations, or gearing creeping above the ~40% AU convention
- Data limitation: stored filing bodies were off-topic, so gearing, AFFO coverage, WALE, occupancy and top-asset concentration are unverified and the gates are marked info
- Currency-basis noise: IASP.L is GBP-denominated, the beta correlation is only 0.38, and the negative 5-year benchmark return inflates CAPM alpha
- Consumer spending slowdown affecting tenant sales and specialty rent growth, plus external-manager fee and related-party transaction alignment risk

## Invalidation Condition
Exit if reported AFFO or FFO distribution coverage falls below 1.0x for two consecutive half-year reporting periods, if look-through gearing rises above 40% (the AU convention) without a credible deleveraging plan, if the DPU is cut by more than 5% from the current run-rate, or if portfolio occupancy declines materially from the high-90s level on weaker tenant sales.
