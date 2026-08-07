# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-07_equity_reit_v1@1.0_9bc0d85638ad`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Neighbourhood & Sub-Regional Shopping Centres
**As of**: 2026-08-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group (RGN.AX) is Australia's largest neighbourhood and sub-regional REIT, anchored by supermarket tenants (Woolworths, Coles) that underpin non-discretionary retail income with occupancy above 98% and CPI-linked rent escalation. At AUD 2.41, the implied distribution yield of approximately 5.9% provides a meaningful spread over the 3-month T-bill rate of 3.74%, and the OU Monte Carlo (E(R)=7.4%, σ=9.7%) produces a PGain of 77.7%. Beta of 0.44 against IASP.L (AUD/GBP currency-basis caveat applies) reflects the defensive income profile of the portfolio relative to the broader APAC REIT universe. A CAPM alpha of +7.0% supports above-average conviction despite two recent substantial-holder exits and partially-priced RBA easing.

## Quantitative Chain

- E(R): 0.0740
- Std dev: 0.0967
- P-gain: 0.7766
- CAPM alpha: 0.0701
- Beta: 0.4409
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA pauses easing cycle; Australian 10-year yield rises 50bps, compressing retail cap rates and widening spreads. Occupancy slips to 96% on softening discretionary spending spillover into neighbourhood centres. DPU coverage falls to 0.97x AFFO on rising finance costs, forcing a distribution cut of ~5%. Multiple contracts; NTA declines on June 2027 valuations. Two substantial-holder exits (MUFG, First Sentier already ceased) add further selling pressure.
- **base**: E(R)=0.0740
  - Central case as built in chain: DPU growth 2.0% p.a. from CPI-linked rent reviews, occupancy stable at ~98.5%, gearing 34%, cap rates flat to modest compression as RBA completes easing. Distribution yield ~5.93% on AUD 2.41; slight multiple drag -0.5% from partial re-rating already achieved.
- **bull**: E(R)=0.1800
  - RBA cuts deliver 75bps in FY27; retail cap rates compress 25-30bps, lifting NTA. Supermarket anchor lease renewals at higher rents drive DPU growth of 4%+. Occupancy reaches 99%+. Re-rating toward pre-2022 highs; multiple expansion adds ~4% to total return. Potential accretive acquisition from neighbourhood centre pipeline reinforces earnings growth.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0593 (Cat B) — Trailing DPU estimated at ~14.3 cpu annualised on current price of AUD 2.41, implying a forward distribution yield of ~5.93%. Derived from ASX filing headline 'RGN Final FY26 Distribution' (RGN.AX, 2026-06-16, PERIODIC REPORTS) and 'Dividend/Distribution - RGN' (RGN.AX, 2026-06-16, DISTRIBUTION ANNOUNCEMENT); filing bodies unavailable (body_unavailable=True for both), so DPU quantum estimated from market-consensus yield range of 5.8-6.1% and recent price history. Classified Category B as filed DPU not directly readable.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflecting CPI-linked rent reviews on supermarket-anchored leases and modest portfolio NOI growth, net of potential headwinds from higher-for-longer Australian rates. Assumes no material accretive acquisition. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Slight cap rate normalisation drag of -0.5% assumed. RGN has re-rated from ~AUD 1.89 (Nov 2024) to AUD 2.41 (+27%) and faces modest multiple compression risk as RBA easing cycle is partially priced. Category C model assumption.
- `gearing` = 0.34 (Cat B) — Region Group (formerly SCA Property Group) historically reported gearing of 33-36% (book-value LVR). June 2026 Property Valuations Update filed 2026-06-16 (body unavailable); estimated from historical disclosure pattern. Below the 40% Australian REIT convention limit. Flagged as Category B — derived estimate with disclosed methodology from prior filings.
- `occupancy` = 0.985 (Cat B) — RGN non-discretionary neighbourhood portfolio typically reports occupancy 98-99%. Estimated from public investor presentations and prior period filings. Category B derived estimate; FY26 full detail unavailable (filing bodies not captured).
- `wale` = 4.5 (Cat B) — WALE estimated at approximately 4-5 years (weighted average lease expiry), consistent with supermarket-anchored retail REIT peer range. Category B estimate from historical filing context.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis introduces noise into the 0.44 estimate and the CAPM alpha. Treated as Category B input. CAPM alpha inherits the same noise from the IASP.L currency basis.
- `filing_body_gap` = disclosed (Cat B) — Three price-sensitive RGN.AX filings from 2026-06-16 (RGN Final FY26 Distribution, Dividend/Distribution - RGN, June 2026 Property Valuations Update) have body_unavailable=True due to ASX body capture limitations. DPU, gearing, and NTA inputs are estimated from observable market data and prior-period public disclosures. This gap is disclosed and reflected in Category B/C classifications.

## Key Risks
- Higher-for-longer Australian rates stalling cap rate compression and eroding the yield spread versus T-bills
- MUFG and First Sentier Investors ceasing as substantial holders signals potential sustained institutional selling pressure
- FY26 distribution filing bodies unavailable — actual DPU, gearing, and NTA not directly verified from filed documents; estimates may deviate
- Consumer spending slowdown reducing specialty tenant sales and deferring rent reviews, compressing NOI growth below 2% p.a.
- AUD/GBP currency volatility distorting beta and CAPM alpha estimates (IASP.L currency-basis risk)

## Invalidation Condition
Exit if reported gearing exceeds 40% on two consecutive half-year balance dates, or if RGN announces a distribution cut of more than 5% without an offsetting NTA accretion event, or if occupancy falls below 95% for two consecutive quarterly updates, or if the RBA signals a reversal to tightening that pushes Australian 10-year yields materially above 5.5%, causing retail cap rates to expand more than 50 basis points from current levels.
