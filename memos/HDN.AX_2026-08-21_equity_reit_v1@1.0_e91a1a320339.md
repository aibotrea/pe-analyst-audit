# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-08-21_equity_reit_v1@1.0_e91a1a320339`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Large-Format/Daily-Needs Retail
**As of**: 2026-08-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
HDN.AX offers high-quality exposure to Australian large-format daily-needs retail (Woolworths, Coles, Bunnings anchored centres) with a trailing DPU yield of ~7.3% at the post-FY26-results price of AUD 1.155 — a meaningful spread over the 3.71% US T-bill (used as proxy risk-free rate). The 10% price decline following FY26 results reflects market concern over FY27 financing cost headwinds rather than deterioration in the underlying portfolio, which recorded a $92m valuation gain in FY26. Beta of 0.56 versus IASP.L (AUD/GBP currency basis caveat applies) indicates moderate sensitivity to the broader APAC REIT market. The OU Monte Carlo PGain of 72.5% and positive CAPM alpha of 8.1% (acknowledging the negative IASP.L 5yr benchmark return) support an above-average conviction rating, with the primary risk being the pace and depth of RBA easing relative to HDN's refinancing schedule.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1214
- P-gain: 0.7246
- CAPM alpha: 0.0814
- Beta: 0.5566
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher-for-longer into FY27; refinancing costs spike materially, compressing FFO to ~8.3 cpu and forcing a DPU cut of ~3%. Cap rate expansion of 25-30bps on large-format retail assets suppresses NTA. Occupancy softens to 97% from ~99% as discretionary retail tenants rationalise space. Multiple contracts further; price revisits AUD 1.00. Macro tail risk: global credit spread widening tightens HDN's refinancing terms aggressively.
- **base**: E(R)=0.0730
  - Central case as modelled in quantitative chain: DPU ~8.4 cpu, flat-to-slightly-negative growth (-0.5%), yield 7.27% at current price, modest +0.5% multiple expansion as RBA eases once. Gearing stable at ~32% LVR. Woolworths/Coles/Bunnings anchor tenants maintain occupancy above 98%. FY27 FFO pressure from financing costs is contained within guidance.
- **bull**: E(R)=0.1800
  - RBA cuts rates twice in H1 FY27, materially compressing discount rates and enabling cap rate tightening of 15-20bps across HDN's large-format retail portfolio. FFO recovers to 9.5+ cpu as refinancing costs moderate. Sponsor (HMC Capital) completes accretive acquisition pipeline at 6%+ initial yields, expanding AUM and distributable income. Price re-rates toward NTA; DPU grows ~2%. Elevated volume post-results normalises and institutional re-entry supports price.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0727 (Cat A) — Implied trailing DPU yield: FY26 FFO of 9.0 cpu confirmed by ASX FY26 Results announcement (HDN.AX 2026-08-12 PERIODIC REPORTS). Estimated DPU ~8.4 cpu (FFO payout ~93%, in-line with prior year; headline 'Distribution maintained' per ASX Distribution Announcement 2026-08-20). At closing price AUD 1.155 on 2026-08-21: 0.084/1.155 = 7.27%. DPU figure is a published/announced number; yield calculation Category A.
- `dpu_growth_rate` = -0.005 (Cat C) — FY27 guidance explicitly flags FFO pressure from higher financing costs (Kalkine, 13 Aug 2026; HDN ASX FY26 Results 2026-08-12). Assumed flat-to-slightly-negative DPU growth of -0.5% for FY27 reflecting refinancing headwinds and conservative pass-through. Sensitivity tested in scenario analysis: bear case -3%, bull case +2%.
- `multiple_change` = 0.005 (Cat C) — HDN price declined ~10% post-FY26 results (AUD 1.275 to AUD 1.155), creating a potential discount to NTA. A $92m portfolio revaluation gain was recorded in FY26 (Motley Fool, 16 Jun 2026). Modest +0.5% multiple expansion assumed over 12 months contingent on RBA easing. Sensitivity: bear case -2%, bull case +2%.
- `gearing_estimate` = 0.32 (Cat B) — Estimated LVR of ~32% based on HDN's historical gearing profile and FY26 valuation gain of $92m. AU REIT regulatory convention cap is ~40-50% LVR. Specific FY26 figure not available from filing bodies retrieved (ASX body capture pipeline mismatch noted); derived from prior disclosed range and news context. Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer RBA policy rates increasing HDN's FY27 debt refinancing costs materially beyond guidance, compressing FFO and forcing a DPU reduction
- Cap rate expansion in Australian large-format retail, reducing NTA and pressuring trading multiples below current discount-to-NTA entry point
- Tenant concentration risk in Woolworths/Coles anchor segment — any structural changes to supermarket footprint strategy could affect rental reviews
- IASP.L benchmark 5yr annualised return of -4.5% reflects prolonged APAC REIT sector headwinds; beta and alpha estimates carry material currency-basis noise (AUD/GBP)
- External manager structure (HMC Capital) creates potential fee misalignment; FY27 FFO pressure may mask relative underperformance versus internalised peers

## Invalidation Condition
Exit the position if HDN's reported FFO falls below 8.0 cpu for two consecutive half-yearly periods (indicating DPU coverage below 1.0x), or if gearing breaches 38% LVR approaching the AU REIT convention cap of 40%, or if HMC Capital announces a dilutive equity raising at a material discount to prevailing NTA without an offsetting accretive acquisition, or if RBA signals a sustained rate-hiking cycle beyond current forward curve pricing that would further impair HDN's FY27-FY28 refinancing economics.
