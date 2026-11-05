# Specialist Memo — VCX.AX

**Memo ID**: `VCX.AX_2026-11-05_equity_reit_v1@1.0_514c76de78da`
**Ticker**: VCX.AX (Vicinity Centres)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-11-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Vicinity Centres is a large Australian retail property trust with a portfolio of premium malls and outlet centres. It is internally managed, which removes external-manager fee leakage, and it has low-to-moderate gearing. The assumed trailing yield of about 4.7% and 3% distribution growth give a 7.5% base E(R), a modest premium to the 4.03% T-bill rate. The OU Monte Carlo gives a PGain of 69% on 14.9% simulated dispersion. Beta of 0.68 against IASP.L carries the currency-basis caveat, and the positive CAPM alpha of 9.05% is flattered by the benchmark's negative five-year return. The David Jones administration (price-sensitive announcement on 2026-11-05) is a near-term headwind. Conviction is Moderate with no gate overrides.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.1492
- P-gain: 0.6908
- CAPM alpha: 0.0905
- Beta: 0.6828
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Retail cap rates widen by 40-50bps as RBA and US rates stay higher for longer. David Jones administration leaves anchor vacancies and rent write-downs beyond the roughly A$34m of rent flagged in the news. Distribution growth is about 0% and FFO payout rises above 80%. The P/FFO multiple de-rates further and a stagflation-style consumer slowdown cuts specialty sales.
- **base**: E(R)=0.0750
  - Central case as built in the chain: yield 4.7%, distribution growth 3%, multiple drift of -0.2%, cap rates flat. The David Jones space is re-let or backfilled with limited income loss, and gearing stays in the mid-to-high 20s%.
- **bull**: E(R)=0.2000
  - Easing in the rate cycle compresses cap rates by 25bps. Retail sales stay resilient and the David Jones space is re-let at higher rents. Distribution growth reaches about 5% and the P/NTA discount narrows, adding a multiple re-rating of about 8-10%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.047 (Cat B) — Approximate trailing distribution of about 11.6-12.0 cents per security against a closing price of AUD 2.47 on 2026-11-05 (get_price). The price is observed. The DPS comes from my recollection of recent published results and not from a retrieved filing, so it is classed B and should be verified. The stored filing bodies returned for VCX.AX were for unrelated issuers and were discarded as off-topic.
- `dpu_growth` = 0.03 (Cat C) — Assumed forward distribution growth of 3%, from comparable-centre NOI growth of about 3% with fixed-rate debt rolling to higher cost. Tested in the bear and bull scenarios at roughly 0% and 5%.
- `multiple_change` = -0.002 (Cat C) — Assumed small P/FFO and NAV discount drift, mainly the David Jones administration drag on sentiment. Cap rates are assumed flat. Sensitivity is covered in the scenario analysis.
- `expected_return_build` = 0.075 (Cat C) — E(R) = yield 4.7% (B) + growth 3.0% (C) + multiple change -0.2% (C) = 7.5%.
- `risk_free_rate` = 0.0403 (Cat A) — FRED DTB3 3-month T-bill rate of 4.03% observed on 2026-11-04.
- `expected_market_return` = -0.0414 (Cat B) — Trailing annualised log return of IASP.L over 1260 days (about 5.2 years of observations). The benchmark is GBP-denominated, so the figure absorbs FX effects. It is negative and makes CAPM alpha look flattering.
- `gearing` = approx. 25-30% (Cat B) — Recalled from recent results, not verified from a retrieved filing. Assumed to be inside the Australian convention of below 40%.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- David Jones administration: anchor-tenant vacancy, rent loss and re-leasing risk across Vicinity's malls (news flags roughly A$34m of rental income exposure). The stored filing bodies did not cover this, so the exposure is unverified.
- Higher-for-longer Australian and US rates widening retail cap rates and compressing the yield spread over the 4.03% T-bill. The yield and gearing inputs are not verified from retrieved filings.
- Consumer spending slowdown hitting specialty-store sales and occupancy cost ratios, which pressures rent growth and FFO.
- Beta and CAPM alpha rely on the GBP-denominated IASP.L benchmark (low correlation of 0.37) and a negative five-year benchmark return, so alpha is overstated and noisy. Treat PGain as the primary metric.
- Fundamental inputs (DPS, gearing, coverage) come from recalled data. The filing bodies retrieved for VCX.AX were unrelated issuers' documents and were not used.

## Invalidation Condition
Exit if Vicinity's distribution cover falls below 1.0x AFFO for two consecutive reporting periods, if gearing rises above 35% (the 40% Australian convention ceiling minus a buffer), or if portfolio occupancy drops below 98% alongside a material rent write-down from the David Jones administration. Also exit on a cut to FFO or distribution guidance of more than 5%, or on a cap rate expansion of more than 50bps in independent valuations.
