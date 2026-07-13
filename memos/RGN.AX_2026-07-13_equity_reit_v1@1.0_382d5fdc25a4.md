# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-07-13_equity_reit_v1@1.0_382d5fdc25a4`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Neighbourhood
**As of**: 2026-07-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group is Australia's largest pure-play neighbourhood and sub-regional retail REIT, anchored by defensive grocery tenants (Woolworths, Coles, ALDI) that provide essential-services resilience throughout economic cycles. A trailing distribution yield of approximately 5.9% at AUD 2.37 offers a meaningful 220bps spread over the 3.71% T-bill rate, supported by CPI-linked rent reviews. Beta of 0.45 against IASP.L (currency-basis caveat applies) indicates below-market systematic risk, while the OU Monte Carlo generates a simulated 12-month return of 6.9% with a PGain of 75.9%, supporting above-average conviction. Internal management structure eliminates external fee drag, aligning manager incentives with unitholders.

## Quantitative Chain

- E(R): 0.0690
- Std dev: 0.0975
- P-gain: 0.7591
- CAPM alpha: 0.0669
- Beta: 0.4479
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA maintains restrictive policy, cap rates expand 30-40bps compressing NTA, occupancy softens to 96% from high-90s, DPU cut 5-8% as tenants request rent relief; AUD/GBP rate shock further amplifies benchmark divergence. Distribution coverage falls toward 0.95x AFFO.
- **base**: E(R)=0.0690
  - Central case as built: DPU yield 5.9%, DPU growth 1.5%, multiple change -0.5%, gearing ~33%, occupancy stable in high-90s% anchored by Woolworths/Coles. RBA eases modestly through FY27.
- **bull**: E(R)=0.1700
  - RBA delivers 2-3 rate cuts, cap rates compress 20bps lifting NTA, accretive acquisitions from neighbourhood retail pipeline at 6%+ entry yields, DPU growth accelerates to 3-4%, re-rating toward 5.5% yield implied price ~AUD 2.55+.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.059 (Cat A) — Annualised DPU estimated at ~AUD 0.140/unit based on observed ex-distribution price drop (~AUD 0.07 half-year) around 23-Jun-2026 and FY26 Final Distribution headline filing (RGN.AX 2026-06-16 PERIODIC REPORTS). At current price AUD 2.37, yield = 5.9%. Filing body unavailable (ASX Phase 01 v3.3 §4); DPU quantum is inferred from ex-date price action and prior-year DPU of ~14.0 cpu.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed: CPI-linked rent reviews on Woolworths/Coles-anchored neighbourhood retail leases typically track CPI at 2-3% with occupancy cost constraints, moderated by modest cap rate sensitivity. Sensitivity tested in scenario analysis. No filing body available to verify forward guidance.
- `multiple_change` = -0.005 (Cat C) — Multiple contraction of -0.5% assumed reflecting RBA tightening cycle and higher-for-longer AUD rate environment persisting into FY27, creating modest headwind to REIT multiple expansion. Category C model assumption.
- `gearing_estimate` = 0.33 (Cat B) — Gearing estimated at ~33% based on sector convention for Australian neighbourhood retail REITs and publicly available prior-year disclosures. Regulatory limit for Australian REITs is <40% by AREIT convention. Filing body unavailable to confirm exact as-of figure; estimate based on publicly known sector range.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Higher-for-longer RBA policy rate compressing the yield spread and prompting cap rate expansion across Australian retail property, with filing body unavailable to confirm exact current gearing
- Tenant concentration in major grocery anchors (Woolworths, Coles) creates binary risk if either anchor renegotiates lease terms or exits at renewal
- IASP.L GBP-denominated benchmark introduces AUD/GBP FX basis noise into beta and alpha calculations; true systematic risk may differ from computed 0.45
- ASX filing body capture unavailable (Phase 01 v3.3 §4) — DPU quantum, AFFO coverage, and exact gearing ratio are inferred rather than confirmed from primary filing text
- Calibration limitation: Phase 2 calibration is directional only; vintage discipline arrives in Phase 5 — conviction score should be treated as indicative, not back-tested

## Invalidation Condition
Exit position if occupancy falls below 97% for two consecutive half-year periods, or if annualised DPU is cut more than 5% below AUD 0.140 per unit, or if gearing breaches 38% of total assets, or if a major anchor tenant (Woolworths or Coles) gives formal notice of non-renewal affecting more than 10% of portfolio income.
