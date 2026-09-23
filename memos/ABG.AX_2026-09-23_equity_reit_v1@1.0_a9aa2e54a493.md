# Specialist Memo — ABG.AX

**Memo ID**: `ABG.AX_2026-09-23_equity_reit_v1@1.0_a9aa2e54a493`
**Ticker**: ABG.AX (Abacus Group)
**Market**: Australia
**Sector**: Office/Diversified
**As of**: 2026-09-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Abacus Group (ABG.AX) is an Australian diversified/office REIT undergoing a significant strategic shift following its partial sale of the Storage King self-storage business in September 2026, concentrating exposure in the structurally challenged Australian office sector. The FY27 distribution reset signals prior payouts were unsustainable, and Morningstar's downgrade following what it described as an 'underwhelming exit' from Storage King adds near-term negative sentiment. E(R) of 2.0% is slim relative to the 4.01% risk-free rate, and the OU Monte Carlo simulation produces a PGain of only 55%, indicating near-coin-flip odds of a positive 12-month return. Qualitative gate failures on distribution coverage and asset quality concentration — combined with -2 gate override steps — reduce conviction to Speculative (1/5), warranting a maximum 1% position size if held at all.

## Quantitative Chain

- E(R): 0.0200
- Std dev: 0.1550
- P-gain: 0.5495
- CAPM alpha: 0.0256
- Beta: 0.5120
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2000
  - Office vacancy rises materially in ABG's core Sydney/Melbourne CBD portfolio as hybrid work adoption accelerates, driving occupancy below 88% and cap rate expansion of 50bps. DPU falls a further 10-15% below FY27 reset level. Storage King exit proceeds are fully redeployed at sub-5% yield, destroying value. RBA holds rates higher-for-longer, compressing REIT multiples; gearing re-rises above 40% on asset devaluations, triggering covenant concern and investor flight. Morningstar downgrade catalyses institutional selling.
- **base**: E(R)=0.0200
  - Central case as built in chain: forward yield 4.5%, DPU growth -1.5%, multiple change -1.0%. Office occupancy stable at ~92-93%; Storage King exit proceeds reduce debt modestly; RBA begins easing cycle which partially offsets office headwinds. Distribution held at reset level.
- **bull**: E(R)=0.1400
  - RBA cuts rates by 75bps within 12 months, compressing cap rates and re-rating office REITs broadly. Storage King exit generates higher-than-expected proceeds redeployed accretively; DPU stabilises at reset level with recovery trajectory. Office occupancy improves to 95%+ on CBD supply constraints. Multiple expands 100bps, delivering capital upside layered on 4.5% yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield_forward` = 0.045 (Cat B) — Forward FY27 DPU estimated at AUD ~0.038/unit post announced distribution reset, yielding approximately 4.5% on the AUD 0.845 closing price. News (Kalkine, Sep 10 2026: 'FY27 Distribution Reset Changes the Income Story') confirms a reset occurred; precise DPU quantum estimated from trailing actuals (~4.5 cpu pre-reset) adjusted downward. ASX body capture for ABG.AX filed distribution notice (2026-08-31) returned mismatched content (body_unavailable for ABG-specific data); figure treated as Category B estimate.
- `dpu_growth_3yr` = -0.015 (Cat C) — Negative DPU growth assumed at -1.5% p.a. reflecting: (1) office sector structural demand headwinds from hybrid working; (2) reduced diversification following partial exit of Storage King self-storage business (ASX announcement 2026-09-17 'Sale of Interest in Storage King Group', price-sensitive); (3) distribution reset indicating prior payout was unsustainably high. Sensitivity: 0% growth would add ~1.5pp to E(R); -3% growth would subtract ~1.5pp.
- `multiple_change` = -0.01 (Cat C) — Cap-rate / multiple headwind of -1.0% assumed, reflecting: (1) Morningstar downgrade of ABG following 'underwhelming exit' from Storage King (Google News, 21 Sep 2026); (2) Australian office REITs facing ongoing derating amid elevated RBA cash rate environment and hybrid work structural shift; (3) proceeds from Storage King sale reducing leverage may partially offset but not reverse negative re-rating. Sensitivity: flat multiples would add 1.0pp to E(R).
- `expected_return_build` = 0.02 (Cat B) — E(R) = forward yield (4.5%) + DPU growth (-1.5%) + multiple change (-1.0%) = 2.0%. Each component individually classified. Represents a slim real return above zero.
- `gearing_level` = 0.37 (Cat B) — ABG gearing estimated at ~35-38% based on prior publicly filed balance sheet data; the Storage King interest sale (ASX 2026-09-17) is expected to generate proceeds that reduce net debt, potentially bringing gearing closer to 33-35%. Exact post-transaction figure unavailable from body capture (ASX body mismatch). Australian REIT convention threshold is 40%. Estimated as Category B pending next quarterly filing.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Office structural demand deterioration: hybrid work adoption in Sydney/CBD markets could drive sustained occupancy and rental decline, expanding cap rates and eroding NTA materially below current unit price.
- Distribution sustainability: the FY27 distribution reset may prove insufficient if AFFO coverage remains below 1.0x post Storage King disposal, risking a further DPU cut.
- Storage King exit execution: proceeds redeployed at unattractive yields or into overpriced office acquisitions would compound NAV destruction; Morningstar's 'underwhelming exit' framing signals market scepticism.
- Interest rate sensitivity: ABG carries meaningful floating-rate debt; any RBA rate hold or further tightening in FY27 compresses net distributable income and increases gearing on devalued assets.
- Calibration limitation: this memo uses Phase 2 directional signals, not a formal backtest. Vintage discipline is absent pending Phase 5; pgain and alpha estimates carry model uncertainty, particularly given the currency basis embedded in the IASP.L beta and market return.

## Invalidation Condition
Exit or size-down the position if ABG reports office portfolio occupancy declining below 90% for two consecutive quarters, or announces a second consecutive DPU reduction below the FY27 reset level, or if reported gearing rises above 40% on revalued assets, or if the Storage King sale proceeds are redeployed into acquisitions at capitalisation rates below 5.5% — any of which would signal accelerating value destruction and invalidate the slim base-case return assumption.
