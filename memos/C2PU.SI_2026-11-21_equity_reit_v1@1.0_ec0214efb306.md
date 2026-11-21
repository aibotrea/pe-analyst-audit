# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-11-21_equity_reit_v1@1.0_ec0214efb306`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-11-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
C2PU.SI (Parkway Life REIT) is a Singapore-listed healthcare REIT with long-dated master leases, CPI-linked escalators and a defensive tenant base. The 12-month E(R) is built at about 7.0%, made up of roughly 4.2% yield, 2.8% growth and no re-rating. The OU Monte Carlo gives a simulated return of 6.97% with a 6.95% standard deviation, so PGain is 84.2%. Beta is low at 0.25 against IASP.L (currency-basis caveat applies), and CAPM alpha is about 4.9%. The numeric chain supports a conviction of 4, but I applied one step down to 3 because the yield, coverage and gearing inputs could not be verified from filings.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.0695
- P-gain: 0.8419
- CAPM alpha: 0.0489
- Beta: 0.2491
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Higher-for-longer rates, with SGD and JPY rate pressure pushing yield expansion of about 50-75bps. DPU growth stalls near 0% as master-lease escalators reset lower. JPY weakness reduces translated Japan income. Gearing rises toward the regulatory limit on valuation declines. A stagflation-style shock hits real-asset valuations.
- **base**: E(R)=0.0700
  - Central case as built in the chain. Yield is about 4.2%, DPU growth is about 2.8% from lease escalators, there is no multiple change, and the master-lease structure keeps coverage stable.
- **bull**: E(R)=0.1600
  - Rates ease and the spread to the 4.16% T-bill widens as yields compress by 25-50bps. Accretive acquisitions or sponsor pipeline assets lift DPU growth to about 5%. Rent escalators come in above CPI.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 3.92 (Cat A) — Latest SGX close of SGD 3.92 on 2026-11-20 from get_price.
- `distribution_yield` = 0.042 (Cat C) — Approximate trailing DPU yield of about 4.2% on the SGD 3.92 price. I could not verify the DPU against a filing. The SGX announcements API returned 403 and no stored filings were available. A news headline from August 2026 reports a 14.6% DPU increase. The yield is an analyst estimate and should be checked against published DPU. A 50bp error moves E(R) by about 0.5pp.
- `dpu_growth` = 0.028 (Cat C) — Assumed forward DPU growth of about 2.8%, driven by CPI-linked and minimum-guaranteed master-lease rent escalators in Singapore and Japan plus modest organic growth. This is not consensus-verified. Sensitivity of plus or minus 1.5pp is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes no change in yield or cap rate. The 12-month price return from re-rating is set to zero. This is a neutral assumption, and the bear case allows for yield expansion.
- `expected_return_build` = 0.07 (Cat B) — E(R) is about 4.2% yield plus 2.8% growth plus 0% multiple change, which is roughly 7.0%. This is a derived estimate and depends on the Category C inputs above.
- `risk_free_rate` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill rate of 4.16% observed 2026-11-19 via get_tbill_rate.
- `expected_market_return` = -0.040739 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (1305 observations), computed in GBP. The result is negative, which is unusual for a CAPM market return, so alpha is mostly driven by Rf and a low beta.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_data_gap` = disclosed (Cat C) — No stored filings were available for C2PU.SI in the 365-day lookback, and the live SGX announcement call failed. Gearing, AFFO coverage, occupancy and WALE could not be verified from issuer documents. The gates are marked info and a one-step conviction haircut was applied for the data gap.

## Key Risks
- Yield spread versus the 4.16% US T-bill is thin on an estimated 4.2% yield. Higher-for-longer rates could drive yield expansion and unit-price declines.
- Unverified fundamentals: the SGX feed failed and no stored filings were available, so gearing, AFFO coverage, WALE and lease-renewal terms are unconfirmed.
- Beta of 0.25 and correlation of 0.29 against the GBP-denominated IASP.L carry heavy FX and basis noise. The negative 5-year benchmark return of -4.1% makes CAPM alpha less reliable.
- JPY and SGD currency exposure on Japan assets, plus master-lease rent reset risk and tenant concentration in a few operators.
- Live-mode analysis with a limited news feed: the 14.6% DPU jump reported in August 2026 coincided with falling revenue and NPI, which may reflect one-offs and may not be sustainable.

## Invalidation Condition
Exit if reported DPU coverage falls below 1.0x for two consecutive half-year periods, if aggregate leverage rises above about 40% on the way to the 45% MAS limit, or if the master-lease rent reset or renewal terms are materially reduced. Exit also if the unit price moves to an implied yield above about 5.0% without improving fundamentals, or if the stated DPU growth proves non-recurring.
