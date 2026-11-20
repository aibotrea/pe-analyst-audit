# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-11-20_equity_reit_v1@1.0_cf352d77d18f`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail (Supermarket-Anchored Neighbourhood Centres)
**As of**: 2026-11-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
RGN offers defensive Australian supermarket-anchored neighbourhood retail exposure, with FY26 FFO growth, higher occupancy and 3% FY27 guidance reported in news coverage. An estimated 5.7% yield plus about 3% growth gives an 8.7% expected return, well above the 4.16% T-bill. Beta of 0.45 versus IASP.L (currency-basis caveat applies) and volatility of 15.3% give an OU Monte Carlo PGain of about 80%. The numeric chain scores conviction 4. I applied a one-step downward override to 3 because leverage, AFFO coverage and WALE could not be verified from issuer filings. An active on-market buy-back is a modest supportive signal.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.1038
- P-gain: 0.7978
- CAPM alpha: 0.0828
- Beta: 0.4541
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Higher-for-longer rates or a stagflation-type shock (sticky inflation, RBA tightening, weaker consumer spending) push cap rates out by 25-50bps. FFO growth stalls at 0-1% and AFFO coverage slips below 1.0x. Gearing drifts above the 40% convention.
- **base**: E(R)=0.0870
  - Central case as built in the chain: 5.7% yield, 3% FFO/DPU growth in line with FY27 guidance, cap rates flat, and occupancy holding at high levels in supermarket-anchored centres.
- **bull**: E(R)=0.1800
  - Rate cuts compress cap rates by 15-25bps for a modest re-rating, and leasing spreads and specialty rents lift FFO growth to 4-5%. Accretive capital recycling and continued buy-backs below NTA support per-security returns.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 2.36 (Cat A) — RGN.AX closing price of AUD 2.36 on 2026-11-20 from get_price.
- `distribution_yield` = 0.057 (Cat B) — Estimated trailing/forward DPU yield of about 5.7% on the AUD 2.36 price. This is my estimate of the DPU (about 13.4c) and is not read from a filing. The stored filings returned for RGN.AX were mismatched or off-topic, so the DPU could not be verified from an issuer document.
- `dpu_growth` = 0.03 (Cat B) — Growth is set at the roughly 3% FY27 FFO growth guidance reported in news coverage of the FY26 result (Kalkine, 2026-08-18). I did not verify the guidance in an issuer filing. DPU growth is assumed to track FFO growth.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in the valuation multiple or cap rate over 12 months. Sensitivity is shown in the bear case (cap-rate expansion) and the bull case (modest re-rating).
- `risk_free_rate` = 0.0416 (Cat A) — US 3-month T-bill (DTB3) of 4.16% on 2026-11-19 from get_tbill_rate.
- `expected_market_return` = -0.040739 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260 trading days). It is GBP-denominated and absorbs FX co-movement. It is negative, which mechanically lifts CAPM alpha for low-beta names.
- `expected_return` = 0.087 (Cat B) — E(R) = 5.7% yield + 3.0% growth + 0% multiple change = 8.7%. The yield and growth components are Category B and the multiple change is Category C.
- `filing_data_gap` = disclosed (Cat B) — get_stored_filings for RGN.AX returned bodies that belong to other issuers (Challenger/EGL, ANZ, Regis, GL1, EQX, Albion) or ASX test documents. These were ignored as off-topic. Leverage, AFFO coverage, WALE, occupancy and top-asset concentration for RGN could not be sourced from filings, and ASX bodies are not captured for this ticker.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer Australian and US rates could widen cap rates and compress the spread of yield over the 4.16% risk-free rate.
- Leverage, AFFO coverage, WALE and sponsor data are unverified because the stored filings were mismatched. Gearing or coverage could be worse than assumed.
- Consumer spending weakness, or supermarket anchor and specialty tenant stress, could hurt rent growth and FFO against the 3% guidance.
- Beta and market return are measured against GBP-denominated IASP.L. The negative 5-year benchmark return inflates CAPM alpha, so alpha is only a supporting input.
- The yield and growth inputs are my estimates (Category B) from news coverage, not from filings. This is a directional live analysis, not a formal backtest.

## Invalidation Condition
Exit if reported AFFO distribution coverage falls below 1.0x for two consecutive half-year periods, or if aggregate gearing rises above about 40% with no credible deleveraging plan. Also exit if portfolio occupancy drops materially below the current high levels, or if FY27 FFO growth guidance is cut to flat or negative, which would invalidate the 8.7% expected return.
