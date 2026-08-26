# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-08-26_equity_reit_v1@1.0_923bd910b71f`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Living Sector / Land Lease Communities
**As of**: 2026-08-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Ingenia Communities Group (INA.AX) is Australia's leading listed land-lease and lifestyle communities operator, with a growing pipeline of residential settlements providing structural long-duration income. The distribution yield of ~3.0% at current prices is below A-REIT peers, reflecting INA's capital-reinvestment model rather than a high-payout structure, but forward DPU growth of ~4.0% p.a. supports a total expected return of ~6.5%. The CAPM alpha of 8.3% versus a negative benchmark return is supportive; however, the proposed acquisition of Peet Limited announced on 2026-08-26 introduces material scheme execution risk, potential leverage uplift, and near-term EPS dilution that reduce near-term visibility. The OU Monte Carlo PGain of 64.5% and elevated annualised volatility of 25.5% (reflecting the acquisition event) support only a low conviction score of 2 at this juncture.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1732
- P-gain: 0.6446
- CAPM alpha: 0.0826
- Beta: 0.6702
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - PPC acquisition fails or is voted down by unitholders leading to deal break costs and prolonged strategic uncertainty; alternatively, deal completes but at a leverage level exceeding 42% LVR triggering a covenant breach or forced equity raise at a deep discount. RBA rate remains elevated above 4.0%, compressing A-REIT multiples by a further 10-15%. Land-lease settlement volumes decline 20% below plan due to housing affordability pressure. DPU cut of 10-15% as distribution coverage falls below 1.0x AFFO.
- **base**: E(R)=0.0640
  - Central case as built in quantitative chain: PPC acquisition completes on schedule (scheme vote H1 FY2027), deal is mildly dilutive in Year 1 but accretive by Year 2. INA maintains gearing below 38% LVR. DPU growth of 4.0% p.a. via land-lease completions and CPI rental escalations. Distribution yield of ~3.0% at current price plus 4.0% growth less 0.5% multiple compression = E(R) 6.5%. RBA cash rate holds stable.
- **bull**: E(R)=0.2200
  - PPC acquisition completes and is immediately accretive, adding 500+ land-lease lots and a significant masterplanned-community land bank at attractive yield-on-cost. Combined entity trades at a premium multiple as the market re-rates a scaled living sector platform. RBA begins rate cutting cycle, compressing cap rates and expanding A-REIT multiples. DPU growth accelerates to 6-7% p.a. as settlement volumes outperform. Occupancy across holiday park portfolio stabilises above 90%. Multiple expansion of +2% contributes alongside a ~3.5% yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.03 (Cat A) — FY2026 DPU estimated at approximately AUD 12.0 cents per unit (consistent with INA's publicly stated FY2026 guidance of delivery exceeding targets, per ASX announcement headline 'Continued Delivery Against Strategy - Guidance Exceeded' dated 2026-08-25). Yield computed at closing price of AUD 3.99 on 2026-08-26 = ~3.0%. INA's distribution yield is structurally lower than A-REIT peers given significant retention for land-lease development capex.
- `dpu_growth_3yr` = 0.04 (Cat C) — Forward DPU growth of 4.0% p.a. assumed over a 3-year horizon. Driven by: (1) land-lease settlement completions from pipeline of ~2,000+ homes across INA's development portfolio, (2) annual CPI-linked rental escalations on ground leases (~3-4% historically), and (3) partial offset from higher interest costs on drawn debt. Sensitivity tested in scenario analysis. Assumes PPC acquisition completes and is accretive on a per-unit basis by Year 2; if deal fails, organic growth assumption of ~3.5% applies.
- `multiple_change` = -0.005 (Cat C) — Modest multiple contraction of -0.5% assumed reflecting: (1) deal-related uncertainty following the proposed Peet Limited (PPC) acquisition announced 2026-08-26 via Scheme Implementation Deed, (2) higher-for-longer RBA rate environment compressing A-REIT multiples, and (3) market digestion of potential gearing uplift post-merger. Sensitivity: if deal fails or is voted down by INA unitholders, multiple could re-rate +1-2% on relief. If deal completes cleanly, multiple could stabilise at current levels.
- `ppc_acquisition_risk` = material (Cat B) — INA announced on 2026-08-26 a proposed acquisition of Peet Limited (ASX: PPC) via Scheme Implementation Deed to create a leading living sector platform (per ASX announcement 'PPC: Combination to Create a Leading Living Sector Platform'). The transaction introduces scheme execution risk, potential leverage uplift above the AU REIT convention threshold of 40% LVR if funded partly with debt, dilution risk if funded via equity at a discount, and integration risk across land-lease and masterplanned-community assets. Price fell ~6.4% on the day of announcement (from ~AUD 4.26 to AUD 3.99) on volume of 6.1M units.
- `gearing_level` = 0.32 (Cat B) — Pre-deal gearing estimated at ~32% LVR based on INA's publicly disclosed half-year and annual report history. INA has historically maintained gearing in the 28-35% range. Post-PPC acquisition, leverage may rise depending on deal consideration structure. Treated as Category B (derived from prior filings; FY2026 full balance sheet not yet captured in filing body).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- PPC acquisition execution risk: scheme vote failure, deal break costs (~AUD 15-30M estimated), or completion at gearing levels approaching/exceeding the 40% LVR AU REIT convention, potentially requiring a discounted equity raise.
- Higher-for-longer RBA rates compressing A-REIT multiples and increasing INA's weighted average cost of debt on refinancing of ~AUD 700-900M of total facilities.
- Land-lease settlement volume shortfall if housing affordability deteriorates or construction cost inflation re-accelerates, delaying DPU growth.
- Holiday-park portfolio softness (INA Holidays segment) in a consumer spending downturn, reducing operating cash flows from the tourism/lifestyle accommodation segment.
- Post-merger integration risk: Peet's masterplanned community business model is strategically adjacent but operationally distinct from INA's land-lease model, creating potential cultural and operational friction.

## Invalidation Condition
Exit if INA's post-acquisition pro-forma gearing exceeds 42% LVR for two consecutive reporting periods, or if the PPC scheme is voted down and management pursues an alternative acquisition that further stretches the balance sheet without unitholder approval, or if DPU is cut by more than 10% from the FY2026 declared level and distribution coverage falls below 0.95x AFFO on a trailing twelve-month basis for two consecutive half-year periods.
