# Specialist Memo — GPT.AX

**Memo ID**: `GPT.AX_2026-09-28_equity_reit_v1@1.0_8a3fd1fdd5ba`
**Ticker**: GPT.AX (The GPT Group)
**Market**: Australia
**Sector**: Diversified REIT (Retail/Logistics/Office)
**As of**: 2026-09-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
GPT Group offers diversified Australian real estate exposure across logistics, retail, and office at a trailing distribution yield of approximately 5.6%, representing a spread of ~150bps over the RBA cash rate. The OU Monte Carlo simulation returns an annualised expected return of 7.0% with a PGain of 69.2%, consistent with a moderate probability of positive outcome but constrained by elevated annualised volatility of 20.6%. Conviction is held at Low (2/5) reflecting the structural headwind from GPT's material office exposure (~30% of portfolio) in an environment of ongoing CBD vacancy pressure, as well as the higher-for-longer rate risk that limits cap rate compression. CAPM alpha of 9.7% is artificially elevated by the negative benchmark return (IASP.L 5-year annualised return of -4.7%) and should be interpreted with caution given the AUD/GBP currency-basis noise inherent in the beta estimate.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1401
- P-gain: 0.6923
- CAPM alpha: 0.0971
- Beta: 0.7630
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office vacancies accelerate to 20%+ in GPT CBD assets driving material DPU cut; RBA holds rates higher-for-longer compressing yield spread; cap rates expand 50bps across retail and logistics offsetting income; overall DPU coverage falls below 1.0x AFFO. Bear case also contemplates a broader A-REIT sector de-rating if global rate shock materialises.
- **base**: E(R)=0.0710
  - Central case as built: distribution yield 5.6%, DPU growth 2.0%, multiple change -0.5%. Logistics and retail outperform; office stable at current occupancy. RBA gradually eases providing modest yield-spread support. Value-add Partnership expansion (announced Sept 2026) contributes modestly to AUM growth.
- **bull**: E(R)=0.1800
  - RBA easing accelerates, compressing cap rates 25-30bps across portfolio; office occupancy stabilises or improves as CBD demand recovers post-2026; logistics rents grow 4%+ driven by e-commerce; value-add Partnership generates accretive acquisitions above 6% yield-on-cost; multiple expansion adds 2-3% to total return.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.056 (Cat A) — Implied trailing distribution yield derived from AUD ~0.248 annualised DPU (H1 2026 distribution announcement filed ASX 2026-08-16) divided by closing price AUD 4.43 on 2026-09-28. Published distribution figure; Category A.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed based on logistics/retail organic rent escalation (~2.5% CPI-linked) partially offset by ongoing office leasing headwinds (~30% of portfolio). Sensitivity tested in scenario analysis. No consensus forward DPU available from stored data.
- `multiple_change` = -0.005 (Cat C) — Slight cap-rate expansion assumption of -0.5% contribution to total return reflecting higher-for-longer RBA rate environment and office sector re-pricing risk. Category C model assumption.
- `gearing_ratio` = 0.28 (Cat B) — GPT Group gearing estimated at approximately 28% look-through (within AU <40% convention). Based on GPT's reported leverage profile from 2026 Interim Result (ASX headline 2026-08-16 'GPT announces its 2026 Interim Result'). Derived estimate — exact figure not extractable from stored filing bodies (ASX body capture returned mismatched content for this ticker).
- `rba_cash_rate` = 0.035 (Cat B) — RBA cash rate assumed approximately 3.5% as of September 2026. Live APAC rates API returned empty for AU; estimate based on publicly known RBA easing trajectory from 4.35% peak. Category B derived estimate.
- `office_portfolio_headwind` = material (Cat B) — GPT office portfolio (~30% of total assets by book value) faces elevated vacancy risk in CBD markets. ASX headline 2026-09-24 Motley Fool comparison article notes GPT vs Dexus value debate; Kalkine Sept 2026 industrial property article flags office as a watchpoint. Treated as Category B qualitative assessment.
- `asx_filing_body_gap` = disclosed (Cat B) — ASX stored filing bodies returned mismatched content (bodies from unrelated issuers). This is a known Phase 01 v3.3 pipeline limitation for ASX tickers. DPU, gearing, and occupancy figures rely on headline-level data and publicly known GPT fundamentals. Disclosed as a data-quality gap.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Office portfolio (~30% of assets) faces structural demand headwinds with elevated CBD vacancy; sustained underperformance could force DPU cuts and discount-to-NAV widening
- Higher-for-longer RBA rates compressing the yield spread versus T-bills (currently ~150bps), reducing relative attractiveness versus fixed income alternatives
- Cap rate expansion risk across retail and logistics if global long-end yields rise, pressuring book values and reported NTA
- ASX filing body data quality gap: stored pipeline returned mismatched content, limiting ability to verify exact H1 2026 DPU, AFFO coverage, and gearing figures from primary filings
- Beta estimate of 0.76 absorbs AUD/GBP FX co-movement versus IASP.L; true property-market beta may differ materially, making CAPM alpha an unreliable standalone signal

## Invalidation Condition
Exit or reduce position if GPT Group announces a DPU cut of more than 5% from the H1 2026 run-rate, or if reported gearing breaches 35% on a look-through basis, or if office portfolio occupancy falls below 85% for two consecutive reporting periods, or if RBA cash rate rises above 4.5% reversing the current easing trajectory.
