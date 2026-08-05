# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-08-04_equity_reit_v1@1.0_d127b15104f6`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-08-04
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is Australia's pre-eminent industrial and logistics REIT-adjacent platform, differentiated by a large global development workbook and growing funds management earnings that are structurally underpinned by AI data-centre and e-commerce logistics demand. At AUD 30.20, the trailing distribution yield of ~1.1% is low but the total return thesis rests on strong EPS growth (~8% forward), with GMG retaining earnings for high-returning development capital allocation. Beta of 0.74 versus IASP.L (AUD/GBP currency-basis caveat applies) reflects moderate correlation to the broader APAC REIT index. The OU Monte Carlo yields a simulated return of ~8.0% with an annualised std dev of 18.7%, producing a PGain of 66.6% — sufficient for moderate conviction. Key risk is valuation: GMG trades at a material premium to NTA and is vulnerable to multiple compression if the development pipeline disappoints or interest rates remain elevated longer than expected.

## Quantitative Chain

- E(R): 0.0810
- Std dev: 0.1870
- P-gain: 0.6658
- CAPM alpha: 0.0986
- Beta: 0.7422
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - Global data-centre and logistics demand slows materially as hyperscaler capex cycles pause and e-commerce growth stalls; development workbook write-downs reduce NTA by 10–15%; cap rate expansion of 50–75bps compresses the premium-to-NTA multiple sharply; AUD rate cut expectations reverse, lifting discount rates; EPS growth flat to negative. Bear case subsumes rate-shock and geopolitical disruption scenarios.
- **base**: E(R)=0.0800
  - Central case as built in chain: distribution yield 1.1%, DPS/EPS growth 8% driven by development completions and FUM expansion, modest 1% multiple compression. Cap rates broadly stable; occupancy maintained above 97%; RBA easing cycle supports stable property values.
- **bull**: E(R)=0.2800
  - Hyperscaler and AI-driven data-centre demand accelerates beyond consensus; GMG's development workbook expands to AUD 16bn+; EPS growth of 12–15%; re-rating of the premium multiple as growth optionality is recognised; AUD/USD stability removes FX headwind on offshore earnings contribution.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.011 (Cat A) — Trailing distribution per security approximately AUD 0.33 on a closing price of AUD 30.20 (2026-08-04). GMG retains the large majority of earnings for development reinvestment; stated yield reflects only the cash dividend component. Price sourced from live feed.
- `eps_dps_growth_3yr` = 0.08 (Cat C) — Forward EPS and DPS growth assumption of 8% p.a.: reflects GMG's structural tailwinds in data-centre and logistics demand, a AUD 13–14bn development workbook, and continued FUM expansion. Sensitivity tested in scenario analysis. GMG's 5-year CAGR in operating EPS has been ~15%; a forward 8% reflects moderation as the development cycle matures and the cost of capital normalises. No filed guidance available from body-captured filings (ASX body capture parked per Phase 01 v3.3 §4); assumption based on public market knowledge.
- `multiple_change` = -0.01 (Cat C) — Modest 1% negative multiple contribution assumed given GMG trades at a significant premium to NTA (~2.5–3x book). As interest rates normalise, premium compression is plausible but contained given GMG's structural growth premium and unique development pipeline. Sensitivity tested in scenarios.
- `gearing_balance_sheet` = 0.11 (Cat B) — GMG's own balance sheet gearing (look-through net debt/total assets) estimated at approximately 10–11%, well within the Australian A-REIT conventional threshold of 40%. GMG's managed funds carry separate leverage not consolidated on GMG's balance sheet. Derived from publicly available FY25 annual report data; filing body unavailable (ASX body capture parked per Phase 01 v3.3 §4).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP noise.

## Key Risks
- Premium-to-NTA compression: GMG trades at ~2.5–3x NTA; any derating of the development/FUM business premium would disproportionately affect total return relative to yield-based A-REITs.
- Development execution risk: GMG's returns are increasingly dependent on development completions and leasing-up of speculative logistics and data-centre projects; delays or cost overruns could impair operating EPS.
- Higher-for-longer AUD rates: elevated RBA cash rate sustains cap rate pressure and increases borrowing costs in managed funds, potentially reducing development returns and compressing asset valuations.
- Hyperscaler capex cycle risk: a pause or reduction in AI and cloud infrastructure spending by major technology tenants could rapidly reduce demand for GMG's data-centre pipeline.
- Currency risk: significant offshore earnings (Europe, North America, Japan) create AUD translation exposure; AUD appreciation would reduce reported EPS and DPS.

## Invalidation Condition
Exit position if GMG reports two consecutive half-year periods of operating EPS growth below 3% (materially below the 8% base case), or if the development workbook falls below AUD 11bn indicating pipeline exhaustion, or if balance sheet look-through gearing rises above 25% signalling a structural shift in capital management discipline, or if the company announces a material impairment to development assets exceeding AUD 1bn in aggregate.
