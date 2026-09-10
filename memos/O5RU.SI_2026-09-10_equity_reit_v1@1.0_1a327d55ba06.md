# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-09-10_equity_reit_v1@1.0_1a327d55ba06`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-09-10
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
AIMS APAC REIT offers an attractive industrial/logistics exposure straddling Singapore and Australia, trading at a trailing DPU yield of approximately 6.4% at SGD 1.440. The recent redemption of the S$250M 5.375% perpetual securities (replaced in part by a lower-cost S$100M 4.25% perp) and completion of the Perth Hazelmere industrial acquisition signal active capital management and AUM growth. Beta of 0.28 versus IASP.L (with SGD/GBP currency-basis caveat) implies materially lower systematic risk than the broad APAC REIT universe, while a CAPM alpha of ~6.0% and PGain of 76% from the OU Monte Carlo support an above-average conviction rating. The unsecured sustainability-linked loan transition further diversifies the funding base and improves balance sheet flexibility.

## Quantitative Chain

- E(R): 0.0740
- Std dev: 0.1043
- P-gain: 0.7595
- CAPM alpha: 0.0599
- Beta: 0.2778
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Occupancy falls below 90% driven by industrial demand softness in Singapore and slower-than-expected Perth ramp-up; DPU coverage drops below 1.0x AFFO as interest costs rise; cap rate expansion of 30-50bps on Singapore industrial assets; AUD/SGD depreciation reduces Perth contribution; SGD rates remain elevated, compressing yield spread. Bear case may be triggered by global macro deterioration or tenant default at a top-5 asset.
- **base**: E(R)=0.0740
  - Central case as built in quantitative chain: DPU yield ~6.4%, DPU growth 1.5%, multiple change -0.5%. Perth Hazelmere acquisition accretive at targeted yield; S$250M perp redemption and partial replacement at 4.25% reduces financing cost; occupancy stable ~95%; Singapore industrial demand supported by data centre and logistics tailwinds; SGD rates gradually easing.
- **bull**: E(R)=0.1800
  - Perth acquisition delivers above-targeted yield and is fully occupied; additional pipeline acquisitions from AIMS sponsor at accretive cap rates; Singapore industrial rents continue strong reversion cycle; S-REIT sector re-rating as interest rates fall materially, compressing cap rates by 20-30bps; AUD strengthens vs SGD boosting Australian portfolio contribution; DPU growth exceeds 3% p.a.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0639 (Cat A) — Trailing DPU yield derived from FY2026 actuals (year ending 31 March 2026). Published DPU estimated at ~9.2 SGD cents based on filed annual report (O5RU.SI 2026-06-26 ANNC: Annual Reports and Related Documents, period ended 31/03/2026) and Beansprout reporting of steady DPU growth; closing price SGD 1.440 on 2026-09-10. Yield = 0.092 / 1.440 = 6.39%.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. reflecting: (i) accretion from newly completed Perth industrial acquisition (398 Bushmead Road & 286 Stirling Crescent, Hazelmere; O5RU.SI 2026-08-05 ANNC), (ii) partial offset from equity dilution from equity fund raising (O5RU.SI 2026-08-05 ANNC: Use of Proceeds), and (iii) organic rental reversion potential from Singapore industrial portfolio. Sensitivity: bear -1.0%, bull +2.5%.
- `multiple_change` = -0.005 (Cat C) — Modest multiple contraction assumption of -0.5% reflecting persisting higher-for-longer SGD rate environment (US T-bill 3.81% as of 2026-09-09) and modest cap rate pressure. Positive offset from perp redemption (S$250M 5.375% called 1 Sep 2026, partially replaced by S$100M 4.25% perp; O5RU.SI 2026-07-31 CACT) improving financial flexibility. Net assumption: slight multiple headwind.
- `perp_securities_redemption` = disclosed (Cat A) — S$250M 5.375% subordinated perpetual securities called by issuer (HSBC Institutional Trust Services as trustee), pay date 1 September 2026 (O5RU.SI 2026-07-31 CACT). Partially replaced by S$100M 4.25% subordinated perpetual securities (O5RU.SI 2026-06-26 ANNC: Tax Ruling re S$100M 4.25% perp). Net reduction in perp cost burden is positive for distributable income.
- `gearing_regulatory_compliance` = est_34_to_36_pct (Cat B) — Aggregate leverage estimated at 34-36% of deposited property based on AIMS APAC REIT's historical gearing disclosures in quarterly and annual reports. Within Singapore MAS limit of 45% (50% with credit rating). Equity fund raising for Perth acquisition (O5RU.SI 2026-08-05 ANNC) suggests proactive leverage management. Exact post-acquisition gearing not available from filing bodies captured; estimated from filing context.
- `occupancy_rate` = 0.95 (Cat B) — Portfolio occupancy assumed ~95% based on historical disclosures from AIMS APAC REIT annual reports and investor presentations. Exact FY2026 figure from Annual Report (O5RU.SI 2026-06-26, period ended 31/03/2026) not extractable from filing body; estimated from prior periods and Maybank-REITAS-SGX investor presentation (O5RU.SI 2026-05-21 ANNC).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer SGD/USD interest rates compressing the yield spread versus the 3.81% T-bill rate and potentially re-pricing gearing costs at refinancing
- Post-equity-fund-raising dilution and slower-than-expected income accretion from the Perth Hazelmere industrial acquisition, particularly if AUD depreciates against SGD
- AIMS Financial Group sponsor concentration risk: as a smaller, non-conglomerate-backed manager, pipeline depth and financial capacity to support the REIT in a distressed scenario is more limited than peers
- Singapore industrial cap rate expansion driven by global rate resets or demand slowdown from electronics and data-centre sectors
- Backtest calibration limitation: Phase 2 calibration is a directional signal only; vintage discipline arrives in Phase 5 — conviction score may be revised upon full calibration

## Invalidation Condition
Exit position if portfolio occupancy falls below 91% for two consecutive reporting quarters, or if DPU coverage drops below 1.0x AFFO as disclosed in any quarterly or annual results, or if aggregate leverage breaches 42% of deposited property (approaching the MAS 45% regulatory limit), or if AIMS Financial Group materially reduces its unitholding or withdraws pipeline asset commitments to the REIT.
