# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-10-27_equity_reit_v1@1.0_89d8f4002f1b`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Office/Industrial
**As of**: 2026-10-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
GOZ offers a high forward yield of about 7.9% in an Australian office and industrial portfolio, and the spread over the 4.05% T-bill rate is meaningful. The 12-month OU Monte Carlo gives a modest expected return of about 5.9% with a standard deviation of 13.5%, so PGain is about 67%. Beta of 0.60 versus IASP.L (currency-basis caveat applies) gives a positive CAPM alpha of about 7%, but this partly reflects the negative trailing benchmark return. Gearing of about 41% is above the 40% Australian convention and office headwinds persist, so conviction is cut one step to Low. Filing data was unusable, so fundamentals rest on secondary sources.

## Quantitative Chain

- E(R): 0.0600
- Std dev: 0.1353
- P-gain: 0.6697
- CAPM alpha: 0.0706
- Beta: 0.5971
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1000
  - Stagflation-style pathway: the RBA stays on hold or hikes from 4.6%, and refinancing costs rise. Office valuations fall another 5-8% on cap-rate expansion of 25-50bps. Gearing moves above 42%. DPU is cut about 8-10% and the yield multiple widens.
- **base**: E(R)=0.0600
  - Central case as built in the chain: yield of about 7.9%, DPU drifting down about 1.5%, flat multiple, gearing steady at 40-41%, and stable occupancy and leasing.
- **bull**: E(R)=0.1700
  - Rate cuts compress AU REIT yields and valuations stabilise. Asset sales reduce gearing below 38% and DPU holds flat. A partial re-rating adds about 5-8% on top of the yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 1.97 (Cat A) — Latest close of GOZ.AX on 2026-10-27 via get_price (AUD).
- `distribution_yield` = 0.079 (Cat B) — Approx. 7.9% forward yield, from FY26 DPU guidance of about 15.5c per security (my recollection, not re-verified) divided by the A$1.97 price. It is consistent with the ~8% yield in Kalkine coverage dated 2026-06-15. Not confirmed against a filed distribution notice, because the stored filing bodies were mismatched.
- `dpu_growth` = -0.015 (Cat C) — Assumes DPU erodes about 1.5% a year. Drivers are higher interest costs on refinancing, with the RBA cash rate at 4.60% (BIS, observed 2026-10-15), and office leasing and incentive pressure. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes a flat price-to-NAV and yield multiple over 12 months. No re-rating is taken in either direction, because the cap-rate outlook is uncertain.
- `expected_return_build` = 0.06 (Cat C) — E(R) is about 7.9% yield, less 1.5% growth, plus 0% multiple change, which gives about 6.4%. I rounded it down to 6.0% for fee and cost drag and the uncertainty in the inputs.
- `gearing` = 0.41 (Cat B) — About 41% gearing, taken from Kalkine coverage dated 2026-06-15. It is a secondary news source and was not verified against a filing. It is slightly above the AU <40% convention in the framework.
- `risk_free_rate` = 0.0405 (Cat A) — DTB3 3-month T-bill rate of 4.05% on 2026-10-26 via get_tbill_rate. This is a US rate, used as the platform risk-free rate.
- `expected_market_return` = -0.045 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (1260-day lookback), via calculate_benchmark_return. It is negative, and the GBP basis adds noise.
- `filing_data_gap` = disclosed (Cat B) — get_stored_filings for GOZ.AX returned bodies that were unrelated to GOZ, from other issuers' documents. No fundamental data (AFFO coverage, occupancy, WALE, NAV) could be sourced from filings. Gates on coverage and asset quality rest on limited evidence and are marked info. ASX body capture is also parked.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer rates: the RBA cash rate is 4.6%, which raises refinancing costs and could force a DPU cut.
- Office valuation and leasing risk: cap-rate expansion, incentive pressure and vacancy could lower NAV and push gearing further above the 40% convention.
- Data gap: stored filings were mismatched, so AFFO coverage, occupancy, WALE and NAV were not verified. Gearing and yield rely on secondary news and recollection.
- Benchmark and currency-basis noise: IASP.L is GBP-denominated and its 5-year return is negative, so beta and alpha are unreliable. Also, calibration is directional rather than a formal backtest, and macro series other than DTB3 were not used.
- Sponsor and governance: a board change was announced on 2026-10-11 with no details sourced, and the sponsor commitment was not verified.

## Invalidation Condition
Exit if gearing rises above 43% or the interest cover covenant comes under pressure, or if DPU coverage by AFFO falls below 1.0x for two consecutive half-year reporting periods. Also exit if the FY27 distribution guidance implies a cut of more than 10%, or if portfolio valuations fall more than 5% in a half-year revaluation without offsetting debt reduction.
