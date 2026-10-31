# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-10-31_equity_reit_v1@1.0_69d8d1973e32`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Retail/Fuel & Convenience
**As of**: 2026-10-31
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Waypoint REIT offers Australian fuel and convenience property exposure on long leases with CPI-linked or fixed escalators. The estimated yield of about 6.5% sits well above the 4.0% T-bill rate. Beta of 0.57 against IASP.L (currency-basis caveat applies) and 17% volatility suggest defensive behaviour. The OU Monte Carlo gives a 12-month return of 7.4% with a PGain of about 74%, which supports a base conviction of 4. The score is cut one step to 3 for tenant concentration and because the filing bodies could not verify the DPU, gearing and WALE inputs.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.1160
- P-gain: 0.7395
- CAPM alpha: 0.0845
- Beta: 0.5656
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Higher-for-longer rates, with a stagflation-type pathway, push cap rates out by 50bps or more and cut valuations by about 7-8%. Refinancing costs erode DPU by 3-5%. Tenant concentration worries or a fuel-transition lease risk with the main tenant widens the yield spread.
- **base**: E(R)=0.0750
  - Central case as built in the chain: 6.5% yield, about 1% DPU growth as rent reviews offset higher interest costs, flat cap rates and stable occupancy near full.
- **bull**: E(R)=0.1900
  - Rate cuts compress cap rates by about 25-50bps and lift valuations. Rent reviews hold at 3% or more, there are accretive acquisitions or recycling, and the yield multiple re-rates upward.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 2.2 (Cat A) — WPR.AX last close AUD 2.20 on 2026-10-30 (get_price).
- `distribution_yield` = 0.065 (Cat B) — Approximate forward cash distribution yield of about 14-14.5 cents per unit on a AUD 2.20 price. The stored filing bodies returned for WPR.AX (dated 2026-08-26 and 2026-09-20) contained other issuers' announcements, not Waypoint's 1H26 results or distribution notice. The DPU figure therefore could not be verified from a filing and is a derived estimate, not observed data.
- `dpu_growth` = 0.01 (Cat C) — Assumes about 1% DPU growth. Contractual or CPI-linked rent reviews of roughly 2.5-3% are largely offset by higher refinancing costs on debt. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes a flat price-to-NAV and yield multiple over 12 months, with no cap-rate movement. The bear case tests cap-rate expansion.
- `expected_return_build` = 0.075 (Cat C) — E(R) = 6.5% yield + 1.0% growth + 0% multiple change = 7.5%. It is a model construct and inherits the Category B and C inputs above.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill at 4.00% on 2026-10-29 (get_tbill_rate). This is a USD rate used as a proxy for an AUD investor.
- `expected_market_return` = -0.0475 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (calculate_benchmark_return, 1260-day lookback). It is GBP-denominated and negative, which mechanically inflates CAPM alpha.
- `tenant_concentration` = high (Cat C) — Portfolio is understood to be concentrated in fuel and convenience properties with a dominant investment-grade tenant (Ampol), on long WALE leases. This is background knowledge, not verified from a retrieved filing, so it is treated as a model assumption. A one-step gate override is applied for concentration and for unverified data.
- `gearing_assumption` = 0.3 (Cat C) — Gearing is assumed to be in the high-20s to low-30s percent, below the Australian convention of 40%. No filing body confirmed the figure.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Tenant concentration in one dominant fuel retailer, with long-run risk from the energy transition and from a lease renewal or repricing at expiry
- Higher-for-longer rates raising refinancing costs and widening cap rates, which would pressure DPU and NAV
- Data-quality gap: the retrieved stored filings were for unrelated issuers, so DPU, gearing, WALE and coverage inputs are unverified Category B/C estimates
- Negative IASP.L 5-year return (-4.75%) inflates CAPM alpha. Beta correlation of about 0.39 and GBP/AUD currency noise reduce the reliability of the beta and alpha
- The forward yield and growth are modelled assumptions, and a 12-month OU simulation is a directional signal rather than a formal backtest

## Invalidation Condition
Exit if the main fuel-retailer tenant gives notice of lease non-renewal or a material rent reset on a large share of portfolio income. Exit if gearing rises above 40% or DPU cover falls below 1.0x AFFO for two consecutive half-year periods. Exit if a published valuation shows cap-rate expansion of more than 50bps without an offsetting rental uplift. Exit if the verified DPU falls well below the assumed 14 cents.
