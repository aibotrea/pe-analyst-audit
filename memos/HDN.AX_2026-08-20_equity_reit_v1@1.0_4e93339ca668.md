# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-08-20_equity_reit_v1@1.0_4e93339ca668`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Retail/Daily Needs
**As of**: 2026-08-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
HomeCo Daily Needs REIT provides exposure to Australian neighbourhood shopping centres and large-format retail anchored by non-discretionary tenants (Coles, Woolworths, Chemist Warehouse), offering a defensive income profile in a subdued growth environment. The post-FY26 de-rating of ~10% has pushed the unit price materially below NTA and lifted the trailing distribution yield to approximately 6.4%, a meaningful real spread over the 3.71% T-bill rate. Beta of 0.56 versus IASP.L (currency-basis caveat applies) reflects moderate co-movement with the broader APAC REIT universe. The OU Monte Carlo simulation returns a PGain of 72.5%, supporting moderate conviction, tempered by a one-step downward gate override reflecting unconfirmed AFFO coverage and rising interest-cost headwinds signalled in softer FY27 guidance.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1213
- P-gain: 0.7248
- CAPM alpha: 0.0810
- Beta: 0.5595
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds rates higher for longer compressing interest coverage further; DPU cut of 10-15% triggered by AFFO coverage falling below 1.0x; cap rate expansion of 50bps across neighbourhood and large-format retail assets driving NTA erosion of 8-10%; occupancy slippage as discretionary tenants vacate large-format space in a consumer spending downturn.
- **base**: E(R)=0.0730
  - Central case as built in chain: DPU growth 0.5%, yield 6.37%, modest +0.5% multiple mean-reversion from post-FY26 de-rating. Occupancy stable, interest costs stabilise as RBA eases modestly, gearing ~37% within regulatory limit.
- **bull**: E(R)=0.1800
  - RBA rate cuts materialise faster than expected, reducing interest costs and compressing cap rates by 25bps; HomeCo sponsor injects accretive pipeline assets at 7%+ yield; distribution coverage recovers above 1.1x AFFO; market re-rates HDN back toward pre-August 2026 levels (~AUD 1.29), implying ~13% capital return plus ~6.4% yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0637 (Cat A) — Trailing annualised DPU estimated at ~7.3 cpu based on distribution announcement headline (Fund Payment Notice, HDN.AX 2026-08-20) and news signal 'distribution maintained' post FY26 result. Current price AUD 1.145 (2026-08-20). Yield = 7.3/114.5 = 6.37%. Body capture for ASX filings unavailable per Phase 01 v3.3 §4 — confirmed distribution maintenance from news sources only, filed as Category A pending formal confirmation.
- `dpu_growth_3yr` = 0.005 (Cat C) — Forward DPU growth assumption set at 0.5% p.a. reflecting softer FY27 guidance per earnings call transcript (Investing.com, 2026-08-13) and rising interest costs reducing distributable income headroom. Materially below historical AUM-driven growth rates given current rate environment. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple expansion assumed as partial mean reversion from post-FY26 de-rating (~-10.3% price decline 12-13 Aug 2026). HDN trades below NTA per news reports (Simply Wall St, 2026-08-14). Full reversion not assumed given sustained higher-rate environment constraining cap rate compression. Category C — model assumption.
- `leverage_gearing` = 0.37 (Cat B) — Estimated gearing ~37% based on news signals indicating rising interest costs and shares trading below NTA (Simply Wall St, 2026-08-14). ASX filing body capture unavailable for HDN per Phase 01 v3.3 §4; exact figure not confirmed from filing. Assumed within AU convention <40% LVR. Category B — derived estimate.
- `distribution_coverage` = unconfirmed (Cat B) — AFFO coverage ratio not confirmable from available filing bodies (ASX body capture for HDN unavailable). News signals: 'interest costs rising' and 'softer FY27 guidance' suggest potential headroom compression. Distribution maintained per Fund Payment Notice (HDN.AX 2026-08-20) but coverage ratio treated as unconfirmed Category B input. Gate applied as 'info' with -1 conviction override.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Sustained higher RBA cash rate eroding interest coverage and pressuring distribution sustainability; softer FY27 guidance already signalling headroom compression.
- Large-format retail structural headwinds from e-commerce penetration reducing foot traffic and tenant demand in discretionary categories within HDN's portfolio.
- Cap rate expansion in Australian retail property if global base rates remain elevated, compressing NTA and triggering further unit price underperformance.
- Concentration risk in HomeCo/HA Group as sponsor and manager — any strategic shift, management fee restructuring, or dilutive equity raising could impair unitholder returns.
- ASX filing body capture unavailable for HDN (Phase 01 v3.3 §4); AFFO coverage ratio, exact gearing, and WALE profile not confirmable from filing text, introducing Category B estimation uncertainty into key assumptions.

## Invalidation Condition
Exit signal triggered if any of the following occur: (1) HDN announces a formal DPU cut exceeding 5% for FY27, confirming AFFO coverage below 1.0x for two consecutive reporting periods; (2) reported gearing breaches the 40% Australian convention threshold without a credible de-leveraging plan approved by unitholders; (3) HomeCo sponsor formally reduces pipeline commitment or restructures management fees in a manner that increases total expense ratio above 0.80% of GAV, signalling misaligned incentives.
