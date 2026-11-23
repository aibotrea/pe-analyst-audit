# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-11-23_equity_reit_v1@1.0_45c1f0023c0b`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Long-WALE Diversified/Net Lease
**As of**: 2026-11-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CLW offers long-WALE Australian net-lease property income, with a forward yield of about 6.8% estimated from steady FY27 guidance. That is a spread of about 270bps over the 4.13% T-bill. The 12-month OU Monte Carlo gives an expected return of 7.2% with a 12.5% standard deviation and PGain of 72%. The numeric chain supports a base score of 4. Conviction is cut one step to 3 because the David Jones administration is a tenant credit event, and exposure size is undisclosed in the data available. Beta of 0.68 against IASP.L carries the currency-basis caveat, and the negative 5-year benchmark return inflates CAPM alpha, so alpha is only a supporting input.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1247
- P-gain: 0.7193
- CAPM alpha: 0.0894
- Beta: 0.6808
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - David Jones administration leads to rent loss or a re-leasing gap, and the roughly AUD 2B refinancing resets at higher margins, so DPU is cut 5-8%. Cap rates expand about 30-50bps in a higher-for-longer or stagflation rate shock, and the price/NAV multiple contracts.
- **base**: E(R)=0.0730
  - Central case as built in the chain: yield of about 6.8%, DPU growth of 0.5% and flat multiple. FY27 guidance is held, David Jones is re-let or absorbed with limited impact, and cap rates are flat.
- **bull**: E(R)=0.1700
  - Rates ease and cap rates compress about 25bps. David Jones space is re-let quickly at similar rents, and refinancing is completed at tight margins. DPU growth of about 2.5% and a rerating toward NAV add roughly 8% in multiple change.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `last_close_price` = 3.5 (Cat A) — CLW.AX ASX close of AUD 3.50 on 2026-11-23 (get_price).
- `distribution_yield` = 0.068 (Cat B) — Forward yield of about 6.8%, estimated from FY27 DPU guidance of roughly 24cpu divided by the AUD 3.50 price. News headlines (Kalkine, 2026-11-18) say FY27 guidance is held steady. The stored filing bodies returned for CLW.AX were mismatched with other issuers, so the DPU figure was not verified against an issuer document. Treated as a derived estimate.
- `dpu_growth` = 0.005 (Cat C) — Assumed 0.5% annual distribution/NAV growth. This reflects steady FY27 guidance against about 2% growth in FY26 (Investing.com FY26 slides headline, 2026-08-12), less drag from David Jones tenant administration and refinancing costs on about AUD 2B of debt. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in cap rate or price/NAV multiple over 12 months. The price recovered from about 3.12 in early October to 3.50 in November. Any rerating is excluded from the base case.
- `expected_return_build` = 0.073 (Cat B) — E(R) is the sum of yield 6.8%, growth 0.5% and multiple change 0.0%, which is 7.3%. It is a derived estimate that depends on the Category B yield and Category C growth and multiple assumptions.
- `risk_free_rate` = 0.0413 (Cat A) — FRED DTB3 3-month T-bill at 4.13% on 2026-11-20 (get_tbill_rate). This is a USD rate used as the risk-free proxy for an AUD asset.
- `expected_market_return` = -0.0434 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (calculate_benchmark_return, 1260 trading days). GBP-denominated, so it absorbs FX co-movement.
- `gearing_estimate` = unverified (Cat B) — Gearing was not captured from a filing body in this run. The leverage gate relies on CLW's historically reported gearing of about 30-33%, which is below the Australian convention of 40%. This is flagged as unverified. The FY26 slides headline mentions a roughly AUD 2B refinancing task.
- `david_jones_tenant_event` = David Jones Administration (Cat A) — CLW.AX 2026-11-05 ASX release headlined 'CLW ASX Release - David Jones Administration' (COMPANY ADMINISTRATION), plus the 2026-11-03 'CLW Portfolio Leasing Update'. Both stored bodies were mismatched with other issuers, so only the headlines are used. The exposure size and rent impact are undisclosed here.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Currency basis noise is material here, as correlation is only 0.44.

## Key Risks
- Tenant credit risk: the David Jones administration (ASX release 2026-11-05) could cut rent or force a costly re-leasing, and the exposure size was not verified in this run.
- Refinancing and rates risk: the roughly AUD 2B refinancing task and higher-for-longer rates could pressure interest cost, DPU and cap rates.
- Data gaps: the stored filing bodies were mismatched with other issuers, so DPU, gearing, AFFO coverage, WALE and occupancy are unverified. Gearing and coverage gates are marked info for this reason.
- Currency-basis noise: IASP.L is GBP-denominated, and correlation of 0.44 means beta and alpha are noisy. A negative 5-year benchmark return of -4.3% flatters CAPM alpha.
- Calibration limitation: this is a directional single-date signal and not a formal backtest. Vintage discipline arrives in Phase 5. Macro inputs besides DTB3 were not used, and the USD T-bill is a proxy risk-free rate for an AUD asset.

## Invalidation Condition
Exit if a CLW filing shows David Jones-related rent loss or a re-leasing gap that cuts the distribution guidance below the roughly 24cpu level assumed. Also exit if reported gearing rises above 40%, if the refinancing is completed at materially wider margins, or if distribution coverage by operating earnings falls below 1.0x for two consecutive reporting periods.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
