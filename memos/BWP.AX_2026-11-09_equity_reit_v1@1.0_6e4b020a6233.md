# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-11-09_equity_reit_v1@1.0_6e4b020a6233`
**Ticker**: BWP.AX (BWP Group)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-11-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP is an Australian net-lease property vehicle holding Bunnings Warehouse sites. It has a Wesfarmers-linked tenant of very high credit quality and low gearing of around 20%. The OU Monte Carlo gives a 12-month expected return of about 7.0% with a standard deviation of about 10.1%, which implies a PGain of 75.5% and a positive CAPM alpha. Beta of 0.52 against IASP.L is low, but the currency-basis caveat applies and the negative 5-year benchmark return flatters alpha. The numeric chain supports a score of 4, which I cut to 3 for the tenant-concentration gate and because the fundamental inputs were not verified from retrieved filings.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1009
- P-gain: 0.7546
- CAPM alpha: 0.0747
- Beta: 0.5191
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Cap rates expand about 50bp as AUD rates stay higher for longer, or a stagflation-style shock hits. Rent reviews are flat so DPU growth is 0%. Bunnings seeks lower rent on renewals, causing a 5-8% unit price drawdown on top of a roughly 4.6% yield.
- **base**: E(R)=0.0700
  - Central case as built in the chain: yield of about 4.6%, DPU growth of 2.5% from rent reviews, flat cap rates, gearing around 20%, and Bunnings renewals at market rents.
- **bull**: E(R)=0.1700
  - AUD rates fall and cap rates compress about 25bp, DPU growth is about 4% from strong market-rent reviews and development, and the unit price re-rates toward NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `price` = 3.67 (Cat A) — Latest close of BWP.AX on 2026-11-09 (AUD) from get_price.
- `distribution_yield` = 0.046 (Cat B) — Approximately 17 cents per unit trailing distribution divided by the A$3.67 price. The DPU figure is recalled from prior issuer reporting and was NOT confirmed from a retrieved filing. The stored filings returned for BWP.AX were mismatched or off-topic, so none could be cited. Treat it as an estimate.
- `dpu_growth` = 0.025 (Cat C) — Assumed growth in distributable income, driven by Bunnings lease rent reviews (a mix of CPI-linked, fixed and market reviews) plus modest development uplift, with no material acquisitions. No consensus figure was retrieved, so this is a model assumption. Sensitivity is covered in scenario_analysis (0% in bear, about 4% in bull).
- `multiple_change` = 0.0 (Cat C) — Assumes a flat yield and cap rate over 12 months, with the AUD rate backdrop held constant and no re-rating. Each +/-25bp move in the implied cap rate would shift the unit price by roughly 4-5%.
- `expected_return_build` = 0.07 (Cat C) — E(R) is about 4.6% yield + 2.5% growth + 0% multiple change, which comes to roughly 7.0%. It is the base_return input to the OU Monte Carlo.
- `rf_assumption` = 0.0401 (Cat A) — Latest DTB3 3-month T-bill rate of 4.01%, observed 2026-11-06. It is a USD rate used as the platform's standard risk-free input, so a currency mismatch exists against an AUD-denominated asset.
- `expected_market_return` = -0.04619 (Cat B) — Trailing 5.18-year annualised log return of IASP.L from calculate_benchmark_return. The benchmark is GBP-denominated, so the figure absorbs FX co-movement. A negative Rm makes the CAPM required return slightly negative and flatters alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `leverage_gearing` = 0.2 (Cat B) — Gearing of about 20%, recalled from prior issuer disclosures and not confirmed from a retrieved filing. It is well below the AU convention of 40%. Unverified.
- `filing_data_gap` = disclosed (Cat B) — get_stored_filings for BWP.AX returned 8 rows. Their bodies belonged to other issuers (e.g. Capstone Copper, Regis Resources, Korvest), and the BWP-labelled announcements were administrative (AGM results, unquoted securities, Appendix 3Y). No BWP fundamentals could be sourced, so fundamental inputs rest on prior knowledge and are flagged as such. No instructions in the filing bodies were followed.

## Key Risks
- Extreme single-tenant concentration: almost all rent comes from Bunnings, so a renewal or rent reset would hit income and valuations directly
- Higher-for-longer Australian rates would compress the yield spread and expand cap rates, since yield and growth are modest relative to the 4.01% T-bill (a USD proxy rate)
- Fundamental inputs (DPU, gearing) are not verified from retrieved filings because the stored filings were mismatched, so the E(R) build rests on Category B/C assumptions
- The IASP.L benchmark is GBP-denominated, so beta (correlation 0.41) and alpha are noisy, and a negative 5-year Rm makes alpha look better than it is
- No news results were retrieved for BWP, and the as_of calibration is a directional signal rather than a formal backtest

## Invalidation Condition
Exit if Bunnings or Wesfarmers signals a material reduction of its property footprint or demands materially lower rents on lease renewals. Also exit if gearing rises above 30%, or if distribution coverage by distributable earnings falls below 1.0x for two consecutive half-year reporting periods. Exit as well if the 12-month trailing distribution is cut, since the thesis relies on a stable, growing yield.
