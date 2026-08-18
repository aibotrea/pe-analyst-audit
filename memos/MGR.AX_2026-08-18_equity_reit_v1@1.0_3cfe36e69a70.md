# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-08-18_equity_reit_v1@1.0_3cfe36e69a70`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified
**As of**: 2026-08-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mirvac Group is a diversified Australian stapled security offering exposure to commercial real estate (office, industrial, retail) and a residential development business, trading at an estimated 15-20% discount to NTA at AUD 1.74 following a ~19% price decline over the prior twelve months. A trailing distribution yield of approximately 4.9% provides a meaningful spread above the 3.72% T-bill rate, and the 2026-08-18 buyback announcement signals management confidence in the valuation. Beta of 0.70 versus IASP.L (currency-basis caveat: AUD/GBP noise absorbed in coefficient) indicates moderate co-movement with the broader APAC REIT universe, with annualised volatility of 21.9% reflecting the dual investment/development earnings profile. The OU Monte Carlo produces a PGain of 67.7% and a CAPM alpha of 8.9% versus a negative IASP.L benchmark return, supporting a moderate conviction rating at a 12-month horizon; the primary risk is continued residential earnings pressure and persistent office sector headwinds dampening DPU recovery.

## Quantitative Chain

- E(R): 0.0690
- Std dev: 0.1491
- P-gain: 0.6766
- CAPM alpha: 0.0893
- Beta: 0.7032
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Residential settlements decline materially, DPU cut to ~7.0cps (yield 4.0%), office vacancy in Sydney/Melbourne CBD rises to 15%+, gearing breaches 35% requiring equity issuance, cap rate expansion of 25-50bps across commercial portfolio, buyback suspended. AUD weakens and/or RBA holds rates higher for longer, compressing yield spread appeal. Bear driver could include a broader Australian property downturn or credit market tightening.
- **base**: E(R)=0.0690
  - Central case as built in chain: DPU ~8.5cps (yield ~4.9%), 1.5% organic DPU growth from commercial portfolio, mild +0.5% multiple reversion as discount to NTA narrows partially, gearing stable ~30%, occupancy broadly maintained, RBA rate cuts provide modest tailwind to valuations.
- **bull**: E(R)=0.2200
  - RBA cuts cash rate meaningfully, compressing cap rates and lifting NTA toward AUD 2.10+, residential settlements recover driving development earnings upside, DPU upgraded to ~10cps, significant discount-to-NTA closes as sentiment improves, buyback programme accelerates re-rating, industrial and office portfolios benefit from leasing spreads turning positive.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.049 (Cat B) — Estimated FY26 DPU of ~8.5 cents per stapled security divided by closing price AUD 1.74 on 2026-08-18. FY26 Distribution Announcement filed ASX 2026-06-17 (body unavailable); DPU estimate derived from Q3 FY26 operational update reaffirming guidance (ASX 2026-04-22, body unavailable) and Mirvac's known half-year distribution cadence. Classified Category B due to body capture failure; exact DPU not confirmed from filing text.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed: commercial portfolio (office, industrial, retail) provides ~1.5-2.0% organic rental growth, partially offset by residential development earnings volatility. Conservative assumption given residential settlement drag documented in market reporting (Motley Fool Australia, April 2026). Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Mild positive multiple reversion of +0.5% assumed. MGR.AX has declined ~19% from ~AUD 2.16 (September 2025) to AUD 1.74 as of 2026-08-18, trading at an estimated 15-20% discount to NTA (~AUD 2.00-2.10 estimated). Buyback announced ASX 2026-08-18 signals management view of undervaluation. Full mean-reversion not assumed given persistent office sector headwinds and residential earnings uncertainty.
- `gearing_estimate` = 0.3 (Cat B) — Mirvac Group gearing estimated at approximately 28-32% based on historically disclosed levels and Q3 FY26 operational update (ASX 2026-04-22, body unavailable). Australian REIT convention threshold is <40%. Filing bodies were unavailable for direct verification (ASX body capture failed for 7 of 8 stored filings). Estimate treated as Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp benchmark noise.

## Key Risks
- Residential development earnings drag: lower settlements or margin compression could reduce DPU coverage and trigger a distribution cut, particularly if Australian housing market conditions deteriorate
- Office sector headwinds: elevated CBD office vacancy in Sydney and Melbourne could lead to cap rate expansion and downward NTA revaluation, extending the price-to-NTA discount
- Higher-for-longer RBA cash rate compressing yield spread attractiveness and raising refinancing costs on ~30% gearing
- ASX filing body capture failure (7 of 8 filings unavailable): key FY26 DPU, AFFO coverage, WALE, and gearing data could not be directly verified from filing text — assumptions rely on public reporting and historical patterns
- Currency basis in beta: IASP.L GBP denomination means beta of 0.70 absorbs AUD/GBP FX co-movement, potentially overstating or understating true property-market sensitivity

## Invalidation Condition
Exit position if: (1) FY26 or FY27 DPU falls below 7.5 cents per stapled security (implying distribution yield below 4.3% at current price, eroding the yield-spread thesis); or (2) reported gearing rises above 37% for two consecutive reporting periods, signalling balance sheet stress; or (3) occupancy across the commercial investment portfolio falls below 90% for two consecutive quarters; or (4) management formally suspends or cancels the buyback programme announced 2026-08-18 while simultaneously flagging earnings downgrades, indicating deteriorating confidence in the valuation.
