# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-07-14_equity_reit_v1@1.0_4d27f31af5ea`
**Ticker**: RGN.AX (Region Group (Region RE Trust))
**Market**: Australia
**Sector**: Retail — Neighbourhood/Sub-Regional
**As of**: 2026-07-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group (RGN.AX) is an internally managed Australian retail REIT anchored by investment-grade supermarket tenants (Woolworths, Coles) across ~75 neighbourhood and sub-regional centres, offering a defensive, inflation-linked income stream. At AUD 2.36, the trust trades at an estimated ~5-8% discount to NTA with a trailing distribution yield of ~5.89%, providing a meaningful spread over a 3.76% T-bill rate in a declining rate environment. Beta of 0.44 versus IASP.L (currency-basis caveat applies) indicates below-market sensitivity to APAC REIT sector movements. The OU Monte Carlo simulation delivers a simulated return of 8.35% with PGain of 80.5% and CAPM alpha of +7.98%, supporting an above-average conviction rating at a 12-month horizon. Key risk is a consumer spending downturn or RBA policy reversal widening cap rates, though the supermarket-anchor model provides structural resilience.

## Quantitative Chain

- E(R): 0.0839
- Std dev: 0.0971
- P-gain: 0.8049
- CAPM alpha: 0.0798
- Beta: 0.4427
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA reverses course or inflation re-accelerates, pushing cap rates wider by 25-50bps; supermarket anchor lease renewals weaken; occupancy slips below 97%; DPU cut of ~8-10% as coverage falls below 1.0x AFFO; Australian retail spending contracts materially in a consumer-led recession driven by mortgage stress, compounding a re-rating to deeper NTA discount.
- **base**: E(R)=0.0830
  - Central case: FY26 DPU AUD 0.139, yield 5.89%, 2.0% DPU growth, modest +0.5% multiple expansion as RBA easing progresses, gearing stable ~36%, occupancy ~98.5%, WALE ~5 years. OU Monte Carlo sim_return 8.35%, PGain 80%.
- **bull**: E(R)=0.2000
  - RBA cuts aggressively to ~3.0%, driving cap rate compression and NTA re-rating toward 10% premium; DPU growth accelerates to 3.5% on strong specialty sales and CPI uplift; portfolio recycling or bolt-on acquisitions at accretive yields; sector rotation into defensive yield plays benefits ASX-listed retail REITs broadly.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0589 (Cat A) — Trailing FY26 DPU estimated at AUD 0.139/unit, derived from observed ex-distribution price step-down of ~AUD 0.070 around 2026-06-22 (H2 FY26) plus inferred H1 FY26 distribution of ~AUD 0.069, consistent with the DISTRIBUTION ANNOUNCEMENT filed 2026-06-16. Current price AUD 2.36 (2026-07-14). Yield = 0.139 / 2.36 = 5.89%. Note: FY26 distribution announcement body unavailable (ASX body capture failed); ex-date price-step methodology used as corroborating evidence. Category A — derived from observed closing prices.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed on basis of: (1) CPI-linked rent reviews on supermarket anchor leases (Woolworths, Coles); (2) modest organic leasing spread improvement in neighbourhood retail; (3) offset by potential cap-rate headwinds from residual rate normalisation. Sensitivity: bear case 0%, bull case 3.5%. No filed forward guidance available (FY26 annual results body capture failed).
- `multiple_expansion` = 0.005 (Cat C) — Modest positive multiple change of +0.5% assumed reflecting RBA easing cycle (cash rate declining from 4.35% peak). Australian neighbourhood retail REITs trade at ~5-10% discount to NTA; modest re-rating as rates fall is the base-case assumption. Category C — model assumption; sensitivity tested in scenario analysis.
- `rba_cash_rate` = estimated_385bps (Cat B) — RBA cash rate estimated at approximately 3.85% as of July 2026 based on RBA easing trajectory from 4.35% peak (February 2025 first cut). Live APAC rates tool returned empty for AU on 2026-07-14. Estimate based on publicly available RBA forward guidance and market pricing. Category B — derived estimate.
- `gearing_ratio` = estimated_36pct (Cat B) — Region Group gearing estimated at ~36% (book debt / total assets) based on FY25 reported figures and the June 2026 Property Valuations Update (price-sensitive filing dated 2026-06-16, body capture failed). AU REIT convention limit is <40%. Estimate is within regulatory bounds. Category B — estimated from prior period actuals; body of June 2026 valuation filing unavailable.
- `distribution_coverage` = estimated_103pct (Cat B) — AFFO distribution coverage estimated at ~1.03x based on Region Group's internally managed cost structure and known rental income profile for neighbourhood retail. FY26 distribution filing body unavailable (ASX body capture failed for 2026-06-16 periodic report). Category B — estimated; body data gap disclosed.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. The IASP index is the FTSE EPRA/NAREIT Asia Developed index, denominated in GBP, introducing an additional AUD/GBP translation effect on the 252-day regression.

## Key Risks
- RBA policy reversal or persistent inflation causing cap rate widening and NTA erosion, reversing the multiple expansion assumption
- Australian consumer spending contraction (mortgage stress, cost-of-living pressure) reducing specialty retailer occupancy and rental growth below CPI
- FY26 distribution coverage data gap: body of FY26 distribution announcement and property valuations update unavailable; actual DPU and gearing could differ from estimates
- Director departure (Michael Herring, July 2026) creates minor governance uncertainty until replacement confirmed
- AUD/GBP currency basis embedded in beta estimate introduces noise in CAPM alpha; true factor exposure may differ materially from the 0.44 beta coefficient

## Invalidation Condition
Exit the position if: (1) reported FY26 AFFO distribution coverage falls below 1.0x for two consecutive half-year periods; (2) gearing breaches 40% following asset revaluations in the June 2026 or December 2026 property update; (3) occupancy at same-centre level falls below 96% for two consecutive reporting periods; or (4) RBA cash rate rises above 4.50% signalling a sustained tightening reversal that would materially compress the yield spread.
