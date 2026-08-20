# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-20_equity_reit_v1@1.0_80318815eab1`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Digital Core REIT offers USD-denominated data centre exposure on SGX, backed by Digital Realty Trust as sponsor — a globally dominant data centre operator with deep hyperscaler relationships. The announced portfolio pivot (selling US$315.9M in North American assets, entering Singapore and expanding into Japan) represents a strategic repositioning toward APAC markets where AI/cloud-driven demand is accelerating and cap rate arbitrage may be favourable. At a closing price of US$0.505, the trailing annualised yield of ~7.1% provides a meaningful spread over the 3.7% T-bill rate, and a CAPM alpha of 8.6% against an already-negative benchmark return (IASP.L -4.4% 5-year annualised) signals strong risk-adjusted excess return potential. A PGain of 72.2% from the OU Monte Carlo and a low beta of 0.34 (note USD/GBP currency-basis caveat) support an above-average conviction rating, with active unit buybacks providing additional per-unit NAV support.

## Quantitative Chain

- E(R): 0.0960
- Std dev: 0.1615
- P-gain: 0.7224
- CAPM alpha: 0.0862
- Beta: 0.3379
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Portfolio transaction fails to complete or closes at unfavourable terms, resulting in NAV dilution. DPU cut as occupancy in legacy US portfolio deteriorates to sub-90% during transition period. Cap rate expansion of 50-75bps driven by higher-for-longer US interest rates compressing data centre valuations. Gearing rises toward or above 45% MAS limit, forcing equity issuance. Unit buyback programme suspended. Bear case also captures tail risk of hyperscaler tenant concentration leading to a non-renewal at a major US facility.
- **base**: E(R)=0.0950
  - Central case as built in quantitative chain: annualised DPU stable at US$0.036 (flat H1 2026 trajectory), portfolio transaction closes on disclosed terms with SG and Japan assets contributing from Q4 2026 onward, 2.0% DPU growth assumption holds, cap rates broadly flat, occupancy above 95%, gearing within regulatory limit, modest +0.5% re-rating from APAC portfolio pivot.
- **bull**: E(R)=0.2200
  - Portfolio transaction accretive: Singapore and Japan data centres acquired at yields above prior US portfolio, driving DPU growth of 4-5% p.a. AI/cloud hyperscaler demand accelerates, driving occupancy to 98%+ and rental reversions above CPI. Unit buybacks provide additional per-unit NAV accretion. Broader re-rating of APAC data centre REITs compresses cap rates 25-50bps, lifting price toward NAV. Digital Realty sponsor injects additional pipeline assets at accretive yields.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0713 (Cat A) — Trailing annualised DPU of US$0.036 (H1 2026 DPU of US$0.018 x 2, per Business Times report dated 29 Jul 2026) divided by closing price of US$0.505 as of 2026-08-20. Observed published figure.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed: (i) portfolio restructuring (sale of US$315.9M North American assets, entry into Singapore and expansion into Japan data centres, announced 12-Aug-2026) expected to be broadly NAV-neutral to slightly accretive given higher-yielding SG/JP markets; (ii) data centre rental escalators typically CPI-linked or fixed at 2-3% p.a.; (iii) H1 2026 DPU was flat at US$0.018, supporting a conservative baseline. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% re-rating expected over 12 months. Pivot from US to Singapore and Japan data centres shifts portfolio toward APAC-premium markets with AI/cloud-driven demand. Active unit buyback programme (2M units/day from 15-Apr-2026; max 129.6M units authorised) provides per-unit NAV accretion. Assumption is conservative given uncertainty around transaction completion timeline.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU.SI is USD-denominated). The currency basis between USD and GBP introduces additional noise into the beta estimate. Treated as Category B input. CAPM alpha inherits the same noise.
- `portfolio_transaction_risk` = disclosed (Cat B) — Digital Core REIT announced a portfolio transaction on 12-Aug-2026 (SGX filing SG260812OTHRGKAJ): disposal of North American assets valued at US$315.9M and simultaneous entry into Singapore plus Japan data centres. Transaction is pending completion; headline and filing body were available but full financial detail (post-close leverage, AFFO impact) was not yet filed as of as_of date. Post-transaction gearing and coverage modelled on management guidance implicit in deal structure.

## Key Risks
- Portfolio transaction execution risk: the sale of US$315.9M in North American assets and simultaneous acquisition of Singapore and Japan data centres is pending completion; unfavourable final terms, regulatory delays, or market-to-market deterioration in asset valuations could impair NAV and DPU.
- Hyperscaler tenant concentration: Digital Core REIT's income is highly concentrated among a small number of hyperscaler tenants (Amazon, Google, Meta via Digital Realty relationships); non-renewal or renegotiation by any single tenant could materially impact DPU.
- Currency basis risk: DCRU.SI distributes in USD while trading on SGX; SGD-based investors absorb USD/SGD volatility on distributions, and the IASP.L benchmark is GBP-denominated, introducing additional noise in beta and CAPM alpha estimates.
- Higher-for-longer interest rate environment: data centre REITs carry meaningful debt loads; if US and Singapore rates remain elevated beyond market expectations, refinancing costs could compress distributable income and widen cap rates, pressuring valuations.
- Regulatory and power supply constraints: Singapore and Japan data centre expansion faces power availability limits and permitting risk; delays in securing power capacity for new acquisitions could defer income contribution and delay DPU accretion.

## Invalidation Condition
Exit position if: (i) the 12-August-2026 portfolio transaction fails to receive regulatory or unitholder approval, or closes at terms materially worse than disclosed (net proceeds below US$300M or acquisition yield below 5.5%); (ii) any single quarter DPU falls below US$0.008 (implying annualised DPU below US$0.032, a >11% cut from current run-rate); (iii) aggregate leverage breaches 43% for two consecutive reporting periods, signalling proximity to MAS 45% limit and potential forced equity issuance; or (iv) Digital Realty Trust formally withdraws or materially reduces its right-of-first-refusal pipeline commitment to Digital Core REIT.
