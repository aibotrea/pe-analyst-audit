# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-08-03_equity_reit_v1@1.0_5765bd0314a9`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Keppel DC REIT offers pure-play Singapore-listed data centre exposure underpinned by structural AI and cloud-driven demand, with a 5.2% trailing distribution yield providing meaningful carry above the 3.7% risk-free rate. The CAPM alpha of 5.0% (Category B, currency-basis caveat applies) and a PGain of 74.9% from the OU Monte Carlo are supportive. However, 1H 2026 saw an occupancy slide alongside income growth, introducing near-term uncertainty on portfolio stabilisation. Low beta of 0.28 versus IASP.L reduces systematic risk but management-fee unit issuance introduces mild dilution pressure that moderates conviction to a 3 (Moderate) rating.

## Quantitative Chain

- E(R): 0.0670
- Std dev: 0.0989
- P-gain: 0.7494
- CAPM alpha: 0.0504
- Beta: 0.2807
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy deteriorates further to sub-90% across Singapore and European assets, driving DPU cuts of 10–15%. Cap rate expansion of 50bps amid rate resurgence and data centre oversupply concerns (hyperscaler in-housing). Gearing rises toward 42% due to valuation compression, pressuring refinancing terms. Potential rights issue or DPU cut scenario.
- **base**: E(R)=0.0670
  - Central case as built in chain: annualised DPU of ~11.4c, 2.0% DPU growth, -0.5% multiple drag from modest cap rate expansion. Occupancy stabilises at current levels; Keppel sponsor supports pipeline. Gearing within 40% regulatory comfort zone.
- **bull**: E(R)=0.1800
  - AI-driven data centre demand surge accelerates AUM growth via accretive Keppel sponsor pipeline acquisitions at 6%+ NPI yield. Occupancy recovers to 96%+. SGD rate cuts compress risk-free rate, driving multiple re-rating. DPU growth of 4–5% pa over 2-year horizon.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0519 (Cat A) — 1H 2026 DPU of 5.714 cents per unit (1 Jan–30 Jun 2026) annualised to 11.428 cents, divided by current market price of SGD 2.20. Source: AJBU.SI 2026-07-23 CACT filing (capital distribution and cash distribution announcements).
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward annualised DPU growth assumption of 2.0%. Anchored by structural data centre demand tailwinds (AI/cloud), partially offset by occupancy softness reported in 1H 2026 and potential dilution from management fee units issuance. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Mild cap rate expansion headwind of -0.5% assumed given negative trailing IASP.L benchmark return (-3.5% annualised 5yr), occupancy slide in 1H 2026, and persistent higher-for-longer rate environment in SGD/USD. Tested in scenario analysis.
- `1h2026_dpu` = 0.05714 (Cat A) — Explicitly stated in AJBU.SI 2026-07-23 CACT filings: total distribution of 5.714 cents per unit for 1 Jan–30 Jun 2026, comprising taxable income 4.838c, tax-exempt 0.358c, capital distribution 0.518c.
- `occupancy_trend` = declining (Cat B) — News headline dated 2026-07-23 (reitsweek) references an occupancy slide in 1H 2026 concurrent with income growth. Specific occupancy figures not available from truncated filing body; classified Category B pending full results document review.
- `management_fee_alignment` = units_issued (Cat A) — SGX filing AJBU.SI 2026-08-03 (General Announcement: Payment of Management Fee by way of Issue of Units in Keppel DC REIT) confirms Q2 2026 management fee paid in units, aligned with unitholder interests.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Occupancy deterioration in 1H 2026 could persist if hyperscalers reduce co-location demand or negotiate lease renewals at lower rates
- Higher-for-longer SGD/USD interest rates compressing the DPU yield spread over T-bills and increasing refinancing costs
- Cap rate expansion driven by sustained negative APAC REIT benchmark returns (-3.5% annualised 5yr IASP.L) reducing NAV and unitprice
- Management fee payment in units creates incremental unit count dilution, capping DPU-per-unit growth
- Currency basis in beta estimate (SGD vs GBP-denominated IASP.L) introduces noise into the CAPM alpha signal; calibration is directional only (Phase 2 limitation)

## Invalidation Condition
Exit if occupancy falls below 88% for two consecutive half-year reporting periods, or if annualised DPU drops more than 10% from the current 11.4 cents run-rate without a clear recovery catalyst, or if aggregate leverage breaches 42% signalling heightened refinancing risk under the Singapore 45% regulatory cap.
