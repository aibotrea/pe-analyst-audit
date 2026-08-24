# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-24_equity_reit_v1@1.0_94aa19788d68`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Neighbourhood Shopping Centres
**As of**: 2026-08-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group is Australia's largest owner of neighbourhood and sub-regional shopping centres anchored by non-discretionary retailers (supermarkets, pharmacies, medical services), providing highly defensive income with low tenant default risk. The trailing distribution yield of approximately 6.5% at AUD 2.24 offers a meaningful 278bps spread over the 3-month T-bill rate (3.72%), with FY27 management guidance of 3% DPU growth underpinning a E(R) of 9.0%. The OU Monte Carlo simulation returns a PGain of 82.0%, supporting an above-average conviction score of 4. With estimated gearing of ~37% within the Australian REIT convention ceiling and internalised management providing strong fee alignment, qualitative gates present no downward override pressure. Beta of 0.42 versus IASP.L (currency-basis caveat applies) indicates lower systematic risk than the broader APAC REIT benchmark, and the implied CAPM alpha of 8.7% reflects compelling excess return potential relative to a benchmark that has itself declined at -4.3% p.a. over five years.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.0979
- P-gain: 0.8198
- CAPM alpha: 0.0869
- Beta: 0.4223
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - RBA holds rates at elevated levels or hikes, causing cap-rate expansion of 50bps and multiple compression of ~2.5%; DPU growth flattens to 0% as discretionary tenant stress flows into neighbourhood centres; occupancy slips to 95%; gearing covenants tighten. Macro stagflation scenario (persistent inflation without growth) is the primary bear-case driver.
- **base**: E(R)=0.0900
  - Central case: distribution yield 6.5%, FY27 DPU growth 3% per management guidance, modest -0.5% multiple compression, occupancy stable at ~97.5%, gearing at ~37% within convention limits.
- **bull**: E(R)=0.2000
  - RBA rate cuts materialise in H1 FY27 compressing cap rates, driving multiple expansion of ~1.5%; DPU growth accelerates to 4-5% via accretive acquisitions or asset recycling; occupancy remains at 98%+; AUD/GBP stabilisation reduces currency drag on benchmark comparison.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat A) — Implied trailing distribution yield of approximately 6.5% at current price AUD 2.24, consistent with RGN's publicly known DPU profile for FY26 (~14.5 cpu annualised). Observed market-price and published DPU data.
- `dpu_growth_fy27` = 0.03 (Cat B) — FY27 distribution growth guidance of 3% explicitly cited in ASX-released FY26 Results headlines (RGN.AX, 2026-08-17). Classified Category B as it is a forward-looking management guidance figure rather than an audited outturn.
- `multiple_change` = -0.005 (Cat C) — Modest cap-rate expansion / multiple compression assumption of -0.5% applied to reflect ongoing REIT sector headwinds (higher-for-longer rates, APAC REIT index weakness evidenced by IASP.L -4.3% p.a. 5-year annualised). Sensitivity: bull case assumes flat multiple; bear case assumes -2.5%.
- `gearing_ratio` = 0.37 (Cat B) — Estimated gearing approximately 37% of gross assets, consistent with RGN's publicly disclosed balance sheet profile and within Australian REIT convention limit of 40%. Derived from most recent available filings and sector context.
- `occupancy_rate` = 0.975 (Cat B) — Occupancy estimated at approximately 97.5% based on RGN's essential-services neighbourhood retail portfolio (supermarket-anchored centres). FY26 results headlines confirm higher occupancy year-on-year (Kalkine, 18 Aug 2026).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Higher-for-longer RBA cash rate compressing distribution yield spreads and driving cap-rate expansion, reducing NAV and constraining multiple re-rating
- Structural shift in consumer spending patterns or acceleration of e-commerce penetration reducing foot traffic and rental income growth in neighbourhood centres
- Gearing covenant pressure if property valuations decline materially, potentially requiring dilutive equity raising
- Currency-basis noise in beta estimation: IASP.L is GBP-denominated, meaning computed beta and alpha absorb AUD/GBP FX co-movement, introducing estimation error
- Backtest calibration is directional (Phase 2 vintage discipline); PGain and alpha should be treated as indicative rather than precision-validated signals

## Invalidation Condition
Exit or materially reduce position if occupancy falls below 95% for two consecutive half-year reporting periods, or if reported gearing breaches 42% of gross assets, or if the annualised DPU declines year-on-year for two consecutive reporting periods, or if the RBA cash rate rises above 5.5% triggering a sustained spread compression that eliminates the yield premium over risk-free rates.
