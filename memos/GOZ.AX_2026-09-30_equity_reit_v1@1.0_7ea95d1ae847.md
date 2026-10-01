# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-09-30_equity_reit_v1@1.0_7ea95d1ae847`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Office/Industrial
**As of**: 2026-09-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Growthpoint Properties Australia offers a high observed distribution yield of ~9.3% (18.4c FY26 DPU at AUD 1.98), providing a substantial spread over the RBA cash rate (4.35%) and 3-month T-bill (4.07%), with FY26 profit rebounding and portfolio occupancy rising. Beta of 0.58 versus IASP.L (currency-basis caveat applies) indicates moderate market sensitivity, while the OU Monte Carlo produces a 12-month simulated return of ~10.2% with PGain of 78.4%, supporting a moderate conviction thesis. The primary risk is structural: GOZ's heavy office weighting exposes it to ongoing hybrid-work demand headwinds across Australian CBDs, contributing to the persistent discount to NTA and justifying a one-step qualitative override on asset quality concentration. The conviction score of 3 reflects the attractive income proposition balanced against sector-specific uncertainty and the absence of a sponsor pipeline to support external growth.

## Quantitative Chain

- E(R): 0.1029
- Std dev: 0.1305
- P-gain: 0.7835
- CAPM alpha: 0.1138
- Beta: 0.5838
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Occupancy falls below 88% as hybrid-work adoption accelerates and multiple CBD anchor tenants opt out at lease expiry. DPU cut by ~15% to ~15.6c, AFFO coverage drops below 1.0x. Cap rates expand 50bps on office assets, driving NTA write-downs of 10–15% and pushing gearing above 40%. RBA holds rates elevated, the yield-spread compression eliminates income premium. Multiple contracts further, generating a total return of approximately -8% including the reduced distribution.
- **base**: E(R)=0.1030
  - Central case as built in the quantitative chain: FY27 DPU grows modestly to ~18.6c (+1%), portfolio occupancy stabilises around current levels, cap rates flat, gearing within the 35–40% range. Distribution yield of ~9.3% dominates total return with near-zero multiple change. OU Monte Carlo sim return of 10.2% with 78.4% PGain.
- **bull**: E(R)=0.2200
  - RBA cuts rates by 75–100bps, compressing the risk-free rate and triggering AREIT re-rating. Office occupancy improves to 93%+ as flight-to-quality drives demand for GOZ's premium-grade assets. DPU growth of ~3% supported by positive leasing spreads. Discount to NTA narrows by 10–15%, adding a capital return component to the ~9.3% income yield, producing a total return of approximately 22%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0929 (Cat A) — FY26 DPU of 18.4c (matched published guidance per Motley Fool Australia, 22 Jun 2026) divided by observed ASX closing price of AUD 1.98 on 2026-09-30. Both DPU and price are Category A observed public data.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. assumed. GOZ is a predominantly office-focused AREIT with portfolio occupancy rising per FY26 results (Motley Fool, 17 Aug 2026) but structural headwinds from hybrid work persist in Australian CBD offices. Growth reflects modest organic rental reversion and limited AUM expansion; sensitivity tested in scenario analysis (bear: -1%, bull: +3%).
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumed. GOZ trades at a material discount to NTA (market-implied yield of ~8.3–9.3% per Kalkine, Jun–Sep 2026 headlines), reflecting structural office sector uncertainty. No near-term catalyst identified for discount compression. Sensitivity tested in scenario analysis.
- `rba_policy_rate` = 4.35 (Cat A) — RBA cash rate target 4.35% per BIS CBPOL_AU, observation date 2026-09-17 (age 13 days). Governs Australian refinancing cost and yield-spread context.
- `fy26_dpu_actuals` = 0.184 (Cat A) — GOZ FY26 DPU of 18.4 cents per unit, matching full-year guidance, per Motley Fool Australia (22 Jun 2026) and Kalkine (31 Jul 2026). FY26 profit rebounded with rising portfolio occupancy (Motley Fool, 17 Aug 2026).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Structural office demand weakness from hybrid-work adoption, sustaining or widening the discount to NTA and suppressing capital returns
- Higher-for-longer RBA rates compressing the yield spread and increasing refinancing costs on floating-rate debt tranches
- Tenant concentration risk in top CBD office assets; loss of a major tenant could materially reduce occupancy and DPU coverage below 1.0x AFFO
- Valuation write-downs on office assets driving NTA erosion and covenant pressure on gearing ratios if cap rates expand further
- GOZ is internally managed with no external sponsor pipeline; limited inorganic growth levers compared to sponsor-backed AREITs

## Invalidation Condition
Exit position if: (1) GOZ portfolio occupancy falls below 88% for two consecutive reporting periods, signalling accelerating tenant attrition in CBD office assets; (2) gearing ratio breaches 40% (Australian REIT convention limit) following asset revaluations; (3) FY27 DPU guidance is cut by more than 10% from the FY26 18.4c baseline, indicating AFFO coverage deterioration; or (4) a major anchor tenant representing more than 5% of income elects not to renew at lease expiry.
