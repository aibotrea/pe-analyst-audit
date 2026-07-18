# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-07-16_equity_reit_v1@1.0_bef65b521a94`
**Ticker**: SGP.AX (Stockland Corporation Limited)
**Market**: Australia
**Sector**: Diversified REIT (Residential/Industrial/Workplace)
**As of**: 2026-07-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Stockland offers diversified Australian REIT exposure spanning residential communities, logistics/industrial, and workplace assets, with a current forward distribution yield of approximately 6.76% at AUD 4.08 — a meaningful spread above the 3.7% risk-free rate. The internally managed stapled structure provides direct management alignment, with FY26 DPU guidance maintained per the 3Q26 Operational Update as residential sales volumes improved. Beta of 0.83 versus IASP.L (AUD/GBP currency-basis caveat applies) reflects meaningful co-movement with the broader APAC REIT universe; annualised historical volatility of 24.9% is elevated relative to pure-play industrial peers, reflecting the residential development earnings mix. The OU Monte Carlo simulation yields a simulated return of 8.2% with a PGain of 68.6%, and CAPM alpha of +10.6% driven mechanically by the negative IASP.L benchmark return over the trailing 5-year period, supporting Moderate conviction at a 12-month horizon.

## Quantitative Chain

- E(R): 0.0830
- Std dev: 0.1695
- P-gain: 0.6862
- CAPM alpha: 0.1059
- Beta: 0.8288
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA re-accelerates rate hikes (rate shock/stagflation pathway), residential lot settlement volumes fall materially as affordability deteriorates; DPU cut to ~24-25 cps (~5-9% reduction); gearing rises above 32% as cap rate expansion of 50bps compresses NTA; multiple contracts sharply. Distribution coverage approaches 1.0x. Yield spread over risk-free narrows to near-zero.
- **base**: E(R)=0.0820
  - Central case as built in chain: DPU maintained at ~27.6 cps (flat YoY), yield of ~6.76%, 1.5% DPU growth assumption, neutral multiple change, gearing ~28%, residential communities recover gradually with RBA easing cycle, logistics and industrial provide organic rent uplift.
- **bull**: E(R)=0.2000
  - RBA cuts accelerate; residential lot settlement volumes surge; DPU upgraded to ~29-30 cps; logistics and data centre pipeline (SGP.AX 2026-03-02 PROGRESS REPORT headline) delivers accretive acquisitions at 5.5-6% yield; sector re-rating on falling rates compresses cap rates by 25bps driving NTA expansion; occupancy improves across workplace segment.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0676 (Cat A) — FY2026 DPU guidance of ~27.6 cents per security maintained per 3Q26 Operational Update (SGP.AX 2026-04-29 PERIODIC REPORTS headline). At closing price of AUD 4.08 on 2026-07-16, trailing/forward yield = 27.6/408 = 6.76%. Price is Category A (observed); DPU guidance is Category A (publicly filed ASX announcement).
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% per annum assumed: residential communities benefiting from gradual RBA easing cycle supporting lot settlements; logistics/industrial segment driving modest organic rent growth (~2-3%); workplace broadly flat. Blended 1.5% is a model assumption. Stockland held FY26 guidance flat YoY supporting a conservative growth rate. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumed over 12-month horizon. ASX property sector faces headwinds from elevated RBA cash rate environment and AI/rate fears cited in market commentary (Stocks Down Under, Feb 2026). Cap rate expansion risk broadly balanced by easing cycle expectations. Net assumption: 0% multiple change. Sensitivity: bear case assumes 50bps cap rate expansion; bull case assumes 25bps compression.
- `rba_rate_environment` = elevated_easing (Cat B) — RBA cash rate cycle entered easing phase per market commentary (Oct 2025, Feb 2026 news items). APAC rates data unavailable from stored source at as_of date; assessed qualitatively from news headlines. Rate trajectory is a key driver of residential lot settlement pace, gearing cost, and sector multiple.
- `gearing_ratio` = 0.28 (Cat B) — Stockland reported gearing estimated at ~27-28% based on FY2025 results context and publicly available guidance. ASX body capture failed for 1H26 Results Annexure (SGP.AX 2026-02-15 PERIODIC REPORTS, body_unavailable=True, Phase 01 v3.3 §4). Estimated below the Australian REIT convention 40% threshold. Treated as Category B given reliance on prior-period estimates.
- `distribution_coverage` = estimated_above_1x (Cat B) — Stockland is internally managed (stapled structure) with FFO payout ratio historically ~80-85%, implying distribution coverage above 1.0x AFFO. Body capture failed for 2H26 Estimated Distribution and DRP Update (SGP.AX 2026-06-22 DISTRIBUTION ANNOUNCEMENT, body_unavailable=True). Estimated coverage is Category B; gap disclosed in key_risks.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise. Correlation of 0.39 over 252 trading days indicates moderate co-movement with partial FX basis distortion.
- `data_availability_caveat` = disclosed (Cat B) — ASX filing body capture failed for 7 of 8 stored filings including the 1H26 Results Annexure, 3Q26 Operational Update, and 2H26 Distribution Announcement (body_unavailable=True, Phase 01 v3.3 §4 — ASX body capture parked). Key financials sourced from guidance headlines, news, and prior-period estimates. This gap is disclosed in key_risks.

## Key Risks
- RBA rate policy uncertainty: re-acceleration of hikes would suppress residential lot settlement volumes and compress the yield spread, directly threatening DPU guidance maintenance.
- ASX filing body capture unavailable for key FY2026 financial disclosures (1H26 Results Annexure, 3Q26 Update, 2H26 Distribution Announcement); exact gearing, FFO coverage, and WALE unconfirmed from primary filing sources at as_of date.
- High historical volatility (24.9% annualised) reflects residential communities earnings cyclicality, increasing Monte Carlo std_dev and capping PGain at 68.6% — below the typical high-conviction threshold.
- Data centre pipeline execution risk: capital allocation to a new asset class (announced SGP.AX 2026-03-02) introduces development and leasing risk not yet reflected in earnings guidance.
- IASP.L benchmark returned -3.5% annualised over 5 years, boosting computed CAPM alpha mechanically; this reflects a weak APAC REIT environment that may persist, limiting sector multiple re-rating potential.
- Calibration limitation: Phase 2 calibration is a directional signal, not a formal backtest. Vintage discipline arrives in Phase 5; this memo should not be treated as a validated point-in-time forecast.

## Invalidation Condition
Exit position if Stockland announces a downward revision to FY26 or FY27 DPU guidance below 25.0 cents per security, or if reported balance sheet gearing breaches 35% in any half-year results disclosure, or if residential lot settlement volumes decline for two consecutive quarterly operational updates without a credible recovery pathway, or if the RBA cash rate is raised above 5.0% signalling renewed tightening that would materially impair residential communities earnings and the sustainability of the current distribution level.
