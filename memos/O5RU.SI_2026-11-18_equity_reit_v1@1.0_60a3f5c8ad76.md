# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-11-18_equity_reit_v1@1.0_60a3f5c8ad76`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-11-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT is a small-cap Singapore industrial REIT with an estimated yield of about 5.7%, about 160bps above the 4.15% US T-bill rate. Management is extending the portfolio into Australian industrial assets, with the Perth Hazelmere acquisition announced in July 2026, and a Beansprout headline reports steady DPU growth in 1Q FY2027. The OU Monte Carlo gives a 12-month expected return of 7.1% with 11.3% standard deviation, which yields a PGain of 73.6%. Beta of 0.37 against IASP.L is low, but the currency-basis caveat applies and correlation is only 0.27. The numeric chain supports conviction 4. I reduced it one step to 3 because the yield, gearing and AFFO coverage figures could not be verified from the filing bodies.

## Quantitative Chain

- E(R): 0.0720
- Std dev: 0.1131
- P-gain: 0.7363
- CAPM alpha: 0.0618
- Beta: 0.3748
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Stagflation or rate-shock path: SGD rates and the 10-year yield rise, so cap rates widen by 25-50bps and P/NAV compresses by about 8-10%. Refinancing costs rise, AFFO coverage slips below 1.0x, the DPU is cut by about 5%, and the new CEO transition adds execution risk.
- **base**: E(R)=0.0720
  - Central case as built: yield about 5.7%, DPU growth about 1.5% (Perth acquisition plus organic reversion), flat multiple, stable occupancy and gearing within the 50% cap.
- **bull**: E(R)=0.1700
  - SGD rates fall, P/NAV re-rates by 5-6%, and accretive acquisitions plus rental reversion lift DPU growth to about 4-5%. The sector income-seeking bid returns.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_close_price` = 1.34 (Cat A) — Stored close for O5RU.SI on 2026-11-18 (SGD 1.34).
- `distribution_yield` = 0.057 (Cat B) — Estimated trailing distribution yield of about 5.7% on SGD 1.34. This is my estimate from recalled historical DPU levels. I could not verify it. The O5RU.SI 2026-10-15 CACT filing shows a declared rate of SGD 0.0016 for 01/07/2026-30/09/2026, and its body was truncated, so it is not usable as a full-period DPU. The 1H FY2027 results body (O5RU.SI 2026-10-15 half-yearly results) only lists attachments and has no figures. Treat the yield as an unverified estimate.
- `dpu_growth_12m` = 0.015 (Cat C) — Assumed forward DPU/NAV growth of 1.5%. This is organic rent reversion plus a small contribution from the Perth (Hazelmere) industrial acquisition announced in O5RU.SI 2026-07-09 asset acquisition announcement, whose body had no financials. A Beansprout headline dated 2026-08-05 reports steady 1Q FY2027 DPU growth. Sensitivity: each +/-1% of growth moves E(R) by about 1 point.
- `multiple_change` = 0.0 (Cat C) — Assumed flat P/NAV and cap rates over 12 months. Price is near the lower end of its recent range. No re-rating is assumed.
- `expected_return_build` = 0.072 (Cat C) — E(R) = yield 5.7% + growth 1.5% + multiple change 0% = 7.2%.
- `risk_free_rate` = 0.0415 (Cat A) — FRED DTB3 3-month T-bill at 4.15% on 2026-11-17 (live tool).
- `expected_market_return` = -0.0419 (Cat B) — IASP.L trailing 5.18-year annualised log return, 1260-day lookback. It is GBP-denominated and absorbs FX effects.
- `historical_volatility` = 0.1664 (Cat B) — 252-day annualised volatility from stored prices (259 observations).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Currency basis caveat applies.
- `beta_value` = 0.3748 (Cat B) — 252-day beta vs IASP.L with correlation of only 0.27. Low explanatory power, so alpha is a weak supporting input.
- `sponsor_and_governance` = info (Cat A) — O5RU.SI 2026-10-01 announcement: Lim Joo Lee (internal, joined 2021, led finance and IR) appointed CEO, replacing Russell Ng. O5RU.SI 2026-06-26 tax ruling: S$100m 4.25% subordinated perpetual securities. Director and manager interest disclosures were filed 2026-10-27, but their content sits in unparsed PDF attachments.
- `leverage_and_coverage_data_gap` = unverified (Cat C) — Gearing, AFFO coverage, occupancy, WALE and top-asset concentration figures were not extractable from the stored filing bodies (PDF attachments only). They were not verified against the framework gates, so a one-step conviction reduction is applied as a prudential measure.

## Key Risks
- Key fundamentals (DPU, gearing, AFFO coverage, occupancy, WALE) were not verified from filing bodies. The yield and E(R) rely on an unverified estimate.
- Higher-for-longer rates (T-bill at 4.15%) compress the yield spread and raise refinancing costs. A perp at 4.25% and floating-rate debt expose DPU to rate resets.
- CEO transition on 2026-10-01 (internal successor) and small-cap liquidity bring execution and governance risk.
- Australian expansion adds AUD/SGD currency exposure and offshore-asset execution risk.
- Low beta correlation (0.27) to a GBP benchmark makes alpha and market return noisy. The 5-year IASP.L return is negative at -4.2%. This is a live (non-backtest) directional estimate, not a vintage-disciplined backtest.

## Invalidation Condition
Exit if gearing rises above the 45-50% MAS limit or AFFO distribution coverage falls below 1.0x for two consecutive reporting periods. Also exit if a DPU cut of more than 5% is declared, or if occupancy falls materially below its current level. Exit as well if verified filings show the actual trailing yield is well below the 5.7% assumed here, which would undermine the expected return of about 7%.
