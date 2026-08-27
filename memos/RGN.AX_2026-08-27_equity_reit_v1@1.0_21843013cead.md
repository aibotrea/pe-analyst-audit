# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-27_equity_reit_v1@1.0_21843013cead`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Neighbourhood Shopping Centres
**As of**: 2026-08-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group is Australia's largest owner of neighbourhood and sub-regional shopping centres, with a portfolio of ~70+ assets anchored predominantly by Woolworths and Coles supermarkets — providing structurally defensive, non-discretionary retail cash flows. At AUD 2.23 as of 27 August 2026, the trust offers a trailing distribution yield of approximately 5.96%, representing a meaningful spread over the 3.7% US T-bill proxy. FY26 results (announced 18 Aug 2026) confirmed growth and a confident management outlook, while the subsequent ~8% price sell-off appears to reflect profit-taking rather than a fundamental deterioration, creating a modest entry point. Beta of 0.44 versus IASP.L (currency-basis caveat applies) indicates below-market sensitivity, consistent with the defensive grocery-anchored retail profile, and the OU Monte Carlo PGain of 80.5% at a 12-month horizon supports an above-average conviction rating.

## Quantitative Chain

- E(R): 0.0846
- Std dev: 0.0977
- P-gain: 0.8054
- CAPM alpha: 0.0841
- Beta: 0.4406
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Supermarket anchor attrition or lease non-renewal drives occupancy below 95%; DPU cut of 5-8% as discretionary specialty tenant failures accelerate amid a domestic consumption downturn or RBA-induced recession; cap rate expansion of 50bps compresses NTA; AUD weakness amplifies offshore cost pressures; gearing rises toward 38% constraining refinancing flexibility.
- **base**: E(R)=0.0840
  - Central case as built in quantitative chain: distribution yield ~5.96%, DPU growth 2.0% (CPI-linked leases), modest +0.5% multiple reversion post FY26 sell-off. Occupancy stable above 98% (supermarket-anchored), gearing maintained in low-to-mid 30s, RBA rates broadly stable in H2 2026.
- **bull**: E(R)=0.2000
  - RBA rate cuts accelerate from H2 2026, compressing cap rates by 25-30bps and driving NTA uplift; specialty tenant demand improves with consumer confidence recovery; DPU growth reaches 3.5% on positive rent reviews; multiple re-rates toward pre-2024 levels as income-seeking capital rotates into defensive Australian REITs; post-results discount fully closes.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0596 (Cat A) — Trailing distribution yield of approximately 5.96% reported in contemporaneous market coverage (Kalkine, 20 Jul 2026) at prices around AUD 2.23-2.40. At the as-of closing price of AUD 2.23, this implies annualised DPU of approximately AUD 0.133. Category A — observed published market data consistent with the FY26 final distribution announcement (ASX: RGN, 2026-08-27).
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% per annum. Basis: Region Group's portfolio is ~70+ neighbourhood and sub-regional shopping centres anchored by Woolworths and Coles, with CPI-linked lease structures typical for the sector. FY26 results (reported 18 Aug 2026) confirmed growth with a confident outlook per market coverage. 2.0% growth reflects CPI linkage (~3% AUD CPI moderated for lease expiry drag) without acquisitive growth assumption. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% positive multiple change assumed reflecting partial mean-reversion after the post-FY26-results sell-off (~8% decline from ~AUD 2.43 to AUD 2.23 between 14-18 Aug 2026). News coverage confirms FY26 delivered growth with confident outlook, suggesting the sell-off creates a modest reversion opportunity rather than a fundamental re-rating. Sensitivity tested in scenario analysis.
- `gearing_estimate` = low-to-mid 30s pct (Cat B) — Region Group has historically maintained gearing in the low-to-mid 30% range, well within the Australian REIT convention of <40%. FY26 Sustainability Report filed 17 Aug 2026 (ASX headline confirmed for RGN) and Appendix 4G filed same date are consistent with ongoing regulatory compliance. Exact gearing figure could not be extracted from filing bodies due to cross-contamination in the stored filing pipeline. Assessed as within regulatory limit; classified Category B (derived estimate from historical pattern with disclosed limitation).
- `internal_management_alignment` = internally managed (Cat A) — Region Group is internally managed by Region RE Limited. Internal management structure structurally aligns management incentives with unitholder returns, eliminating external manager fee conflicts. Application for quotation of securities (ASX, 26 Aug 2026) is consistent with routine DRP activity, not dilutive capital raising.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Beta of 0.441 and correlation of 0.359 over 252 trading days to 2026-08-27.
- `filing_body_contamination_disclosure` = disclosed (Cat B) — The stored filing pipeline returned cross-contaminated document bodies for RGN.AX — filing bodies contained content from unrelated ASX-listed entities (APA Group, ECP Emerging Growth, NGS, TNC, DNL). Financial substance (DPU, gearing, AFFO coverage) could not be extracted from filing bodies. Analysis relies on: (1) ASX announcement headlines attributable to RGN.AX, (2) contemporaneous news coverage, (3) publicly known characteristics of Region Group's portfolio. This limitation is disclosed and relevant assumptions are classified Category B or C accordingly.

## Key Risks
- Higher-for-longer RBA rates compressing the yield spread versus cash and constraining cap rate normalisation, sustaining the discount to NTA
- Supermarket operator consolidation or format evolution reducing anchor demand, particularly if Woolworths or Coles accelerates smaller-format strategies that reduce reliance on large-format neighbourhood centres
- Consumer spending downturn reducing specialty tenant viability, increasing vacancy rates and weakening DPU coverage
- AUD/GBP currency volatility introducing noise into the IASP.L beta estimate, limiting the reliability of the CAPM alpha signal
- Filing body pipeline contamination limited the direct extraction of FY26 DPU, gearing, and AFFO coverage figures from source documents — key financial assumptions carry elevated Category B/C uncertainty

## Invalidation Condition
Exit if Region Group reports occupancy falling below 97% for two consecutive half-year periods, or if annualised DPU is cut by more than 5% from the FY26 level, or if gearing breaches 38% without a credible deleveraging plan, or if either Woolworths or Coles formally reduces its anchor presence across more than 10 portfolio assets within a 12-month window.
