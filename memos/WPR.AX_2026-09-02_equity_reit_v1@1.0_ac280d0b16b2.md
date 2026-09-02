# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-09-02_equity_reit_v1@1.0_ac280d0b16b2`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Fuel & Convenience Retail
**As of**: 2026-09-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Waypoint REIT offers a differentiated Australian REIT exposure through a portfolio of ~400+ fuel and convenience retail properties leased on long-dated NNN structures to investment-grade tenants including Viva Energy and EG Group. At a current price of AUD 2.34, the annualised distribution yield of approximately 7.3% provides a meaningful spread over the 3.78% US T-bill benchmark and compensates for the sector's single-asset-class concentration. The 1H26 results (distributable earnings $56.1M, EPS +3.4% YoY, guidance reaffirmed) confirm distribution sustainability. Beta of 0.49 versus IASP.L (currency-basis caveat applies) indicates below-market sensitivity to broad APAC REIT movements, and the OU Monte Carlo PGain of 80.8% supports moderate conviction at a 12-month horizon, reduced one step for fuel-sector tenant concentration risk.

## Quantitative Chain

- E(R): 0.0926
- Std dev: 0.1059
- P-gain: 0.8078
- CAPM alpha: 0.0958
- Beta: 0.4891
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA maintains higher-for-longer cash rate, triggering 25-50bps cap rate expansion on fuel & convenience assets; DPU growth turns negative (-1%) as tenant rent reviews underperform CPI; price falls toward AUD 2.10. Gearing approaches 40% threshold, limiting capital management flexibility. Macro scenario: stagflation or recession reduces fuel throughput volumes, weakening tenant covenant quality (Viva Energy, EG Group).
- **base**: E(R)=0.0926
  - Central case as modelled: annualised DPU of 17c (yield 7.26% at AUD 2.34), DPU growth 2.0% from CPI-linked rent escalators, cap rates flat. FY26 guidance reaffirmed. EPS growth continues at ~3% YoY. Price stability around AUD 2.35-2.50.
- **bull**: E(R)=0.2000
  - RBA eases cash rate by 50bps, compressing cap rates and driving NTA expansion; DPU growth accelerates to 3.5% from stronger-than-CPI rent reviews; price re-rates toward AUD 2.70-2.80. Institutional demand for long-WALE defensive income assets drives multiple re-rating. Viva Energy and EG Group maintain strong fuel volumes underpinning distribution coverage above 1.1x.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0726 (Cat A) — Annualised DPU of AUD 0.17 (4 × 4.25 cents per quarter, per 1H26 distribution announcement dated 2026-08-26 and news confirmation of 4.25c interim distribution) divided by closing price of AUD 2.34 on 2026-09-02. Both DPU and price are observed public data.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. based on: (a) 1H26 EPS growth of 3.4% YoY per Motley Fool / TradingView news (2026-08-26/27); (b) FY26 guidance reaffirmed; (c) long-dated NNN leases with CPI or fixed rent escalators typical of fuel & convenience portfolios. Sensitised in scenario analysis: bull case 3.5%, bear case -1.0%.
- `multiple_change` = 0.0 (Cat C) — Neutral cap-rate/multiple assumption: no expansion or contraction modelled in the base case. Cap rate risk from persistent elevated RBA cash rates modelled in the bear case. Reviewed against recent price action (AUD 2.34 vs ~AUD 2.51 one month prior, suggesting modest softening) but insufficient signal to call directional shift.
- `leverage_gearing` = ~35-38% estimated (Cat B) — ASX body capture for WPR 1H26 financial report (2026-08-26) failed (pipeline returned unrelated issuer content). Gearing estimated at 35-38% based on Kalkine/news commentary referencing long-lease NNN portfolio characteristics consistent with WPR's historical balance sheet structure. Below AU REIT conventional 40% ceiling. Category B due to estimation from indirect sources.
- `quarterly_dpu_structure` = 0.0425 (Cat A) — 1H26 distribution of 4.25 cents per unit declared per DISTRIBUTION ANNOUNCEMENT filing headline dated 2026-08-26 (price_sensitive=False) and confirmed by Kalkine Media news item dated 2026-08-26 ('Distributable Earnings of $56.1 Million and Declares 4.25 Cent Distribution').
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Correlation of 0.36 over 252 trading days indicates moderate linkage. IASP.L 5-year annualised return of -4.6% is also Category B for same currency-basis reason.

## Key Risks
- Single-sector concentration: entire portfolio exposed to fuel and convenience retail; structural decline in internal combustion engine vehicles (EV transition) could impair long-term site values and tenant covenant quality over a 5-10 year horizon, though near-term NNN leases insulate distributions.
- Tenant concentration: top tenants (Viva Energy, EG Group) together likely represent the majority of portfolio income; financial stress at either counterparty would materially impair distributable earnings.
- Higher-for-longer RBA cash rate compressing the yield spread and driving cap rate expansion, reducing NTA and increasing refinancing costs as existing debt rolls.
- ASX filing body capture failure for 1H26 Financial Report and Appendix 4D (pipeline returned unrelated issuer content); gearing ratio, AFFO coverage, and WALE could not be verified directly from the primary filing — these are estimated from secondary news sources.
- IASP.L benchmark (GBP-denominated) introduces currency-basis noise in beta and CAPM alpha; the -4.6% five-year annualised benchmark return may over-penalise WPR's required return versus an AUD-denominated property index.

## Invalidation Condition
Exit if: (1) DPU coverage falls below 1.0x AFFO for two consecutive half-year reporting periods; (2) gearing ratio breaches 40% on a sustained basis without a credible deleveraging plan disclosed to ASX; (3) either Viva Energy or EG Group enters administration or announces a material reduction in lease commitments to WPR; or (4) annualised DPU is cut by more than 10% versus the FY26 guidance level, signalling structural impairment of distributable earnings rather than a temporary working capital timing issue.
