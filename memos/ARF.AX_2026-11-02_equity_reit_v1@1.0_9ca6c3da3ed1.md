# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-11-02_equity_reit_v1@1.0_9ca6c3da3ed1`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Social Infrastructure (Early Learning/Childcare and Healthcare)
**As of**: 2026-11-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
ARF offers Australian social-infrastructure exposure (childcare and healthcare) with a guided FY27 distribution yield of about 7.4% at the AUD 2.64 price, well above the 3.99% T-bill rate. The October 2026 guidance upgrade and Goodstart's takeover of 31 Edge Early Learning businesses reduce, but do not eliminate, the tenant-credit overhang from Edge's administration. The 12-month OU Monte Carlo gives a simulated return of 8.3% on 25.2% standard deviation and a PGain of 62.9%. Beta of 0.72 versus IASP.L carries a currency-basis caveat and a low correlation of 0.23. The base score of 3 is cut by one step to 2 because of the unresolved tenant-concentration and credit event and the sharp recent rally.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.2516
- P-gain: 0.6290
- CAPM alpha: 0.1068
- Beta: 0.7190
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - Edge Early Learning wind-up leaves a larger share of the childcare portfolio vacant or re-let at lower rents, and the Goodstart transaction covers fewer sites than expected. FY27 distributions come in below the 19.0c low end of guidance, and a rate shock or stagflation pushes cap rates out by 25-50bps. The yield multiple compresses and the stock gives back the October rally to around 2.0-2.1.
- **base**: E(R)=0.0840
  - Central case as built in the chain: distributions land near the 19.6c guidance midpoint (7.4% yield), growth is 2.0%, Goodstart takes over the Edge sites without material rent loss, cap rates are flat, and the multiple gives back 1%.
- **bull**: E(R)=0.2500
  - Goodstart (a not-for-profit childcare operator) takes over the 31 Edge businesses at or above passing rents, FY27 distributions reach the 20.2c top end or higher, and development completions add earnings. RBA easing compresses AU REIT yields, and the multiple re-rates by about 8-10% on top of the 7.4% yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 2.64 (Cat A) — ARF.AX closing price 2026-11-02 (AUD) from get_price. The stock rallied about 33% from the 2026-10-05 low of 1.985 after the FY27 guidance upgrade and the Edge/Goodstart news.
- `distribution_yield` = 0.074 (Cat B) — FY27 distribution guidance of 19.0-20.2 cents per security (midpoint 19.6c), as reported in news coverage of the 2026-10-19 guidance upgrade. The guidance is issuer-published but forward-looking, so it is Category B. Yield is 19.6c divided by the 2.64 price. I could not read the primary ASX document: the stored filing bodies returned for ARF.AX were mismatched content from other issuers, which I ignored.
- `dpu_growth` = 0.02 (Cat C) — Assumed 2.0% distributable earnings and DPU growth over 12 months from rent indexation and development completions. This is partly offset by uncertainty over Edge Early Learning rent recovery and re-letting. Sensitivity is covered in the bear and bull cases.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% yield-multiple contraction (negative return contribution) as partial mean reversion after the sharp rally from the October lows. A flat multiple would add 1 percentage point to E(R).
- `expected_return_build` = 0.084 (Cat C) — E(R) = 7.4% yield + 2.0% growth - 1.0% multiple change = 8.4%. Components are classified B, C and C as above.
- `risk_free_rate` = 0.0399 (Cat A) — FRED DTB3 3-month T-bill rate of 3.99% observed 2026-10-30, from get_tbill_rate.
- `expected_market_return` = -0.04732 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260-day lookback). It is a GBP-denominated index, so the figure absorbs FX noise. A negative Rm makes CAPM alpha look mechanically high.
- `historical_volatility` = 0.370236 (Cat B) — 252-day annualised realised volatility, 262 observations. This is elevated by the October 2026 tenant-event price swings, so it may overstate the forward steady-state volatility of a net-lease REIT.
- `gearing_data_gap` = not_verified (Cat C) — I did not retrieve a filed gearing or ICR figure for ARF in this session. The leverage gate is marked info. The assumption is that gearing sits inside the AU <40% convention, which is unverified.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Tenant credit and concentration: the Edge Early Learning administration and rent default could mean longer vacancy, lower re-let rents or impairments if the Goodstart transition is incomplete.
- Rate and cap-rate risk: higher-for-longer AU or US rates, or a stagflation shock, would widen cap rates and compress valuations. The 12-month realised volatility of 37% is high for a net-lease REIT.
- Data gaps: gearing, ICR and AFFO coverage were not verified from primary filings, because the stored filing bodies were mismatched content from other issuers. The FY27 guidance figures come from secondary news coverage.
- Momentum reversal after a roughly 33% rally in a month, with the multiple-contraction assumption being a Category C judgment.
- Benchmark and macro limits: IASP.L is GBP-denominated, so beta and Rm carry currency noise. The negative 5-year Rm (-4.7%) inflates CAPM alpha. Only one macro series (DTB3) was used, and any Phase 2 calibration is a directional signal rather than a formal backtest.

## Invalidation Condition
Exit if Edge Early Learning rent is not substantially replaced under the Goodstart transaction, for example if more than about 10% of childcare portfolio income stays vacant or is re-let at materially lower rents. Also exit if FY27 distribution guidance is cut below the 19.0 cent low end, if filed gearing rises above 40% or distribution coverage by distributable earnings falls below 1.0x, or if the price falls back below roughly AUD 2.00, the pre-upgrade low.
