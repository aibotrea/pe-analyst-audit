# Specialist Memo — CIP.AX

**Memo ID**: `CIP.AX_2026-11-22_equity_reit_v1@1.0_2a3688220f0b`
**Ticker**: CIP.AX (Centuria Industrial REIT)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-11-22
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
CIP is an ASX-listed pure-play industrial REIT with a guided distribution yield of about 5.9% at a price of AUD 2.92. That gives a modest spread of roughly 1.7 points over the 4.16% US T-bill rate. The 12-month expected return is 7.4%, built from yield, 1.5% growth and no multiple change. Beta of 0.52 versus IASP.L carries the currency-basis caveat and is based on a low correlation of 0.36. The OU Monte Carlo gives a PGain of 74% with a one-year standard deviation of 11.5%, which supports a base conviction of 4. Conviction is cut to 3 because gearing, coverage and tenant data could not be verified from issuer filings.

## Quantitative Chain

- E(R): 0.0740
- Std dev: 0.1147
- P-gain: 0.7392
- CAPM alpha: 0.0749
- Beta: 0.5158
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Higher-for-longer rates or a stagflation-type shock push Australian industrial cap rates out by about 50bps. Valuations fall about 6-8%, distribution growth turns flat or negative as funding costs rise, and AFFO coverage drops below 1.0x. The price-to-NTA multiple contracts further.
- **base**: E(R)=0.0740
  - Central case as built in the chain: yield of about 5.9% on guidance of 17.3c, 1.5% growth, flat cap rates and a flat multiple. Occupancy and rent escalators hold.
- **bull**: E(R)=0.1700
  - RBA easing compresses cap rates by about 25bps and the units re-rate toward NTA. Rent reversion on industrial assets is strong, with data centre and development upside. Distribution growth reaches 3-4% and the total return approaches 17%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 2.92 (Cat A) — CIP.AX last close AUD 2.92 on 2026-11-20 from get_price.
- `distribution_yield` = 0.059 (Cat B) — FY27 distribution guidance of about 17.3c per unit, taken from a Kalkine news headline dated 2026-11-11 and not from an issuer filing. Divided by the AUD 2.92 price, this gives about 5.9%. The stored filing bodies returned for CIP.AX were mismatched documents from other issuers, so the guidance could not be checked against the issuer's own filing.
- `dpu_growth_12m` = 0.015 (Cat C) — Assumed 1.5% growth in distribution and NTA. This reflects contracted rent escalators of roughly 3-4% offset by higher funding costs and capex. It is not consensus data. The scenario analysis tests it.
- `multiple_change` = 0.0 (Cat C) — Assumes flat cap rates and a flat price-to-NTA multiple over 12 months. There is no data-backed view on re-rating, and sensitivity is covered in the bear and bull cases.
- `expected_return_build` = 0.074 (Cat B) — E(R) is yield 5.9% + growth 1.5% + multiple change 0.0%, which sums to about 7.4%. Each component is classified above.
- `risk_free_rate` = 0.0416 (Cat A) — DTB3 3-month T-bill rate of 4.16% as of 2026-11-19, from get_tbill_rate. This is a US rate, used as the platform's standard Rf. It is not an AUD rate.
- `expected_market_return` = -0.0407 (Cat B) — Trailing 5.18-year annualised log return of IASP.L, from calculate_benchmark_return. It is GBP-denominated and absorbs FX noise. It is negative, which makes the CAPM required return very low and flatters alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gate_data_gap` = disclosed (Cat C) — Gearing, AFFO coverage, WALE and tenant data could not be verified. The stored CIP.AX filing bodies were unrelated documents from other issuers, and the Q1 FY27 Operating Update body was not retrievable. One conviction step down was applied for the unverified gates. This is a model assumption.

## Key Risks
- Cap rate expansion if Australian and global rates stay higher for longer. This would hit NTA and the unit price, given the thin yield spread over the T-bill rate.
- Distribution coverage or gearing could be weaker than assumed. The FY27 guidance of 17.3c came from a news source, and the stored filing bodies were not the issuer's documents.
- Industrial rent growth could slow, or tenant concentration could be an issue. Data centre exposure adds development and execution risk.
- The IASP.L GBP benchmark adds currency-basis noise to beta and alpha. The 5-year benchmark return is negative (-4.1%), which inflates CAPM alpha. Beta correlation is only 0.36.
- This is a live (non-backtest) analysis, but the macro inputs are limited to the T-bill rate. No FEDFUNDS, T10Y2Y or credit-spread signals were used. The analysis is a directional signal with no vintage discipline.

## Invalidation Condition
Exit if reported gearing moves above 40% or the interest cover covenant comes under pressure. Exit if AFFO coverage of the distribution falls below 1.0x for two consecutive reporting periods, or if FY27 distribution guidance is cut below about 17.3c per unit. Also exit if portfolio occupancy drops below 95% or independent valuations show cap rate expansion of more than 50bps.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
