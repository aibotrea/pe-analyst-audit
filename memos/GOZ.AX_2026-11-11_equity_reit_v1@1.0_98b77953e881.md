# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-11-11_equity_reit_v1@1.0_98b77953e881`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Diversified (Office/Industrial)
**As of**: 2026-11-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
GOZ offers a high forward cash yield of about 7.3% (Category C, unverified against filed DPU) on a diversified office and industrial portfolio, at 2.04 AUD after a roughly 10% rebound from early-October lows. The OU Monte Carlo gives a 12-month simulated return of 6.9% with a 13.5% standard deviation, so PGain is about 70%. The CAPM alpha of 7.8% is flattered by a negative 5-year IASP.L return and a currency-basis beta of 0.57, and it should not carry much weight. The base score of 3 is cut one step to 2 because leverage, AFFO coverage and WALE could not be verified. The filing bodies returned for this ticker belonged to other issuers. The position cap is therefore 3%.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1346
- P-gain: 0.6969
- CAPM alpha: 0.0783
- Beta: 0.5667
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation-style rate shock: AUD rates move higher and the 3m rate stays above 4%. Office cap rates expand 50bps, valuations fall about 5-6%, and DPU is cut 3-4% as hedges roll and AFFO coverage drops below 1.0x. Beta-driven drawdown with vol of about 20%.
- **base**: E(R)=0.0700
  - Central case as built in the chain: about 7.3% yield, flat DPU, flat cap rates, and a small -0.3% multiple drift. Rebound from the October lows is partly retained.
- **bull**: E(R)=0.2000
  - Rate relief compresses cap rates by about 25bps and the yield spread narrows. Office leasing improves, DPU grows about 2%, and units re-rate toward NAV, adding a 9-10% multiple gain on top of income.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 2.04 (Cat A) — GOZ.AX closing price 2026-11-11 from get_price (AUD). Price was about 1.85 on 2026-10-05 and has rebounded about 10% since.
- `distribution_yield` = 0.073 (Cat C) — Forward distribution yield assumption of about 7.3%, equal to roughly 14.9 cents per unit on a 2.04 price. I could not verify this against a filed FY26 DPU or guidance figure, because the stored filing bodies returned for GOZ.AX belonged to other issuers (see filing_body_gap). Sensitivity: each 1 cpu DPU change moves yield by about 0.5pp.
- `dpu_growth` = 0.0 (Cat C) — Zero forward DPU growth. Office rental growth is offset by higher funding costs as hedges roll, and industrial reversion is modest. Tested in scenario analysis (bear -2% to -4% DPU, bull +2%).
- `multiple_change` = -0.003 (Cat C) — Small negative allowance for multiple and NAV drift, with a flat cap-rate assumption. The AUD 3m T-bill-equivalent environment (DTB3 4.06%) keeps the yield spread thin. E(R) is about 7.0% = 7.3% yield + 0.0% growth - 0.3% multiple.
- `risk_free_rate` = 0.0406 (Cat A) — FRED DTB3 3-month T-bill 4.06% observed 2026-11-09 via get_tbill_rate. This is a US rate used as the platform risk-free rate, not an AUD rate.
- `expected_market_return` = -0.0457 (Cat B) — IASP.L trailing 5.18y annualised log return from calculate_benchmark_return (1260 trading days). GBP-denominated and sensitive to the sample window. A negative Rm inflates CAPM alpha mechanically.
- `filing_body_gap` = disclosed (Cat B) — get_stored_filings for GOZ.AX returned bodies belonging to unrelated issuers (Helix Resources, TerraCom, Kingfisher, Invex, BCAL and others) under GOZ headlines. These were ignored as off-topic. No leverage, AFFO coverage, WALE or occupancy figures were sourced from filings. ASX body capture is also parked. Qualitative gates are therefore unverified.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unverified fundamentals: filing bodies returned for GOZ.AX were from unrelated issuers, so gearing, AFFO coverage, occupancy and WALE are not confirmed. The distribution yield is a Category C estimate.
- Higher-for-longer rates and office cap-rate expansion could compress valuations and push gearing toward or above the 40% AU convention.
- Distribution coverage risk: a payout ratio near or above 100% of AFFO could force a DPU cut if hedges roll at higher rates.
- Currency-basis noise: beta (0.57, correlation 0.34) and Rm (-4.6%) are measured against the GBP-denominated IASP.L, which makes CAPM alpha unreliable.
- Live-mode data and calibration limits: this is a directional signal rather than a formal backtest, with no point-in-time vintage discipline. The risk-free rate is a US T-bill used as a proxy for AUD rates.

## Invalidation Condition
Exit if a filed result or update shows AFFO coverage below 1.0x or a DPU cut of more than 5%, or if aggregate gearing rises above 40% with portfolio valuations falling more than 5%. Also exit if office occupancy or WALE deteriorates materially, or if the unit price closes below about 1.85 AUD, the October 2026 low, on a sustained basis.
