# Specialist Memo — RGN.AX

**Memo ID**: `RGN.AX_2026-08-21_equity_reit_v1@1.0_ee46099f3461`
**Ticker**: RGN.AX (Region Group)
**Market**: Australia
**Sector**: Retail — Neighbourhood/Convenience
**As of**: 2026-08-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Region Group (RGN.AX) owns a high-quality portfolio of approximately 100 neighbourhood and convenience-based retail centres across Australia, anchored predominantly by non-discretionary tenants (supermarkets, pharmacies, medical) that have demonstrated resilient income through multiple economic cycles. FY26 results released 18 August 2026 confirmed FFO growth and higher occupancy, with management guiding to 3% FFO per unit growth in FY27, providing tangible near-term income visibility. At a price of AUD 2.26 the implied distribution yield of ~6.2% offers a meaningful spread of approximately 250bps over the 3-month T-bill rate (3.71%), and the OU Monte Carlo simulation implies an 82.5% probability of positive total return over 12 months. RGN's internally managed structure eliminates external manager fee drag and aligns management incentives directly with unitholders, while estimated gearing of ~30% remains well inside the Australian REIT convention threshold, providing balance sheet headroom.

## Quantitative Chain

- E(R): 0.0920
- Std dev: 0.0978
- P-gain: 0.8254
- CAPM alpha: 0.0898
- Beta: 0.4271
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Australian retail consumer spending deteriorates materially due to sustained RBA rate pressure or household credit stress; RGN occupancy falls from ~98% to ~94%; cap rates expand 25–35bps driven by higher-for-longer AUD borrowing rates; DPU growth flat or negative; potential equity raising risk if LVR breaches 35% threshold. Bear case also captures a scenario where the RBA holds or raises rates, compressing the spread between RGN's distribution yield and the risk-free rate, forcing a de-rating.
- **base**: E(R)=0.0920
  - Central case as modelled: distribution yield ~6.2%, FY27 FFO growth 3% per management guidance, cap rates flat. RBA begins cautious easing cycle, occupancy stable at ~98%, neighbourhood convenience retail demand resilient. No material acquisitions or disposals; steady distributions maintained.
- **bull**: E(R)=0.1800
  - RBA accelerates rate cuts driving cap rate compression of 15–20bps; RGN re-rates toward NAV premium; FFO growth exceeds 3% guidance on strong specialty rent spreads and CPI-linked rent escalations; potential bolt-on portfolio acquisitions accretive at >6.5% yields; market re-rates internally managed REITs more favourably, closing the discount to NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.062 (Cat B) — Trailing annualised distribution yield estimated at ~6.2%, derived from FY26 reported distributions and current market price of AUD 2.26 (trade date 2026-08-21). Exact DPU quantum not directly confirmed from a filed document body (ASX body capture not available in Phase 01 v3.3); estimate based on publicly disclosed FY26 results headline (18 Aug 2026) and historical ~14c annualised DPU range for RGN at this price. Category B: derived estimate from published results signal and observable price.
- `dpu_ffo_growth` = 0.03 (Cat A) — 3% FFO per unit growth guidance for FY27 explicitly disclosed in Region Group FY26 Results Announcement dated 18 Aug 2026 (ASX:RGN). Treated as Category A — observed publicly disclosed management guidance figure.
- `multiple_change` = 0.0 (Cat C) — Flat cap rate / multiple assumption over 12-month horizon. Australian neighbourhood retail cap rates have been broadly stable; no material compression or expansion assumed. Sensitivity: +25bps cap rate expansion would reduce E(R) by ~1.5–2.0% (bear case). Category C model assumption.
- `expected_return_build` = 0.092 (Cat B) — E(R) = distribution yield 6.2% (B) + FFO/DPU growth 3.0% (A) + multiple change 0.0% (C) = 9.2%. Composite classification B given yield component is estimated. Sensitivity to yield +/-50bps: E(R) range 8.7%–9.7%.
- `gearing_estimate` = 0.3 (Cat B) — RGN's balance sheet gearing estimated at approximately 30% loan-to-value ratio, consistent with its historical reporting and well within ASIC/ASX REIT convention of <40%. Body capture unavailable for FY26 annual report (ASX Phase 01 v3.3 limitation); estimated from publicly available analyst commentary and prior period disclosures.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces noise into the beta estimate and, by inheritance, into the CAPM alpha. Treated as Category B input. CAPM alpha inherits the same noise. IASP.L is the FTSE EPRA/NAREIT Asia Developed index; its GBP denomination means the computed beta reflects joint equity-FX dynamics, not pure property-market sensitivity.

## Key Risks
- Higher-for-longer RBA rates compressing the yield spread and triggering a cap-rate-driven de-rating of AUD retail property assets
- Household consumption slowdown reducing specialty retailer profitability and increasing vacancy risk beyond the supermarket-anchor floor
- AUD/GBP currency basis introducing noise into the IASP.L beta estimate, potentially overstating or understating systematic risk in CAPM alpha
- Body capture unavailable for FY26 annual report (ASX Phase 01 v3.3 limitation) — key financial metrics including exact DPU, gearing covenant levels and WALE are estimated from news sources rather than verified from filed documents
- Absence of a major institutional sponsor means RGN relies solely on its own balance sheet for growth capital; a soft IPO/capital markets environment could constrain accretive acquisitions

## Invalidation Condition
Exit position if RGN's portfolio occupancy falls below 95% for two consecutive reporting periods, or if reported LVR breaches 37% (approaching the 40% regulatory threshold), or if FY27 FFO per unit guidance is withdrawn or revised downward by more than 150 basis points from the 3% level disclosed on 18 August 2026, or if management confirms a dilutive equity raising at a material discount to NTA without a clearly accretive deployment target.
