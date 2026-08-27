# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-08-27_equity_reit_v1@1.0_f235b62da9ea`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified
**As of**: 2026-08-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus (DXS.AX) is Australia's largest diversified property group with significant office concentration in Sydney and Melbourne CBDs, an asset class facing structural headwinds from hybrid work adoption and persistent cap rate pressure. The trailing distribution yield of approximately 5.1% offers modest spread over the 3.7% T-bill rate, but the OU Monte Carlo simulation returns a PGain of 60.3% and a simulated expected return of 3.5%, insufficient to compensate for annualised volatility of 20%. An ongoing on-market buy-back (confirmed via multiple ASX notifications in August 2026) provides partial NTA support and signals management confidence. The CAPM alpha of 4.5% (Category B, currency-basis caveat) appears positive but is partially illusory given the deeply negative IASP.L benchmark return (-4.6% annualised over 5 years), and conviction is capped at Low (2/5) reflecting office devaluation risk, marginal AFFO coverage, and elevated gearing relative to the stated 25-35% target range.

## Quantitative Chain

- E(R): 0.0360
- Std dev: 0.1360
- P-gain: 0.6026
- CAPM alpha: 0.0445
- Beta: 0.5501
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office occupancy deteriorates further to below 90% in CBD markets, DPU cut to ~25cpu (yield ~4.3%), gearing breaches 40% triggering covenant risk, cap rates expand 50bps compressing NTA by 10-15%, RBA holds higher-for-longer compressing yield spread. This pathway would likely be driven by a commercial real estate credit tightening cycle or a sustained WFH structural demand shift accelerating office vacancy.
- **base**: E(R)=0.0360
  - Central case as built: DPU ~29-30cpu, yield ~5.1%, DPU growth -0.5%, multiple contraction -1.0%, gearing stable at ~37%, office stabilisation in H2 2026 with partial offset from industrial/logistics and healthcare assets, buy-back programme continues.
- **bull**: E(R)=0.1400
  - RBA pivots to rate cuts (2-3 cuts in 2026-27), office cap rates compress 25-30bps, occupancy recovers to 94%+, DPU growth resumes at 2%+, discount to NTA narrows materially as asset values recover, buy-back programme accelerates, industrial/logistics and healthcare exposure increasingly valued by market at premium multiples.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=fail
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.051 (Cat A) — Estimated trailing DPU yield based on ~AUD 29-30cpu DPU against observed closing price of AUD 5.78 on 2026-08-27. DXS FY2025 DPU has been in the 29-30cpu range following distribution resets amid office portfolio revaluations. Yield ~5.1%. Observed price is Category A; DPU estimate informed by disclosed FY2025 annual report guidance.
- `dpu_growth` = -0.005 (Cat C) — DPU growth assumption of -0.5% p.a. reflecting continued office sector headwinds, vacancy pressure in CBD office markets, and partial offset from industrial/logistics and healthcare asset growth. News sources (Motley Fool Australia, Jul 2026) confirm ongoing office portfolio valuation falls partially offset by industrial gains. Sensitivity: bear case assumes -3%, bull case assumes +2%.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% cap rate drift/multiple contraction on office assets. Australian office cap rates remain under upward pressure as higher-for-longer RBA rates persist. Buy-back programme (confirmed via ASX notifications Aug 2026) provides partial support. Discount to NTA may narrow slowly but office devaluation risk dominates.
- `gearing_ratio` = 0.37 (Cat B) — Estimated gearing of approximately 37% based on published guidance (Dexus targets 25-35% look-through gearing). Elevated relative to target range following property devaluations compressing asset values. Directionally supported by SimplyWallSt commentary (Aug 2026) referencing debt strains. Within AU REIT convention of <40% but above stated target range. Category B as derived from guidance range, not latest audited balance sheet.
- `rba_cash_rate` = 0.04 (Cat B) — RBA cash rate estimated at approximately 4.0% as of Aug 2026 based on publicly known rate trajectory. Stored APAC rates for AU returned no data; rate assumed from public knowledge of RBA policy setting. Relevant as cost-of-debt driver for DXS. Category B due to estimation.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The IASP.L currency basis means the measured beta of 0.550 reflects both Dexus's underlying property risk and AUD/GBP currency dynamics. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Continued office cap rate expansion driven by higher-for-longer RBA rates compressing NTA and forcing distribution cuts below 1.0x AFFO coverage
- Structural demand shift in CBD office markets (hybrid/remote work) driving occupancy below 90% and triggering asset impairments
- Gearing ratio exceeding 40% covenant threshold amid further property devaluations, constraining distribution capacity and capital management flexibility
- Concentration risk: office assets represent the majority of portfolio value and are disproportionately exposed to the weakest sub-sector in Australian commercial real estate
- AUD/GBP currency basis noise in beta and CAPM alpha estimates may overstate true risk-adjusted outperformance; macro series (FEDFUNDS, credit spreads) unavailable for this analysis, which limits cross-asset calibration

## Invalidation Condition
Exit if Dexus announces a DPU cut below 25 cents per unit for any half-year period, or gearing breaches 40% on a look-through basis per any disclosed quarterly or half-year update, or CBD office occupancy across the managed office portfolio falls below 88% for two consecutive reporting periods, or management withdraws or materially reduces the on-market buy-back programme without a value-accretive alternative capital deployment announcement.
