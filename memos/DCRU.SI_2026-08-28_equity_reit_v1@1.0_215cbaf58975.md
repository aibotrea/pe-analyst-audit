# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-28_equity_reit_v1@1.0_215cbaf58975`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT is executing a strategically significant portfolio pivot — divesting US$315.9M in North American assets and redeploying into Singapore and Japan data centres — repositioning itself within the high-demand APAC digital infrastructure corridor. The implied distribution yield of ~8% on a USD 0.505 unit price provides material income compensation for transition risk, supported by hyperscaler-grade tenant covenants and near-100% occupancy typical of data centre assets. Beta of 0.34 against IASP.L (currency-basis caveat applies) reflects lower co-movement with the broader APAC REIT index, consistent with the idiosyncratic nature of data centre fundamentals. An active unit cancellation buy-back programme (2M units/day since April 2026, sourced from SGX filings) signals management conviction that units trade below intrinsic value. The OU Monte Carlo yields a 75.7% probability of positive 12-month return with a CAPM alpha of +10.6%, supporting moderate conviction pending confirmation of post-divestment DPU sustainability.

## Quantitative Chain

- E(R): 0.1150
- Std dev: 0.1637
- P-gain: 0.7574
- CAPM alpha: 0.1060
- Beta: 0.3371
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - APAC repositioning yields below expectations: SG/Japan assets deliver <5% NOI yield; DPU cut of 15-20% as interest costs on retained debt exceed rental income from acquired assets; gearing breaches 45% if asset valuations decline; US asset sale closes at discount to book, crystallising a loss. Bear driver may include a global rate re-escalation scenario that compresses data centre cap rate multiples.
- **base**: E(R)=0.1140
  - Central case as modelled: 8% distribution yield on current price, 3% DPU growth from APAC hyperscaler demand, modest +0.5% multiple re-rating. US divestment completes at disclosed terms, leverage falls below 45%, buy-back continues to provide NAV support.
- **bull**: E(R)=0.2500
  - Data centre rental escalation accelerates in SG and Japan driven by AI/hyperscaler infrastructure investment; DCRU DPU grows 6%+; significant P/NAV re-rating as market recognises APAC data centre scarcity premium; Digital Realty injects further APAC pipeline assets at accretive yields; buy-back at discount contributes additional NAV uplift.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.08 (Cat C) — Implied trailing yield of ~8.0% on USD 0.505 unit price. No confirmed DPU figure available from filed financial statements in the 180-day lookback window (filings dominated by unit buy-back notices). Sector context (Beansprout, Jun 2026) cites SG data centre REITs at yields up to 8%; Smart Investor (Jun 2026) cites DCRU in 7%+ yield cohort. Assumed USD ~0.0404 DPU. Sensitivity tested in scenario analysis.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth of 3.0% per annum assumed post-portfolio repositioning. DCRU's Aug 2026 pivot to SG and Japan data centres (Business Times, 12 Aug 2026: US$315.9M North America asset sale + APAC entry) is expected to capture hyperscaler-driven rental escalations in tier-1 APAC markets. Sensitivity: bear case uses 0% growth, bull case uses 6%.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% P/NAV re-rating assumed. DCRU is trading at a material discount to book following 2022-2024 interest rate headwinds and portfolio concentration concerns. Active unit cancellation buy-back (2M units/day since Apr 2026, per SGX filings DCRU.SI 2026-08-19 to 2026-08-28 ANNC) signals management belief in NAV undervaluation. Offset by ongoing portfolio transition uncertainty.
- `leverage_post_divestment` = est_below_45pct (Cat C) — Leverage estimated to fall to below 45% SG regulatory cap following the US$315.9M North America asset divestment (Business Times, 12 Aug 2026). Pre-divestment gearing was elevated; proceeds applied to debt reduction. Exact post-close gearing not yet filed. Assumption subject to revision on next financial result.
- `buy_back_programme` = active (Cat A) — Unit buy-back by way of market acquisition confirmed daily from SGX filings (DCRU.SI 2026-08-19 to 2026-08-28 ANNC). Mandate: 129,602,591 units authorised. Observed daily volume: 2,000,000 units per session on 19, 20, 21 Aug 2026 filings. All repurchased units cancelled — NAV-accretive.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU trades in USD on SGX). Treated as Category B input. CAPM alpha inherits the same currency and IASP basis noise.

## Key Risks
- DPU sustainability uncertainty: post-repositioning distribution level is unconfirmed in available filings; if APAC asset yields disappoint relative to disposed US assets, a DPU cut would materially reset the yield thesis.
- Portfolio transition execution risk: simultaneous divestment and acquisition introduces timing mismatch — idle cash between sale close and deployment depresses near-term distributions.
- Leverage and refinancing risk: elevated historical gearing and USD-denominated debt create sensitivity to USD interest rate trajectory; a return to higher-for-longer Fed policy could erode interest coverage.
- Concentration risk: post-repositioning portfolio concentrated in a small number of APAC assets; any single-asset vacancy or tenant non-renewal would have outsized impact on DPU.
- Sponsor dependency: Digital Realty Trust (DLR) is DCRU's primary pipeline source; any DLR capital allocation shift away from APAC or weakening of DLR's own balance sheet would reduce the quality of DCRU's growth optionality.

## Invalidation Condition
Exit or reduce position if: (1) the post-repositioning DPU falls below USD 0.032 per unit on an annualised basis (implying >20% cut from the assumed USD 0.0404 base), signalling that APAC asset yields do not compensate for lost US income; or (2) aggregate leverage ratio is confirmed above 45% in the next filed financial statements, breaching the Singapore MAS regulatory cap; or (3) Digital Realty Trust publicly reduces its APAC pipeline commitment to DCRU or transfers pipeline assets to competing vehicles.
