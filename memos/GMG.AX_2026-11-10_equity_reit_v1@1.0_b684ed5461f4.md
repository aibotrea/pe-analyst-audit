# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-11-10_equity_reit_v1@1.0_b684ed5461f4`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-11-10
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is a global industrial and logistics developer and fund manager. It is increasingly weighted toward data-centre development, and it is internally managed with a strong alignment record. Operating EPS growth of about 7% drives most of the 7.0% E(R), because the 1.2% distribution yield is small. The OU Monte Carlo gives a PGain of 63% on 20.8% simulated dispersion. The 30.5% historical volatility and the large new NEXTDC stake cap conviction at Moderate. Beta of 0.77 versus IASP.L is only a rough guide because of the currency-basis caveat and a low correlation of 0.30.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.2076
- P-gain: 0.6303
- CAPM alpha: 0.0957
- Beta: 0.7680
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2200
  - Rates stay higher for longer, or inflation rises while growth slows (a stagflation path). Data-centre development yields and valuations de-rate, and the NEXTDC stake is marked down. Operating EPS growth falls to about 2%. The premium multiple contracts by 15-20%, and development WIP is delayed.
- **base**: E(R)=0.0700
  - Central case as built in the chain. The yield is about 1.2%, operating EPS growth about 7%, and the multiple contracts about 1%. Development completions and partnership capital stay on track.
- **bull**: E(R)=0.2500
  - Hyperscale data-centre demand lifts the power-secured pipeline and development earnings. EPS growth reaches 12% or more and the NEXTDC stake adds strategic optionality. The multiple expands about 8-10% as Australian rates ease.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 29.13 (Cat A) — GMG.AX closing price on 2026-11-10 in AUD from get_price.
- `distribution_yield` = 0.0124 (Cat B) — Assumed FY27 DPS of about AUD 0.36, held flat on the prior-year level, divided by the 29.13 price. I did not verify the FY27 DPS guidance against a filing. ASX filing bodies are unavailable, so this is derived and not observed.
- `earnings_growth` = 0.07 (Cat C) — Operating EPS growth of about 7%, assumed from development-WIP and data-centre-led earnings momentum and discounted from the roughly 9% typically guided. Only part of this accrues to the unit price over 12 months, because the payout ratio is low and earnings are retained. Sensitivity is tested in the bear and bull scenarios.
- `multiple_change` = -0.0124 (Cat C) — Assumed modest multiple contraction of about 1.2%. The stock is on a premium multiple, and the 4.06% US T-bill rate and the NEXTDC stake add capital-allocation uncertainty. The components sum to E(R) of about 7.0%.
- `expected_return` = 0.07 (Cat C) — E(R) is yield 1.2% + growth about 7% + multiple change about -1.2%, rounded to 7.0%. It is a model-built figure.
- `risk_free_rate` = 0.0406 (Cat A) — FRED DTB3 3-month T-bill rate of 4.06% on 2026-11-09.
- `expected_market_return` = -0.0457 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return, a GBP-denominated series. The negative value reflects a weak APAC REIT index over the window and is a poor forward-looking proxy.
- `nextdc_stake` = 0.099 (Cat A) — GMG ASX announcement dated 2026-11-08 reporting acquisition of a 9.9% interest in NEXTDC, flagged price-sensitive. The headline is observed. Funding and strategic rationale were not reviewed.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- The 9.9% NEXTDC stake adds concentration in data centres and capital-allocation risk. Funding, control intent and the exit path are unclear.
- Valuation de-rating is likely if long-end rates stay high. The 4.06% T-bill sits far above the 1.2% distribution yield, so the stock relies on growth.
- Data-centre power and development execution risk, including construction costs, grid connection delays and hyperscale tenant concentration.
- The IASP.L benchmark is GBP-denominated with a negative 5-year return of -4.6%. Alpha of 9.6% is inflated by this weak market proxy and by currency-basis noise, with beta correlation of only 0.30.
- Gearing, AFFO coverage and WALE were not verified from filing bodies, because ASX body capture is unavailable. The gates marked info rest on public knowledge, not checked filings.

## Invalidation Condition
Exit if Goodman's operating EPS growth guidance is cut below about 4%, if look-through gearing rises materially above 10% because of funding for the NEXTDC stake or data-centre development, or if hyperscale pre-commitments and development WIP fall sharply for two consecutive reporting periods. Exit also if the stock de-rates more than 20% without any improvement in earnings.
