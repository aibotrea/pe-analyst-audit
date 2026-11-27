# Specialist Memo — SKG.AX

**Memo ID**: `SKG.AX_2026-11-27_equity_reit_v1@1.0_dd7299723032`
**Ticker**: SKG.AX (Storage King Group)
**Market**: Australia
**Sector**: Self-Storage
**As of**: 2026-11-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Storage King Group is an internalised ASX self-storage REIT, formerly Abacus Storage King. Management signalled a distribution reset with the FY26 result, and the units are down about 23% over a year. The modelled 12-month OU Monte Carlo return is 7.1% against a 4.16% T-bill. Volatility is high at 24%, giving a PGain of 66.7% and a low-conviction base score of 3. A one-step downward gate on distribution coverage, where the announced cut makes sustainability unverified, reduces conviction to 2. Beta of 0.57 versus IASP.L carries the currency-basis caveat, and the positive CAPM alpha is flattered by a negative trailing benchmark return.

## Quantitative Chain

- E(R): 0.0720
- Std dev: 0.1650
- P-gain: 0.6670
- CAPM alpha: 0.0778
- Beta: 0.5666
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - The distribution cut is deeper than expected, taking yield to about 4%, and occupancy recovery stalls. A stagflation or higher-for-longer rate path pushes AU cap rates out by 25-50bps and compresses the multiple by about 10%. Gearing rises above the 40% convention if the development pipeline is funded with debt.
- **base**: E(R)=0.0720
  - Central case as built in the chain. Forward yield is 5.2%, DPU growth is 2%, and the multiple and cap rates stay flat. Internalisation savings are absorbed by the reset payout.
- **bull**: E(R)=0.2000
  - Occupancy and street rates recover faster than expected, development completions are accretive, and internalisation cost savings flow through. The multiple re-rates by 8-10% from a depressed base after the 23% decline.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `closing_price` = 1.135 (Cat A) — SKG.AX latest close 2026-11-27 in AUD from get_price.
- `forward_distribution_yield` = 0.052 (Cat C) — No verified DPU figure was retrievable. The stored ASX filing bodies for SKG.AX were mismatched and carried other issuers' content, so they were ignored. The 5.2% forward yield is my own assumption. It allows for the 'distribution cut ahead' headline on the FY26 slides (Investing.com, 2026-08-13) and the post-internalisation payout reset. Sensitivity is covered in the bear and bull scenarios.
- `dpu_growth_12m` = 0.02 (Cat C) — Assumed 2% growth from organic self-storage rental growth, occupancy recovery and the development pipeline cited in FY26 results coverage (Kalkine, 2026-08-14 and 2026-11-24). This is above the consensus I could verify, which is none. Sensitivity is tested in the scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes the valuation multiple and cap rate stay flat. The units are down about 23% over a year (Kalkine, 2026-10-04), so a re-rating is possible but is not assumed.
- `expected_return_build` = 0.072 (Cat C) — E(R) = 5.2% yield + 2.0% growth + 0.0% multiple change = 7.2%. This sum is a model assumption built on the Category C components above.
- `risk_free_rate_source` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill rate of 4.16% on 2026-11-25. It is a USD rate, used as the platform's standard Rf.
- `expected_market_return` = -0.0421 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (calculate_benchmark_return, 1260 trading days). It is GBP-denominated and absorbs FX co-movement. A negative trailing market return makes CAPM alpha look mechanically high.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `historical_volatility` = 0.2428 (Cat B) — 252-day annualised volatility from stored prices, 262 observations. Elevated for a REIT, which reflects the restructure and internalisation.
- `filing_body_gap` = disclosed (Cat B) — SKG.AX ASX filings for 2026-09-29 to 2026-11-27 returned bodies belonging to other issuers (Scorpion Minerals, Cobram Estate, Nanosonics and others). They were discarded as off-topic. Gearing, AFFO coverage, occupancy and NTA could not be verified from primary documents.

## Key Risks
- Distribution cut and payout reset: the DPU and AFFO coverage figures could not be verified from primary filings, so the yield assumption of 5.2% is uncertain.
- Primary-filing data gap: the stored ASX filing bodies were mismatched, so gearing, occupancy, WALE and NTA are unverified. Leverage could exceed the 40% Australian convention if development is debt-funded.
- Higher-for-longer rates: the 4.16% T-bill leaves a thin yield spread and risks AU cap-rate expansion.
- Self-storage demand and occupancy softness, plus execution risk on internalisation and the development pipeline.
- Beta and the market return carry the IASP.L currency-basis noise, and the 5-year benchmark return is negative, inflating CAPM alpha. This is a live-mode directional analysis, not a formal backtest.

## Invalidation Condition
Exit if the next half-year result shows DPU coverage by AFFO below 1.0x or a distribution cut deeper than the roughly 4% yield bear case. Also exit if look-through gearing rises above 40% or occupancy declines for two consecutive quarterly updates. Another trigger is any equity raising at a material discount to NTA, which would undermine the internalisation and recovery thesis.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
