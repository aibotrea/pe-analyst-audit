# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-08-24_equity_reit_v1@1.0_1c639ebfba37`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail REIT
**As of**: 2026-08-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Scentre Group offers high-quality, dominant Westfield-branded retail REIT exposure in Australia and New Zealand with an ~4.8% trailing distribution yield, ~99% occupancy, and an internally managed structure that fully aligns management incentives with unitholders. The H1 FY2026 results released on 2026-08-24 alongside maintained 2026 growth targets and rising foot traffic support a 3–4% forward DPU growth assumption. The OU Monte Carlo simulation yields a 12-month sim return of 8.7% with a 76.4% probability of positive return, and CAPM alpha of 10.7% versus the IASP.L benchmark (currency-basis caveat applies). The RBA easing cycle provides a constructive backdrop for cap-rate compression, supporting mild multiple expansion that underpins the base-case E(R) of 8.8%.

## Quantitative Chain

- E(R): 0.0880
- Std dev: 0.1214
- P-gain: 0.7643
- CAPM alpha: 0.1070
- Beta: 0.6966
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Consumer recession drives retail sales declines and specialty tenant vacates; occupancy falls to 96%, DPU cut by 8–10%, cap-rate expansion of 40–50bps reverses multiple; RBA remains on hold or tightens; yield spread collapses. Stagflation or global risk-off event accelerates capital outflows from APAC REITs.
- **base**: E(R)=0.0880
  - Central case as built: distribution yield 4.84%, DPU growth 3.5%, mild net multiple expansion of 0.5% as RBA easing progresses; occupancy stable at ~99%; FFO coverage >1.0x; gearing ~32% LVR.
- **bull**: E(R)=0.2000
  - RBA cuts rates aggressively (125bps+), driving significant cap-rate compression and multiple expansion; DPU grows 5%+; retail sales outperform; JV at Westfield Mt Gravatt and further asset recycling are accretive; stock re-rates toward NAV premium.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0484 (Cat A) — Trailing annualised DPU of ~17.75c (FY2025 actuals/guidance) divided by closing price of AUD 3.67 on 2026-08-24. Published distribution figure; observed public data.
- `dpu_growth_3yr` = 0.035 (Cat C) — Forward DPU growth of 3.5% p.a. based on Scentre's publicly stated 2026 growth targets (news: 'Scentre Group maintains 2026 growth targets', May 2026) and 'sales rise and more visitors for Westfield' (April 2026). Consensus range 3–4%. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Assumed net +0.5% contribution from mild cap-rate compression as RBA easing cycle progresses. Dominant retail REITs trade at modest premiums to NAV in falling-rate environments. Central case assumes flat to marginal expansion; bear case assumes modest compression. Sensitivity tested in scenarios.
- `occupancy` = 0.99 (Cat A) — Scentre Group Westfield centres consistently report ~99% occupancy across the portfolio. Premium-grade dominant Westfield assets with high-demand retail catchments in Australia and New Zealand.
- `gearing` = 0.32 (Cat B) — Scentre Group has maintained LVR in the 30–34% range across recent reporting periods, well within the Australian REIT convention of <40%. Exact H1 FY2026 figure pending full report parse (filing lodged 2026-08-24; body not available in pipeline). Estimate based on prior period trajectory.
- `internal_management` = disclosed (Cat A) — Scentre Group is internally managed with no external responsible entity fees. Alignment with unitholders is direct; no sponsor pipeline dependency. Published corporate governance disclosures.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Consumer spending slowdown or rising unemployment in Australia reducing retail sales and weakening Scentre's rental growth and specialty sales growth metrics
- RBA rate path more hawkish than expected, compressing yield-spread attractiveness and keeping property cap rates elevated or expanding
- Structural retail headwinds from e-commerce penetration, particularly for discretionary specialty tenants beyond the dominant Westfield format
- AUD/GBP and AUD/USD FX movements affecting international investor appetite for ASX-listed REITs and the beta estimate versus IASP.L (GBP-denominated currency basis)
- H1 FY2026 results (filed 2026-08-24) not yet fully parsed in pipeline — any negative surprise on FFO, gearing above 37%, or DPU cut would invalidate the base case

## Invalidation Condition
Exit if Scentre Group reports two consecutive half-year periods of DPU cuts or FFO coverage below 1.0x, or if portfolio occupancy falls below 97% (from ~99% currently), or if LVR breaches 40% without a credible deleveraging plan, or if the RBA makes three or more rate rises in the next 12 months signalling a materially higher-for-longer rate environment that compresses the yield spread below 100bps versus the 3-month T-bill.
