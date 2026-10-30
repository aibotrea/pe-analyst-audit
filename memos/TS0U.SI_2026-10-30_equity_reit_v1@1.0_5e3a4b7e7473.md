# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-10-30_equity_reit_v1@1.0_5e3a4b7e7473`
**Ticker**: TS0U.SI (OUE Real Estate Investment Trust (OUE REIT))
**Market**: Singapore
**Sector**: Diversified Commercial/Hospitality
**As of**: 2026-10-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
OUE REIT offers a high running yield of about 7.3% on a SGD 0.335 unit price, roughly 330bps above the 4.0% T-bill rate. Momentum is positive: 1H2026 DPU rose 28.6% y-o-y to 1.26 cents and 3Q26 NPI rose 4.6% y-o-y. The OU Monte Carlo gives a 12-month expected return of about 8.2% against a 14.3% standard deviation, for a PGain of 71.8%. The beta of 0.27 has weak fit (correlation 0.15) and carries the IASP.L currency-basis caveat, so the positive CAPM alpha of 6.7% is only a supporting input. Conviction is held at 3 (moderate) rather than 4 because the A$864m Sydney acquisition's funding and gearing impact, and AFFO coverage, are unverified.

## Quantitative Chain

- E(R): 0.0830
- Std dev: 0.1425
- P-gain: 0.7183
- CAPM alpha: 0.0666
- Beta: 0.2697
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Stagflation or higher-for-longer rate pathway lifts SG cap rates and REIT yields by about 50bps. The A$864m Salesforce Tower acquisition is funded with debt-heavy or dilutive equity, so gearing moves toward the 45-50% area and DPU is cut. Singapore office and hotel recovery stalls and Sydney office valuations soften. Distribution yield falls to about 6%, with a multiple de-rating of about 10%.
- **base**: E(R)=0.0830
  - Central case as built in the chain: 7.3% yield, 1% growth, no multiple change. The acquisition is broadly DPU-neutral, Singapore commercial rents hold, and gearing stays within limits.
- **bull**: E(R)=0.2000
  - Acquisition is accretive and funded prudently, with asset recycling proceeds such as Crowne Plaza Changi Airport used to cut debt. DPU growth of 5% or more is sustained, SG rate cuts compress yields by about 50bps, and the unit price re-rates about 8%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 0.335 (Cat A) — Latest close SGD 0.335 on 2026-10-30 from get_price.
- `distribution_yield` = 0.073 (Cat B) — 1H2026 DPU of 1.26 cents (+28.6% y-o-y, per news reports of the 2026-07-21 results release; the stored filings carry no body text for that release) annualised to about 2.5 cents and divided by SGD 0.335 gives about 7.5%. Trimmed to 7.3% for possible dilution from the Salesforce Tower acquisition funding and the Crowne Plaza Changi Airport divestment completed 2026-10-30. The annualisation is my own derivation.
- `dpu_growth` = 0.01 (Cat C) — Forward DPU/NAV growth of 1% a year. This is a conservative assumption: the 28.6% 1H26 DPU jump is not extrapolated, and the A$864m acquisition of about 50% of 180 George Street (TS0U.SI 2026-10-23 asset acquisitions and disposals filing) is treated as roughly neutral until funding terms are verified. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No yield re-rating or de-rating assumed over 12 months. A cap-rate or yield move of +/-50bps would move total return by roughly -/+6 to 7 percentage points.
- `expected_return_build` = 0.083 (Cat B) — E(R) = 7.3% yield + 1.0% growth + 0.0% multiple change = 8.3%. It is an additive build from the components above.
- `risk_free_rate` = 0.04 (Cat A) — 3M T-bill (DTB3) of 4.00% on 2026-10-29 from get_tbill_rate.
- `expected_market_return` = -0.047539 (Cat B) — Trailing 5-year annualised log return of IASP.L (1260-day lookback, 5.17 years observed). It is negative and GBP-denominated, so it absorbs FX moves. As the CAPM market return it lowers the required return, so it flatters alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `beta_reliability` = 0.2697 (Cat B) — Beta of 0.27 with correlation of only 0.152 over 252 observations. The low fit means CAPM alpha is a weak supporting input, which is why PGain is the primary metric.
- `sponsor_and_fee_structure` = OUE Limited sponsor; base fee paid in units (Cat A) — TS0U.SI 2026-10-26 and 2026-07-27 general announcements show base fees paid in new units. TS0U.SI 2026-07-27 substantial unitholder notice (Form 3) shows OUE Limited remains a substantial unitholder.
- `gearing_unverified` = not verified (Cat C) — Aggregate leverage, AFFO coverage and WALE could not be sourced because the 3Q26 business update body was PDF-only, and the SGX live API returned a 403 error. The assumption is that gearing stays below the MAS 50% limit after the Salesforce Tower acquisition. A one-step conviction override was applied for this gap.

## Key Risks
- Acquisition funding and leverage: the A$864m, roughly 50% stake in Salesforce Tower (180 George Street, Sydney) could lift gearing or dilute DPU through equity issuance. Gearing, funding mix and coverage figures were not verified.
- Interest-rate and refinancing risk: higher-for-longer rates could widen yield spreads, raise the cost of debt and compress valuations in a high-yield, higher-gearing REIT.
- Concentration and cyclicality: exposure to Singapore CBD office and hospitality, plus new Australian office and AUD currency exposure, raises the risk of valuation and tenant-demand shocks.
- Statistical weakness: beta correlation is only 0.15 and IASP.L is GBP-denominated with a negative 5-year return, so the CAPM alpha is noisy. Sponsor-related transactions (OUE Limited interested person transactions) add governance risk.
- Data gaps: the 3Q26 business update, the acquisition announcement and the Crowne Plaza divestment body text were PDF attachments that were not captured, and the SGX live API failed. DPU yield rests on news-reported 1H26 figures.

## Invalidation Condition
Exit if gearing after funding the Salesforce Tower acquisition rises above about 45% (toward the 50% MAS limit), or if DPU coverage by AFFO falls below 1.0x for two consecutive reporting periods. Also exit if the acquisition is funded with materially DPU-dilutive equity that cuts forward DPU by more than 10%, or if Singapore office and hotel occupancy drops sharply with negative rental reversions.
