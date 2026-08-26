# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-26_equity_reit_v1@1.0_11711eeb5037`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers a high nominal yield (~7.3%) anchored in long-WALE data centre leases with hyperscaler tenants, supported by a world-class sponsor in Digital Realty Trust. The AI and cloud computing secular tailwind underpins data centre demand across Asia-Pacific, and the announced pivot from North American to Singapore and Japan assets improves geographic alignment with growth markets. However, the 12-month investment horizon coincides with a significant portfolio transformation — a USD 315.9M North America divestment alongside simultaneous Asia acquisitions — introducing transitional DPU uncertainty and execution risk that suppresses near-term conviction. The active unit buy-back programme (cancelling approximately 2 million units daily since April 2026) provides meaningful DPU-per-unit accretion and signals management confidence; PGain of 69.4% and positive CAPM alpha (0.074) support a directional long stance, but elevated annualised volatility (23.8%) and single-step downward gate override for asset concentration during transition warrants a low conviction score of 2 with a 3% maximum position.

## Quantitative Chain

- E(R): 0.0830
- Std dev: 0.1619
- P-gain: 0.6943
- CAPM alpha: 0.0739
- Beta: 0.3433
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - North America asset sale falls through or completes at material discount to book value, forcing leverage above 45% MAS limit. Asia acquisitions yield sub-5% NPI, triggering a DPU cut of 15-20%. Cap rate expansion of 50bps across Asia data centres driven by sustained higher-for-longer Fed funds rate and UST 10-year above 5.5%. Occupancy in retained portfolio dips to 90% on hyperscaler non-renewal. Rate shock scenario embedded in this pathway.
- **base**: E(R)=0.0820
  - Central case as built in quantitative chain: trailing yield 7.3%, DPU growth 2.0%, multiple contraction -1.0%. North America divestment completes on disclosed terms by Q4 2026. Singapore and Japan acquisitions stabilise at 6%+ NPI yield. Occupancy maintained above 95% on long-WALE hyperscaler leases. Unit buy-back programme continues to support per-unit DPU accretion.
- **bull**: E(R)=0.2200
  - Asia acquisitions prove immediately accretive at 7%+ NPI yield, triggering DPU upgrade. Fed begins rate-cutting cycle, compressing discount-to-NAV from 30% to 15% and driving multiple re-rating of 8-10%. Digital Realty Trust injects additional Asia pipeline assets. DPU growth accelerates to 5% on AI hyperscaler demand surge for Singapore and Tokyo colocation. Unit buy-back reduces unit count by 5% over 12 months, amplifying per-unit DPU.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.073 (Cat A) — Implied trailing distribution yield estimated at approximately 7.3% based on annualised DPU of ~USD 0.037 per unit against observed closing price of USD 0.51 on 2026-08-26. DPU sourced from publicly reported quarterly distributions. Category A given observed price and published DPU figures; yield is sensitive to near-term DPU trajectory during portfolio transition.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumed at 2.0% p.a. reflecting AI/cloud demand tailwinds for data centre assets offset by near-term uncertainty from portfolio transformation (USD 315.9M North America asset sale and simultaneous entry into Singapore and Japan markets announced August 12, 2026). Conservative estimate pending confirmation of acquisition yield and transition cash flows. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Multiple contraction assumption of -1.0% reflecting near-term transition risk premium as DCRU pivots from a US-centric portfolio to Asia-Pacific. DCRU trades at a material discount to NAV (estimated 25-35% based on sector comparables); while rerating potential exists if rates ease, execution risk on the North America divestment and Asia acquisition introduces cap-rate uncertainty in the 12-month horizon. Sensitivity tested in scenario analysis.
- `unit_buyback_programme` = active (Cat A) — DCRU conducting daily open-market unit repurchases and cancellations since April 15, 2026, with mandate for up to 129,602,591 units. Daily buyback of approximately 2,000,000 units confirmed from DCRU.SI SGX filings dated 2026-08-18 through 2026-08-21. Accretive to per-unit DPU as units are cancelled. Treated as positive management-alignment signal.
- `portfolio_transformation` = in_progress (Cat A) — USD 315.9M North America asset divestment and concurrent acquisition of Singapore and Japan data centres announced August 12, 2026 (Business Times). Introduces transitional risk: gap period between asset sale and new asset stabilisation, potential leverage and DPU impact during settlement. Category A as publicly disclosed corporate event.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU.SI trades and distributes in USD while listed on SGX). Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Portfolio transition execution risk: simultaneous North America disposal (USD 315.9M) and Asia acquisition could create a DPU gap if settlement timelines diverge or if Asia asset yields disappoint relative to underwriting assumptions.
- Higher-for-longer US interest rates sustaining wide spreads between cap rates and cost of debt, suppressing the discount-to-NAV re-rating catalyst and increasing refinancing costs on any floating-rate debt.
- Tenant concentration risk: data centre assets are typically single-tenanted per facility with hyperscaler counterparties; a non-renewal by a top-3 tenant (Google, Microsoft, or equivalent) would materially impair occupancy and DPU.
- Currency basis risk: DCRU distributes in USD and Japan assets introduce JPY-denominated operating costs; JPY depreciation versus USD reduces Japan NPI contribution in USD terms and may widen leverage ratios measured at the REIT level.
- Macro data coverage gap: FRED supporting series (credit spreads, yield-curve signals) used as secondary macro overlay were not available for this as_of date; their absence reduces macro-scenario confidence and is disclosed as a limitation per Phase 2 calibration constraints.

## Invalidation Condition
Exit position if aggregate leverage exceeds 42% of deposited property value for two consecutive quarters following the North America divestment and Asia acquisition settlement, signalling post-transaction balance sheet stress; or if DPU is cut by more than 15% from the most recently declared quarterly level without a corresponding accretive acquisition announcement offsetting cash flow; or if Digital Realty Trust reduces its sponsor stake below 20% or formally withdraws pipeline commitment to DCRU; or if occupancy across the retained Asia-Pacific portfolio falls below 92% for two consecutive reporting periods.
