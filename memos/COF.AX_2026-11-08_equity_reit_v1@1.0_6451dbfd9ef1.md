# Specialist Memo — COF.AX

**Memo ID**: `COF.AX_2026-11-08_equity_reit_v1@1.0_6451dbfd9ef1`
**Ticker**: COF.AX (Centuria Office REIT)
**Market**: Australia
**Sector**: Office
**As of**: 2026-11-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
COF is a pure-play Australian office REIT. It offers a high trailing yield of about 11% that is well above the 4.0% T-bill rate, and FY26 results reportedly met distribution guidance. The OU Monte Carlo gives a 12-month simulated return of about 8.9% with a standard deviation of 12.9%, which implies a PGain of about 75.5% and a CAPM alpha of about 9.4%. That alpha is inflated by IASP.L's negative trailing return and carries currency-basis noise. Conviction is cut one step from 4 to 3 because of office structural headwinds, occupancy of about 91%, and incomplete filing verification of leverage and coverage.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1294
- P-gain: 0.7552
- CAPM alpha: 0.0935
- Beta: 0.5050
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or higher-for-longer rates push Australian bond yields up. Office cap rates expand about 50bps and occupancy falls below 89%. Incentives and refinancing costs cut DPU by 15% or more, coverage falls below 1.0x, gearing breaches the 40% convention, and the P/NTA discount widens.
- **base**: E(R)=0.0900
  - Central case as built in the chain: about 11% yield, DPU drifts down 2%, occupancy stable near 91%, cap rates and the P/NTA discount flat.
- **bull**: E(R)=0.2500
  - RBA easing and tighter office cap rates lift valuations. Leasing lifts occupancy toward 93-94%, asset sales at or near book value cut gearing, DPU is held flat, and the discount to NTA narrows by about 10%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `price` = 0.905 (Cat A) — Latest ASX close of AUD 0.905 on 2026-11-06 (get_price).
- `distribution_yield` = 0.11 (Cat B) — Trailing yield of about 11.3% (about 10.2cpu on AUD 0.905). It is taken from secondary news coverage (Kalkine, Jul 2026, quoting 11.28%) and reported FY26 results that met distribution guidance (Motley Fool, Aug 2026). I could not verify the DPU from a filing body, so I haircut it slightly to 11.0%.
- `dpu_growth` = -0.02 (Cat C) — Assumes DPU drifts down about 2% over 12 months. Office faces refinancing and incentive drag, and occupancy is about 91% (Kalkine, Aug 2026). No FY27 guidance was retrievable. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in the cap rate or P/NTA discount over 12 months. Sensitivity is covered in the scenarios.
- `expected_return_build` = 0.09 (Cat C) — E(R) = 11.0% yield + (-2.0%) DPU growth + 0.0% multiple change = 9.0%.
- `filing_body_gap` = disclosed (Cat B) — The stored filing bodies for COF.AX returned by get_stored_filings (Q1 FY27 update, FY26 results, annual report, distribution notices) contain text from unrelated issuers (DevEx, Culpeo, Wiseway, etc.). They were discarded as parsing mismatches. Gearing, WALE, coverage and NTA were not extracted from filings, and the gates below are provisional.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill at 4.00% on 2026-11-05 (get_tbill_rate). This is a USD rate used as the CAPM risk-free input per methodology.
- `expected_market_return` = -0.046088 (Cat B) — Trailing 5.18-year annualised log return of IASP.L from calculate_benchmark_return (lookback 1260). It is GBP-denominated and absorbs FX noise.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Office structural weakness: occupancy around 91%, rising incentives and capex, and possible further valuation write-downs that erode NTA and widen the discount.
- Higher-for-longer rates or an inflation shock (Kalkine flagged an inflation test for the yield). This could force cap-rate expansion, raise refinancing costs, and cut DPU, with gearing near the 40% convention.
- Data gaps: the stored filing bodies were mismatched with other issuers, so gearing, coverage, WALE, NTA and FY27 DPU guidance are unverified. The yield rests on secondary news coverage.
- Beta of 0.50 has a correlation of only 0.32 with the GBP-denominated IASP.L, and the negative 5-year benchmark return makes CAPM alpha look flattering.
- A distribution cut or an equity raise at a deep NTA discount would dilute unitholders. The OU model also may understate tail risk.

## Invalidation Condition
Exit if COF cuts its distribution below guidance or DPU coverage by AFFO falls below 1.0x for two consecutive reporting periods. Also exit if gearing rises above 40% with covenant headroom narrowing, if portfolio occupancy drops below 88% (about 91% now), or if COF raises equity at a steep discount to NTA that dilutes unitholders.
