# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-11-22_equity_reit_v1@1.0_1461916ea703`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified/Commercial (Office, Retail, Hospitality)
**As of**: 2026-11-22
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
OUE REIT is a Singapore-listed commercial REIT with office, retail and hospitality assets, now adding Sydney office exposure through the proposed additional ~50% stake in Salesforce Tower while recycling out of Crowne Plaza Changi Airport. Estimated E(R) of 6.5% comprises about 5.0% yield, 1.5% growth and no multiple change. That is only modestly above the 4.16% T-bill rate, with 21% historical volatility. The OU Monte Carlo gives a PGain of 67% and CAPM alpha of 4.9%, but the alpha comes from a negative IASP.L market return and a low beta of 0.31 (currency-basis noise applies). Missing leverage and DPU coverage data, plus acquisition-funding uncertainty, justify a one-step downward override, leaving Low conviction and a small position.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1448
- P-gain: 0.6715
- CAPM alpha: 0.0485
- Beta: 0.3051
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Debt-funded Salesforce Tower acquisition pushes aggregate leverage toward the 45-50% limit. Refinancing at higher SGD rates and softer Singapore office and hospitality income cut DPU by about 8%. Cap rates expand by 25-50bps, and a stagflation-type rate shock widens the yield spread and compresses P/NAV.
- **base**: E(R)=0.0650
  - Central case as built in the chain: 5.0% yield, 1.5% DPU growth and a flat multiple. The Salesforce Tower acquisition is broadly DPU-neutral after funding costs, Crowne Plaza proceeds are used to reduce debt, and Singapore office occupancy is stable.
- **bull**: E(R)=0.2000
  - The Sydney acquisition is accretive on an equity-funded or low-cost basis. Further asset recycling closes part of the NAV discount. SGD rates ease, lifting the multiple by about 8-10% and DPU growth to about 4%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 0.34 (Cat A) — Latest SGD close of 0.34 on 2026-11-20 from get_price.
- `distribution_yield` = 0.05 (Cat B) — Estimated trailing distribution yield of about 5.0%. I did not retrieve a published DPU figure, and none appears in the retrieved filing bodies. This is my approximation of DPU per unit over the 0.34 price and should be verified against the latest issuer DPU. 3QFY2026 NPI rose 4.6% y-o-y per The Edge Singapore, 2026-10-21 headline.
- `dpu_growth_12m` = 0.015 (Cat C) — Assumed organic DPU growth of 1.5%. It rests on 3QFY2026 NPI growth of 4.6% y-o-y, offset by dilution from the base fee paid in units, the funding cost of the proposed Salesforce Tower acquisition, and the loss of income from the Crowne Plaza Changi Airport divestment. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumed flat P/NAV and yield multiple over 12 months. It is a neutral assumption with no re-rating, and the bear and bull cases flex it.
- `expected_return_build` = 0.065 (Cat C) — E(R) = yield 5.0% + growth 1.5% + multiple change 0.0% = 6.5%. It is a derived estimate that inherits the Category B and C classifications of its components.
- `acquisition_salesforce_tower` = proposed ~50% additional interest in Salesforce Tower (180 George St, Sydney) (Cat A) — TS0U.SI 2026-10-23 ANNC (asset acquisition) and news headlines report an agreed price of about A$539.3m for the additional stake, with the property valued at A$864.0m. The attachments' body was truncated, so funding mix, yield and pro forma gearing were not extracted.
- `divestment_crowne_plaza` = completed (Cat A) — TS0U.SI 2026-10-30 ANNC: completion of the divestment of Crowne Plaza Changi Airport. The price and use of proceeds were not available in the retrieved body.
- `manager_fee_in_units` = base fee paid in units (Cat A) — TS0U.SI 2026-10-26 ANNC: 3Q26 manager base fee paid by issue of new units. This aligns the manager with unitholders but adds minor dilution.
- `leverage_data_gap` = not retrieved (Cat C) — No gearing ratio or interest coverage figure was obtained from the stored filings (SGX live announcements API returned 403). The leverage and coverage gates are therefore assessed as info, with a one-step conviction haircut for the data gap and the acquisition-funding risk.
- `risk_free_rate` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill at 4.16% on 2026-11-19.
- `expected_market_return` = -0.040739 (Cat B) — Trailing 5.18-year annualised log return of IASP.L over 1260 trading days, computed via calculate_benchmark_return. It is GBP-denominated and absorbs FX co-movement.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Acquisition funding and leverage: the Salesforce Tower purchase of about A$539m could lift gearing toward the regulatory ceiling, or dilute DPU if funded by equity at a 0.34 price.
- Higher-for-longer rates: refinancing costs and a narrow spread over the 4.16% T-bill limit total return upside and could compress valuations.
- Concentrated, cyclical exposure to Singapore and Sydney office, plus hospitality and retail, with FX translation risk from AUD income.
- Data gaps: DPU, AFFO coverage and gearing were not retrieved. The yield input is an estimate (Category B) and the 0.31 beta rests on only 0.17 correlation, so the CAPM alpha is weak evidence. Live SGX API access also failed.
- The expected-return build rests on Category C assumptions for growth and multiple change, and a negative 5-year IASP.L return distorts the CAPM alpha.

## Invalidation Condition
Exit if aggregate leverage rises above about 45% after funding the Salesforce Tower acquisition, or if distribution coverage by AFFO falls below 1.0x for two consecutive quarters. Also exit if DPU declines more than 10% year on year, if Singapore office occupancy drops materially below recent levels, or if the 12-month total return outlook falls below the 4.16% risk-free rate.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
