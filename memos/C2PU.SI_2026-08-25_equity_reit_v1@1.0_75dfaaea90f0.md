# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-08-25_equity_reit_v1@1.0_75dfaaea90f0`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-08-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
ParkwayLife REIT offers one of the most defensively structured income streams in the Singapore REIT universe, underpinned by long-dated master leases with IHH Healthcare's Parkway Pantai hospitals (WALE ~18 years) and CPI-linked rents across a 49-property Japan nursing home portfolio. At a closing price of SGD 4.15, the estimated forward distribution yield of ~3.66% plus 2% organic DPU growth produces an E(R) of 5.7%, which the OU Monte Carlo translates into a 77.5% probability of positive 12-month return with an annualised vol of 10.9%. CAPM alpha of 4.0% versus a negative-trending IASP.L benchmark (currency-basis caveat applies) further supports above-average conviction. Gearing of ~37% provides meaningful headroom below the MAS 45% limit, preserving debt capacity for selective acquisitions that have historically been accretive.

## Quantitative Chain

- E(R): 0.0566
- Std dev: 0.0745
- P-gain: 0.7749
- CAPM alpha: 0.0398
- Beta: 0.2502
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - DPU growth stalls at 0% (SGD strength vs JPY erodes Japan nursing home income; no CPI escalation triggers); gearing rises toward 42% following a debt-funded acquisition at unfavourable terms; IHH Healthcare credit stress leads to renegotiation of Singapore hospital master lease at lower rents; cap rate expansion of 30bps compresses NAV by ~7%; SG rate environment remains elevated with T-bill above 4.5%, compressing yield spread and triggering sentiment-driven re-rating. This scenario also captures a macro stagflation pathway where healthcare capex cuts reduce rent renewal upside.
- **base**: E(R)=0.0570
  - Central case as built in quantitative chain: DPU yield 3.66%, DPU growth 2.0% p.a., neutral multiple change. Japan nursing homes provide CPI-linked uplift; Singapore hospital master leases renew on contractual schedule. Gearing stable at ~37%, T-bill at 3.72%, yield spread ~140bps maintained.
- **bull**: E(R)=0.1500
  - Accretive acquisition of additional Japan nursing home portfolio at 5.5%+ NPI yield funded at below-NAV cost of debt; SGD/JPY FX movement favourable (JPY appreciation adds ~2% to NPI translation); DPU growth accelerates to 3.5%; market re-rates healthcare REITs on defensive income demand, driving 8-10% price appreciation; T-bill rate declines to 3.0%, yield spread widens attractively.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0366 (Cat B) — FY2025 DPU estimated at SGD 0.152 per unit based on confirmed 2H2025 DPU growth reported in news (Feb 2026 distribution raised; Dr Wealth Feb 2026 article). Divided by closing price SGD 4.15 as of 2026-08-25. Category B as DPU is a forward estimate derived from growth trajectory; filed FY2024 DPU was ~SGD 0.1488.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. for 12-month horizon. PLife REIT benefits from CPI-linked rent escalation on Japan nursing home leases (~49 properties) and contractual step-ups on Singapore hospital master leases (IHH/Parkway Pantai). Historical DPU CAGR 2018-2025 was approximately 2-3% p.a. Sensitivity: bear case 0%, bull case 3.5%.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumption for 12-month horizon. At SGD 4.15 the REIT trades at a modest premium to estimated book NAV (~SGD 3.80-4.00 range based on sector comparables and CPI-adjusted asset values). No catalyst expected to materially expand or compress the multiple over the next 12 months; sensitivity tested in scenario analysis.
- `gearing_ratio` = 0.37 (Cat B) — ParkwayLife REIT has maintained aggregate leverage of approximately 35-38% historically, well below the MAS 45% regulatory limit. Estimate derived from most recent publicly available financial data and confirmed by news references to strong balance sheet (The Smart Investor Jun 2026, Oct 2025). No filed annual report body available in stored filings for this as_of date.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency basis noise. The low beta of 0.25 partially reflects SGD/GBP decorrelation in addition to the defensive healthcare-REIT business model.

## Key Risks
- JPY depreciation versus SGD reducing income contribution from Japan nursing homes (~34% of revenue), given rents are denominated in JPY but distributions are paid in SGD
- IHH Healthcare / Parkway Pantai creditworthiness — any deterioration in the anchor tenant (contributing ~60% of income) would materially impair DPU coverage and trigger a re-rating
- Higher-for-longer SGD interest rates compressing the yield spread versus T-bills and making the ~3.7% distribution yield less competitive for income investors
- Absence of filed financials in the data store means FY2025 DPU and gearing figures are derived estimates (Category B/C); actual filed numbers may differ from model assumptions
- Benchmark IASP.L is GBP-denominated; 5-year annualised return of -4.4% reflects GBP/APAC FX headwinds rather than pure property fundamentals — CAPM-derived required return and alpha carry elevated estimation error

## Invalidation Condition
Exit position if any of the following are observed: (1) ParkwayLife REIT's reported aggregate leverage breaches 43% for two consecutive semi-annual reporting periods, signalling deteriorating balance sheet headroom; (2) IHH Healthcare announces a material renegotiation or early termination of any Singapore hospital master lease at rental rates more than 10% below prevailing levels; (3) actual FY2025 or FY2026 DPU falls below SGD 0.148 per unit (below FY2024 actuals), confirming a reversal of the established DPU growth trend; or (4) SGD/JPY exchange rate moves such that Japan nursing home NPI contribution falls below 28% of total revenue for two consecutive periods.
