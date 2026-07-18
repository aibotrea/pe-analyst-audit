# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-07-17_equity_reit_v1@1.0_7a9b2bc6d936`
**Ticker**: BWP.AX (BWP Trust)
**Market**: Australia
**Sector**: Retail/Bulky Goods (Bunnings Warehouse)
**As of**: 2026-07-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP Trust offers a highly defensive, income-oriented exposure to Australian large-format retail real estate through an effectively single-tenant portfolio of Bunnings Warehouse properties. The trailing distribution yield of ~4.7% at AUD 3.92 is supported by long-dated triple-net leases with CPI-linked rent reviews, and the trust's gearing of ~32% is comfortably within Australian REIT regulatory norms. CAPM alpha of 6.3% versus the IASP.L benchmark (Category B, currency-basis caveat applies) reflects the trust's strong income profile relative to APAC REIT peers, with a 12-month PGain of 74.8% from the OU Monte Carlo. Conviction is held at Moderate (3/5) due to extreme single-tenant concentration — Bunnings accounts for over 97% of rental income — which represents an idiosyncratic risk not fully captured by beta or the broader REIT universe comparison.

## Quantitative Chain

- E(R): 0.0670
- Std dev: 0.0996
- P-gain: 0.7479
- CAPM alpha: 0.0632
- Beta: 0.4665
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Bunnings/Wesfarmers terminates or does not renew leases on a meaningful portion of properties (5-10%), driving occupancy below 95% and DPU cut of 10-15%. Cap rate expansion of 50bps as RBA rate cut cycle reverses or global risk-off event hits AUD property valuations. Negative property revaluations erode NTA. Price declines toward AUD 3.40. This scenario also captures a macro stagflation pathway where RBA is forced to re-tighten while retail spending weakens.
- **base**: E(R)=0.0670
  - Central case as built: DPU growth 2.0% via CPI-linked rent reviews, occupancy remains ~99%, gearing stable at ~32%, cap rates flat, price returns anchored to distribution yield of ~4.7% plus modest growth.
- **bull**: E(R)=0.1800
  - RBA easing cycle accelerates, driving cap rate compression of 25-50bps and meaningful NTA uplift. Wesfarmers exercises Bunnings expansion pipeline adding new properties at accretive yields. FY2026 DPU upgrades to ~19 cpu. Unit price re-rates toward AUD 4.30-4.40 on yield compression.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0467 (Cat A) — Trailing DPU ~18.33 cpu (FY2025 actuals, consistent with BWP Trust's published distribution history) divided by current price AUD 3.92 (observed 2026-07-17). Body of June 2026 distribution announcement (BWP.AX 2026-06-23 DISTRIBUTION ANNOUNCEMENT) unavailable — ASX body capture failed; yield estimate based on prior-year actuals pending FY2026 full-year results briefing announced 2026-07-02.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflecting CPI-linked rent reviews embedded in Bunnings triple-net leases. BWP has historically delivered modest but consistent DPU growth of ~1.5-2.5% p.a. Sensitivity tested in scenario analysis. A property revaluation gain was noted in June 2026 announcement (body unavailable), which may support modest asset base growth but not necessarily higher distributions.
- `multiple_change` = 0.0 (Cat C) — Assumed flat cap-rate/multiple environment over the 12-month horizon. BWP trades at a premium to NTA historically given lease quality; modest property revaluation gains (June 2026 announcement) provide mild support. Neutral assumption consistent with RBA easing cycle partially offsetting global rate uncertainty.
- `single_tenant_concentration` = disclosed (Cat A) — Bunnings Warehouse (Wesfarmers subsidiary) accounts for >97% of BWP Trust rental income across approximately 80 properties. This is a structural characteristic of the trust, observable from published annual reports. Wesfarmers holds ~24% of BWP units as anchor unitholder.
- `gearing_ratio` = 0.32 (Cat B) — Estimated gearing ratio ~30-33% based on BWP Trust's historically reported balance sheet. Full FY2026 balance sheet data pending annual results briefing (announced 2026-07-02). Body of relevant filings unavailable from ASX pipeline. Estimate derived from prior period actuals; within AU REIT convention of <40%.
- `rba_policy_rate` = not_available (Cat C) — RBA cash rate data not available from stored APAC rates on this as_of date. As of mid-2026, consensus indicates RBA has been in an easing cycle from 4.35% peak; estimated current cash rate ~3.85-4.10%. Risk-free rate anchored to US 3M T-bill (3.70%) as disclosed proxy. AUD rate differential is a secondary input only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP noise. The beta of 0.467 reflects BWP's relatively defensive, single-tenant lease profile versus the broader APAC REIT universe.

## Key Risks
- Single-tenant concentration: Bunnings/Wesfarmers accounts for >97% of rental income; any lease non-renewal, renegotiation at lower rents, or Wesfarmers strategic pivot would have a severe impact on DPU
- Cap rate expansion risk: if the RBA easing cycle stalls or reverses, property valuations could decline, depressing NTA and increasing effective gearing
- Limited growth optionality: BWP's growth is almost entirely dependent on Bunnings' expansion appetite; organic DPU growth beyond CPI is structurally constrained
- FY2026 full-year results pending: June 2026 distribution announcement body was unavailable; actual DPU and gearing figures for FY2026 are unconfirmed at this as_of date — results briefing scheduled imminently
- AUD/GBP currency basis in beta calculation: beta of 0.467 vs IASP.L absorbs FX noise; true property market beta may differ materially from computed figure (Category B caveat)

## Invalidation Condition
Exit if Bunnings/Wesfarmers announces non-renewal or early termination of leases covering more than 5% of portfolio GLA, or if BWP's reported gearing exceeds 38% for two consecutive reporting periods, or if FY2026 DPU is reported materially below 17.5 cpu implying a distribution cut of more than 5% from FY2025 actuals, or if Wesfarmers reduces its unitholding below 15% signalling reduced strategic commitment to the trust.
