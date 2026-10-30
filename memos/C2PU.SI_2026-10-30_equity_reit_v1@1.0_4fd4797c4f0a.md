# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-10-30_equity_reit_v1@1.0_4fd4797c4f0a`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-10-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Parkway Life REIT offers defensive healthcare exposure anchored by long master leases on Singapore hospitals, with IHH Healthcare as sponsor and rent partly linked to CPI. News reports 1HFY2026 DPU up 14.6% y-o-y to 8.77 cents under a new rental arrangement. The built E(R) of 6.3% is about 2.3pp above the 4.0% T-bill. Realised volatility is low at 10.2% and beta is 0.24 against IASP.L (currency-basis caveat applies). The OU Monte Carlo gives PGain of 81.8% and a base conviction of 4. This is cut one step to 3 because the 12-month distribution and coverage figures could not be verified against filings. The excess return over the risk-free rate is also thin.

## Quantitative Chain

- E(R): 0.0630
- Std dev: 0.0691
- P-gain: 0.8178
- CAPM alpha: 0.0438
- Beta: 0.2373
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Stagflation-style rate shock: SGD yields rise and implied yield expands about 40bp, with a roughly 8% unit price drawdown. The 1HFY2026 DPU uplift partly reverses and DPU growth is 0%. Japan and Malaysia FX translation weakens, and the SGD hospital master-lease reset is less favourable.
- **base**: E(R)=0.0630
  - Central case as built: 4.3% yield, 2% DPU growth from CPI-linked rent escalators, flat yield multiple, gearing stable in the mid-to-high 30s%, and no major rental or lease disruption.
- **bull**: E(R)=0.1400
  - SGD rates ease and the implied yield compresses about 25bp. DPU growth reaches 4% from accretive acquisitions and the new rental arrangement, supporting 3-4% multiple expansion on top of the yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_close_price` = 3.98 (Cat A) — SGD closing price on 2026-10-30 from get_price.
- `distribution_yield` = 0.043 (Cat B) — Estimated forward yield. 1HFY2026 DPU of 8.77 cents (up 14.6% y-o-y, new rental arrangement) is from a news headline dated 2026-08-03. The stored filings reader returned no filings and the SGX announcements API returned 403, so the full-year DPU was not verified against a filing. The yield is approximated at roughly 16.5-17 cents of run-rate DPU over a 3.98 price, with a haircut for the uncertain 2H figure.
- `dpu_growth` = 0.02 (Cat C) — Assumed forward DPU growth. Basis: CPI-linked master-lease rent escalators on the Singapore hospitals, plus the Japan nursing-home and Malaysia assets. The 1HFY2026 step-up is treated as one-off and not extrapolated. Sensitivity is covered in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — No yield or cap-rate re-rating assumed over 12 months. Flat multiple is the neutral assumption. A 25bp move in implied yield would shift total return by about 5-6 percentage points.
- `expected_return_build` = 0.063 (Cat B) — E(R) = 4.3% yield + 2.0% growth + 0.0% multiple change = 6.3%.
- `risk_free_rate` = 0.04 (Cat A) — FRED DTB3 3-month T-bill rate of 4.0% on 2026-10-29, via get_tbill_rate.
- `expected_market_return` = -0.0475 (Cat B) — IASP.L trailing 5.17-year annualised log return, from calculate_benchmark_return (1260-day lookback). The negative figure reflects the weak APAC REIT market over the period, and CAPM alpha is flattered by it.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `gearing_assumption` = 0.37 (Cat C) — Aggregate leverage assumed at about 35-39%, below the 50% Singapore cap. This is from background knowledge, not a filing retrieved this session, so it is unverified.

## Key Risks
- The distribution and AFFO coverage figures are not verified. The filings reader returned nothing and the SGX API returned 403, so DPU and gearing rest on a news headline and background knowledge. The gates are marked info for that reason.
- The yield spread over a 4.0% US T-bill is only about 2.3pp. Higher-for-longer rates could compress the unit price or the valuation multiple.
- The 1HFY2026 DPU uplift from the new rental arrangement may be non-recurring. Master-lease reset terms and tenant concentration in the IHH-related Singapore hospitals are a concentration risk.
- Foreign-asset FX translation (JPY, MYR) and a weak SGD against GBP could add noise. Beta and CAPM alpha are distorted by the GBP benchmark basis, and the negative 5-year IASP.L return flatters alpha.
- The OU Monte Carlo compresses dispersion, with std of 6.9% against 10.2% realised volatility. PGain may therefore be overstated.

## Invalidation Condition
Exit if a filed distribution statement shows DPU coverage by AFFO below 1.0x, or if the 1HFY2026 DPU uplift proves non-recurring and run-rate DPU falls more than 10% below the assumed level. Also exit if aggregate leverage rises above about 45%, or if the Singapore hospital master-lease renewal terms are materially reduced or IHH support is withdrawn.
