# Specialist Memo — DXI.AX

**Memo ID**: `DXI.AX_2026-10-18_equity_reit_v1@1.0_afeba5adcfd4`
**Ticker**: DXI.AX (Dexus Industria REIT)
**Market**: Australia
**Sector**: Industrial/Office
**As of**: 2026-10-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
DXI offers Australian industrial and office exposure with a trailing yield of about 6.9% against a 4.1% USD T-bill, and an active buy-back suggests management sees value at a discount to NTA. The 12-month OU Monte Carlo gives a simulated return of about 8.3% with a standard deviation of about 11.1%, so PGain is 77%. Beta of 0.475 versus IASP.L is low, but the currency-basis caveat applies and correlation is only 0.34. CAPM alpha of 8.6% is flattered by the negative trailing benchmark return and is a supporting input only. Base conviction of 4 is cut one step to 3 because gearing and AFFO coverage could not be verified from primary filings.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.1111
- P-gain: 0.7738
- CAPM alpha: 0.0864
- Beta: 0.4750
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Higher-for-longer rates, or a stagflation-type shock, lift Australian bond yields and push cap rates out by about 25-50bps. Valuations fall, gearing rises towards or above the 40% convention, and AFFO coverage slips below 1.0x. DPU growth turns to roughly -3%, and the multiple de-rates by about 8-10%.
- **base**: E(R)=0.0840
  - Central case as built in the chain: a 6.9% yield, 1.5% DPU growth, and flat cap rates and multiple. The buy-back adds mild support, and the OU Monte Carlo gives a simulated return of about 8.3% with a standard deviation of about 11.1%.
- **bull**: E(R)=0.1900
  - Rate cuts compress cap rates by about 25bps and the discount to NTA narrows by about 8%. Leasing spreads lift DPU growth to about 3.5%, and the buy-back is accretive.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.069 (Cat A) — Trailing distribution yield of about 6.9%, taken from a Kalkine headline dated 2026-07-22 (6.93% yield) and the FY26 distribution coverage in Kalkine dated 2026-09-28. This is a secondary news source, not an issuer filing. The latest close was AUD 2.30 on 2026-10-16. The stored DXI filings returned by the tool contained unrelated issuer content, so no DPU or AFFO figures could be verified from primary documents.
- `dpu_growth` = 0.015 (Cat C) — Assumed DPU/NTA growth of 1.5% a year from fixed rent escalators and modest leasing reversion, roughly in line with inflation-linked escalators less capex drag. There is no consensus figure in the toolset. Tested in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumed no re-rating or de-rating over 12 months. The ongoing on-market buy-back (ASX notices Oct 2026) is a modest supportive factor for the discount to NTA, but it is not credited in E(R).
- `expected_return_build` = 0.084 (Cat B) — E(R) = 6.9% yield + 1.5% growth + 0% multiple change = 8.4%. This is a derived estimate that depends on the Category C growth and multiple assumptions.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month T-bill at 4.10% on 2026-10-15. This is a USD rate, used as the risk-free proxy under the platform methodology. It is not an AUD rate.
- `expected_market_return` = -0.0504 (Cat B) — IASP.L trailing 5.17-year annualised log return of -5.04%, from calculate_benchmark_return over a 1260-day lookback. It is GBP-denominated and absorbs currency co-movement. It is a negative backward-looking figure that inflates CAPM alpha mechanically.
- `historical_volatility` = 0.1635 (Cat B) — Annualised volatility of 16.35% from 252-day stored daily prices (262 observations).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gate_data_gap` = disclosed (Cat C) — Gearing, AFFO coverage, WALE and top-tenant concentration could not be verified from primary filings. The stored DXI filings returned were unrelated to DXI, and ASX body capture is not available for DXI. A one-step conservative conviction override was applied to the distribution_coverage gate for this reason.

## Key Risks
- Higher-for-longer Australian rates, or a stagflation shock, widen cap rates and compress NAV and the multiple.
- Distribution coverage and gearing are unverified from primary filings, so the yield estimate rests on a secondary news source and could be wrong.
- Tenant, asset and lease-expiry concentration in a small-cap REIT, with possible office exposure and refinancing risk.
- The benchmark is GBP-denominated, so beta and alpha carry currency noise. The negative 5-year benchmark return distorts CAPM alpha, and the 4.1% USD risk-free rate is not an AUD rate.
- The backtest is a directional signal, not a formal backtest, and the E(R) growth and multiple inputs are Category C assumptions.

## Invalidation Condition
Exit if reported AFFO coverage falls below 1.0x for two consecutive reporting periods, or if look-through gearing rises above 40% without a credible deleveraging plan. Also exit if the DPU is cut by more than 5%, or if a material tenant loss pushes portfolio occupancy below 94%.
