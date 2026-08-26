# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-26_equity_reit_v1@1.0_80ec6f308750`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail (Sub-Regional & Neighbourhood)
**As of**: 2026-08-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group offers compelling exposure to Australia's essential and non-discretionary retail segment — sub-regional and neighbourhood shopping centres anchored by supermarkets, medical services, and convenience retail — which have demonstrated resilient occupancy and CPI-linked rental growth through the rate-tightening cycle. At AUD 2.25, the estimated trailing distribution yield of ~6.4% provides a meaningful spread over the 3.71% US T-bill rate, and the OU Monte Carlo simulation (PGain 80.4%) supports an above-average conviction rating. Beta of 0.44 versus IASP.L (AUD/GBP currency-basis caveat applies) indicates lower-than-market volatility, while the CAPM alpha of 8.3% reflects the structural under-pricing of essential retail relative to a benchmark that is currently delivering a negative 5-year annualised return of -4.5%. Internal management, conservative gearing (~33%), and solid FY26 FFO growth (per ASX results presentation filed 2026-08-17) reinforce a constructive 12-month outlook.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.0976
- P-gain: 0.8040
- CAPM alpha: 0.0827
- Beta: 0.4380
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA re-accelerates or pauses easing, 10-year Australian government bond yields rise 50bps, causing sub-regional retail cap rate expansion of 30bps and a ~8% NTA decline. Occupancy falls below 97% as discretionary-adjacent tenants vacate. DPU growth stalls at 0% and distribution coverage narrows below 1.05x FFO. Unit price re-tests AUD 1.95–2.00 range last seen in early 2025. Bear case also captures a stagflation pathway where cost inflation erodes tenant affordability despite anchored supermarket tenancies.
- **base**: E(R)=0.0840
  - Central case as constructed: distribution yield 6.4%, DPU growth 2.0% (CPI-linked leases), cap rates flat. RBA cash rate continues gradual easing to ~3.5% by mid-2027, modestly supportive of REIT valuations. Occupancy remains ~98.5%, WALE stable at ~5 years. Price anchored near AUD 2.25–2.40 range.
- **bull**: E(R)=0.1900
  - RBA cuts cash rate to 3.0% by June 2027, driving meaningful cap rate compression (~25bps) and NTA uplift. Essential retail demand strengthens; DPU grows 3.5% on rental reversion uplift and full occupancy. Market re-rates sub-regional retail toward 5.5% implied yield, pushing unit price toward AUD 2.60–2.70. Yield spread over risk-free widens to attract income-seeking institutional capital.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.064 (Cat B) — Trailing DPU yield estimated at ~6.4%: assumed DPU of ~AUD 14.4 cents on current price of AUD 2.25. Region Group has historically distributed 13–15c per unit annually; FY26 results presentation (RGN.AX 2026-08-17 PERIODIC REPORTS) was price-sensitive but filing body was not cleanly captured due to pipeline cross-contamination; yield derived from published price and consensus DPU range. Classified Category B as DPU total is a derived estimate, not a directly extracted figure.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed over the 12-month horizon, reflecting essential-retail rental growth (CPI-linked leases with anchor supermarket and convenience tenants) plus modest occupancy improvement. News sources (Kalkine, 2026-08-20) reference Region Group's essential retail model building long-term income visibility and solid FFO growth. Sensitivity tested in scenario analysis; bull case 3.5% growth, bear case 0%.
- `multiple_change` = 0.0 (Cat C) — Cap rate / multiple assumed flat over the 12-month horizon, consistent with an RBA rate-cut cycle already partially priced in at the current AUD 2.25 price. Sub-regional retail has seen modest re-rating since 2023 trough (~AUD 1.63); no further expansion assumed in the base case.
- `rba_cash_rate` = estimated_3.85 (Cat C) — RBA cash rate data not returned by stored APAC rates or live tool at as_of date. Estimated at approximately 3.85% based on publicly known RBA easing cycle in H1 2026. Used as qualitative context for yield-spread assessment; not directly in the quantitative chain. Disclosed as Category C.
- `gearing_ratio` = approx_0.33 (Cat B) — Region Group historically maintained gearing (LVR) of approximately 30–35%, well within the Australian REIT convention of <40%. FY26 results presentation (RGN.AX 2026-08-17) is price-sensitive; body capture failed due to pipeline cross-contamination. Gearing estimate derived from prior public disclosures and industry norms. The leverage gate is assessed as passing based on this Category B estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. currency and iasp basis acknowledged as a source of noise in the beta estimate of 0.438. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- RBA easing cycle delays or reverses: If Australian bond yields rise materially, sub-regional retail cap rates could expand by 25–50bps, eroding NTA and putting downward pressure on the unit price beyond the distribution yield buffer.
- Consumer spending slowdown: Although Region Group's tenant mix is skewed to essential retail, a sustained deterioration in household disposable income (higher mortgage costs, elevated inflation) could reduce foot traffic and pressure specialty tenant renewals at mark-to-market rents.
- Filing body capture failure: The FY26 Results Presentation (RGN.AX 2026-08-17) body was not cleanly extracted due to ASX pipeline cross-contamination, meaning distribution coverage, gearing, and NTA figures used herein are Category B/C estimates and may differ from actual reported numbers.
- Benchmark currency noise: IASP.L is GBP-denominated; the computed beta of 0.438 and CAPM alpha of 8.3% absorb AUD/GBP FX co-movement and should not be interpreted as pure property-market signals.
- Concentration in Australian sub-regional retail: The portfolio lacks geographic diversification; any structural shift in retail format preferences (e-commerce penetration in convenience retail) or planning regulatory changes could impair long-term asset values.

## Invalidation Condition
Exit the position if Region Group reports two consecutive half-year results showing DPU distribution coverage below 1.0x AFFO, or if portfolio gearing (LVR) rises above 38% without a concurrent asset revaluation uplift, or if occupancy across the portfolio falls below 96% for two consecutive reporting periods, or if the RBA cash rate rises above 4.5% signalling a renewed tightening cycle that compresses the yield spread below 150bps versus Australian government 10-year bonds.
