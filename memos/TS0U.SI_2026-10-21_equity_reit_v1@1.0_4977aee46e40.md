# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-10-21_equity_reit_v1@1.0_4977aee46e40`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified (Office/Retail/Hospitality)
**As of**: 2026-10-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
OUE REIT is a Singapore diversified REIT (CBD office, retail and hospitality) trading near its 52-week low at S$0.33. The estimated yield of about 6.8% sits roughly 270bps above the 4.1% T-bill, backed by 1H FY2026 DPU growth of 28.6% YoY to 1.26 cents. The Crowne Plaza Changi divestment, below book value, is a modest deleveraging positive but reduces income. The OU Monte Carlo gives a 12-month expected return of about 6.9% with a standard deviation of 14.1% and PGain of 68.9%. Together with a CAPM alpha of 5.1% (flattered by the negative IASP.L trailing return and a low, noisy beta), this supports moderate conviction at a 5% maximum position.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1407
- P-gain: 0.6890
- CAPM alpha: 0.0508
- Beta: 0.2392
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Singapore rates stay higher for longer or a stagflation-type shock lifts cap rates by 25-50bps. Office and retail rental reversions turn negative. Hotel and Crowne Plaza sale proceeds are redeployed at lower yields, so DPU falls 8-10% and coverage drops below 1.0x. The yield re-rates to about 8%.
- **base**: E(R)=0.0700
  - Central case as built in the chain: yield of about 6.8%, DPU growth of 0.5%, and flat valuation multiple. The divestment closes on schedule and proceeds repay debt, with leverage stable.
- **bull**: E(R)=0.1900
  - Office rents rise on strong CBD demand. Divestment proceeds repay debt, which lowers interest cost. SORA falls and the yield compresses by about 50bps, which adds a re-rating of roughly 7% to a DPU growth of 4-5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `last_price` = 0.33 (Cat A) — TS0U.SI close of S$0.33 on 2026-10-21 from stored prices. The unit price has drifted from about S$0.345 to S$0.33 over the past month.
- `distribution_yield` = 0.068 (Cat B) — Trailing yield estimated from the reported 1H FY2026 DPU of 1.26 cents (+28.6% YoY, news headline, Yahoo Finance Singapore, 2026-07-22) against the S$0.33 price. 1H is simply annualised and haircut for seasonality and the Crowne Plaza Changi divestment income drag. Full-year DPU and the 3Q26 DPU were not retrievable. The 3Q26 business update filing (TS0U.SI 2026-10-21 ANNC) body contains only attachment references.
- `dpu_growth_12m` = 0.005 (Cat C) — Assumed modest forward DPU growth. Lower interest cost and higher office and hospitality income are offset by lost hotel income from the Crowne Plaza Changi Airport divestment (below book value; call option exercise announced in TS0U.SI 2026-10-21 ANNC). Sensitivity is covered in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — Assumes no net yield or cap-rate re-rating over 12 months. The unit trades near its 52-week low, so mean reversion is possible, but there is no clear catalyst and the unit is trending down.
- `expected_return_build` = 0.07 (Cat C) — E(R) is roughly 6.8% yield + 0.5% growth + 0% multiple change, rounded to 7.0%.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month T-bill from get_stored_macro, 4.10% on 2026-10-19. The live get_tbill_rate tool errored, so the stored series was used. This is a USD rate applied to an SGD asset, which is a basis mismatch.
- `expected_market_return` = -0.050186 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return. GBP-denominated, so FX co-movement is included. A negative trailing return makes CAPM alpha look flattering.
- `historical_volatility` = 0.20696 (Cat A) — Annualised volatility from 252-day lookback, 259 observations, stored prices.
- `sponsor_commitment` = OUE Limited sponsor; manager base fee paid in units (Cat A) — TS0U.SI 2026-07-27 ANNC 'Payment of Base Fee by way of issue of new units' and OUE Limited Form 3 filing of 2026-07-27 indicate manager fee alignment and a continuing sponsor unitholding. Sponsor pipeline details were not available.
- `leverage_coverage_data_gap` = not_retrieved (Cat C) — Aggregate leverage and AFFO coverage figures could not be retrieved. The 3Q26 update and 1H26 filing bodies are attachment stubs. The gates are marked info rather than pass, with no override applied. Assumed leverage is below the 50% MAS cap, which is a model assumption.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Currency basis noted: computed beta is 0.239 with correlation of only 0.136, so it is a weak estimate.

## Key Risks
- Higher-for-longer SGD or USD rates compress the yield spread and raise refinancing costs. The unit is price-sensitive to rates and is near its 52-week low.
- Data gaps: aggregate leverage, AFFO coverage, WALE and top-asset concentration were not verified from filing bodies, which are attachment stubs. The yield is estimated from 1H annualised, not from full-year DPU.
- Crowne Plaza Changi sale at below book value could signal NAV erosion and reduce income, with execution and redeployment risk.
- Hospitality and retail earnings are cyclical, and concentration in Singapore CBD office adds single-market risk.
- Beta (0.24, correlation 0.14) and the negative IASP.L 5-year return (GBP basis) make CAPM alpha a weak supporting input, and the USD T-bill is a mismatched Rf for an SGD asset. This is a live-mode directional memo, not a formal backtest.

## Invalidation Condition
Exit if aggregate leverage rises above about 45% toward the 50% MAS limit, if DPU coverage falls below 1.0x AFFO for two consecutive reporting periods, or if the Crowne Plaza Changi divestment fails or proceeds are redeployed into lower-yielding assets that cut DPU by more than 10%. Also exit if the unit breaks decisively below S$0.30 with negative office rental reversions.
