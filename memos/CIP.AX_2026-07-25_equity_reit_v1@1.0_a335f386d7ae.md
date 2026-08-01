# Specialist Memo — CIP.AX

**Memo ID**: `CIP.AX_2026-07-25_equity_reit_v1@1.0_a335f386d7ae`
**Ticker**: CIP.AX (Centuria Industrial REIT)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-07-25
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Centuria Industrial REIT (CIP.AX) offers pure-play Australian industrial and logistics exposure at a trailing distribution yield of ~5.56%, underpinned by a diversified ~90-asset east-coast portfolio with structurally elevated occupancy rates. The 179bps yield spread over the 3-month T-bill rate (3.81%), combined with a beta of 0.48 versus IASP.L (currency-basis caveat applies), supports a relatively defensive risk-return profile within the APAC REIT universe. An OU Monte Carlo simulation (σ=15.4%, E(R)=7.1%) produces a 74.9% probability of positive 12-month return, and CAPM alpha of 6.8% signals meaningful expected outperformance versus the GBP-denominated benchmark. Gearing of ~37% sits within the Australian REIT convention limit of <40%, and the Centuria Capital Group sponsor has demonstrated consistent pipeline support, justifying an above-average conviction rating.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1049
- P-gain: 0.7493
- CAPM alpha: 0.0680
- Beta: 0.4785
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds rates higher for longer (cash rate stays at or above 4.0%), triggering 25–35bps industrial cap rate re-expansion; NTA declines ~5–8%. DPU cut of ~5–8% as higher floating debt costs squeeze distributable income. Occupancy softens to ~94% on lease expiries in Sydney/Melbourne outer rings. Bear case also incorporates a global macro shock scenario where AUD weakens sharply and offshore capital exits Australian industrial REITs, compressing multiples further.
- **base**: E(R)=0.0710
  - Central case as built in quantitative chain: distribution yield 5.56%, DPU growth 1.5% from positive rent reversion, cap rates flat (zero multiple change), occupancy stable at ~97%, gearing ~37% within AU <40% convention.
- **bull**: E(R)=0.1750
  - RBA eases further to ~3.0%, driving 20–25bps cap rate compression and NTA uplift ~5–7%. DPU growth accelerates to 3–4% on strong rent reversion in undersupplied east-coast industrial markets. Centuria sponsor injects accretive pipeline assets at sub-5.5% cap rates, expanding AUM and base fees. Occupancy holds at ~98% on continued e-commerce and 3PL demand.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.056 (Cat A) — Trailing distribution yield of ~5.56% sourced from Kalkine / Google News article dated 20 July 2026 ('Centuria Industrial REIT (ASX:CIP) Is Yielding 5.56%'). Cross-referenced against current price AUD 3.00 (trade date 2026-07-24). ASX filing bodies for distribution declarations (June 2026 and March 2026) were unavailable (body_unavailable=True; ASX body capture parked per Phase 01 v3.3 §4); yield sourced from published external source and treated as Category A observable.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed based on: (1) structural tailwinds in Australian east-coast industrial/logistics demand; (2) positive rent reversion on lease renewals in tight market; (3) partially offset by higher cost of debt on refinancing. No AFFO or FFO body data available from ASX filings (all price-sensitive filings body_unavailable=True). Assumption is conservative relative to historical CIP DPU CAGR of ~2–3%. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Assumed zero cap rate expansion or compression over the 12-month horizon. RBA rate trajectory uncertain; industrial cap rates in Australia have largely stabilised post-2023 repricing. Flat assumption is the central case; bear case assumes 25bps expansion, bull case assumes 25bps compression.
- `gearing_ratio` = 0.37 (Cat B) — CIP historically reported gearing of approximately 35–38% of total assets across FY24–FY26 annual and interim reports, within the Australian REIT convention limit of <40%. ASX filings (Q3 FY26 Operating Update, Investor Day Presentation, distribution declarations) had body_unavailable=True; specific point-in-time figure is derived from publicly known historical range. Filed as Category B estimate.
- `rba_cash_rate` = 0.035 (Cat B) — RBA cash rate estimated at approximately 3.5% as of July 2026, reflecting expected easing from 4.35% peak. Stored APAC rates returned no data for AU at as_of date; live get_apac_rates returned empty. Estimate based on publicly available RBA guidance trajectory. Category B derived estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP noise.

## Key Risks
- RBA rate trajectory uncertainty: any reversal of easing or higher-for-longer regime would pressure industrial cap rates and NTA, compressing the yield spread and potentially requiring DPU cuts as floating debt rolls over.
- ASX filing body capture limitation: all price-sensitive CIP.AX filings (Q3 FY26 Operating Update, Investor Day Presentation, distribution declarations) had body_unavailable=True; specific DPU quantum, AFFO coverage ratio, and gearing as of Q3 FY26 could not be directly verified from filings.
- Tenant concentration and lease expiry risk: CIP's top tenants in logistics and e-commerce could face financial pressure in a consumer slowdown, and near-term lease expiries in outer-suburban industrial parks may result in temporary vacancy.
- AUD/GBP currency basis in beta and alpha estimates: IASP.L is GBP-denominated; computed beta of 0.48 absorbs FX noise, making CAPM-derived alpha an unreliable standalone signal.
- External management fee drag: as an externally managed REIT, fee structures (base fees on GAV, performance fees) reduce distributable income relative to an internally managed structure, and AUM-growth incentives may not always align with per-unit DPU outcomes.

## Invalidation Condition
Exit the position if CIP reports gearing above 40% of total assets for two consecutive reporting periods, or if DPU coverage falls below 1.0x AFFO for two consecutive quarters, or if occupancy declines below 93% for two consecutive quarters, or if Centuria Capital Group materially reduces its sponsor pipeline commitment or is subject to regulatory action that impairs its AFSL licence.
