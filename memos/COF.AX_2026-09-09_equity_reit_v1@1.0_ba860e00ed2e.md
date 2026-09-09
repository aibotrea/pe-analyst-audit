# Specialist Memo — COF.AX

**Memo ID**: `COF.AX_2026-09-09_equity_reit_v1@1.0_ba860e00ed2e`
**Ticker**: COF.AX (Charter Hall Retail REIT)
**Market**: Australia
**Sector**: Convenience Retail
**As of**: 2026-09-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Charter Hall Retail REIT (COF.AX) offers a high-quality, defensive income stream anchored by Woolworths and Coles-tenanted convenience retail properties, with CPI-linked lease escalations providing organic DPU growth. At AUD 0.87, the REIT trades at an estimated 8-9% discount to NTA (~AUD 0.95), providing a margin of safety that supports total return. The trailing distribution yield of ~6.5% is approximately 270bps above the 3.8% T-bill rate, representing an attractive risk-adjusted income spread underpinned by near-full occupancy (~98.5%) and a WALE of approximately 7.5 years. OU Monte Carlo (10,000 iterations) over a 12-month horizon produces a simulated return of 8.4% with a 74.9% probability of positive return, supporting above-average conviction at a position size of 8.0%.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1258
- P-gain: 0.7490
- CAPM alpha: 0.0891
- Beta: 0.4975
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA surprises with renewed rate hikes pushing 10-year AGB yields above 5.5%, cap rate expansion of 50bps causing NTA erosion to AUD 0.82-0.84, DPU maintained flat (0% growth) but yield spread narrows materially; tenant sales volumes soften as consumer spending contracts amid higher mortgage stress, occupancy slips to 96%; stock re-rates to 15% discount to compressed NTA.
- **base**: E(R)=0.0850
  - Central case as built in chain: distribution yield 6.5%, DPU growth 1.5% (CPI-linked), multiple change +0.5% on modest NTA discount mean-reversion as RBA holds rates. Occupancy stable at ~98.5%, gearing ~36%, WALE ~7.5 years. No material acquisitions or disposals.
- **bull**: E(R)=0.2000
  - RBA cuts cash rate by 75bps through 2026-2027, cap rates compress 25-30bps driving NTA re-rating toward AUD 1.05+, DPU growth accelerates to 2.5% on stronger CPI and specialty rent reversion. COF re-rates from 8% discount to NTA toward par or slight premium, delivering total return of approximately 20% including income.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat A) — Trailing distribution yield estimated at ~6.5% based on observed market price AUD 0.870 (COF.AX close 2026-09-09) and FY26 DPU lifted per ASX announcement COF FY26 Results Announcement 2026-08-03. DPU approximately 5.6-5.7 cpu implied on annualised basis. Category A: price and announced DPU are publicly observable.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. based on CPI-linked lease escalations embedded in Woolworths/Coles-anchored convenience retail portfolio. Limited acquisition pipeline growth assumed. Sensitivity: bear case 0%, bull case 2.5%. Category C: forward estimate not yet filed.
- `multiple_change` = 0.005 (Cat C) — Modest positive multiple change of +0.5% assumed, reflecting COF trading at approximately 8-9% discount to estimated NTA (~AUD 0.95). Partial mean-reversion assumed over 12-month horizon as RBA rate cycle stabilises. Category C: model assumption dependent on rate outlook.
- `gearing_ratio` = 0.36 (Cat B) — Gearing estimated at approximately 36%, consistent with Charter Hall Retail REIT's historically reported range of 35-38%. Sourced from COF FY26 Results Announcement headline (ASX 2026-08-03); body capture misfiled (ASX pipeline cross-contamination). Treated as Category B — derived from published range, not direct extraction.
- `occupancy` = 0.985 (Cat B) — Portfolio occupancy estimated at ~98.5%, consistent with COF's historically reported convenience retail portfolio anchored by Woolworths and Coles. Sourced from headline of COF FY26 Property Compendium (ASX 2026-08-03); body unavailable due to filing pipeline cross-contamination. Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis noise is material given AUD/GBP cross-currency dynamics. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Renewed RBA rate hike cycle compressing yield spreads and driving cap rate expansion, reducing NTA and suppressing multiple re-rating
- Australian consumer stress from mortgage affordability pressures reducing specialty retail tenant sales and increasing leasing risk at non-anchor components
- High anchor tenant concentration (Woolworths/Coles estimated >60% of gross income) creates single-counterparty sensitivity, though offset by investment-grade credit quality
- AUD/GBP currency basis absorbs into beta calculation (IASP.L is GBP-denominated), introducing noise into CAPM alpha signal; true systematic risk may differ from computed beta of 0.50
- ASX filing body capture misfiled for COF FY26 results (pipeline cross-contamination) — key metrics including exact DPU, NTA, and gearing sourced from public knowledge and news headlines rather than direct filing extraction, introducing Category B uncertainty into yield and leverage assumptions

## Invalidation Condition
Exit position if occupancy falls below 95% for two consecutive reporting periods, or if DPU is cut (any reduction from FY26 declared level), or if gearing rises above 40% breaching the Australian REIT convention threshold, or if Charter Hall Group (CHC.AX) reduces its COF management mandate or pipeline commitment. A confirmed RBA rate hike cycle resuming above 5.0% cash rate would also trigger reassessment.
