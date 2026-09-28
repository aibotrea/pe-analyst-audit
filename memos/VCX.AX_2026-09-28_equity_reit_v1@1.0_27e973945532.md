# Specialist Memo — VCX.AX

**Memo ID**: `VCX.AX_2026-09-28_equity_reit_v1@1.0_27e973945532`
**Ticker**: VCX.AX (Vicinity Centres)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-09-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Vicinity Centres is Australia's second-largest retail REIT with a high-quality portfolio anchored by dominant sub-regional and premium centres including Chadstone. Trading at a ~12% discount to mid-2026 levels and at a modest discount to NTA, the implied distribution yield of ~5.3% offers a meaningful spread above the 3-month T-bill rate of 4.1%. Beta of 0.66 versus IASP.L (AUD/GBP currency basis caveat applies) indicates moderate co-movement with the APAC REIT universe. The OU Monte Carlo generates a simulated 12-month return of 7.2% with a PGain of 69.5%, consistent with a moderate conviction position. Key swing factor is the RBA easing path — a rate reduction cycle would compress retail cap rates and drive NTA recovery, while a higher-for-longer scenario would sustain spread compression pressure on the unit price.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1422
- P-gain: 0.6946
- CAPM alpha: 0.0898
- Beta: 0.6571
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Australian retail downturn driven by household balance sheet stress (mortgage cliff, elevated RBA cash rate). Occupancy falls to 95%, NPI growth turns negative (-1%), DPU cut of 8-10%, cap rate expansion of 50bps compresses NAV. Higher-for-longer rate environment (RBA cash rate stays above 4%) widens spread compression, price target ~AUD 1.90-2.00.
- **base**: E(R)=0.0730
  - Central case: DPU yield 5.3%, organic NPI growth 2.0%, neutral multiple change. Occupancy stable at 98.8%, gearing ~27% LVR, RBA begins easing cycle providing modest tailwind to cap rate compression. Price drifts toward NTA ~AUD 2.45-2.50 over 12 months.
- **bull**: E(R)=0.2200
  - RBA cuts rates 75-100bps, retail spending recovers strongly with consumer confidence rebound, positive re-leasing spreads accelerate to 8-10%, cap rate compression of 25-30bps drives NTA uplift. Chadstone and premium flagship assets command premium pricing. Price target AUD 2.70-2.80, DPU growth 3.5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.053 (Cat A) — Trailing DPU yield derived from current closing price of AUD 2.28 (2026-09-28) and publicly guided full-year DPU of approximately AUD 12.1 cents, consistent with Vicinity Centres FY2025 actuals and FY2026 guidance signals. Yield = 0.121 / 2.28 ≈ 5.3%. Observed market price is Category A; DPU figure carries minor Category B rounding given body capture failure for ASX filings.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflecting organic net property income growth from CPI-linked lease structures and positive re-leasing spreads in dominant sub-regional and premium retail centres. No acquisition growth included given no confirmed pipeline at as_of date. Sensitivity: bear case applies 0%, bull case applies 3.5%. Source: analyst assumption with reference to VCX historical NPI growth trajectory 2019-2025 and Australian retail CPI environment.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumption. VCX trades at a modest discount to last published NTA (~AUD 2.40-2.50 range implied by news signals). Price has corrected ~12% from July 2026 highs of ~2.70 to 2.28. Assumed mean-reversion potential offsets cap rate expansion risk, netting to zero multiple change over 12 months. Cap rate sensitivity is tested in scenario analysis.
- `gearing_lvr` = 0.27 (Cat B) — Vicinity Centres has historically maintained look-through gearing of approximately 24-28% LVR, well within ASIC/ASX A-REIT convention of <40%. Assumed 27% LVR as midpoint of stated target range based on Vicinity FY2025 disclosures. ASX filing body capture returned mismatched content (unrelated entities) for all VCX filings; this figure is sourced from publicly known fundamentals and is disclosed as Category B due to the data gap.
- `occupancy` = 0.988 (Cat B) — Vicinity Centres portfolio occupancy has consistently traded at 98-99% across its premium and sub-regional assets. Assumed 98.8% for the modelling period. Filing body capture unavailable for VCX at as_of date; assumption based on publicly known operational metrics and news signals confirming distribution is supported by retail property income.
- `asx_filing_body_gap` = disclosed (Cat B) — All 8 ASX filing bodies retrieved for VCX.AX contained mismatched content from unrelated entities (PENGANA, LUMOS DIAGNOSTICS, TECHGEN METALS, TERRAMIN, RareX, APA Group, Beamtree). No VCX-specific financial substance (DPU, AFFO coverage, gearing, occupancy) could be extracted from filing bodies. Key quantitative assumptions are sourced from publicly available fundamentals, news signals, and price data. This limitation is disclosed per §4 of the filing body protocol.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. The benchmark IASP.L annualised return of -4.7% over 5 years reflects both APAC REIT performance and AUD/GBP currency movements, and should not be interpreted as a clean estimate of property market returns.

## Key Risks
- Higher-for-longer RBA cash rate compressing the yield spread versus risk-free assets and applying cap rate expansion pressure on portfolio NTA
- Australian household consumption slowdown — mortgage cliff and cost-of-living stress reducing specialty retail tenant sales and re-leasing spreads
- E-commerce structural headwinds for discretionary specialty tenants, increasing vacancy risk in non-flagship centres
- ASX filing body data gap: no VCX-specific financial detail (AFFO coverage, exact gearing ratio, DPU quantum) was extractable from stored filings due to body capture mismatch; key assumptions carry higher Category B/C uncertainty than normal
- AUD/GBP currency basis in beta and market return estimates introduces noise into the CAPM framework; alpha of 8.9% should be interpreted cautiously

## Invalidation Condition
Exit position if Vicinity Centres reports portfolio occupancy below 96% for two consecutive half-year periods, or announces a distribution cut greater than 5% from FY2026 guided levels without a credible recovery pathway, or if look-through gearing rises above 35% LVR due to asset devaluations or debt-funded acquisitions at dilutive yields, or if the RBA raises rates by more than 50bps from the September 2026 level reversing the expected easing cycle.
