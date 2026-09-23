# Specialist Memo — COF.AX

**Memo ID**: `COF.AX_2026-09-23_equity_reit_v1@1.0_04f8287c1938`
**Ticker**: COF.AX (Centuria Office REIT)
**Market**: Australia
**Sector**: Office
**As of**: 2026-09-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Centuria Office REIT (COF.AX) offers an elevated distribution yield of approximately 9.3% at the current AUD 0.865 unit price, supported by a metropolitan and suburban Australian office portfolio with 91% occupancy as at FY26 results, showing signs of stabilisation. However, persistent structural headwinds — sub-lease oversupply, tenant-flight-to-quality toward CBD premium assets, and higher-for-longer refinancing costs — create material risks to DPU sustainability and NTA. Beta of 0.52 versus IASP.L (AUD/GBP currency basis embedded) indicates moderate co-movement with the APAC REIT universe, while annualised historical volatility of 18.6% reflects meaningful unit price risk at this stage of the office cycle. The OU Monte Carlo PGain of 67.3% is constructive but insufficient to overcome qualitative concerns on distribution coverage, external management alignment, and filing data quality, resulting in a Low conviction score.

## Quantitative Chain

- E(R): 0.0575
- Std dev: 0.1267
- P-gain: 0.6733
- CAPM alpha: 0.0637
- Beta: 0.5181
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Occupancy declines from 91% to 85% due to accelerating lease expiries and tenant downsizing in metro office markets; DPU cut of 15-20% drives coverage below 1.0x AFFO; cap rate expansion of 50bps compresses NTA further and widens discount by 8-10%; gearing approaches 40% covenant, potentially forcing distressed asset sales. Macro overlay: prolonged RBA higher-for-longer regime spikes refinancing costs and accelerates income erosion.
- **base**: E(R)=0.0570
  - Central case as built in quantitative chain: distribution yield ~9.25%, DPU growth -2.0% per annum, multiple change -1.5%. Occupancy stable at ~91%, gearing contained at ~36%, cap rates broadly flat. Modest RBA easing provides incremental refinancing relief.
- **bull**: E(R)=0.2200
  - Australian office demand recovery driven by return-to-office mandates lifts occupancy to 94-95%; DPU flat-to-modestly-positive; cap rate compression of 25bps as RBA cuts accelerate; persistent discount-to-NTA narrows materially, contributing 6-8% positive multiple expansion. Centuria Capital executes accretive asset recycling above book value.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0925 (Cat B) — Estimated trailing DPU of ~8.0 cpu annualised divided by observed closing price of AUD 0.865 on 2026-09-23. DPU estimate derived from COF FY26 Results Announcement (COF.AX 2026-08-03 PERIODIC REPORTS) headline and news context indicating FY26 stabilisation. Filing body text was unavailable/mismatched in data pipeline; DPU is analyst-estimated. Category B — derived estimate with disclosed methodology.
- `dpu_growth_3yr` = -0.02 (Cat C) — Forward DPU growth of -2.0% per annum reflecting ongoing Australian office market headwinds: elevated sub-lease supply in metro markets, tenant-flight-to-quality, and leasing incentive pressure. Sensitivity: bull case assumes flat DPU; bear case assumes a further 15-20% cut. Based on COF FY26 Results Announcement headline and news indicating 91% occupancy stabilisation (COF.AX 2026-08-03 PERIODIC REPORTS).
- `multiple_change` = -0.015 (Cat C) — Cap rate expansion headwind assumed at -1.5% contribution to total return, reflecting persistent discount-to-NTA for Australian office REITs and risk of further cap rate expansion in suburban/metro office assets amid a higher-for-longer rate environment. Sensitivity tested across bear/base/bull scenarios.
- `occupancy` = 0.91 (Cat A) — Portfolio occupancy of 91% sourced from news coverage of Centuria Office REIT FY26 results (Kalkine, 2026-08-04) referencing the COF FY26 Results Announcement (COF.AX 2026-08-03). Observable published metric.
- `gearing_estimate` = 0.36 (Cat B) — Gearing estimated at approximately 36% based on COF FY26 Results Announcement headline (COF.AX 2026-08-03 PERIODIC REPORTS); filing body was cross-contaminated in the ASX data pipeline, preventing direct extraction of the reported figure. Estimate is consistent with COF historical gearing range of 32-38% and remains below the Australian REIT convention limit of 40%. Category B — analyst estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP basis noise.

## Key Risks
- Distribution coverage deterioration: if DPU exceeds AFFO, a distribution cut would likely compress unit price materially given COF already trades at a deep discount to NTA.
- Gearing and refinancing risk: elevated debt in a higher-for-longer rate environment could force asset sales at distressed valuations, further eroding NTA and unitholder returns.
- Structural office demand decline: accelerating hybrid/remote work adoption and tenant flight to CBD quality could persistently suppress suburban/metro office occupancy below 88%.
- External manager conflict: Centuria Capital's fee structure incentivises AUM growth over capital discipline; acquisitions at sub-optimal yields remain a risk for unitholders.
- Data pipeline limitation: COF.AX ASX filing bodies were cross-contaminated with unrelated issuers in the retrieval pipeline, preventing direct extraction of DPU, gearing, and WALE; key assumptions rely on analyst estimates and published news headlines rather than primary filing data.

## Invalidation Condition
Exit position if: (1) reported portfolio occupancy falls below 88% for two consecutive half-year reporting periods; (2) DPU coverage by AFFO is confirmed below 1.0x in any half-year result announcement; (3) aggregate gearing is reported at or above 40% without a credible and time-bound deleveraging plan disclosed by management; or (4) Centuria Capital announces a DPU cut exceeding 15% without a commensurate occupancy improvement or accretive asset recycling catalyst supporting long-term income recovery.
