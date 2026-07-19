# Specialist Memo — APZ.AX

**Memo ID**: `APZ.AX_2026-07-16_equity_reit_v1@1.0_8dc279f98204`
**Ticker**: APZ.AX (Aspen Group)
**Market**: Australia
**Sector**: Diversified/Affordable Accommodation
**As of**: 2026-07-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Aspen Group offers exposure to Australia's affordable accommodation and holiday park sector — a structurally undersupplied niche benefiting from domestic tourism resilience and cost-of-living-driven demand for affordable living options. The estimated distribution yield of ~4.4% at A$5.00 provides a modest spread over the 3.7% T-bill rate, supported by a CAPM alpha of +8.6% relative to the deeply negative IASP.L benchmark return. However, the stock's annualised volatility of 33.8% — unusually high for a REIT — and an OU Monte Carlo PGain of 60.8% reflect the small/mid-cap nature of the portfolio and limited filing-level transparency on FY26 AFFO coverage. The one-step downward gate override applied due to unverifiable distribution coverage data constrains conviction to Low (2/5), with a 3% maximum position size until FY26 financial report provides AFFO verification.

## Quantitative Chain

- E(R): 0.0640
- Std dev: 0.2297
- P-gain: 0.6080
- CAPM alpha: 0.0855
- Beta: 0.8088
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Holiday park occupancy falls materially due to a domestic tourism slowdown (cost-of-living squeeze reducing discretionary travel) or a rate shock causing cap rate expansion of 50-75bps. DPU cut of 10-15% as earnings cover deteriorates. Gearing creeps toward 38-40%, limiting capital recycling capacity. This pathway also captures a rate-shock scenario where RBA unexpectedly tightens again, compressing yield spreads across the sector.
- **base**: E(R)=0.0630
  - Central case as built in chain: trailing yield ~4.4%, DPU growth 2.0% p.a., zero multiple change. Occupancy stable at ~90%+ across the holiday park portfolio. Gearing remains ~32-33%. RBA on hold or modest easing in 2H 2026, providing mild tailwind to REIT valuations.
- **bull**: E(R)=0.2200
  - RBA delivers 50-75bps of easing over the next 12 months, compressing cap rates and expanding NTA. Domestic tourism demand remains resilient, occupancy lifts to 93-95% driving DPU growth of 4-5%. Potential strategic acquisition of additional parks at accretive yields or a corporate activity premium from institutional consolidation (institutional holders MFG/PPT holding substantial stakes). Multiple expands from ~4.4% yield to ~3.8%, generating price appreciation of 12-15% on top of distributions.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.044 (Cat C) — Estimated trailing distribution yield of ~4.4% at A$5.00 current price, implying ~A$0.22/unit annual DPU. A FY26 distribution was declared on 2026-06-18 (ASX filing documentKey=2924-03101557-2A1678056, price_sensitive=True) but body capture failed (body_unavailable=True), preventing direct DPU verification. Estimate derived from Aspen Group's historical payout range (~21-25 cents/unit) and current market price. Category C due to unverifiable body.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. over 3 years based on: (1) structural demand for affordable accommodation/holiday parks driven by domestic tourism and cost-of-living pressures; (2) modest organic rental uplift; (3) limited inorganic pipeline visibility given no live acquisition guidance available. Conservative relative to sector organic growth. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Zero multiple expansion/contraction assumed in base case. APZ has re-rated from ~A$4.60 trough (May 2026) to ~A$5.00, appearing to have digested the FY26 distribution news. Neutral stance given high volatility (34% annualised) and limited near-term catalysts beyond steady distributions.
- `gearing_estimate` = 0.325 (Cat B) — Estimated gearing of ~32.5% based on Aspen Group's historical balance sheet disclosures (FY2024/FY2025 annual reports showing net debt/total assets in the 30-35% range). FY26 balance sheet body unavailable from filed documents; estimate held flat pending FY26 annual report. AU REIT convention threshold is <40%. Treated as Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- FY26 distribution coverage unverifiable from available filings (body_unavailable for 2026-06-18 distribution announcement); risk of AFFO payout ratio above 1.0x if earnings fell short of DPU
- High annualised volatility (33.8%) driven by small/mid-cap liquidity and concentrated holiday park exposure; stock can move ±10% on thin volume
- Interest rate sensitivity: gearing of ~32-33% and a narrow yield spread over T-bills (~70bps) leave APZ vulnerable to renewed RBA tightening or sustained higher-for-longer cash rates
- Domestic tourism cyclicality: holiday park occupancy and rental uplift are sensitive to household discretionary spending, which remains compressed by mortgage stress in Australia
- Institutional shareholder flux: multiple changes in substantial holdings by MFG and PPT in recent weeks introduce near-term price pressure risk from large block trades

## Invalidation Condition
Exit if FY26 annual report reveals DPU coverage below 1.0x AFFO for two consecutive reporting periods, or if reported gearing exceeds 40% of total assets triggering proximity to the Australian REIT convention threshold, or if portfolio occupancy across holiday and residential parks declines below 85% for two consecutive semi-annual periods, indicating structural demand deterioration rather than seasonal softness.
