# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-08-11_equity_reit_v1@1.0_0a43bdcb1324`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-08-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Waypoint REIT offers a highly defensive income stream via approximately 580 triple-net leased fuel and convenience sites predominantly occupied by Viva Energy (BP/Liberty brands) under long-dated leases with CPI-linked rent reviews. The trailing DPU yield of ~6.87% at AUD 2.52 provides a meaningful spread over the 3.74% T-bill rate, and the OU Monte Carlo simulation returns a PGain of 77.6% at a 12-month horizon. Beta of 0.47 versus IASP.L (AUD/GBP currency-basis caveat applies) confirms relatively low co-movement with the broader APAC REIT market, reinforcing the defensive income profile. Conviction is moderated to 3 from the quantitative base of 4 due to extreme single-tenant concentration (Viva Energy >90% of income), the secular EV-transition headwind to fuel demand, and the inability to directly verify distribution coverage from filed documents given ASX body capture limitations.

## Quantitative Chain

- E(R): 0.0790
- Std dev: 0.1037
- P-gain: 0.7755
- CAPM alpha: 0.0787
- Beta: 0.4724
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Viva Energy exercises lease restructure or renegotiation rights, reducing rental income by 5-8%; concurrent cap rate expansion of 50bps reflecting higher-for-longer AUD rates and EV-driven demand concerns, compressing NTA by ~10%; DPU coverage falls below 1.0x AFFO; gearing breaches 40% covenant threshold requiring dilutive equity raise. Rate shock scenario (RBA holds elevated or re-hikes) amplifies cap rate headwind.
- **base**: E(R)=0.0790
  - Central case: distribution yield 6.87%, DPU growth 1.5% from CPI-linked rent reviews, multiple change -0.5%. Viva Energy honours lease obligations across all sites. Gearing stable at ~37%. RBA rate profile broadly as priced by market. OU Monte Carlo sim return 7.85%.
- **bull**: E(R)=0.1700
  - RBA delivers additional rate cuts compressing risk-free rate to <3%, improving yield spread and triggering re-rating of defensive income REITs. CPI-linked rent reviews deliver 3%+ DPU growth. Viva Energy strengthens covenant through Ampol acquisition or strategic partnership. Cap rate compression of 25bps on fuel-and-convenience assets. Potential privatisation or buyout premium given heavily discounted NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0687 (Cat A) — Trailing DPU yield of approximately 6.87% derived from analyst and financial media commentary referencing WPR's published distribution announcements (ASX filing 2026-06-18, body unavailable). Current price AUD 2.52 (observed closing price 2026-08-11). Yield figure is consistent with multiple third-party sources reporting 6.87-6.90% as of late July 2026.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. based on CPI-linked rent review provisions in Waypoint REIT's triple-net leases with Viva Energy (BP/Liberty brands). Australian CPI has moderated toward the RBA 2-3% target band; 1.5% reflects a conservative pass-through assumption given fuel-site-specific lease terms. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Modest negative multiple change assumption of -0.5% reflecting secular headwind from electric vehicle adoption and long-term structural risk to fuel retail demand. Partially offset by convenience retail diversification. Cap rate expansion risk present in a still-elevated rate environment. Sensitivity tested in scenario analysis.
- `tenant_concentration_viva_energy` = high (Cat A) — Waypoint REIT's portfolio of approximately 580 fuel and convenience sites is overwhelmingly leased to Viva Energy Group (operating BP and Liberty brand sites) under long triple-net leases. Viva Energy accounts for the substantial majority (>90%) of WPR rental income. This is a structural feature of the REIT and is publicly disclosed. Filing bodies from ASX are largely unavailable (Phase 01 v3.3 §4 — ASX body capture parked).
- `wale_and_lease_structure` = triple_net_long_wale (Cat B) — Waypoint REIT operates on triple-net lease terms with a historically reported WALE of 10+ years. Tenant covers all outgoings. Distribution coverage by AFFO is expected to be >1.0x given this structure, but the June 2026 distribution announcement filing body is unavailable (body_unavailable=True) preventing direct verification from filed documents.
- `gearing_level` = 0.37 (Cat B) — Estimated gearing of approximately 37% based on publicly reported figures from prior annual results and financial media. Australian REIT regulatory convention is <40% gearing. ASX filing bodies are unavailable for direct verification from the filing store (body_unavailable=True for all available filings). Assumed within regulatory limit pending confirmation from next periodic report.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces noise into the 0.472 beta estimate. Treated as Category B input. CAPM alpha inherits the same noise. The IASP index is the mandated benchmark under the equity_reit_v1 framework.

## Key Risks
- Single-tenant concentration: Viva Energy accounts for >90% of rental income; any lease renegotiation, insolvency, or strategic exit would materially impair distributions and NTA.
- Electric vehicle transition reducing long-term demand for petrol station sites, compressing cap rates and impairing asset values beyond the current modest multiple-change assumption.
- Higher-for-longer AUD interest rates narrowing the yield spread over risk-free rate and triggering cap rate expansion with negative NTA impact on a geared balance sheet.
- External management fee structure (Charter Hall) may not be fully aligned with unitholder outcomes; management costs reduce distributable income relative to an internalised manager.
- ASX filing body capture unavailability (Phase 01 v3.3 §4 parked) prevents direct verification of FY2026 distribution coverage, gearing ratio, and any covenant updates from the most recent periodic reports.

## Invalidation Condition
Exit the position if Viva Energy announces a material restructure, termination, or renegotiation of its master lease agreement with Waypoint REIT, or if WPR reports gearing above 40% for two consecutive half-year periods, or if DPU coverage falls below 1.0x AFFO for one reporting period, or if the RBA cash rate rises above 4.75% signalling a structural reversal of the easing cycle that underpins the yield-spread thesis.
