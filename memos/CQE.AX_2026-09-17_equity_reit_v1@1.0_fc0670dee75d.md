# Specialist Memo — CQE.AX

**Memo ID**: `CQE.AX_2026-09-17_equity_reit_v1@1.0_fc0670dee75d`
**Ticker**: CQE.AX (Charter Hall Social Infrastructure REIT)
**Market**: Australia
**Sector**: Social Infrastructure / Diversified
**As of**: 2026-09-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Charter Hall Social Infrastructure REIT (CQE.AX) offers a defensive, government-anchored income stream through its portfolio of early learning centres, healthcare, and government-tenanted assets, underpinned by a high-quality Charter Hall sponsor with a demonstrated capital recycling and pipeline delivery capability. The trailing distribution yield of approximately 6.47% provides a meaningful 248bps spread over the current 3-month T-bill rate of 3.99%, and FY27 guidance has been reaffirmed alongside a broadening tenant mix. Historical volatility of 23.3% is elevated for the sector, reflecting AUD sensitivity and the REIT's smaller market cap, which moderates the OU Monte Carlo-derived PGain to 69.1%. CAPM alpha of 9.8% relative to a negative 5-year IASP.L benchmark return underlines absolute return attractiveness, though beta of 0.65 (currency-basis caveat applies) implies meaningful co-movement with broader APAC REIT sentiment. Conviction is set at moderate (3/5) reflecting the high annualised volatility and unconfirmed gearing level from filing data.

## Quantitative Chain

- E(R): 0.0797
- Std dev: 0.1585
- P-gain: 0.6908
- CAPM alpha: 0.0982
- Beta: 0.6532
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA maintains higher-for-longer rates compressing A-REIT cap rates by 30–50bps; CQE gearing breaches 40% following asset revaluation declines; DPU coverage falls below 1.0x due to tenant attrition in childcare sub-sector; distribution cut of 10–15%. Multiple contraction drives price back toward AUD 2.00.
- **base**: E(R)=0.0790
  - Central case as built in chain: distribution yield 6.47%, DPU growth 2.0%, multiple change -0.5%. Gearing remains within regulatory convention, FY27 distribution guidance maintained, government-anchored tenant occupancy stable.
- **bull**: E(R)=0.2000
  - RBA cuts rates 50–75bps by mid-2027, compressing cap rates and driving NAV expansion; Charter Hall sponsor injects accretive social infrastructure pipeline at 6.5%+ yield; DPU growth accelerates to 4%+ on CPI-linked rent reviews; price re-rates toward AUD 2.85–3.00.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0647 (Cat A) — Trailing distribution yield derived from current price of AUD 2.40 (observed 2026-09-17). Kalkine news (2026-07-21 and 2026-07-22) reported distribution yield of 6.46–6.49%; mid-point 6.47% used as primary Category A signal. FY26 distribution was lifted per ASX announcement (Kalkine 2026-08-17).
- `dpu_growth_2yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. based on: (1) FY27 guidance reaffirmed per ASX announcement headline 2026-08-10; (2) tenant mix broadening into social infrastructure sub-segments (Kalkine 2026-09-15); (3) government-anchored leases providing CPI-linked or fixed step-up rent reviews. Sensitivity tested in scenario analysis. Category C as no numerical guidance quantum was available from filing bodies.
- `multiple_change` = -0.005 (Cat C) — Modest cap-rate drift assumption of -0.5% on total return, reflecting residual Australian interest-rate uncertainty at September 2026. APAC rate data for Australia was unavailable from stored sources; assumption is model-based. Sensitivity tested in bear scenario.
- `expected_return_build` = 0.0797 (Cat B) — E(R) = distribution yield (6.47%, Cat A) + DPU growth (2.0%, Cat C) + multiple change (-0.5%, Cat C) = 7.97%. Components are classified individually; blended result is Category B.
- `gearing_level` = not_confirmed (Cat C) — No verified gearing figure was extractable from ASX filing bodies (filing body content retrieved was cross-contaminated with other issuers). Based on Kalkine news coverage (no gearing breach mentioned), gearing is assumed within the AU convention of <40%. This assumption carries model risk and is disclosed in key_risks. Annual Report filed 2026-08-20; body unavailable to confirm.
- `wale_occupancy` = not_confirmed (Cat C) — WALE and occupancy not quantitatively confirmed from accessible filing bodies. Social infrastructure assets (early learning centres, government tenancies, healthcare) structurally carry long WALEs typically 10–15 years. Qualitative assessment of asset quality gate is based on sector characteristics and news headlines only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Gearing level unconfirmed from accessible filing bodies — if gearing has drifted above 40% following FY26 revaluations, the leverage gate would require a downward conviction override.
- Elevated annualised volatility (23.3%) significantly wider than large-cap A-REIT peers, reducing probability-of-gain and amplifying drawdown risk in a risk-off environment.
- Higher-for-longer RBA rate policy compressing social infrastructure cap rates and reducing distribution coverage if refinancing costs rise materially.
- Childcare sub-sector regulatory risk: any changes to Commonwealth childcare subsidy policy could reduce operator viability and increase tenant default risk.
- Beta coefficient of 0.65 absorbs AUD/GBP currency basis noise (IASP.L denomination), creating uncertainty in the CAPM-derived required return and alpha estimates.
- Phase 2 calibration limitation: the quantitative chain reflects a directional signal only; formal vintage discipline is not yet implemented (Phase 5). Backtest-mode accuracy caveats apply.

## Invalidation Condition
Exit if CQE.AX reports gearing above 40% LVR for two consecutive semi-annual periods, or if the annualised distribution per unit is cut by more than 10% from the FY26 level without a corresponding NAV-accretive asset disposal, or if occupancy in the childcare sub-segment falls below 90% for two consecutive reporting periods, or if Charter Hall Group formally reduces or withdraws its pipeline commitment to the REIT.
