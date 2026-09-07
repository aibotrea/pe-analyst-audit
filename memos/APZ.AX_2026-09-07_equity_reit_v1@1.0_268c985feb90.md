# Specialist Memo — APZ.AX

**Memo ID**: `APZ.AX_2026-09-07_equity_reit_v1@1.0_268c985feb90`
**Ticker**: APZ.AX (Aspen Group)
**Market**: Australia
**Sector**: Residential/Affordable Housing
**As of**: 2026-09-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Aspen Group (APZ.AX) is an Australian affordable housing and manufactured homes REIT offering a structural thematic in undersupplied low-cost residential accommodation. The FY26 result showed rental and development earnings expanding and FY27 guidance was lifted, supporting a 3.0% DPU growth assumption. However, a 76% jump in net debt materially elevates gearing risk, likely breaching the Australian REIT convention of 40% gearing, which triggers a one-step downward conviction override. High annualised volatility of 33.8% — more than double typical defensive REIT levels — reflects the development income component and thin float, resulting in an OU Monte Carlo PGain of only 61.3% at a 12-month horizon. At conviction 2 (Low), a small position is justified by the structural affordable housing tailwind, but size must be constrained pending balance sheet clarification.

## Quantitative Chain

- E(R): 0.0670
- Std dev: 0.2300
- P-gain: 0.6128
- CAPM alpha: 0.0970
- Beta: 0.8027
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Gearing breaches 50% covenant threshold forcing equity raising at a discount; DPU cut by 15-20% as interest costs spike; occupancy in manufactured housing parks falls to 88% on weaker consumer sentiment; AUD/GBP currency moves amplify mark-to-market losses for foreign investors; RBA holds rates higher for longer, compressing REIT multiples sector-wide.
- **base**: E(R)=0.0670
  - Central case as modelled: distribution yield ~4.2%, DPU growth 3.0% driven by FY27 guidance uplift, -0.5% multiple contraction from elevated net debt. Occupancy stable. RBA on gradual easing path providing modest tailwind.
- **bull**: E(R)=0.2200
  - RBA delivers 75bps of rate cuts by mid-2027, compressing cap rates and lifting REIT valuations; affordable housing policy support (government demand for social housing) drives higher occupancy and rent growth of 5-6%; net debt concerns abate as asset sales reduce gearing below 35%; strong 12-month price momentum continues.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.042 (Cat B) — Estimated trailing distribution yield at AUD 4.81 closing price (2026-09-07). APZ historically pays approximately 19-21 cents DPU per annum; ~20 cents assumed, implying ~4.2% yield. Derived from public price and historical payout pattern. Classified Category B as precise FY26 DPU was not confirmed via a retrievable filing body (ASX filing body capture returned cross-contaminated content for this ticker).
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth of 3.0% p.a. assumed based on: (1) FY27 guidance uplift announced August 2026 (news: 'Aspen Group Lifts FY27 Guidance'); (2) expanding rental and development earnings per August 2026 reporting; (3) affordable housing structural tailwinds in Australia. Sensitivity tested in scenarios. Category C: forward-looking model assumption beyond consensus data.
- `multiple_change` = -0.005 (Cat C) — Modest -0.5% multiple contraction applied due to 76% net debt increase reported in FY26 results (news: 'Aspen Group Lifts FY27 Guidance as Net Debt Jumps 76%'), which may pressure valuation multiples as investors reassess gearing risk. Category C: judgmental assumption.
- `gearing_estimate` = elevated (Cat B) — Net debt reported to have jumped 76% in FY26 (Kalkine news, August 2026). Precise gearing ratio not confirmed due to filing body unavailability for APZ.AX in stored system (cross-contaminated results returned). Estimated gearing likely approaching or above the Australian REIT convention of 40%. Classified Category B — derived from news headline disclosure without full balance sheet.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. IASP correlation of 0.27 is low, amplifying the currency basis concern.

## Key Risks
- Net debt increased 76% in FY26; if gearing exceeds 40-45% and interest coverage deteriorates, a dilutive equity raise or DPU cut becomes probable.
- High historical volatility (33.8% annualised) reflects development income uncertainty and liquidity constraints — adverse market conditions could see APZ trade well below NTA.
- RBA policy path uncertainty: a higher-for-longer rates environment compresses REIT multiples and increases financing costs on the enlarged debt book.
- Affordable housing regulatory risk: government rent control or changes to social housing policy could cap achievable rent growth below the 3.0% assumed.
- IASP.L benchmark currency basis: beta of 0.80 absorbs AUD/GBP FX noise; low correlation (0.27) means CAPM alpha of 9.7% may be substantially overstated — treat alpha as directional only.

## Invalidation Condition
Exit or reduce to zero if: (1) reported gearing ratio exceeds 45% in the next filed half-year or annual results without a credible de-leveraging plan; (2) DPU is cut by more than 10% from FY26 levels in any forthcoming distribution announcement; (3) occupancy in the residential parks portfolio falls below 90% for two consecutive reporting periods; or (4) management issues a profit warning citing interest cost headwinds exceeding 20% of operating earnings.
