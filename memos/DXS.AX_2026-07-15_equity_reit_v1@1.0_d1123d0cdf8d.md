# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-07-15_equity_reit_v1@1.0_d1123d0cdf8d`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Office/Industrial
**As of**: 2026-07-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus is Australia's largest office-focused REIT trading at a decade-low price of AUD 5.63, offering a trailing distribution yield of approximately 6.3% — a meaningful 253bps spread over the current 3.71% T-bill rate. The OU Monte Carlo (12-month horizon) returns a simulated return of 6.24% with PGain of 68.1%, indicating a moderate probability of positive outcomes. However, a price-sensitive portfolio valuation update filed July 2026 confirms ongoing office devaluations partially offset by industrial gains, gearing of ~38.5% is near the Australian convention ceiling, and distribution coverage data for FY2026 is unavailable — collectively warranting a one-step downward gate override to conviction 2. Beta of 0.54 vs IASP.L (currency-basis caveat: AUD/GBP co-movement absorbed) indicates moderate correlation with the broader APAC REIT universe, which has itself delivered a negative 5-year annualised return of -3.4%.

## Quantitative Chain

- E(R): 0.0630
- Std dev: 0.1326
- P-gain: 0.6810
- CAPM alpha: 0.0640
- Beta: 0.5392
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Office cap rates expand 50bps beyond current levels, triggering a further portfolio devaluation and pushing gearing above 40% covenant ceiling; distribution cut of 15-20% as AFFO coverage falls below 0.90x; multiple compression of 3% as market re-rates the vehicle; AUD weakens materially, increasing cost of any offshore debt. Net return driven by income loss compounding capital erosion.
- **base**: E(R)=0.0620
  - Central case as built in quantitative chain: DPU yield 6.3%, growth -0.5%, multiple change +0.5%. Office valuations stabilise in H2 2026 as RBA holds rates; industrial assets provide partial offset; gearing remains ~38.5%; distribution maintained at current levels.
- **bull**: E(R)=0.2000
  - RBA pivots to rate cuts in H2 2026, compressing cap rates and driving office/industrial portfolio revaluation upward; DXS trades back toward NAV from current discount; distribution coverage improves as refinancing costs fall; multiple expansion of 3-4% on re-rating of the office sector; occupancy improves to 93%+ on renewed CBD leasing demand.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat A) — Trailing DPU yield of approximately 6.3% referenced in Kalkine analysis (15 Jun 2026) and consistent with the ASX distribution announcement headline 'Estimated distribution details for 30 June 2026' (DXS.AX 2026-06-23 DISTRIBUTION ANNOUNCEMENT). Body unavailable for the filing; gap disclosed. Price AUD 5.63 as at 2026-07-15.
- `dpu_growth` = -0.005 (Cat C) — DPU growth assumption of -0.5% p.a. reflects net-negative pressure from continuing office portfolio devaluations (DXS.AX 2026-07-05 PERIODIC REPORTS 'Portfolio valuation update' — price-sensitive). Industrial asset gains partially offset office cap-rate headwinds. Zero organic growth assumed; -0.5% applied for distribution dilution risk. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple-change assumption reflecting mean-reversion potential from decade-low price level per Kalkine (Jun 2026) commentary. Highly uncertain; bear case assumes -2% multiple compression. Category C due to model dependency.
- `gearing_level` = 0.385 (Cat B) — Gearing estimated at approximately 38.5%, derived from Dexus 2026 Half Year Results (Feb 2026, Australian Property Markets News). Near but below the Australian REIT convention ceiling of 40%. Treated as Category B as exact figure pending FY2026 full-year results.
- `distribution_coverage_gap` = unavailable (Cat B) — AFFO coverage ratio not extractable — filing bodies for DXS.AX 2026-06-23 DISTRIBUTION ANNOUNCEMENT filings carry body_unavailable=True (ASX body capture parked per Phase 01 v3.3 §4). Gap disclosed in key_risks. Kalkine (15 Jun 2026) headline raises sustainability concern at 6.3% yield.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis means the 0.539 figure reflects both Australian property sector dynamics and AUD/GBP exchange rate co-movement. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Continued office portfolio devaluations compressing NAV and triggering gearing covenant breach above the 40% Australian convention ceiling — particularly if cap rates widen further in the second half of 2026.
- Distribution sustainability uncertainty: AFFO coverage data unavailable for FY2026 (filing bodies not captured); Kalkine (Jun 2026) explicitly questions whether the 6.3% yield is sustainable at current earnings.
- Higher-for-longer RBA cash rate environment compressing the yield spread versus risk-free, reducing relative attractiveness and sustaining downward pressure on DXS unit price.
- Structural headwinds in the office sector from hybrid working patterns reducing net effective rental demand, particularly in CBD office markets where DXS has its highest concentration.
- Backtest calibration limitation: Phase 2 calibration is a directional signal only; formal vintage discipline arrives in Phase 5. This memo should be treated as indicative, not as a formally backtested output.

## Invalidation Condition
Exit position if DXS gearing rises above 40% (Australian convention ceiling) for one reporting period, or if the FY2026 full-year distribution announcement confirms AFFO coverage below 1.0x, or if office portfolio occupancy declines below 90% for two consecutive quarterly updates, or if management announces a distribution cut exceeding 10% without an accretive acquisition pipeline to offset the earnings dilution.
