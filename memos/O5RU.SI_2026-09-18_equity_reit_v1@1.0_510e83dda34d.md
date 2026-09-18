# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-09-18_equity_reit_v1@1.0_510e83dda34d`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-09-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers a ~6.8% trailing distribution yield from a diversified Singapore-and-Australia industrial/logistics portfolio, with DPU growing 2.5% in the nine months to December 2025. The recently completed Perth Hazelmere acquisition and new sustainability-linked loan facility signal active capital recycling. However, the S$2bn MDIP expansion, a concurrent equity fund raising, and the mid-tier AIMS Financial Group sponsorship introduce execution and dilution risk that tempers near-term conviction. Beta of 0.28 versus IASP.L (currency-basis caveat applies) indicates materially lower co-movement with the GBP-denominated APAC REIT benchmark, while a PGain of 74.9% from the OU Monte Carlo supports a moderate long position at a 12-month horizon.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1049
- P-gain: 0.7493
- CAPM alpha: 0.0562
- Beta: 0.2765
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy declines to below 91% as industrial demand softens amid global trade contraction and tariff escalation; DPU growth reverses to flat or negative; equity fund raising proceeds deployed into lower-yielding Australian assets at compressed cap rates; gearing rises toward 44–45% MAS limit constraining further capital deployment; perpetual securities distribution adds fixed-cost drag; multiple contracts 3.5% as market reprices Singapore mid-cap industrial REITs.
- **base**: E(R)=0.0710
  - Central case: annualised DPU yield of ~6.76% at current SGD 1.43 price, DPU growth 2.0% from continued rental reversions and Perth asset contribution, multiple contracts 1.7% due to equity dilution overhang and expanded MDIP. Occupancy stable at ~94–95%. Gearing comfortably below 45% with perpetual securities classified as equity.
- **bull**: E(R)=0.1800
  - Perth acquisition delivers 6%+ entry yield and accretive to DPU within 12 months; DPU growth accelerates to 3.5% driven by strong Singapore industrial rental reversions; sponsor expands pipeline with further Australian and Singapore assets at accretive terms; S-REIT sector re-rates as MAS signals rate easing; multiple expands +0.5%; new unsecured loan structure improves cost of debt.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info [override_applied=-1]
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0676 (Cat A) — 9M FY2026 DPU of S$0.0725 (April–December 2025) reported by Business Times on 5 Feb 2026; annualised to S$0.0967 at full-year run-rate, divided by closing price S$1.43 on 2026-09-18. Observed published distribution figure.
- `dpu_growth_rate` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a.: 9M DPU grew 2.5% YoY per Business Times Feb 2026 headline; trimmed to 2.0% to reflect near-term dilution from Aug 2026 equity fund raising (O5RU.SI 2026-08-05 ANNC). Sensitivity: bear 0%, bull 3.5%.
- `multiple_change` = -0.017 (Cat C) — Assumed -1.7% multiple contraction reflecting: (1) expanded Multicurrency Debt Issuance Programme from S$750M to S$2bn announced 2026-09-18 (O5RU.SI 2026-09-18 ANNC) increasing debt-capacity overhang; (2) dilutive equity fund raising with proceeds deployment in Australian industrial assets at entry yield uncertainty. Sensitivity: bear -3.5%, bull +0.5%.
- `gearing_level` = estimated_below_45pct (Cat B) — S$100M 4.25% subordinated perpetual securities issued Jun 2026 (O5RU.SI 2026-06-26 ANNC) are equity-classified under IFRS, which supports reported gearing headroom. New unsecured sustainability-linked loan and syndicated facility obtained May 2026 (O5RU.SI 2026-05-21 ANNC). Exact as-of gearing not available from truncated filings; estimated below 45% MAS threshold based on public statements around equity raising.
- `acquisition_pipeline` = Perth_Hazelmere_completed (Cat A) — Completion of acquisition of 398 Bushmead Road and 286 Stirling Crescent, Hazelmere, Perth Western Australia announced 2026-08-05 (O5RU.SI 2026-08-05 ANNC). Adds Australian industrial exposure; specific acquisition price and yield not available from headline alone.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. The currency basis between SGD and GBP introduces noise in the beta estimate that cannot be isolated from the underlying REIT co-movement. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Dilution risk from equity fund raising: proceeds deployed into Australian assets may be initially yield-dilutive pending rental ramp-up, compressing near-term DPU per unit.
- Gearing headroom narrows if Australian property valuations decline, reducing LTV buffer against the 45% MAS regulatory limit.
- Mid-tier sponsor concentration: AIMS Financial Group lacks the pipeline scale and balance-sheet depth of blue-chip Singapore REIT sponsors, limiting injection optionality.
- SGD interest rate and refinancing risk: expanded S$2bn MDIP may be drawn at higher credit spreads if Singapore risk-free rates remain elevated above 3.9%.
- Macro/calibration caveat: Phase 2 calibration is directional only; formal vintage backtest discipline arrives in Phase 5. Absence of intra-period macro series (FEDFUNDS, credit spreads) limits scenario modelling precision.

## Invalidation Condition
Exit the position if: (1) reported portfolio occupancy falls below 91% for two consecutive quarterly reporting periods; (2) annualised DPU coverage drops below 1.0x AFFO as disclosed in any half-year or full-year results; (3) aggregate leverage breaches 43% of total assets for two consecutive periods, signalling proximity to the MAS 45% regulatory threshold; or (4) AIMS Financial Group formally reduces its pipeline commitment or divests its stake in the REIT manager, removing the primary internalised acquisition channel.
