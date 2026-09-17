# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-09-17_equity_reit_v1@1.0_0a31bc9ad0a8`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail/Neighbourhood & Sub-Regional Shopping Centres
**As of**: 2026-09-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group offers Australian non-discretionary retail REIT exposure anchored by grocery and convenience tenants (Woolworths, Coles, ALDI) across approximately 70 neighbourhood and sub-regional centres, delivering a ~6.34% distribution yield at the current AUD 2.24 price. The OU Monte Carlo simulation produces a PGain of 77.2% over a 12-month horizon, supported by a high CAPM alpha of 7.2% relative to a negative-returning IASP.L benchmark. Gearing at ~32% is conservatively positioned below the 40% AU REIT convention threshold, and the active on-market buy-back programme signals management's view that units are undervalued relative to intrinsic NTA. Beta of 0.44 versus IASP.L (currency-basis caveat applies) reflects the defensive, income-oriented character of the sub-regional retail model.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.0972
- P-gain: 0.7723
- CAPM alpha: 0.0724
- Beta: 0.4401
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - RBA holds cash rate elevated into 2027 causing cap rate expansion of 30–40bps; AUD commercial property valuations decline; DPU flat or cut as leasing spreads compress and Coles/Woolworths exercise lease-renewal leverage; gearing rises above 35% requiring equity issuance at a discount; buy-back suspended. This scenario incorporates a potential broader Australian economic slowdown or housing-driven consumer spend weakness feeding through to specialty retail tenants and reducing non-anchor income.
- **base**: E(R)=0.0730
  - Central case as built in the quantitative chain: distribution yield ~6.34%, DPU growth 1.5%, modest -0.5% multiple headwind, occupancy stable at ~98.6%, gearing ~32% within covenant limits, on-market buy-back continues. IASP.L benchmark delivers negative annualised return over the trailing 5y window (-4.9%), providing strong positive CAPM alpha of 7.2%.
- **bull**: E(R)=0.1800
  - RBA commences rate cutting cycle in H1 2027, compressing cap rates by 20–25bps and driving NTA re-rating back toward AUD 2.55+; price re-rates to narrow the NTA discount from ~12% to ~5%; DPU growth accelerates to 3% driven by positive leasing spreads and rental reversion; buy-back provides additional EPS accretion. Total return boosted by capital appreciation component on top of ~6.3% income yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0634 (Cat A) — Trailing DPU of approximately 14.2 cpu (based on filed 'Taxation Components - RGN Final Distribution June 2026' headline, RGN.AX 2026-08-27 DISTRIBUTION ANNOUNCEMENT, and semi-annual distribution cadence) divided by observed market price of AUD 2.24 on 2026-09-17. Yield = 14.2 / 224 = 6.34%.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed based on: (1) CPI-linked rent review clauses common in neighbourhood retail leases, (2) moderate leasing spread momentum in grocery-anchored centres, (3) conservative assumption given higher-for-longer rate environment in Australia. Sensitivity: bear case 0%, bull case 3.0%. No explicit FY2027 guidance extracted from filings (ASX body-capture unavailable for detailed report bodies).
- `multiple_change` = -0.005 (Cat C) — Modest cap-rate/multiple de-rating of -0.5% assumed. RGN trades at a discount to estimated NTA of approximately AUD 2.50-2.55 (consensus estimate). On-market buy-back programme (evidenced by multiple ISSUED CAPITAL filings in August–September 2026) partially offsets re-rating risk but discount persistence limits positive multiple revision near-term.
- `nta_discount` = 0.12 (Cat B) — Estimated ~12% discount to NTA at current price AUD 2.24 vs estimated NTA ~AUD 2.53 (consensus-derived estimate; Category B as NTA involves independent valuation methodology not directly observable). Buy-back programme is management's response to this discount.
- `gearing_estimate` = 0.32 (Cat B) — Gearing estimated at ~32% (look-through balance sheet gearing). Derived from last publicly available annual report data and consistent with Region Group's historical gearing band of 30–35%. Below AU REIT convention maximum of 40%. No filed balance sheet data directly accessible from body capture pipeline for this as_of date.
- `occupancy` = 0.986 (Cat B) — Portfolio occupancy estimated ~98.6% based on Region Group's historical occupancy profile (non-discretionary grocery-anchored tenants including Woolworths, Coles, ALDI). High structural occupancy is a feature of the sub-regional model. No filed update accessible from body capture.
- `affo_coverage` = 1.07 (Cat B) — AFFO distribution coverage estimated at ~1.07x, consistent with Simply Wall St commentary (August 2026 news: 'solid FFO growth') and Region Group's historical payout discipline. Neighbourhood retail model generates relatively stable recurring cash flows.
- `buyback_signal` = active (Cat A) — On-market share buy-back programme confirmed active via multiple consecutive ISSUED CAPITAL 'Update - Notification of buy-back - RGN' ASX announcements filed 2026-08-31 through 2026-09-07. This is a Category A observable fact from ASX announcement headlines.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input due to currency and IASP basis noise. CAPM alpha inherits the same noise. Correlation of 0.36 over 252-day window is moderate, consistent with partial FX dilution of the property signal.

## Key Risks
- Higher-for-longer RBA cash rate compressing yield spreads and expanding cap rates, leading to NTA write-downs and a wider discount to NTA at the current unit price
- Structural retail headwinds from e-commerce penetration reducing specialty tenant demand and leasing spreads, particularly in smaller sub-regional centres with weaker trade areas
- Anchor tenant renegotiation leverage: Woolworths and Coles represent significant rental income concentration and have demonstrated willingness to negotiate lower rents at lease renewal
- ASX filing body-capture pipeline did not return RGN-specific annual report or results data for this memo; gearing, AFFO coverage and DPU figures rely on published consensus and historical data rather than directly verified FY2026 annual report text — a data-quality gap that would be resolved by manual verification of the August 2026 results release
- Currency basis in beta: beta of 0.44 against GBP-denominated IASP.L absorbs AUD/GBP FX co-movement, making CAPM alpha of 7.2% partly an artefact of AUD strength/weakness relative to GBP rather than pure property alpha

## Invalidation Condition
Exit or materially reduce position if: (1) reported portfolio occupancy falls below 96% for two consecutive semi-annual reporting periods, indicating structural demand deterioration beyond the non-discretionary anchor thesis; or (2) announced gearing breaches 38% (approaching the 40% AU convention ceiling) due to valuation declines or debt-funded acquisitions at unfavourable yields; or (3) Region Group suspends the on-market buy-back AND announces a DPU reduction of more than 5% in a single period, signalling cashflow stress rather than a conservative payout decision; or (4) a major anchor tenant (Woolworths or Coles) vacates more than five centres simultaneously.
