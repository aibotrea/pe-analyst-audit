# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-10-16_equity_reit_v1@1.0_1b2fdad40556`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centres
**As of**: 2026-10-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT is a US-dollar data-centre REIT on SGX with sponsor backing from Digital Realty (the Digital CR Singapore Holding unitholder). It offers an assumed 7.5% forward yield, a large spread over the 4.1% T-bill. The OU Monte Carlo gives a simulated 12-month return of 6.9% with 17.1% standard deviation, which implies a PGain of 65.7%. Beta of 0.34 against IASP.L is low but correlation is only 0.16, so it is a weak guide (currency-basis caveat applies). Conviction is cut one step to Low because the stock fell about 16% in two months, the yield, gearing and coverage inputs could not be verified, and an EGM on 22 October 2026 has unknown content.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1711
- P-gain: 0.6570
- CAPM alpha: 0.0598
- Beta: 0.3369
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - Stagflation or rate-shock path: US and SGD rates stay high, data-centre cap rates widen about 50bps and refinancing costs rise. DPU is cut about 10% and the yield multiple de-rates further, extending the recent 16% drawdown. The EGM outcome is dilutive or NAV-destructive. Gearing climbs toward the SG limit and coverage drops below 1.0x.
- **base**: E(R)=0.0700
  - Central case as built: about 7.5% yield, flat DPU, slight multiple contraction of 0.5%, stable occupancy, and no major capital-structure shock.
- **bull**: E(R)=0.2200
  - The EGM and capital recycling prove accretive and lower leverage. AI-driven data-centre demand supports rental reversion of 3-5%. The yield compresses 75-100bps as the price recovers part of the recent drawdown.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `closing_price` = 0.44 (Cat A) — DCRU.SI last close 2026-10-16 in USD (get_price). The stock fell about 16% from 0.525 on 2026-08-18, so there is negative price momentum.
- `distribution_yield` = 0.075 (Cat C) — Forward distribution yield assumption of about 7.5% on a 0.44 price. I could not verify the latest published DPU: the stored SGX filings I retrieved were announcements with no DPU figure, and news searches returned none. The yield is therefore a model assumption, and I tested it in the scenarios.
- `dpu_growth_12m` = 0.0 (Cat C) — Assumes flat DPU growth. Rent escalators and renewals are offset by higher financing costs and possible dilution or asset recycling. An EGM is scheduled for 2026-10-22 (circular dated 2026-10-07; DCRU.SI 2026-10-07 EGM notice). The circular body was not captured, so the resolution content is unknown.
- `multiple_change` = -0.005 (Cat C) — Assumes slight yield-multiple contraction of about 0.5%. The recent drawdown may mean-revert, but there is no catalyst evidence and the EGM outcome is uncertain. E(R) = 7.5% + 0% - 0.5% = 7.0%.
- `risk_free_rate` = 0.041 (Cat A) — FRED DTB3 3-month T-bill 4.10% on 2026-10-15 (get_tbill_rate).
- `expected_market_return` = -0.050363 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return, 1260-day lookback. It is GBP-denominated and absorbs currency noise. The negative market return makes CAPM required return very low (1.02%), which flatters alpha.
- `historical_volatility` = 0.2518 (Cat B) — Annualised volatility from 252-day lookback (259 observations).
- `leverage_data_gap` = not_verified (Cat C) — No gearing or ICR figure was retrievable from the stored filings. Treated as unverified against the 50% SG regulatory ceiling. Conviction was reduced by one step for the data gap and the recent price weakness.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unverified inputs: DPU, AFFO coverage and gearing could not be sourced from retrieved filings, so the yield and growth assumptions are Category C and may be wrong
- EGM on 22 October 2026 (content not captured) could bring dilutive equity issuance, acquisitions or disposals that hurt NAV or DPU
- Sharp price drawdown of about 16% since mid-August with elevated 25% volatility, which may reflect information not captured in the retrieved data
- Higher-for-longer USD rates that raise refinancing costs and widen data-centre cap rates
- Tenant concentration in a few hyperscale or colocation operators, and a sponsor-dependent pipeline
- Benchmark caveats: IASP.L is GBP-denominated with low correlation (0.16) to DCRU, and the negative 5-year market return flatters CAPM alpha

## Invalidation Condition
Exit if the 22 October 2026 EGM approves a transaction that is materially dilutive to DPU or NAV, or if reported aggregate leverage exceeds about 45% (the Singapore limit is 50%), or if DPU coverage by AFFO falls below 1.0x for two consecutive reporting periods, or if the sponsor Digital Realty materially reduces its unitholding or pipeline support.
