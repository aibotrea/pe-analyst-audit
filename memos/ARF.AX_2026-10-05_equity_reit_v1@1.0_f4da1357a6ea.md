# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-10-05_equity_reit_v1@1.0_f4da1357a6ea`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Social Infrastructure / Childcare
**As of**: 2026-10-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Arena REIT trades at a deeply discounted A$1.985 following the Edge Early Learning tenant default shock in August 2026, representing a ~39.5% drawdown from July 2026 levels. The current implied distribution yield of approximately 6.8% is attractive relative to the RBA cash rate (4.35%), and management has reaffirmed FY2026 DPU guidance following containment of the Edge dispute. However, high annualised volatility (34.4%) and significant tenant concentration risk in a single childcare sub-sector warrant a cautious position size. The OU Monte Carlo PGain of 66.1% and positive CAPM alpha of 12.1% support a speculative recovery thesis, but the asset_quality_concentration gate failure limits conviction to Level 2 (Low), reflecting the still-elevated risk of further operator defaults or distribution cuts.

## Quantitative Chain

- E(R): 0.0980
- Std dev: 0.2335
- P-gain: 0.6610
- CAPM alpha: 0.1212
- Beta: 0.6745
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2500
  - Edge Early Learning default escalates (further tenants vacate or additional operators default), DPU cut by 20-25%, occupancy falls materially, management forced into dilutive equity raise at distressed price, cap rate expansion of 75bps. RBA holds rates elevated (4.35%+), compressing yield spread further. Multiple re-rates to historical distressed levels, implying unit price A$1.40-1.60.
- **base**: E(R)=0.0970
  - Central case as built in chain: Edge default contained, FY2027 DPU ~13.5c (yield 6.8%), DPU growth 1.0%, 2.0% modest multiple reversion. Occupancy broadly maintained across non-Edge portfolio. RBA begins easing cycle, providing modest tailwind. Price stabilises around A$2.00-2.20.
- **bull**: E(R)=0.3500
  - Edge portfolio rapidly re-tenanted at market rents, DPU reinstated to prior FY2025 run-rate (~15c), cap rate compression on RBA easing, price recovers to A$2.50-2.80. Board renewal and AMIT regime adoption improve governance premium. Sector re-rating as childcare demand fundamentals (government funding, population growth) reassert. Multiple reversion to 50% of pre-shock level.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.068 (Cat B) — Estimated FY2027 DPU of ~A$0.135/unit at current price A$1.985, implying 6.80% forward yield. ARF reaffirmed FY2026 guidance following containment of Edge Early Learning default (Kalkine/Investing.com, Aug 2026). DPU estimate is conservatively reduced from FY2025 run-rate (~15.4c) to reflect ongoing Edge portfolio transition. Filing bodies for ARF.AX were unavailable due to ASX body-capture pipeline cross-contamination; estimate sourced from news synthesis.
- `dpu_growth_3yr` = 0.01 (Cat C) — Assumed DPU growth of 1.0% pa reflecting conservative portfolio outlook post Edge default. Arena REIT's childcare centres carry CPI-linked rent reviews, but tenant credit stress constrains upside. Sensitivity tested in scenario analysis. Basis: analyst judgement; no direct filing confirmation available.
- `multiple_reversion` = 0.02 (Cat C) — Assumed 2.0% one-year positive price reversion from post-shock level (A$1.985 vs pre-shock ~A$3.28, a ~39.5% de-rating). Partial reversion assumed as the Edge dispute is contained and guidance reaffirmed. Highly uncertain; tested in bear/bull scenarios. Assumes no further tenant defaults or equity raises.
- `edge_default_containment` = disclosed (Cat B) — Arena REIT issued default notices to Edge Early Learning in August 2026 (ASX DISTRIBUTION ANNOUNCEMENT, ARF.AX, 2026-09-21). Multiple news sources (Kalkine, Investing.com, Aug-Sep 2026) confirm management 'contained' the default and reaffirmed FY2026 DPU guidance. The tenant dispute represents the primary idiosyncratic risk and has materially repriced the unit. Filing body capture for ASX failed to deliver ARF-specific content; news synthesis used.
- `rba_policy_rate` = 0.0435 (Cat A) — RBA cash rate target 4.35% as at observation date 2026-09-24, sourced from BIS WS_CBPOL (age 11 days). Informs Australian rate environment context for yield spread analysis.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP currency basis. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Edge Early Learning default escalation: further tenants fail to pay rent, default spreads to other childcare operators in the portfolio, triggering additional DPU cuts and potential equity raises at distressed prices.
- Higher-for-longer RBA rates (4.35% cash rate) compressing the AUD yield spread and increasing refinancing costs, with ARF's floating-rate debt exposure elevating interest cover pressure.
- Sector concentration: ARF's ~95%+ allocation to early learning / childcare centres leaves it highly exposed to a single sub-sector — government childcare policy changes or operator funding cuts could simultaneously impair multiple tenants.
- Cap rate expansion driven by persistent inflation and higher-for-longer global rates could further compress NAV, making any equity raise more dilutive.
- Filing body data unavailability (ASX pipeline cross-contamination) means DPU, gearing, WALE, and AFFO coverage ratios are estimated from news synthesis rather than directly observed filings, increasing category-B/C input uncertainty.

## Invalidation Condition
Exit if any of the following occur: (1) Arena REIT announces a formal DPU reduction exceeding 15% from the reaffirmed FY2026 guidance level, indicating the Edge containment has failed; (2) a second material tenant default is announced across the childcare portfolio within the next two quarters; (3) gearing rises above 35% LVR (approaching the Australian REIT convention limit of 40%) due to asset devaluations or drawdowns; (4) management announces a discounted equity raise at below A$1.80/unit, signalling balance sheet stress.
