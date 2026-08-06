# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-08-06_equity_reit_v1@1.0_293634cbec8b`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Healthcare/Social Infrastructure (Childcare)
**As of**: 2026-08-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Arena REIT is Australia's pre-eminent childcare and early learning infrastructure REIT, with an internally managed structure, near-100% occupancy, and a long-dated NNN lease book (WALE exceeding 15 years) providing exceptional income visibility. The June 2026 quarterly distribution of 4.8125 cents implies an annualised yield of ~5.96% at current prices — a meaningful spread over the 3.74% T-bill rate — underpinned by CPI-linked annual escalators on triple-net leases. At a beta of 0.49 versus IASP.L (currency-basis caveat applies), ARF exhibits significantly lower co-movement with the broader APAC REIT market, offering defensive characteristics in a volatile rate environment. The OU Monte Carlo simulation yields a base-case sim return of 8.40% with a PGain of 74.4%, and a CAPM alpha of 8.38% against an IASP.L benchmark that has delivered a negative five-year annualised return, supporting an above-average conviction score of 4.

## Quantitative Chain

- E(R): 0.0846
- Std dev: 0.1282
- P-gain: 0.7438
- CAPM alpha: 0.0838
- Beta: 0.4920
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA reverses course or rates stay higher for longer, driving cap rate expansion of 50–75bps; NAV declines ~8–12%. Childcare demand shock (policy funding cuts or affordability crisis) causes operator stress, DPU coverage falls below 1.0x AFFO, and distribution is trimmed by 10–15%. Occupancy softens to 95% from near-100%. Combined drag from yield re-pricing and capital loss yields a negative total return of approximately -6%.
- **base**: E(R)=0.0840
  - Central case as built in the quantitative chain: distribution yield 5.96%, DPU growth 2.5% (CPI-linked escalators), flat cap rates / NAV multiple. Occupancy remains near 99%, operator covenant is stable, and the RBA continues a measured easing cycle. Total return approximately 8.4%.
- **bull**: E(R)=0.2000
  - RBA cuts accelerate, driving 25–50bps cap rate compression and a 5–8% NAV uplift. Arena REIT announces accretive pipeline acquisitions from its development programme at yields above 6.0%. DPU growth surprises to the upside at 3.5%+ on CPI beat. Re-rating to a tighter cap rate regime rewards the defensive income profile with a total return of approximately 20%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0596 (Cat A) — Trailing annualised DPU derived from June 2026 quarterly distribution of 4.8125 cents per stapled security (annualised: 19.25 cents) divided by closing price of AUD 3.23 on 2026-08-06. Source: ASX distribution announcement 2026-07-29 and live closing price.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% pa assumed, consistent with CPI-linked annual rental escalators embedded in Arena REIT's NNN childcare lease structures (~2–3% pa historically). Sensitivity tested in scenario analysis. Terminal growth not modelled beyond the 12-month horizon.
- `multiple_change` = 0.0 (Cat C) — Flat cap rate / price-to-NAV multiple assumed over 12-month horizon. ARF has historically traded at a modest premium to NAV; RBA easing could provide upside but uncertainty around global rate trajectory warrants a neutral assumption. Sensitivity tested in scenario analysis.
- `expected_return_components` = 0.0846 (Cat B) — E(R) = distribution yield (5.96%, Category A) + DPU growth (2.50%, Category C) + multiple change (0.00%, Category C). Aggregated as a sum of components per the equity REIT framework.
- `leverage_gearing` = 0.22 (Cat B) — Arena REIT has reported gearing ratios in the approximately 20–25% range in recent periods, well below the Australian convention threshold of 40%. Derived from publicly available annual/interim reports and news coverage; specific figure from most recent ARF filings.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Childcare sector policy risk: Federal Government funding changes to the Child Care Subsidy could impair operator revenues and, in a tail scenario, challenge operator lease covenant quality.
- Sector concentration: ARF's portfolio is approximately 90%+ early learning / childcare assets — a material single-sector concentration that amplifies idiosyncratic policy and demographic risk.
- Interest rate risk: Although the RBA is in an easing cycle, a reversal or delay in rate cuts could compress the yield spread and drive cap rate expansion, reducing NAV.
- AUD/GBP currency-basis noise in beta: The 0.49 beta is measured against the GBP-denominated IASP.L benchmark and absorbs AUD/GBP FX co-movement, potentially overstating or understating true property-market sensitivity.
- Calibration limitation: This analysis is a directional signal; Phase 2 calibration lacks full vintage discipline (arriving Phase 5). Results should not be treated as a formal backtest.

## Invalidation Condition
Exit position if Arena REIT's portfolio occupancy falls below 95% for two consecutive reporting periods, or if the annualised DPU is cut by more than 5% from the current 19.25 cent run-rate, or if Australian Federal Government materially reduces Child Care Subsidy funding in a way that impairs top-10 tenant covenant quality, or if reported gearing exceeds 35% of total assets.
