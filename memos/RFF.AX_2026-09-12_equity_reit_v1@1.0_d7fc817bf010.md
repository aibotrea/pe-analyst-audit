# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-09-12_equity_reit_v1@1.0_d7fc817bf010`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agricultural/Farmland
**As of**: 2026-09-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Rural Funds Group is Australia's only listed pure-play agricultural REIT, providing AUD-denominated exposure to diversified farmland assets across cattle, almonds, macadamia nuts, cotton, and grapes under a long-WALE (~11.5 years) triple-net lease structure that provides structural income stability. At AUD 1.945 per unit, the implied trailing distribution yield of approximately 5.9% offers a meaningful spread over the current risk-free rate, while the unit price appears to trade at a discount to underlying farmland NAV. Beta of 0.50 versus IASP.L (currency-basis caveat: coefficient absorbs AUD/GBP FX co-movement) reflects moderate co-movement with the broader APAC REIT universe. The OU Monte Carlo yields a simulated 12-month return of 8.34% with PGain of 73.6%, supporting a Moderate conviction score of 3 (post one-step gate override for AFFO coverage concerns), and a maximum position size of 5.0%.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.1324
- P-gain: 0.7355
- CAPM alpha: 0.0896
- Beta: 0.4982
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds rates higher for longer, compressing yield spread; AFFO coverage falls below 1.0x requiring a 10-15% DPU cut; rural land cap rates expand 50bps driving NAV decline of 7-10%; agricultural commodity softness (almonds, beef) weakens tenant covenant; tail-risk rate shock with Australian 10-year bond yields rising to 5.5%+ triggers further de-rating.
- **base**: E(R)=0.0830
  - Central case as built in quantitative chain: distribution yield 5.9%, DPU growth 2.0%, multiple expansion +0.5%, gearing stable at ~33%, WALE ~11.5 years; RBA begins gradual rate normalisation in H1 2027 providing modest support to land valuations.
- **bull**: E(R)=0.2000
  - RBA delivers 75-100bps of cuts over 12 months compressing cap rates; unit price re-rates toward implied NAV of AUD 2.20-2.30; DPU growth recovers to 3.5-4.0% on CPI-linked escalators; strong agricultural commodity prices (almonds, beef, cotton) improve tenant covenant quality and support asset revaluation gains.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.059 (Cat A) — Trailing DPU estimate of approximately 11.48 cents per unit for FY2026, divided by current unit price of AUD 1.945 (ASX close 2026-09-11), implying a distribution yield of ~5.9%. Two distribution announcements filed: RFF.AX 2026-08-31 DISTRIBUTION ANNOUNCEMENT and 2026-07-30 Update - Dividend/Distribution - RFF (filing bodies unavailable due to ASX pipeline contamination; yield derived from price and consensus DPU knowledge).
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth set at 2.0% p.a., conservative relative to RFF's historical 4% CPI-linked rent escalation mechanism. Reduced from historical guide following SimplyWallSt market commentary (22 Aug 2026) noting AFFO stalling — indicating higher financing costs are absorbing the benefit of rent escalations. Sensitivity tested across bear/base/bull scenarios.
- `multiple_change` = 0.005 (Cat C) — Modest positive multiple re-rating of +0.5% assumed as RFF currently trades at an estimated discount to NAV (implied farmland NAV ~AUD 2.20-2.30 based on historical independent land valuations). Dependent on RBA rate trajectory and investor risk appetite for illiquid agricultural assets.
- `gearing_ratio` = 0.33 (Cat B) — Estimated look-through gearing of approximately 33% derived from prior-period balance sheets. Within Australian REIT convention threshold of <40%. Classified Category B as FY2026 audited figure not confirmed — ASX filing bodies returned pipeline-contaminated content and could not be relied upon for financial data extraction.
- `wale_years` = 11.5 (Cat B) — Weighted average lease expiry estimated at ~11.5 years based on RFF's historical disclosure pattern of long-term agricultural leases. Long-WALE profile provides structural income visibility. Category B as exact FY2026 WALE not confirmed from filing bodies (pipeline returned off-topic documents).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- AFFO stagnation: Market commentary (Aug 2026) flags AFFO stalling — higher floating-rate financing costs and operating expenses may compress distribution coverage below 1.0x, risking a DPU cut and negative unit price re-rating.
- Interest rate sensitivity: Long-duration farmland assets are structurally exposed to cap rate expansion; a 25bps rise in rural land capitalisation rates could reduce NAV by 3-5%, extending the discount to market price.
- Agricultural commodity and weather risk: Tenant income and lease covenant quality are indirectly exposed to soft commodity price cycles, drought severity, and La Niña/El Niño patterns across Australian farming regions.
- Related-party manager conflict: Rural Funds Management (RFM) also manages the tenant entities that lease farmland from RFF, creating a structural related-party dynamic that requires ongoing monitoring for non-arm's-length transactions.
- Filing data gap: ASX filing body pipeline returned contaminated (off-topic) documents for RFF.AX during this analysis cycle; FY2026 audited financial data (exact gearing, WALE, AFFO coverage) could not be confirmed from primary source filings, increasing reliance on Category B and C estimates.

## Invalidation Condition
Exit position if RFF.AX reports AFFO distribution coverage below 1.0x for two consecutive half-year reporting periods, or announces a formal DPU reduction exceeding 5% from the current annualised level, or if the ASX-disclosed gearing ratio breaches 40% (the Australian REIT regulatory convention threshold), or if Rural Funds Management announces any related-party asset acquisition priced materially above independent valuation without formal unitholder approval at a properly convened general meeting.
