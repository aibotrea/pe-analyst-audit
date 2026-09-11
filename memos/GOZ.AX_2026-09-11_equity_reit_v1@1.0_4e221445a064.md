# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-09-11_equity_reit_v1@1.0_4e221445a064`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Office/Industrial
**As of**: 2026-09-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Growthpoint Properties Australia offers one of the highest trailing distribution yields in the Australian listed REIT market at approximately 8.67% at current prices, providing significant income support even in a flat capital-return environment. FY26 results saw record office leasing activity and FFO near the top of guidance, indicating the portfolio has stabilised following post-COVID office market disruption. However, gearing of ~41% sits above the informal 40% Australian REIT convention, creating balance-sheet risk if asset values deteriorate or refinancing costs rise. The OU Monte Carlo simulation implies a 74.7% probability of positive 12-month returns (sim return 8.64%), and CAPM alpha of ~10% reflects the elevated yield above the IASP.L benchmark's negative 5-year trailing return. Conviction is held at Moderate (3/5) reflecting the leverage gate breach and reliance on continued office leasing momentum.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.1302
- P-gain: 0.7465
- CAPM alpha: 0.0995
- Beta: 0.5764
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office vacancies rise materially, occupancy falls below 90%, DPU cut of 10-15% as FFO deteriorates. Gearing covenants approach limits forcing asset sales at depressed cap rates. RBA rate hikes re-emerge, compressing yield spreads. Multiple contracts 15-20%. AUD weakness amplifies costs on any USD-denominated debt.
- **base**: E(R)=0.0870
  - Central case as built in chain: distribution yield 8.67%, DPU growth 1.0%, multiple change -1.0%, occupancy resilient, gearing stable at ~41%. FFO near guidance peak with record office leasing activity. RBA holds rates broadly flat.
- **bull**: E(R)=0.2200
  - RBA eases rates, re-rating of Australian office/industrial REITs. Gearing falls below 38% via accretive asset recycling or equity raise. Occupancy improves to 95%+, DPU growth re-accelerates to 3-4% p.a. Cap rate compression drives NTA uplift of 10-15%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0867 (Cat A) — Trailing distribution yield of 8.67% sourced from Kalkine market data (July 2026) at observed market price of AUD 2.01 per unit on 2026-09-11. Published DPU at prevailing price.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth assumption of 1.0% p.a.: GOZ FY26 FFO near top of guidance and record office leasing (news, August 2026) supports modest organic growth, but office sector headwinds and high gearing (~41%) constrain upside. Conservative 1.0% reflects CPI-linked escalators offset by leasing friction. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% cap rate/multiple drag. GOZ gearing of ~41% is above the 40% Australian REIT convention. Elevated interest costs and office sector discount risk create mild headwind to multiple expansion. Neutral-to-slight compression assumed in base case.
- `gearing_ratio` = 0.41 (Cat B) — ~41% gearing reported in Kalkine articles (June and August 2026) referencing GOZ balance sheet as at FY26. Derived from public reporting; classified Category B as exact statutory gearing calculation not independently confirmed from filing body (ASX filing body capture returned cross-ticker data).
- `occupancy_leasing` = resilient (Cat B) — Kalkine (August 2026) reports GOZ 'returns to profit as occupancy and leasing stay resilient' and 'delivers record office leasing as FY26 FFO nears guidance peak'. No numeric occupancy figure independently confirmed from filing body due to pipeline cross-contamination. Classified Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Gearing at ~41% exceeds the 40% AU REIT convention — any material asset devaluation could trigger covenant pressure or a dilutive equity raise
- Office sector structural headwinds: flexible work patterns could slow leasing momentum and compress occupancy beyond base-case assumptions
- RBA rate re-acceleration compressing AUD yield spreads and increasing cost of floating-rate debt
- Benchmark IASP.L is GBP-denominated; beta of 0.58 absorbs AUD/GBP currency noise and may overstate or understate true property-market sensitivity
- Filing body data pipeline returned cross-ticker content for GOZ.AX, meaning distribution coverage and occupancy figures could not be independently verified from primary filings — reliance on third-party news estimates introduces Category B/C uncertainty into key inputs

## Invalidation Condition
Exit position if gearing rises above 45% for one reporting period without a credible de-leveraging plan, or if DPU is cut by more than 10% on a trailing twelve-month basis, or if occupancy falls below 88% across the portfolio for two consecutive half-year reporting periods, signalling structural deterioration in office demand beyond base-case assumptions.
