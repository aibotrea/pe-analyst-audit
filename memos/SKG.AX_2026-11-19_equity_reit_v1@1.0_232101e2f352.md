# Specialist Memo — SKG.AX

**Memo ID**: `SKG.AX_2026-11-19_equity_reit_v1@1.0_232101e2f352`
**Ticker**: SKG.AX (Storage King Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-11-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
SKG.AX is a recently internalised Australian self-storage platform (Storage King Group) trading at AUD 1.14. It offers an assumed forward yield of about 6.5% (Category C) and modest growth from internalisation savings. The OU Monte Carlo gives a 12-month simulated return of about 8.9% on 16.5% dispersion, for a PGain of 70.6%. The numeric chain supports a four-point conviction. One step is removed because distribution coverage, gearing and sponsor commitments could not be verified from the stored filings, so the score is 3. The CAPM alpha is flattered by the negative IASP.L trailing return and by currency-basis noise in beta, so PGain is the primary basis for the call.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1651
- P-gain: 0.7056
- CAPM alpha: 0.0992
- Beta: 0.6012
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or higher-for-longer rate pathway: AUD cap rates expand 50bps and the unit price de-rates by about 10%. Overhang from the Abacus exit persists, and self-storage rent growth stalls so distribution growth is 0%. Gearing is above 35%, so coverage falls below 1.0x AFFO and the yield stays near 6.5%.
- **base**: E(R)=0.0900
  - Central case as built in the chain: 6.5% yield, 2.5% distribution growth including some internalisation savings, no multiple change. Cap rates are flat and occupancy is stable.
- **bull**: E(R)=0.2200
  - Internalisation savings are delivered in full and development or acquisition is accretive. RBA easing compresses cap rates by 25bps, and the unit price re-rates 8-10% toward NAV as the Abacus overhang clears. Distribution growth reaches 5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 1.14 (Cat A) — SKG.AX last close AUD 1.14 on 2026-11-19 (get_price).
- `distribution_yield` = 0.065 (Cat C) — Forward distribution yield assumed at 6.5% of the AUD 1.14 price. No SKG distribution, DPU or AFFO figure could be verified from stored filings, because the returned filing bodies belonged to other issuers. The 6.5% is an assumption based on sector-typical self-storage yields, not an observed number. Sensitivity: each +/-1% in yield moves E(R) by +/-1%.
- `dpu_growth_12m` = 0.025 (Cat C) — Forward distribution growth of 2.5%. Basis is organic self-storage rent growth, plus part of the roughly A$7m annual savings reported in Aug 2026 press coverage from internalising management (unverified against a filing). Sensitivity is covered in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — Assumes no re-rating of the price to NAV or AFFO multiple over 12 months. The Abacus stake sale in Sep 2026 and the 2026-09-18 block volume (about 132m units) point to possible overhang or price discount dynamics, but the direction is uncertain, so none is modelled.
- `expected_return` = 0.09 (Cat C) — E(R) = yield 6.5% (C) + growth 2.5% (C) + multiple change 0% (C) = 9.0%. This is the base_return input to the OU Monte Carlo.
- `risk_free_rate` = 0.0416 (Cat A) — FRED DTB3 3-month US T-bill rate of 4.16% on 2026-11-18 (get_tbill_rate). This is a USD rate, used as the platform-standard Rf, not an AUD rate.
- `expected_market_return` = -0.0429 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (calculate_benchmark_return, 1260-day lookback). The GBP-denominated benchmark return absorbs FX movement. A negative Rm makes CAPM alpha mechanically large and favourable, so it is a weak signal.
- `historical_volatility` = 0.2429 (Cat B) — 252-day annualised volatility from stored prices, 262 observations (calculate_historical_volatility). The window is short and includes the Sep 2026 sell-down event, so it may overstate steady-state volatility.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. This is a currency-basis (currency/IASP) disclosure. Beta of 0.60 and correlation of only 0.30 indicate low explanatory power.
- `filing_data_gap` = disclosed (Cat B) — Stored filings tagged SKG.AX for 2026-09-24 to 2026-11-19 (AGM Addresses and Quarterly Update 2026-11-12, Amended Constitutions 2026-11-19 and others) returned bodies from unrelated issuers (an IML ETF report, Citi warrants, Thor Energy, Nanosonics and others). No SKG gearing, occupancy, WALE or coverage figures were extracted. ASX announcement headlines were used only as a timing reference.

## Key Risks
- Unverified fundamentals: the stored SKG filings returned bodies from unrelated issuers, so gearing, AFFO coverage, occupancy and the actual distribution are not confirmed. The 6.5% yield is an assumption.
- Post-Abacus-exit overhang and low free float: the 2026-09-18 block volume of roughly 132m units shows the stock is exposed to sell-downs and liquidity swings.
- Australian rate and cap-rate risk: a stagflation or higher-for-longer pathway would widen cap rates and compress self-storage valuations and distribution coverage.
- Currency-basis noise in beta and Rm: IASP.L is GBP-denominated, correlation is only 0.30, and the negative 5-year benchmark return inflates alpha.
- Calibration limitation: this is a live-mode directional signal, not a formal backtest. Macro series other than DTB3 were not used, and the US T-bill rate stands in for an AUD risk-free rate.

## Invalidation Condition
Exit if the next SKG half-year or full-year results show distribution coverage below 1.0x AFFO, gearing above 40% (the Australian convention cap), or like-for-like self-storage occupancy falling more than 3 percentage points. Exit also if internalisation savings of about A$7m are not delivered, or if the price breaks below roughly AUD 1.00 on sustained heavy volume after a further sell-down by major holders.
