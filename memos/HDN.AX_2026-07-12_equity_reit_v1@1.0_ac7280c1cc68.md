# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-07-12_equity_reit_v1@1.0_ac7280c1cc68`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Retail - Neighbourhood/Daily Needs
**As of**: 2026-07-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
HomeCo Daily Needs REIT offers AUD-denominated exposure to necessity-based retail (neighbourhood centres anchored by Woolworths, Coles and pharmacy/healthcare tenants) at a trailing distribution yield of 6.57%, representing a meaningful spread over the 3.69% 3-month T-bill rate. The June 2026 $92M gross valuation gain affirms ongoing asset quality and supports NAV, while the DRP issue price announcement in July 2026 confirms distribution continuity. With an OU Monte Carlo PGain of 74.8% and a positive CAPM alpha of 8.3% (acknowledging the AUD/GBP currency basis in the IASP.L benchmark), the quantitative chain supports an above-average conviction. The daily needs retail sub-sector exhibits structural resilience underpinned by non-discretionary spending patterns, insulating HDN from cyclical retail pressures better than discretionary mall REITs.

## Quantitative Chain

- E(R): 0.0757
- Std dev: 0.1127
- P-gain: 0.7476
- CAPM alpha: 0.0834
- Beta: 0.5629
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA pauses easing or re-hikes, driving cap rate expansion of 40-50bps and a 5-8% decline in NTA; DPU cut by 8-10% as AFFO coverage falls below 1.0x amid higher interest costs on refinancing; occupancy slips to 96% on specialty tenant attrition; AUD depreciation adds pressure on any foreign-currency debt facilities. This scenario also captures a stagflation or global credit shock pathway where higher-for-longer rates globally reprice Australian property cap rates sharply.
- **base**: E(R)=0.0757
  - Central case as modelled: distribution yield 6.57%, DPU growth 1.5% p.a. from CPI-linked escalations, mild cap rate headwind -0.5%; occupancy stable at ~99%; RBA continues measured easing cycle; gearing stays below 37%; valuation gains modest but positive.
- **bull**: E(R)=0.1800
  - RBA cuts accelerate, compressing cap rates by 25-30bps and driving 8-10% NTA uplift beyond the June 2026 valuation gain; DPU growth of 3-4% on strong rent review outcomes; HomeCo sponsor injects accretive pipeline assets at sub-6% cap rates; market re-rates neighbourhood/daily needs REIT sector to a tighter yield premium.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0657 (Cat A) — Trailing distribution yield of 6.57% sourced from Kalkine/market analysis (15 Jun 2026) consistent with ASX distribution announcement HDN 15-Jun-2026. At the observed price of AUD 1.275 (2026-07-10), this implies annualised DPU of approximately AUD 0.0838. DRP issue price announced 9 Jul 2026 confirms distribution continuity.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed. Daily needs centres carry CPI-linked rent reviews (typical 3-4% fixed or CPI-linked escalations on leases to Woolworths, Coles and specialty tenants); however, the RBA rate environment and retailer cost pressures constrain net organic growth. Conservative 1.5% reflects ~50% of lease escalation flowing through to DPU after funding costs. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Mild cap rate headwind of -0.5% to total return assumed. Australian retail cap rates have faced modest expansion pressure as bond yields remain elevated despite RBA easing cycle beginning. The June 2026 $92M valuation gain (ASX announcement HDN 15-Jun-2026) is a positive offset but is treated as a one-period event rather than a trend. Net multiple change assumption is -0.5% for the 12-month horizon.
- `gearing_estimate` = 0.35 (Cat B) — Gearing estimated at approximately 35% based on 1H FY26 reporting context (news reference: Australian Property Markets News, 11 Feb 2026) and the $92M valuation gain announced Jun 2026 which reduces effective LVR. ASX body capture for HDN.AX filings is pending per Phase 01 v3.3 §4; confirmed gearing figure not available from filing body. Treated as Category B estimate. Australian REIT regulatory convention is <40%.
- `distribution_coverage_estimate` = unconfirmed (Cat B) — AFFO coverage not confirmed from filing bodies (ASX body capture parked per Phase 01 v3.3 §4 — body_unavailable). Kalkine analysis (15 Jun 2026) queried distribution sustainability at 6.57% yield, indicating market attention to coverage. HDN's daily needs model with strong anchor tenants (Woolworths/Coles) supports structural rental income but payout ratio cannot be independently verified at this as_of. Disclosed as a key uncertainty.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. Computed beta of 0.563 with correlation 0.398 over 257 observations at 252-day lookback.

## Key Risks
- Distribution coverage uncertainty: filing bodies unavailable (ASX Phase 01 v3.3 §4); if AFFO payout ratio exceeds 100% the 6.57% yield would be unsustainable, consistent with Kalkine's June 2026 sustainability query
- RBA rate environment: although the RBA has begun an easing cycle, any re-acceleration of inflation halting further cuts would sustain cap rate pressure on Australian retail property and compress the yield spread
- Sponsor concentration risk: HomeCo/David Di Pilla ecosystem is less diversified than major institutional REIT managers; pipeline dependent on single-sponsor capital allocation decisions
- AUD depreciation risk: a weaker AUD relative to other major currencies does not directly affect AUD-denominated distributions but could reduce relative total returns for international investors and affect debt refinancing costs on any USD/EUR-denominated facilities
- Phase 2 calibration is directional only; vintage discipline arrives in Phase 5 — this analysis should be treated as a screening signal, not a formal backtest result

## Invalidation Condition
Exit or downgrade to Conviction 1 if: (1) reported gearing rises above 40% LVR for two consecutive reporting periods without a credible deleveraging plan; (2) DPU is cut by more than 5% in any single distribution announcement, signalling AFFO coverage breach; (3) anchor tenant vacancy (Woolworths or Coles departure from more than two centres) is announced; or (4) the HomeCo sponsor group publicly reduces pipeline commitment to HDN or undergoes a material adverse change in credit standing.
