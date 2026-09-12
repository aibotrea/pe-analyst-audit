# Specialist Memo — ME8U.SI

**Memo ID**: `ME8U.SI_2026-09-12_equity_reit_v1@1.0_ba80884a008d`
**Ticker**: ME8U.SI (Mapletree Industrial Trust)
**Market**: Singapore
**Sector**: Industrial / Data Centres
**As of**: 2026-09-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mapletree Industrial Trust offers a differentiated Singapore-listed industrial REIT profile anchored by approximately 50% data centre AUM (US and Singapore), providing structural demand tailwinds from hyperscaler growth. A trailing distribution yield of ~6.34% at the current SGD 1.91 price represents a material 248bps spread over the 3-month T-bill rate of 3.86%, compensating for near-term risks. Beta of 0.30 versus IASP.L (currency-basis caveat applies) indicates substantially lower price volatility than the broader APAC REIT universe, and the OU Monte Carlo PGain of 84.6% supports a positive return view at the 12-month horizon. Conviction is held at Moderate (3/5) rather than Above-Average due to the CEO transition effective 1 October 2026, USD/SGD translation exposure on US data centre income, and residual rate uncertainty that could cap multiple expansion.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.0763
- P-gain: 0.8457
- CAPM alpha: 0.0663
- Beta: 0.3039
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - DPU cut of 5–8% driven by: US data centre JV income declining on USD/SGD weakness, occupancy in Singapore industrial portfolio falling to 91%, and rising interest costs pushing gearing stress. CEO transition leads to strategy disruption or dilutive acquisition. Cap rate expansion of 50bps compresses NAV. Higher-for-longer global rates cause REIT sector de-rating. Bear case encompasses a potential rate-shock scenario where MAS tightening and Fed policy divergence amplify SGD translation losses on US assets.
- **base**: E(R)=0.0780
  - Central case as built in chain: trailing DPU yield of 6.34%, forward growth of 1.5%, no multiple expansion. Occupancy stable at ~93–94%. CEO transition orderly with incoming CEO maintaining strategy continuity. USD/SGD broadly stable. Gearing at ~37–38%, well within limits.
- **bull**: E(R)=0.1800
  - US data centre demand accelerates; MIT secures additional hyperscaler pre-commitments driving accretive AUM growth at 6%+ cap rates. SGD strengthens modestly vs USD improving DPU translation. Singapore industrial rents tighten further. Market re-rates MIT toward historical P/NAV of 1.3x on improved growth visibility. New CEO executes capital recycling that is NAV-accretive. MAS pivots to easing, compressing risk-free rate.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.0634 (Cat A) — Trailing DPU yield derived from published FY2025/26 annual DPU of approximately SGD 0.121 per unit divided by last closing price of SGD 1.91 (trade date 2026-09-11). Observed market price and issuer-published distribution figure.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% per annum. Based on: (i) MIT's ~50% data centre AUM providing structural tailwind from hyperscaler demand; (ii) Singapore industrial portfolio benefiting from tight vacancy; (iii) offset by USD/SGD translation headwind on US data centre income and higher-for-longer financing costs. Sensitivity tested in scenario analysis.
- `multiple_expansion_assumption` = 0.0 (Cat C) — No multiple expansion assumed in base case. Imminent CEO transition (effective 1 October 2026 per SGX filing ME8U.SI 2026-08-21 ANNC) introduces near-term strategic uncertainty. Rate environment remains elevated. P/NAV assumed flat.
- `us_datacenter_fx_exposure` = disclosed (Cat B) — Approximately 50% of MIT AUM is US-domiciled data centres held via JV structures. SGD DPU is partially exposed to USD/SGD translation. No hedging assumption modelled; FX risk treated as embedded in the DPU growth estimate.
- `ceo_transition` = disclosed (Cat A) — Ms Ler Lily resigned as CEO effective 1 October 2026 to assume Group CFO role at Mapletree Investments Pte Ltd. Mr Anand Tze Ming Chandran (age 43) appointed as incoming CEO effective same date. Source: SGX filings ME8U.SI 2026-08-21 ANNC (cessation and appointment announcements).
- `gearing_ratio` = 0.375 (Cat B) — MIT's aggregate leverage estimated at approximately 37–38% of total assets, consistent with publicly reported figures through FY2025/26 and well within Singapore's 50% regulatory limit. Derived from most recent available public disclosures; exact 1Q FY2026/27 figure not captured in stored filing bodies.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- CEO transition (effective 1 October 2026) creates near-term strategic uncertainty; incoming CEO Anand Chandran's execution track record at MIT scale is unproven.
- USD/SGD currency translation risk on US data centre JV distributions — approximately 50% of AUM is USD-denominated; a sustained USD weakening reduces SGD DPU.
- Higher-for-longer interest rate environment: MIT's floating-rate debt exposure could pressure distribution coverage if refinancing costs exceed DPU growth.
- US data centre market concentration risk: hyperscaler demand is cyclical; a pullback in AI/cloud capex spend could affect occupancy and lease renewal terms at US assets.
- Calibration limitation: phase 2 directional signal only; formal vintage-discipline backtest not available until Phase 5. Beta and alpha inherit GBP/SGD currency basis noise from IASP.L benchmark.

## Invalidation Condition
Exit position if: (1) MIT announces a DPU cut exceeding 5% on a trailing four-quarter basis relative to FY2025/26 levels, signalling distribution stress; (2) reported aggregate leverage breaches 42% for two consecutive quarters, approaching the 45% MAS regulatory buffer threshold; (3) US data centre occupancy falls below 90% for two consecutive reporting periods, indicating hyperscaler demand reversal; or (4) the incoming CEO announces a materially dilutive acquisition (>10% of AUM) within the first six months of tenure without clear accretion to DPU within 24 months.
