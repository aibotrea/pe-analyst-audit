# Specialist Memo — APZ.AX

**Memo ID**: `APZ.AX_2026-09-18_equity_reit_v1@1.0_533ef026c7d7`
**Ticker**: APZ.AX (Aspen Group)
**Market**: Australia
**Sector**: Residential/Affordable Housing Land Lease
**As of**: 2026-09-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Aspen Group (APZ.AX) is a niche Australian REIT providing exposure to the affordable housing land lease and holiday park segments, underpinned by structural demand for low-cost residential accommodation. The current price of AUD 4.63 represents a meaningful pullback of approximately 27% from the February 2026 peak of AUD 6.36, presenting a potential re-entry opportunity with an estimated E(R) of 7.3% built from a 3.35% distribution yield and 4.5% DPU growth supported by rental indexation and accretive pipeline additions including the Adelaide Villas settlement in September 2026. However, exceptionally high annualised volatility of 34.1% translates to a Monte Carlo std_dev of 23.2% over 12 months, producing a PGain of only 62.2%, which combined with niche concentration risk, opacity from unavailable filed financials, and a negative 5-year IASP.L benchmark return of -5.1%, supports only a low conviction rating of 2 out of 5. Alpha of 11.1% versus IASP.L is noted but inherits GBP/AUD currency basis noise from the IASP benchmark mismatch and should not be relied upon independently.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.2316
- P-gain: 0.6220
- CAPM alpha: 0.1106
- Beta: 0.8569
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2000
  - Residential rental growth stalls or reverses as RBA rate cuts fail to materialise and housing affordability pressures reduce tenant demand. DPU coverage falls below 1.0x AFFO due to development cost overruns at Adelaide Villas and other pipeline assets. Multiple compression accelerates as the market prices in a sector de-rating similar to the Mar 2026 drawdown. Gearing breaches 40% LVR following debt-funded acquisitions. A macro shock amplifies drawdown given beta of 0.86 and underlying volatility of 34%.
- **base**: E(R)=0.0730
  - Central case as built in chain: distribution yield 3.35%, DPU growth 4.5% p.a. from rental growth and accretive pipeline, modest multiple compression -0.5%. Occupancy stable across land lease and holiday park portfolio. Adelaide Villas fully integrated. RBA holds or makes one rate cut, supporting residential property fundamentals.
- **bull**: E(R)=0.2800
  - RBA delivers multiple rate cuts stimulating residential property demand, driving occupancy improvements and above-consensus rental growth of 7%+ p.a. Development pipeline delivers accretive yields of 6%+, re-rating NTA upward. Multiple expansion recovers toward peak Feb 2026 levels as affordable housing narrative gains wider institutional interest. DPU upgraded significantly, making the current yield of 3.35% look deeply discounted ex-post.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0335 (Cat B) — Estimated trailing DPU of approximately AUD 0.155/unit (consensus-implied from prior FY disclosures and rental growth trajectory) divided by closing price of AUD 4.63 on 2026-09-18. No filed FY2026 financials available from stored filings (ASX body capture parked, Phase 01 v3.3 §4); yield is a derived estimate and therefore Category B.
- `dpu_growth_3yr` = 0.045 (Cat C) — Forward DPU growth assumption of 4.5% p.a. driven by: (1) residential rental growth in land lease and affordable housing segments (supported by news Sep 2026 flagging rental growth and development scale); (2) accretive pipeline additions including Adelaide Villas settlement (Sep 8, 2026 ASX announcement); (3) FY27 positive outlook per news sources Sep 2026. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Modest negative multiple change assumption of -0.5% reflecting mean reversion after extreme price run-up (AUD 2.08 Oct 2024 to AUD 6.36 Feb 2026 peak, now at AUD 4.63). Current trading at a discount to the Feb 2026 peak implies partial re-rating downside risk remains. Conservative assumption to reflect post-peak normalisation.
- `gearing_estimate` = ~30-35% LVR estimated (Cat B) — Estimated from historical Aspen Group balance sheet disclosures indicating LVR in the 30-35% range in prior periods. No FY2026 filed financials available from stored filings pipeline (ASX body capture parked); estimate based on prior disclosed figures. Assumed within AU REIT convention of less than 40% LVR.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis effect is particularly significant for a small-cap Australian REIT where AUD/GBP movements can materially distort the iasp-derived beta. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Extreme price volatility (34.1% annualised sigma) creates substantial drawdown risk — the stock declined approximately 27% from Feb to Sep 2026 already, and could revisit AUD 3.50-4.00 in a further de-rating episode.
- Niche affordable housing and land lease concentration with limited asset-class diversification; adverse government rental regulation or changes to residential park legislation in any Australian state could materially impair earnings.
- Filed financials unavailable (ASX body capture parked under Phase 01 v3.3 §4): gearing, AFFO coverage, WALE and occupancy metrics cannot be independently confirmed from stored filings as of this memo date, creating valuation opacity.
- Development and execution risk from active acquisition pipeline including Adelaide Villas and FY27 projects: cost overruns or delays could impair DPU coverage and trigger a negative re-rating.
- Macro sensitivity: as a small-cap AUD-denominated REIT with beta 0.86 vs IASP.L, the stock is sensitive to both domestic RBA rate settings and global REIT sentiment shifts; the 5-year APAC REIT benchmark has delivered -5.1% annualised, signalling a challenging broader sector backdrop.

## Invalidation Condition
Exit position if reported gearing (LVR) exceeds 40% for any two consecutive reporting periods without a credible deleveraging plan disclosed to ASX, or if DPU is cut by more than 15% relative to FY2026 actuals signalling AFFO coverage breakdown, or if the unit price declines below AUD 3.50 on a closing basis for three consecutive trading days indicating further multiple compression beyond the bear case, or if any ASX announcement discloses a material adverse change to the Adelaide Villas development or other pipeline assets including abandonment or cost overrun exceeding 20% of project budget.
