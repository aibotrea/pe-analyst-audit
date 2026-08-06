# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-06_equity_reit_v1@1.0_cde06118380b`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Convenience
**As of**: 2026-08-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group is Australia's pre-eminent convenience retail REIT, owning approximately 100 grocery-anchored neighbourhood and sub-regional shopping centres with Woolworths and Coles as anchor tenants — providing highly defensive income backed by non-discretionary consumer spending. At AUD 2.41, the trailing distribution yield of approximately 6.0% offers a compelling ~250bp spread over the RBA cash rate within a rate-easing environment, while the 14.2% annualised volatility is comfortably below the broader REIT sector. The OU Monte Carlo simulation generates a simulated return of 7.96% with PGain of 79.5% and a CAPM alpha of 7.55% (noting IASP.L currency-basis caveat), supporting an above-average conviction score. Internalised management and conservative gearing (~32%) further underpin the risk-adjusted return profile.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.0967
- P-gain: 0.7946
- CAPM alpha: 0.0755
- Beta: 0.4417
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA rate-cut cycle stalls or reverses due to renewed inflation, compressing RGN's yield spread and driving cap rate expansion of 25-50bps. Occupancy softens to 94% as specialty tenants exit amid consumer spending weakness. DPU coverage falls toward 1.0x AFFO, forcing a distribution cut of ~5%. Total return deteriorates to approximately -6% including a 10-12% price correction partially offset by the distribution.
- **base**: E(R)=0.0800
  - Central case as modelled: 6.0% distribution yield, 2.0% DPU growth, flat cap rates and NTA. Occupancy stable at ~97% (grocery-anchored resilience). RBA cash rate around 3.25-3.50%, providing a ~250bp yield spread. No major acquisition or divestment activity.
- **bull**: E(R)=0.1800
  - RBA cuts further toward 2.75%, compressing cap rates by 15-25bps and driving NTA uplift. DPU growth accelerates to 3.5% from stronger specialty rental reversion and bolt-on acquisitions. Investor re-rating of convenience retail REITs as a defensive income class pushes unit price toward AUD 2.65-2.75, generating total return of approximately 18%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.06 (Cat A) — Trailing distribution yield estimated at ~6.0% based on RGN's observable published DPU of approximately 14.5c per annum at the current market price of AUD 2.41 (ASX distribution announcement filed 2026-06-16; body capture unavailable for precise FY26 DPU confirmation, so headline figure used as Category A proxy from prior-year published DPU). Price observed as Category A on 2026-08-06.
- `dpu_growth_3yr` = 0.02 (Cat C) — Organic DPU growth of 2.0% per annum assumed, reflecting CPI-linked rental escalations (~2-3%) typical in RGN's convenience retail leases and modest specialty rental reversion. No major accretive acquisition pipeline identified in announcements to supplement growth. Sensitivity: bear case 0%, bull case 3.5%.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change/cap rate contribution assumed. RGN trades at approximately NTA (historically AUD 2.40-2.60 range). No clear catalyst for re-rating or de-rating at current levels. June 2026 property valuations update filed (body capture failed) limits NAV precision; neutral assumption applied.
- `gearing_ratio` = 0.32 (Cat B) — Estimated gearing ratio of approximately 32% based on historical reported figures and prior disclosures. Within Australian REIT convention of <40%. Body of FY26 periodic report unavailable (ASX body capture parked per Phase 01 v3.3 §4); estimate derived from trajectory of prior half-year disclosures.
- `rba_cash_rate` = 0.035 (Cat B) — RBA cash rate estimated at approximately 3.5% as of August 2026 reflecting the easing cycle that commenced in early 2025. Live APAC rate query returned no data; estimate based on publicly available RBA meeting decisions through mid-2026. Influences yield-spread attractiveness assessment.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP.L is the FTSE EPRA/NAREIT Asia Developed Real Estate Index.

## Key Risks
- Inflation re-acceleration preventing further RBA rate cuts, compressing the yield spread and triggering cap rate expansion that erodes NTA
- Consumer spending deterioration weakening specialty tenant sales performance, leading to higher vacancy and reduced rental reversion
- Concentration risk: Woolworths and Coles collectively represent a significant portion of gross rent; any material deterioration in anchor tenant credit or lease renewal risk could impair cash flows
- FY26 property valuations body unavailable — precise NTA and cap rate movements could not be confirmed; cap rate assumptions carry elevated uncertainty (Category C)
- IASP.L benchmark currency basis inflates measured alpha; the AUD/GBP FX co-movement embedded in beta and alpha is a structural limitation of this framework applied to an AUD-denominated REIT

## Invalidation Condition
Exit or reduce position if RGN reports two consecutive half-year periods of occupancy below 95% (from a current base of ~97%), DPU coverage falling below 1.0x AFFO for two consecutive reporting periods, gearing breaching 38% of total assets, or a formal announcement of a dilutive equity raise exceeding 10% of units on issue that is not demonstrably accretive to NTA and DPU.
