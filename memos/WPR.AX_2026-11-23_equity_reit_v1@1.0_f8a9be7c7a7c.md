# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-11-23_equity_reit_v1@1.0_f8a9be7c7a7c`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Retail/Convenience (Fuel & Convenience Net Lease)
**As of**: 2026-11-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Waypoint REIT is a listed Australian owner of fuel and convenience net-lease properties. It has a long WALE, CPI-linked or fixed rent escalators and low gearing, which supports a roughly 5.9% yield plus modest growth. The OU Monte Carlo gives a 12-month simulated return of about 7.3% with a PGain of 73%, and a base conviction of 4. Beta of 0.57 versus IASP.L (currency-basis caveat applies) indicates defensive co-movement. Tenant concentration, mainly Ampol, and the long-term EV transition risk to fuel retail assets lead to a one-step downward override, giving conviction 3. Key inputs such as the DPU, gearing and coverage could not be verified because the stored filing bodies were mismatched.

## Quantitative Chain

- E(R): 0.0740
- Std dev: 0.1172
- P-gain: 0.7345
- CAPM alpha: 0.0809
- Beta: 0.5693
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Stagflation or rate-shock pathway: AU bond yields rise and cap rates expand about 50bps, giving roughly -8% to -9% valuation drag. DPU growth is flat as refinancing costs rise. A major tenant renegotiates or reduces its site footprint, and AFFO coverage falls toward 1.0x.
- **base**: E(R)=0.0740
  - Central case as built in the chain: 5.9% yield, 1.5% DPU growth from CPI-linked rent reviews, flat cap rates and gearing in the low 30s%.
- **bull**: E(R)=0.1900
  - RBA easing and falling bond yields compress cap rates about 25bps for a roughly +5% re-rating. DPU growth is 3% and accretive recycling or acquisitions are done at above-WACC yields.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 2.27 (Cat A) — WPR.AX latest close 2026-11-23 from get_price (AUD).
- `distribution_yield` = 0.059 (Cat B) — Approx. 13.4c annual DPU divided by the 2.27 AUD price. The DPU is recalled from prior issuer guidance and is not verified against a current filing. The stored WPR.AX filing bodies returned for 2026-08/09 contained other issuers' content (parsing mismatch), so no distribution figure could be extracted. The 2026-09-20 distribution announcement body was unusable.
- `dpu_growth` = 0.015 (Cat C) — Assumes modest DPU growth. Rents are CPI-linked or fixed 2.5-3% reviews with a long WALE, offset by higher refinancing costs on hedged debt rolling off. Sensitivity is in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes no re-rating (flat cap rate and flat yield) over 12 months. Sensitivity of roughly +/-25bps of cap rate is reflected in the bear and bull cases.
- `expected_return_build` = 0.074 (Cat C) — E(R) = yield 5.9% (B) + growth 1.5% (C) + multiple change 0% (C) = 7.4%.
- `risk_free_rate` = 0.0413 (Cat A) — FRED DTB3 3-month T-bill 4.13% dated 2026-11-20. This is a USD rate used as the platform risk-free input, not an AUD rate.
- `expected_market_return` = -0.0434 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260-day window). It is negative and GBP-based, so the CAPM hurdle is very low and alpha is flattered.
- `historical_volatility` = 0.1725 (Cat B) — 252-day annualised volatility from stored prices (262 observations).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gearing_assumption` = 0.3 (Cat C) — Gearing assumed in the low-30s% range from recalled issuer disclosure and not verified from a current filing. It is below the AU <40% convention.
- `tenant_concentration` = high (Cat C) — Portfolio assumed to be predominantly fuel and convenience sites leased to a small number of tenants, with Ampol the dominant tenant. It has a long WALE and investment-grade-type covenants. Not verified from a current filing.

## Key Risks
- Tenant concentration, with Ampol as the dominant tenant and counterparty. A lease renegotiation or credit event would hit income directly.
- Long-term structural risk to fuel retail from EV adoption, which could weaken re-leasing and residual values at lease expiries.
- Higher-for-longer AU and US rates could widen cap rates and raise refinancing costs as hedges roll off. The 4.13% USD T-bill is the platform Rf, not an AUD rate.
- Data gap: the WPR.AX filing bodies retrieved for 2026-08/09 contained other issuers' content, so DPU, gearing, coverage and WALE are unverified and rely on prior recalled disclosures (Category B/C). The news search also returned no results.
- The IASP.L benchmark is GBP-based and its negative 5-year return makes CAPM alpha look inflated. The Phase 2 calibration is a directional signal rather than a formal backtest.

## Invalidation Condition
Exit if gearing rises above 40% or AFFO coverage of the distribution falls below 1.0x for two consecutive half-year reporting periods. Exit also if the dominant tenant disputes, reduces or fails to renew a material part of the lease portfolio, or if the cap rate expands more than 50bps without offsetting DPU growth.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
