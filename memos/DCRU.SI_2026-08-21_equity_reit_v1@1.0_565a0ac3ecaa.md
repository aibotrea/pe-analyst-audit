# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-21_equity_reit_v1@1.0_565a0ac3ecaa`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT is undergoing a material strategic pivot, disposing of ~US$315.9M in North American data centre assets and redeploying into Singapore and Japan, repositioning toward higher-growth APAC digital infrastructure markets. The trailing distribution yield of ~7.1% at the current price of US$0.510 is attractive in absolute terms, but nearly half of the H1 2026 distribution (US$0.0088 of US$0.018 per unit) comprises capital return rather than income, raising sustainability questions about the full payout. CAPM alpha of 7.1% versus the IASP.L benchmark is supportive, but elevated annualised volatility of 23.8% and a PGain of 68.8% from the OU Monte Carlo yield only average statistical support for a positive 12-month return. The active unit buyback programme (2M units/day cancelled) is a constructive management alignment signal, but conviction is capped at Low (2) pending confirmation that the APAC acquisitions restore income coverage.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1615
- P-gain: 0.6882
- CAPM alpha: 0.0711
- Beta: 0.3459
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - APAC asset acquisitions (Singapore and Japan data centres) prove dilutive or face integration delays; income gap from US asset disposal is larger than anticipated; DPU cut reduces income component further below US$0.0092/unit per half; AFFO coverage deteriorates to below 0.85x; cap rate expansion of 50bps in data centre assets driven by persistent higher-for-longer US rates spilling into APAC financing costs; unit price reverts toward NAV discount of 20%+.
- **base**: E(R)=0.0800
  - Central case as built in chain: annualised DPU maintained at US$0.036 with 1.5% forward growth; APAC asset integration proceeds on schedule; capital return component of distribution gradually replaced by income as new assets stabilise; gearing remains below 40% post-transaction; unit buyback programme continues, providing price support.
- **bull**: E(R)=0.2200
  - APAC data centre acquisitions prove strongly accretive (yield-on-cost above 6.5%); AI-driven hyperscale demand in Singapore and Japan drives occupancy to 99%+ and enables DPU uplift of 5%+; capital distribution component is eliminated as income coverage recovers above 1.1x AFFO; Digital Realty sponsor injects further APAC pipeline assets; multiple re-rating as APAC-focused data centre premium is applied.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0706 (Cat A) — Annualised DPU of US$0.036 (H1 2026 DPU of US$0.018 × 2, per DCRU.SI 2026-07-29 CACT filing) divided by current price of US$0.510. Observed published distribution figure.
- `capital_return_component` = 0.49 (Cat A) — 49% of H1 2026 distribution (US$0.0088 of US$0.018 per unit) is a capital distribution rather than income; tax-exempt income component is US$0.0092 per unit. Sourced from DCRU.SI 2026-07-29 CACT filing. Raises AFFO coverage concern.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed: H1 2026 DPU was flat year-on-year per news reports. The August 2026 portfolio transaction (disposing ~US$315.9M of North America assets, acquiring Singapore and Japan data centres per DCRU.SI 2026-08-12 ANNC) introduces near-term income disruption but should stabilise with APAC asset integration. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% drag from portfolio repositioning transition uncertainty. The US-to-APAC asset swap involves execution risk and temporary income gap. Sensitivity: if accretion is confirmed at announcement, this assumption reverts to zero or positive.
- `unit_buyback_signal` = active (Cat A) — Management purchasing 2,000,000 units per day by market acquisition from 18-21 August 2026 (per DCRU.SI daily buy-back notices); mandate cap 129,602,591 units authorised from 15 April 2026. All units cancelled on repurchase. Management confidence signal.
- `portfolio_transaction` = US$315.9M North America asset disposal; Singapore and Japan DC acquisition (Cat A) — Per DCRU.SI 2026-08-12 ANNC (Asset Acquisitions and Disposals); trading halt lifted 12-Aug-2026 12:33. Portfolio strategic pivot from US data centres to APAC data centres. Leverage impact: disposal proceeds expected to reduce gearing meaningfully below Singapore 45% regulatory limit.
- `leverage_gearing` = estimated_post_transaction_below_40pct (Cat B) — Full gearing ratio not available in truncated filing bodies. Pre-transaction gearing for DCRU estimated in the 35-40% range based on public disclosures; US$315.9M disposal proceeds will further reduce leverage. Estimated to remain within Singapore 45% regulatory limit post-transaction. Category B given derivation from partial data.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. Currency basis is material given DCRU.SI trades in USD and the benchmark is priced in GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Capital return constitutes ~49% of H1 2026 distribution; if income generation from new APAC assets does not replace the capital return component, the sustainable DPU could be materially lower than the headline US$0.036 annualised figure.
- Portfolio transition execution risk: the near-simultaneous disposal of US assets and acquisition of Singapore and Japan data centres introduces an income gap period and integration uncertainty.
- Higher-for-longer US interest rates increasing financing costs on any residual USD-denominated debt and widening cap rates in APAC data centre markets, compressing NAV.
- Elevated annualised volatility of 23.8% relative to APAC REIT peers reflects the niche data centre sector and USD-reporting base; macro-rate shocks could cause outsized drawdowns.
- Phase 2 calibration limitation: this analysis is a directional signal; vintage discipline and formal backtest calibration are deferred to Phase 5, and the macro signals (FEDFUNDS, credit spreads) are not incorporated in this memo.

## Invalidation Condition
Exit or reduce position if the next semi-annual DPU (H2 2026, expected January 2027) falls below US$0.016 per unit, or if the capital return component of the distribution persists above 40% of total DPU for two consecutive periods, signalling a structural shortfall in income generation from the reconstituted APAC portfolio. Additionally, exit if disclosed post-transaction gearing exceeds 42% of total assets (approaching Singapore's 45% regulatory limit), or if Digital Realty Trust materially reduces its sponsor pipeline commitment to DCRU.
