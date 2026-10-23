# Specialist Memo — CRPU.SI

**Memo ID**: `CRPU.SI_2026-10-23_equity_reit_v1@1.0_128f57a6e95b`
**Ticker**: CRPU.SI (Sasseur REIT)
**Market**: Singapore
**Sector**: Retail (Outlet Malls)
**As of**: 2026-10-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Sasseur REIT offers a high headline cash yield from China outlet-mall assets, held through a Singapore-listed vehicle. The base-case E(R) of 5.5% is built from an estimated 8.5% yield, flat DPU growth and a 3% de-rating. The OU Monte Carlo gives a PGain of about 70% with a standard deviation of about 10.4%. CAPM alpha is only about +0.2% because the 5.5% E(R) is roughly in line with the required return. The beta of -0.15 against IASP.L is statistically unreliable (currency basis, 42 observations), so it is not a hedge claim. Conviction was cut one step from 4 to 3 because no filing data was available to verify gearing, AFFO coverage or sponsor support.

## Quantitative Chain

- E(R): 0.0550
- Std dev: 0.1038
- P-gain: 0.7003
- CAPM alpha: 0.0019
- Beta: -0.1462
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - China outlet-mall consumer spending weakens and tenant sales fall. Master-lease and turnover-rent income compresses, and DPU is cut by about 10%. The yield multiple de-rates a further 8-10% as SGD/CNY weakness and higher-for-longer rates (a stagflation-style squeeze) widen the spread to the 4.04% T-bill. Gearing climbs toward the 50% cap.
- **base**: E(R)=0.0550
  - Central case as built: 8.5% distribution yield, flat DPU, and a 3% de-rating of the yield multiple. Occupancy and rent are stable, and gearing and coverage stay within covenants.
- **bull**: E(R)=0.1700
  - Chinese retail spending recovers and outlet sales grow. DPU grows 4-5% from rental reversion and possible sponsor-pipeline injections. The yield multiple recovers about 5% as SGD rates ease and the unit price re-rates toward earlier levels.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=fail
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 0.6 (Cat A) — Latest SGX close of SGD 0.60 on 2026-10-23 from get_price. The stored series shows a drop from about 0.68 to about 0.65 on 2026-09-04, which is possibly an ex-distribution date, and the price has drifted lower to 0.60 since.
- `distribution_yield` = 0.085 (Cat B) — Forward cash yield of 8.5%. This is an analyst estimate from my recollection of Sasseur's recent DPU run-rate, haircut for uncertainty. I could not verify it: get_stored_filings returned zero rows and the SGX announcements lookup failed for CRPU.SI. Treat it as unverified.
- `dpu_growth` = 0.0 (Cat C) — Assumed flat DPU. China outlet-mall consumption is uncertain and the base case gives no credit for organic growth or acquisitions. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = -0.03 (Cat C) — Assumed 3% yield-multiple de-rating over 12 months. The price has fallen about 12% in the last two months, and the 4.04% T-bill rate competes with the yield. E(R) = 8.5% + 0.0% - 3.0% = 5.5%.
- `risk_free_rate_assumption` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill rate of 4.04% on 2026-10-22, via get_tbill_rate.
- `expected_market_return` = -0.0463 (Cat B) — IASP.L trailing 5.17-year annualised log return of -4.63% from calculate_benchmark_return. It is GBP-denominated, so the figure absorbs FX co-movement.
- `data_sample_limitation` = 42 observations (Cat B) — Stored price history holds only about 42 daily observations. The volatility (15.3%) and beta (-0.146, correlation -0.09) are therefore statistically weak. The negative beta is likely noise, not a real hedge characteristic.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unverified fundamentals: no filings or SGX announcements were retrievable, so the yield, gearing, DPU coverage and sponsor-support inputs are not confirmed by Category A data.
- Asset concentration in a small number of China outlet-mall assets, with income sensitive to Chinese consumer spending and RMB/SGD currency moves. The concentration gate is marked fail on that basis, without a conviction override.
- Short price history (42 observations) makes volatility and beta unreliable. The beta is negative, which is likely noise. Price momentum is negative, with about 12% drawdown over two months.
- Higher-for-longer rates (4.04% T-bill) compress the yield spread, and the benchmark IASP.L has a negative 5-year return. A stagflation or rate shock is a downside path.

## Invalidation Condition
Exit if the next reported DPU falls more than 10% year on year, or if AFFO distribution coverage drops below 1.0x for two consecutive reporting periods. Also exit if aggregate leverage rises above 45% without a credible deleveraging plan, if outlet-mall tenant sales or occupancy fall materially, or if verified filings show the assumed 8.5% yield is materially overstated.
