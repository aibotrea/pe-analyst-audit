# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-07-17_equity_reit_v1@1.0_826415829888`
**Ticker**: SGP.AX (Stockland Corporation Limited)
**Market**: Australia
**Sector**: Diversified REIT (Residential Communities / Logistics / Workplace / Data Centres)
**As of**: 2026-07-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Stockland offers diversified Australian property exposure with a 6.5% distribution yield supported by reaffirmed guidance for 2H26, conservative gearing (~28%, well below the 40% AU convention), and an emerging data centre pipeline (AUD $3bn+ Melbourne project) that provides longer-dated growth optionality. The stock has de-rated approximately 29% from its August 2025 high of AUD 5.88 to AUD 4.15, creating a valuation entry point. CAPM alpha of 10.75% versus IASP.L (subject to AUD/GBP currency-basis caveat) signals meaningful expected excess return relative to the APAC REIT benchmark. The OU Monte Carlo simulation generates a PGain of 69% at a 12-month horizon, consistent with moderate conviction; the principal risk is the MPC segment's cyclicality and the elevated annualised volatility of 25%, which reflects SGP's mixed-use REIT structure with significant development exposure rather than pure income-REIT dynamics.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1698
- P-gain: 0.6900
- CAPM alpha: 0.1075
- Beta: 0.8360
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - RBA easing stalls or reverses; Australian residential market softens materially with MPC sales volumes falling >20% YoY; cap rate expansion of 50bps compresses NTA by ~10%; gearing rises toward 35%; distribution cut of 10-15%; data centre pipeline write-downs on cost overruns. This pathway also captures a broader risk-off scenario where AUD weakness relative to GBP amplifies beta losses versus IASP.L benchmark.
- **base**: E(R)=0.0840
  - Central case as modelled: distribution yield 6.5%, DPU growth 2.0%, flat cap rates, gearing stable ~28%. RBA eases modestly; MPC volumes stabilise; logistics and workplace segments contribute stable income; data centre pipeline progresses to planning approval stage without material capital commitment.
- **bull**: E(R)=0.2500
  - RBA cuts rates aggressively (100bps+), re-igniting Australian housing demand and MPC volumes; DPU growth exceeds 4%; cap rate compression of 25bps drives NAV re-rating; data centre partnership announced with a hyperscaler providing accretive yield-on-cost; stock re-rates from current ~29% discount to 12-month highs back toward AUD 5.50+.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat A) — Trailing/current DPU estimate ~AUD 27c annualised at current price of AUD 4.15 implies ~6.5% distribution yield. Stockland reaffirmed 2H26 distribution guidance per ASX price-sensitive announcement 2026-06-22 (SGP.AX DISTRIBUTION ANNOUNCEMENT: '2H26 Estimated Distribution and DRP Update'). Body of filing unavailable (ASX body capture parked per Phase 01 v3.3 §4); yield calculated from headline and price. Published reaffirmation of guidance treated as Category A observable.
- `dpu_growth_1yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0%: RBA easing cycle supports lower funding costs; logistics and workplace segments contribute stable organic growth ~1-1.5%; masterplanned communities (MPC) recovery in FY2026/27 contributes incrementally. Data centre pipeline (AUD $3bn+ Melbourne project, per Green Street News 2026-05-27) is longer-dated optionality. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Central case assumes flat cap rate / multiple expansion. SGP trades at a material discount to 12-month highs (~29% below AUD 5.88 peak of Aug 2025). Market re-rating risk remains given macro uncertainty. Bull scenario allows modest re-rating; bear scenario incorporates further de-rating.
- `gearing_ratio` = 0.28 (Cat B) — Stockland's reported gearing was in the 27-29% range as of FY2025 results (derived from publicly available annual report disclosures). Well below the Australian REIT conventional limit of ~40%. ASX filing bodies for recent periods unavailable (Phase 01 v3.3 §4 — body capture parked for ASX). Category B as derived from prior period disclosures without in-period body verification.
- `rba_rate_environment` = easing (Cat B) — RBA cash rate directional signal. Live get_apac_rates returned no data for AU. Based on publicly available context as of mid-2026, the RBA had commenced an easing cycle, reducing rates from the 4.35% peak. Exact current rate unavailable via tool; treated as qualitative supporting input only, Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency basis noise. IASP.L is the FTSE EPRA/NAREIT Asia Developed index quoted in GBP.

## Key Risks
- Masterplanned Communities (MPC) segment cyclicality: residential settlement volumes are sensitive to interest rates, consumer confidence, and housing affordability — a deteriorating macro backdrop could reduce DPU coverage and trigger a distribution cut.
- High annualised volatility (25%) reflects SGP's development-heavy model; this is materially above typical pure-play income REITs and compresses the risk-adjusted return profile.
- Data centre pipeline ($3bn+ Melbourne project) carries execution, capital allocation, and yield-on-cost risk; early-stage development may dilute near-term FFO before income streams are established.
- AUD/GBP and AUD/USD FX movements affect both NAV comparability and beta calculation against GBP-denominated IASP.L benchmark; a strengthening AUD could mask or amplify returns in benchmark-relative terms.
- ASX filing body capture was unavailable for all recent material filings (distribution announcement, 3Q26 operational update, data centre update); exact DPU coverage ratio, WALE, and occupancy data could not be sourced from filings and are disclosed as data gaps in this analysis.

## Invalidation Condition
Exit position if Stockland announces a distribution cut exceeding 10% versus prior corresponding period DPU, or if reported gearing rises above 37% for one or more consecutive reporting periods, or if the MPC segment reports settled lot volumes declining more than 25% year-on-year for two consecutive quarters, signalling structural rather than cyclical demand weakness, or if management formally abandons or materially delays the data centre pipeline while simultaneously guiding to lower-than-previously-flagged FY27 FFO per unit.
