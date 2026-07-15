# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-07-14_equity_reit_v1@1.0_b0299a9ac87e`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail/Shopping Centre
**As of**: 2026-07-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Scentre Group is Australia's pre-eminent owner and operator of super-regional Westfield shopping centres, with a portfolio of ~42 centres delivering record occupancy (~99%) and sustained specialty retail sales growth into 2026. At AUD 3.85, the implied distribution yield of ~4.7% offers a meaningful spread over the prevailing 3-month T-bill rate of 3.76% with a credible 3% DPU growth pathway supported by re-leasing spreads and consumer resilience. An internally managed structure removes external fee conflicts, and gearing of ~30% sits comfortably within the AU REIT convention of sub-40%. The OU Monte Carlo simulation (10,000 paths, 12-month horizon) produces a PGain of 73.7% and a CAPM alpha of 9.4% — both supportive of an above-average conviction score of 4, warranting an 8% maximum position.

## Quantitative Chain

- E(R): 0.0770
- Std dev: 0.1207
- P-gain: 0.7367
- CAPM alpha: 0.0941
- Beta: 0.7230
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Australian consumer spending deteriorates materially as mortgage stress intensifies; RBA rate cuts are insufficient to offset discretionary retail weakness. Portfolio occupancy slips from 99% toward 97%, specialty re-leasing spreads turn negative, and DPU growth stalls at 0%. Subordinated notes refinancing executes at materially wider spreads, increasing funding costs. Cap rates expand 25bps driven by global risk-off sentiment and AUD/GBP FX volatility compressing REIT multiples.
- **base**: E(R)=0.0770
  - Central case as built in quantitative chain: DPU growth of 3.0% p.a., occupancy stable at ~99%, cap rates flat, RBA easing cycle provides modest tailwind to consumer spending and REIT valuations. Liability management (subordinated notes tender) completed without spread blow-out. AUD broadly stable versus GBP.
- **bull**: E(R)=0.1700
  - RBA eases more aggressively than expected, driving a meaningful re-rating of Australian retail REITs. Specialty retail sales growth accelerates to 5%+ enabling DPU growth of 5% p.a. Cap rates compress 15bps on improved investor risk appetite. Multiple expansion of ~5% adds to total return. Asset recycling or capital management initiatives (buyback or special distribution) from strong balance sheet.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0468 (Cat B) — Estimated trailing DPU of AUD 0.180 per security (derived from FY2025 guidance signals: record occupancy driving FFO growth per Feb 2026 investor slides, and 'sales rise and more visitors for Westfield in 2026' per Apr 2026 earnings release) divided by observed closing price of AUD 3.85 on 2026-07-14. Category B because DPU is analyst-derived from available signals rather than a formally lodged FY2025 annual distribution notice; body capture for ASX filings was unavailable for this ticker (Phase 01 v3.3 §4).
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth of 3.0% p.a. over a 3-year horizon. Supported by record occupancy across the Westfield portfolio (Feb 2026 slides), positive specialty retail sales trends, potential RBA rate-cut tailwind to consumer spending, and SCG's ability to drive specialty re-leasing spreads. Assumes no material deterioration in Australian retail spending. Sensitivity tested in scenario analysis (bear: 0%, bull: 5%).
- `multiple_change` = 0.0 (Cat C) — Neutral cap-rate / multiple change assumption over 12-month horizon. Australian REIT sector cap rates broadly stable with RBA easing cycle beginning. Near-term uncertainty from global rate volatility limits assuming expansion; no compression assumed either. Sensitivity tested in scenario analysis.
- `gearing_ratio` = 0.3 (Cat B) — Scentre Group's gearing (net debt / total assets) has consistently been reported at approximately 29-31% in public results presentations. Two price-sensitive ASX announcements in April-May 2026 relate to a tender offer and refinancing of Non-Call 2030 Subordinated Notes, indicating active liability management. Body capture for ASX filings unavailable (Phase 01 v3.3 §4); estimate based on headline announcements and public record prior to this as_of date. Well within the AU REIT convention of <40%.
- `occupancy` = 0.99 (Cat B) — Scentre Group reported record portfolio occupancy per the February 2026 investor slides ('record occupancy drives FFO growth'). SCG has historically maintained 99%+ occupancy across its super-regional Westfield centres. Estimate set at 99.0% reflecting publicly available headline disclosures. Body capture unavailable for direct filing verification.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces noise into the beta estimate that cannot be decomposed without a local-currency benchmark. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Prolonged weakness in Australian discretionary consumer spending compressing specialty tenant sales and impairing re-leasing spreads and DPU coverage.
- AUD depreciation versus USD and GBP amplifying the IASP.L beta currency-basis noise and potentially misrepresenting systematic risk; a sustained AUD sell-off also raises refinancing costs on offshore debt.
- Cap rate expansion driven by a global higher-for-longer interest rate environment reversing the modest multiple-neutral assumption embedded in E(R).
- Retail structural headwinds from continued e-commerce penetration growth in Australia, particularly in categories (electronics, fashion) that anchor Westfield tenancy.
- Subordinated notes refinancing executed in April-May 2026 — if coupon resets are materially higher than legacy rates, interest coverage metrics could deteriorate and constrain DPU growth.

## Invalidation Condition
Exit the position if Scentre Group reports two consecutive half-year periods with portfolio occupancy below 97.5%, or if DPU coverage by FFO falls below 1.0x for two consecutive reporting periods, or if reported gearing (net debt / total assets) rises above 37% without a credible deleveraging plan disclosed to the ASX, or if the RBA cash rate rises above 5% contrary to the easing-cycle base case assumption underpinning the DPU growth estimate.
