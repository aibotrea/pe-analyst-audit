# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-11-17_equity_reit_v1@1.0_60f14924c34d`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified (Office/Industrial/Residential Development)
**As of**: 2026-11-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mirvac is a diversified Australian property group with office, industrial, retail and residential development exposure. After a roughly 22% one-year share price decline, it trades on an estimated yield of about 5.3%, which sits above the 4.16% T-bill proxy by only about 1.1 points. An active buy-back and a reportedly lower-gearing balance sheet support the base-case E(R) of about 7.8%. The OU Monte Carlo gives a 12-month PGain of 68%, with 16% simulated standard deviation, which supports moderate conviction. Beta of 0.79 against IASP.L carries the currency-basis caveat. Fundamental inputs such as DPS, gearing and coverage rest on unverified secondary information, which limits conviction.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1609
- P-gain: 0.6845
- CAPM alpha: 0.1015
- Beta: 0.7868
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or higher-for-longer rate pathway: AU and US yields rise and cap rates widen by about 50bps. Office valuations fall. Residential settlements slip, FFO and DPS growth turn about -3%, and the multiple compresses about 10%.
- **base**: E(R)=0.0780
  - Central case as built in the chain: yield about 5.3%, DPS growth 2.5%, flat multiple and cap rates. The buy-back provides modest support.
- **bull**: E(R)=0.2200
  - RBA easing and tighter cap rates. Residential development earnings recover, the buy-back is accretive, and the discount to NTA narrows, giving about 10% multiple expansion with DPS growth of about 5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `last_price` = 1.925 (Cat A) — MGR.AX closing price on 2026-11-17 from get_price, AUD.
- `distribution_yield` = 0.053 (Cat B) — Approximate forward distribution yield of about 5.3% at the AUD 1.925 price. This is my estimate from recalled FY26 distribution guidance of roughly 10c per security. I could not verify it against a filing, because the stored filing bodies returned for MGR.AX were mismatched documents from other issuers. Treat as an unverified estimate.
- `dpu_growth` = 0.025 (Cat C) — Assumed 2.5% annual distribution/FFO growth: modest rental reversion in office and industrial, plus residential development recovery and buy-back accretion. This is not consensus-sourced. Sensitivity is shown in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes flat P/FFO and cap rates over 12 months. Shares are down about 22% over one year per news headlines, so there is upside optionality if the discount to NTA narrows. None is assumed in the base case.
- `expected_return_build` = 0.078 (Cat C) — E(R) = yield 5.3% (B) + growth 2.5% (C) + multiple change 0.0% (C) = 7.8%.
- `risk_free_rate_source` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill rate of 4.16% on 2026-11-16 from get_tbill_rate. This is a USD rate used as the risk-free proxy for an AUD asset, which adds currency mismatch.
- `expected_market_return_source` = -0.04108 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return, 1260-day lookback. It is GBP-denominated and absorbs FX effects. The negative value inflates CAPM alpha mechanically.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gearing_assumption` = lower gearing, unverified (Cat B) — News headlines on 2026-11-06 describe Mirvac as having a lower-gearing balance sheet alongside an active on-market buy-back. The ASX buy-back notifications are dated 2026-10-29 to 2026-11-04. I did not verify the gearing figure, which I assume is below the 40% AU convention.

## Key Risks
- Office valuation and cap-rate risk if AU and US rates stay higher for longer, with stagflation as the bear-case pathway
- Residential development earnings are cyclical and settlement timing could disappoint, which affects distribution coverage
- Fundamental inputs (DPS, gearing, AFFO coverage) are not verified from primary filings, because the retrieved filing bodies were off-topic. Estimates therefore carry model risk.
- Beta and alpha are computed against GBP-denominated IASP.L with a correlation of only 0.39. The negative 5-year benchmark return inflates CAPM alpha, so alpha is a weak supporting input.
- The USD T-bill is used as the AUD risk-free proxy, and 12-month OU Monte Carlo outputs are model-dependent

## Invalidation Condition
Exit if reported gearing rises above 35-40% or distribution coverage falls below 1.0x AFFO for two consecutive reporting periods. Also exit if Mirvac cuts its DPS guidance or halts the buy-back because of asset devaluations, or if the AU 10-year yield rises sharply and office cap rates widen by 50bps or more, which would undermine the 7.8% expected return.
