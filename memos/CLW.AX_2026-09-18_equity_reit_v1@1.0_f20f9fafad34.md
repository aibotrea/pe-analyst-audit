# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-09-18_equity_reit_v1@1.0_f20f9fafad34`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified Long WALE (Office/Industrial/Retail/Social Infrastructure)
**As of**: 2026-09-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Charter Hall Long WALE REIT offers a compelling income yield of approximately 7.25% on a closing price of AUD 3.38, backed by a portfolio of long-WALE assets (~12 year WALE) leased to investment-grade and government tenants with near-100% occupancy. The CAPM alpha of 9.8% (Category B, subject to AUD/GBP currency basis noise vs IASP.L) indicates significant expected outperformance relative to CAPM-implied required return, even accounting for a negative IASP.L benchmark return over the trailing 5-year period. The OU Monte Carlo PGain of 76.4% at a 12-month horizon supports a moderate conviction position. Key constraint is distribution coverage tightness as elevated borrowing costs pressure AFFO, growth stalls (CLW trades below NTA), and cap rate re-rating in either direction remains the dominant risk factor. Charter Hall Group as sponsor provides strong governance and co-investment alignment.

## Quantitative Chain

- E(R): 0.0825
- Std dev: 0.1140
- P-gain: 0.7639
- CAPM alpha: 0.0979
- Beta: 0.6107
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA reverses easing cycle or cap rates re-expand 30-40bps driven by global rate shock; DPU cut of 8-10% as elevated debt refinancing costs compress distributable income; gearing breaches 40% triggering asset sales at distressed prices below NTA; occupancy dips to 96% as government tenants vacate and replacement leasing is delayed; AUD/GBP cross depreciates, amplifying benchmark divergence.
- **base**: E(R)=0.0820
  - Central case as built in quantitative chain: distribution yield 7.25%, DPU growth 1.5% p.a., multiple drag -0.5%. Occupancy stable at ~99%, WALE ~12 years, gearing ~37%. RBA easing continues gradually; borrowing cost pressure moderates. CLW trades at modest discount to NTA throughout period.
- **bull**: E(R)=0.2000
  - Accelerated RBA easing drives 50-75bps cap rate compression; NTA discount closes and CLW re-rates toward or above book value (~AUD 4.10-4.30 implied); DPU growth improves to 3-4% underpinned by CPI rent reviews beating expectations; Charter Hall sponsor injects accretive pipeline assets at 6%+ yield-on-cost; AUD strengthens, attracting foreign REIT capital.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0725 (Cat A) — Trailing DPU estimated at ~24.5 AUc per unit on closing price of AUD 3.38 as at 2026-09-18. CLW announced a price-sensitive distribution on 2026-09-16 (ASX DISTRIBUTION ANNOUNCEMENT, document 2924-03136119-2A1697448). FY2025 published DPU was ~24.7c; modest decline assumed given stalling growth noted in market commentary (SimplyWallSt, 14 Aug 2026). Yield = 24.5c / 338c = 7.25%.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed. CLW has a long WALE (~12 years) with majority fixed or CPI-linked rent reviews, providing downside protection. However, market commentary as at Aug 2026 flags growth stalling, elevated borrowing costs, and below-NTA trading. Growth assumption is below CPI and below historical trend. Sensitivity tested in scenario analysis. Category C: model assumption with disclosed basis.
- `multiple_change` = -0.005 (Cat C) — Modest cap rate / multiple drag of -0.5% assumed. CLW trades below NTA (confirmed in market commentary, SimplyWallSt 14 Aug 2026), implying modest negative reversion risk relative to intrinsic value. RBA easing cycle underway as of mid-2026 provides partial offset, but gearing near upper band of comfort constrains multiple re-rating. Net multiple change assumed -0.5% in base case. Category C assumption.
- `rba_cash_rate` = 0.0385 (Cat B) — RBA cash rate estimated at approximately 3.85% as at September 2026, based on publicly available RBA communications reflecting an easing cycle from the peak. APAC rates stored reader returned no data for AU at this as_of date; estimate sourced from market-implied consensus. Category B: disclosed methodology.
- `gearing_ratio` = 0.37 (Cat B) — CLW gearing estimated at ~37% of total assets based on publicly reported FY2025 figures and market commentary indicating gearing near but within the Australian REIT convention of <40%. Body capture for ASX annual report filing (2026-08-20) returned pipeline mismatch content; gearing figure is a Category B estimate from historical disclosures.
- `occupancy` = 0.99 (Cat B) — CLW has historically maintained near-100% occupancy (~99%) reflecting long WALE structure and government/investment-grade tenant base. This is a Category B estimate informed by historical filing disclosures; FY2026 actual not independently confirmed via filing body (ASX body capture returned mismatch content).
- `wale` = 12.0 (Cat B) — Weighted Average Lease Expiry estimated at approximately 12 years based on CLW's historical disclosures and REIT structure focused on long-WALE assets. Category B: derived from historical public disclosures.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP noise. The currency basis means the beta of 0.611 should be interpreted with caution as a standalone risk measure.

## Key Risks
- Elevated Australian borrowing costs (RBA cash rate ~3.85%) pressuring interest cover and AFFO distribution coverage, potentially forcing a DPU cut if refinancing costs exceed assumptions
- Continued trading below NTA with no near-term catalyst for discount closure, particularly if property cap rates remain elevated or expand further
- Beta of 0.611 vs IASP.L (GBP-denominated) absorbs AUD/GBP FX noise; actual property market beta may differ materially from reported coefficient
- Concentration in long-duration lease assets creates mark-to-market duration risk: a 25bps rise in long-bond yields could reduce NAV by ~3-5% depending on WALE and discount rate sensitivity
- ASX filing body capture returned pipeline mismatch content for CLW's annual report and distribution announcement filings; FY2026 DPU, gearing, and AFFO coverage could not be independently verified from filing text — key assumptions remain Category B/C estimates

## Invalidation Condition
Exit position if CLW announces a DPU reduction greater than 5% versus prior corresponding period for two consecutive half-yearly distributions, or if reported gearing exceeds 40% on a look-through basis for two consecutive reporting periods, or if WALE falls below 10 years due to material lease expiry or tenant default on a top-5 tenant, or if Charter Hall Group reduces its direct co-investment stake in CLW below 10% — any of these signals a structural deterioration in the income and capital value thesis.
