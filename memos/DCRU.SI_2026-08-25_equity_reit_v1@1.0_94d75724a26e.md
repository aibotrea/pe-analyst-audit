# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-25_equity_reit_v1@1.0_94d75724a26e`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers exposure to the secular data centre theme via a Singapore-listed USD-denominated vehicle backed by sponsor Digital Realty Trust. A trailing distribution yield estimated at ~7.5% provides an above-average income cushion, and the ongoing unit buy-back programme (cancelling up to 129.6M units since April 2026) signals management confidence at current prices. However, the REIT is in a complex portfolio transition — divesting US assets and redeploying capital into Singapore and Japan — creating near-term DPU uncertainty that limits conviction. The OU Monte Carlo (12-month horizon) produces a PGain of 68.7% and simulated return of 7.9% with an annualised vol of 23.9%, resulting in a base conviction score of 3 that is reduced to 2 by a one-step distribution-coverage gate override.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1624
- P-gain: 0.6872
- CAPM alpha: 0.0726
- Beta: 0.3659
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - US asset disposal proceeds are redeployed at materially lower yields than divested assets, causing DPU to decline 15%+. SG/JP acquisition cap rates compress unexpectedly, leaving the portfolio smaller with lower income. Gearing rises above 45% regulatory threshold, limiting further acquisitions. Potential rate shock (Fed re-tightening) expands data centre cap rates and pressures valuation. Unit buy-back is suspended.
- **base**: E(R)=0.0800
  - Central case as built in the quantitative chain: distribution yield ~7.5%, flat DPU growth as US divestments offset by SG/JP acquisitions, modest +0.5% re-rating from active unit buy-back programme. Gearing remains within MAS regulatory limits. Sponsor (Digital Realty) maintains pipeline commitment.
- **bull**: E(R)=0.2200
  - SG/JP acquisitions are accretive at 7%+ NPI yields, driving DPU growth of 5%+. Global rate normalisation accelerates, compressing data centre cap rates and expanding unit NAV. Unit buy-back at discount to NAV proves highly accretive per remaining unit. AI-driven data centre demand tightens occupancy to 99%+ and provides rental uplift on lease renewals.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.075 (Cat B) — Estimated trailing DPU yield of ~7.5% based on current unit price of USD 0.51 (DCRU.SI 2026-08-25) and market commentary indicating Singapore data centre REITs yielding up to 8% (Beansprout, Jun 2026). No filed DPU statement available in the 8 most-recent SGX filings (all unit buy-back notices). Category B due to derived nature.
- `dpu_growth_3yr` = 0.0 (Cat C) — Assumed flat DPU growth (0%) over the 12-month horizon. DigiCore REIT is in active portfolio transition — divesting US data centres and acquiring Singapore and Japan assets (news, Aug 2026). Asset sale proceeds and reinvestment timing create near-term DPU uncertainty; any growth from new SG/JP assets is expected to roughly offset lost US income in 12 months. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple expansion assumption. Active unit buy-back programme (mandate 129.6M units, running since April 2026 at ~2M units/day per SGX filings dated Aug 2026) is supportive of re-rating. Modest positive given transitional portfolio state and elevated global rate uncertainty.
- `unit_buyback_programme` = active (Cat A) — Unit buy-back programme active from 15 April 2026, maximum 129,602,591 units authorised for cancellation. Daily purchases of approximately 2,000,000 units confirmed in SGX filings (DCRU.SI 2026-08-19, 2026-08-20, 2026-08-21). CEO John Stewart personally signing notifications. All repurchased units are cancelled.
- `portfolio_pivot` = US divestment / SG-JP acquisition (Cat A) — Public news (Dr Wealth, 20 Aug 2026) confirms DigiCore REIT is selling US data centre assets and acquiring Singapore and Japan data centres. This is a strategic geographic reorientation by the manager.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU.SI units are USD-denominated on SGX). Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- DPU compression during the US asset disposal / SG-JP acquisition transition period, particularly if disposal proceeds are redeployed at lower yields or with timing gaps
- Elevated annualised volatility of ~23.9% relative to the data centre REIT sector average, indicating price sensitivity that is high for an income vehicle
- Gearing transparency: recent SGX filings consist entirely of unit buy-back notices with no interim financial results visible; leverage position cannot be independently verified at as_of date
- USD/SGD currency basis: DCRU.SI units are USD-denominated on SGX, creating an additional currency layer not present in most S-REITs, and contributing to beta noise vs the GBP-denominated IASP.L benchmark
- Concentration risk increasing post-pivot: moving from a multi-geography (US/SG/JP) portfolio to predominantly Asia Pacific data centres reduces diversification at a time when regional regulatory risk (data sovereignty, AI compute policy) is rising

## Invalidation Condition
Exit if DigiCore REIT reports two consecutive half-year distributions showing DPU decline exceeding 10% year-on-year, or if aggregate leverage breaches 45% without a concurrent rights issue or asset recycling plan approved by unitholders, or if Digital Realty Trust (sponsor) publicly reduces or withdraws its pipeline commitment to the REIT, or if the unit buy-back programme is suspended while units continue to trade at a discount to NAV exceeding 20%.
