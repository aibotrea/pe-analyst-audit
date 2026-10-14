# Specialist Memo — NTDU.SI

**Memo ID**: `NTDU.SI_2026-10-14_equity_reit_v1@1.0_afeb2411eb55`
**Ticker**: NTDU.SI (NTT DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-10-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
NTT DC REIT offers USD-denominated data-centre exposure backed by the NTT group sponsor, with long-lease hyperscale and colocation tenants. The forward yield is estimated at about 6.5%, and the DPU was reported above the IPO forecast. The OU Monte Carlo gives an expected 12-month return of 7.4% and a PGain of about 71%. Beta of 0.28 versus IASP.L is low but has weak explanatory power because of the currency basis. The numeric chain scores 4, but I lowered it to 3 because gearing, AFFO coverage and lease profile could not be confirmed from filings.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.1350
- P-gain: 0.7092
- CAPM alpha: 0.0601
- Beta: 0.2839
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Higher-for-longer USD rates, or a stagflation-type shock, widen the SGX data-centre REIT yield spread by about 75bps and compress valuations. Hyperscale tenant renewals are weaker, DPU growth is 0%, and gearing rises toward the 50% regulatory limit on refinancing at higher cost. Yield is about 6.0% and the multiple change is about -14%.
- **base**: E(R)=0.0750
  - Central case as built in the chain: 6.5% yield, 2% DPU growth from rent escalators, and 1% multiple drag. Occupancy stays near full, gearing is stable, and the OU Monte Carlo gives a mean of 7.4%.
- **bull**: E(R)=0.1900
  - AI and cloud demand drives accretive sponsor-pipeline acquisitions and positive rent reversions. DPU growth is about 5%, and a US rate cuts cycle compresses yields for a 7% multiple gain. Yield is about 7%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 0.87 (Cat A) — Latest close on 2026-10-14 from get_price, quoted in USD (the REIT is USD-denominated and listed on SGX).
- `distribution_yield` = 0.065 (Cat B) — News reports (Business Review, May 2026) give an FY2026 DPU of about US$0.0708, 2.6% above the IPO forecast. I could not confirm whether that figure covers a full 12 months, and no stored filings or SGX announcements were available. Dividing it by the 0.87 price gives about 8.1%. I used a conservative 6.5% forward yield instead and treated it as a derived estimate. Sensitivity: each 1pt change in yield moves E(R) by 1pt.
- `dpu_growth` = 0.02 (Cat C) — Assumed forward DPU growth of 2%, from contractual rent escalators on long-WALE hyperscale and colocation leases, with no acquisitions assumed. This is not backed by consensus data. It is tested in the bear and bull cases.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% drag from yield-multiple compression reversing. The price of 0.87 is about 24% above the S$/US$0.70 IPO level as I recall it. Sensitivity is covered in the scenarios.
- `expected_return_build` = 0.075 (Cat B) — E(R) = 6.5% yield + 2.0% growth - 1.0% multiple change = 7.5%. It is a sum of the components above, which are classed B and C.
- `risk_free_rate` = 0.0409 (Cat A) — FRED DTB3 3-month T-bill rate of 4.09% on 2026-10-13, via get_tbill_rate. The REIT is USD-denominated, so the USD risk-free rate fits.
- `expected_market_return` = -0.0507 (Cat B) — Trailing 5.17-year annualised log return of IASP.L, from calculate_benchmark_return with a 1260-day lookback. The benchmark is GBP-denominated, so the return absorbs FX noise. It is negative, which mechanically lifts CAPM alpha for a low-beta stock.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. The computed beta is 0.28 with a correlation of only 0.17, so it has low explanatory power.
- `filing_data_gap` = no_filings_available (Cat B) — get_stored_filings returned 0 rows for NTDU.SI, and the SGX announcements tool returned 'NTDU.SI not in SGX lookup table'. Gearing, AFFO coverage, WALE, tenant concentration and fee structure could not be verified from primary filings. One-step downward gate override applied for this reason.

## Key Risks
- Unverified balance sheet and distribution data: no filings were retrievable, so gearing, AFFO coverage, WALE and tenant concentration are unconfirmed, and the DPU annualisation is uncertain
- Rates and refinancing: USD T-bill rates are about 4.1%, which narrows the yield spread and raises refinancing cost on floating-rate debt
- Tenant and asset concentration: a small portfolio with a few hyperscale tenants and a few large data-centre assets, plus a sponsor-dependent growth pipeline
- Valuation: the price is about 24% above IPO, which leaves less room for multiple expansion, and data-centre supply and power constraints could pressure rents
- Beta and alpha are noisy because of IASP.L's GBP basis, and the benchmark's negative 5-year return inflates CAPM alpha; the live-data analysis is a directional signal and not a formal backtest

## Invalidation Condition
Exit if aggregate leverage rises above 45% (toward the 50% Singapore regulatory limit) or DPU coverage falls below 1.0x AFFO for two consecutive reporting periods. Also exit if a major hyperscale tenant fails to renew or cuts its lease, if NTT formally withdraws its pipeline commitment, or if the price falls more than 20% from 0.87 with no change in fundamentals.
