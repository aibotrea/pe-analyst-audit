# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-08-07_equity_reit_v1@1.0_2df37e416e99`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail/Shopping Centres
**As of**: 2026-08-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Scentre Group is Australia's dominant internally-managed retail REIT, owning 42 Westfield-branded super-regional shopping centres with ~99% occupancy and deeply entrenched catchment positions that are structurally difficult for e-commerce to replicate. A trailing distribution yield of approximately 5.4% at the current AUD 3.98 price provides a meaningful 166bps spread over the 3-month T-bill rate of 3.74%, with DPU growth of ~2.5% p.a. anchored by fixed rent escalations and specialty retail sales productivity gains. Gearing at ~32% LVR is conservative relative to the 40% AU convention, providing significant balance sheet headroom, and internal management eliminates external fee drag on unitholder returns. The OU Monte Carlo (12-month horizon) returns a simulated return of 7.84% with 74.2% probability of positive return, and CAPM alpha of 9.42% (Category B, currency-basis caveat applies) supports an above-average conviction score of 4.

## Quantitative Chain

- E(R): 0.0790
- Std dev: 0.1209
- P-gain: 0.7417
- CAPM alpha: 0.0942
- Beta: 0.6927
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - DPU growth falls to 0% as specialty retail sales contract amid consumer spending slowdown and e-commerce substitution accelerates. Occupancy slips to 97% as anchor tenants exit. Cap rate expansion of 30-50bps on rising Australian base rates (RBA re-tightening cycle) compresses NTA by ~8-10%, driving negative total return despite maintained distribution. Gearing rises toward 36% LVR on asset value decline, approaching but not breaching AU limit.
- **base**: E(R)=0.0790
  - Central case as built in chain: DPU growth 2.5% p.a. anchored to fixed escalations and specialty sales productivity; occupancy stable at ~99%; cap rates flat; AUD/GBP FX stable; RBA on hold. Distribution yield ~5.4% contributes majority of total return.
- **bull**: E(R)=0.1900
  - DPU growth accelerates to 4.5% as specialty retail sales exceed expectations and leasing spreads widen positively. RBA cuts rates by 50-75bps driving cap rate compression of 20-25bps and NTA uplift of 5-7%. Sector re-rating as institutional allocators increase REIT weight, compressing yield spread. Occupancy holds at 99%+ with no anchor departures.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.054 (Cat A) — Trailing DPU yield derived from FY2025 distribution of ~AUD 0.215 per security (published guidance) divided by closing price AUD 3.98 on 2026-08-07. Observed/published company-issued number.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. over 3-year horizon. Anchored to Scentre's own guidance of low-to-mid single digit distributable earnings growth, underpinned by fixed rent escalations (~3-4% p.a.), specialty sales productivity gains, and moderate leasing spread improvement. Sensitivity tested in scenario analysis: bear assumes 0%, bull assumes 4.5%.
- `multiple_change` = 0.0 (Cat B) — Assumes flat price-to-NAV multiple over 12-month horizon. SCG currently trades at a modest premium to book NTA (~AUD 3.55-3.65 estimated NTA); no material re-rating expected given stable interest rate environment and already-elevated retail REIT multiples. Derived estimate — classified Category B.
- `gearing_ratio` = 0.32 (Cat A) — SCG LVR of approximately 32% as reported in FY2025 results (company ASX filings); well within the AU REIT conventional limit of 40%. Full filing body was unavailable via pipeline (body_unavailable=True for key financial results filings); figure sourced from publicly known half-year/full-year results disclosures.
- `occupancy` = 0.99 (Cat A) — Portfolio occupancy ~99% as of latest reported period. Westfield super-regional portfolio benefits from dominant catchment positioning, anchored by major department stores and specialty retail. Sourced from publicly reported SCG operational metrics.
- `filing_body_gap` = disclosed (Cat B) — ASX filing bodies were unavailable (body_unavailable=True) for 6 of 8 filings in the lookback window, and the 2 captured bodies contained content mismatched to unrelated ASX issuers (pipeline cross-contamination). Key financial assumptions (gearing, DPU, occupancy) are sourced from publicly known SCG reported results and news analysis rather than parsed filing text. This gap is disclosed per §4 of filing policy.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. The IASP.L benchmark annualised return of -3.86% over 5 years reflects both APAC property weakness and GBP/AUD FX movements over the period.

## Key Risks
- Consumer spending contraction in Australia reducing specialty retail sales, weakening tenant lease renewal demand and leasing spreads
- RBA rate re-tightening cycle compressing asset values through cap rate expansion, reducing NTA and potentially constraining distribution growth
- Structural e-commerce substitution risk over medium-to-long term despite Westfield portfolio's current resilience and experiential retail positioning
- 100% retail sector concentration — no diversification across industrial, office or residential asset classes limits defensive repositioning optionality
- AUD/GBP currency basis noise inflating CAPM beta estimate (0.69); true property market beta may differ materially from the reported figure

## Invalidation Condition
Exit the position if SCG portfolio occupancy falls below 97% for two consecutive reporting periods, or if the LVR gearing ratio breaches 38% (within 2 percentage points of the 40% AU REIT convention limit), or if the annualised DPU is cut by more than 5% from the FY2025 base without a credible recovery pathway disclosed by management within one reporting cycle.
