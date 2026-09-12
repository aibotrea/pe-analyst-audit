# Specialist Memo — HDN.AX

**Memo ID**: `HDN.AX_2026-09-12_equity_reit_v1@1.0_7ac2020a301d`
**Ticker**: HDN.AX (HomeCo Daily Needs REIT)
**Market**: Australia
**Sector**: Retail - Daily Needs Anchored
**As of**: 2026-09-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
HomeCo Daily Needs REIT (HDN.AX) offers exposure to Australia's defensive daily-needs retail subsector — supermarket, pharmacy, and service-station anchored centres — at a yield of ~7.3% following a ~15% sell-off from estimated NTA. The OU Monte Carlo simulation (sigma 18.0%, horizon 12 months) yields a simulated return of 7.7% with PGain of 73.7%, supporting a moderate conviction entry. CAPM alpha of 9.2% versus the IASP.L benchmark (noting AUD/GBP currency basis) reflects the excess return embedded in the current price. The primary risk to the thesis is FY27 FFO compression from elevated financing costs — management explicitly flagged this in the August 2026 results — which constrains distribution growth and limits the upside to the base case. Conviction is held at 3 (Moderate) after a one-step gate reduction for tightening distribution coverage.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1223
- P-gain: 0.7366
- CAPM alpha: 0.0923
- Beta: 0.5968
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds cash rate above 4.5% through FY27, driving cap-rate expansion of 50bps across the portfolio and pushing gearing toward 40%+. DPU is cut to ~7.0cpu (from ~8.0cpu) as AFFO coverage falls below 1.0x. Multiple contracts a further 5–7% from current levels. Unit price declines toward AUD 0.95–1.00. This bear case also captures a tail-risk scenario where a major anchor tenant vacates or renegotiates, accelerating occupancy-driven NOI pressure.
- **base**: E(R)=0.0780
  - Central case as built in quantitative chain: DPU maintained at ~8.0cpu, yield of 7.3% at AUD 1.09, DPU growth of 1.5% p.a., cap-rate flat to mild -1.0% multiple drag. Gearing stable at ~38%. Occupancy sustained above 98%. RBA begins easing in H1 2027, providing modest tailwind to unit price in the back half of the 12-month horizon.
- **bull**: E(R)=0.2000
  - RBA pivots to easing by early 2027, compressing capitalisation rates 25bps and supporting a NTA re-rating toward AUD 1.25–1.30. DPU grows 3%+ driven by rent reviews and incremental acquisitions from the HomeCo pipeline at accretive yields. Portfolio gearing declines to ~34% as property values increase. Unit price re-rates toward AUD 1.25, delivering total return inclusive of distribution income of approximately 20%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.073 (Cat A) — Trailing DPU of approximately 8.0 cpu divided by current market price of AUD 1.09 (trade date 2026-09-11, sourced from live price feed). Distribution maintained per FY26 Results ASX Announcement (HDN.AX, 2026-08-12, PERIODIC REPORTS). Yield computed as 8.0/109.0 = 7.34%, rounded to 7.3%.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. reflects constrained organic growth given FY27 FFO pressure from higher financing costs (flagged in news, HomeCo FY26 slides 2026-08-12). HDN's daily-needs anchored portfolio supports moderate rental growth (CPI-linked reviews), partly offset by refinancing headwinds. Sensitivity tested in scenario analysis: bear case assumes flat/negative growth; bull case assumes 3% growth.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% multiple drag from mild cap-rate expansion in a higher-for-longer RBA environment. HDN trades at a ~15% discount to estimated NTA (~AUD 1.28), and further multiple compression remains possible if RBA holds rates elevated through FY27. Sensitivity: bull case assumes flat multiples; bear case assumes -3.0% multiple headwind.
- `gearing_ratio` = 0.38 (Cat B) — Estimated gearing of ~38% based on HDN's historical disclosure range of 36–38% and FY26 Results ASX Announcement (HDN.AX, 2026-08-12). Derived estimate — FY26 Appendix 4E body unavailable due to ASX filing pipeline mismatch. Within AU REIT convention of <40%; classified Category B pending confirmed FY26 balance sheet.
- `occupancy` = 0.98 (Cat B) — Portfolio occupancy estimated at ~98%+ based on HDN's reported track record in daily-needs anchored retail (supermarkets, pharmacies, service stations). FY26 investor presentation body unavailable due to ASX filing pipeline mismatch; estimate from news context (Kalkine, 2026-08-13: 'strong operations').
- `distribution_coverage` = ~1.0x (Cat B) — AFFO coverage estimated at approximately 1.0x AFFO for FY26/FY27 given FY27 FFO pressure from higher financing costs (HomeCo FY26 slides, 2026-08-12, Investing.com: 'strong operations offset by rate headwinds'). Maintained distribution signals management confidence but leaves limited margin. FY26 Appendix 4E body unavailable; this is a derived estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. Beta of 0.597 (corr 0.383) reflects modest correlation to the global APAC REIT index, consistent with HDN's domestic-defensive positioning.

## Key Risks
- Higher-for-longer RBA cash rate compressing FFO and distribution coverage below 1.0x AFFO, potentially triggering a distribution cut and further re-rating of the unit price.
- Cap-rate expansion in Australian retail property if long bond yields rise materially, increasing the discount to NTA and pressuring valuations across the portfolio.
- Related-party complexity: HomeCo platform manages both HDN and HealthCo REIT (HCW.AX), creating potential conflicts of interest in asset allocation, pipeline prioritisation, and fee extraction.
- Refinancing risk: with elevated near-term debt maturities and rising all-in borrowing costs, any deterioration in credit markets could force dilutive equity issuance or asset sales below book value.
- Tenant concentration: while daily-needs anchoring is defensive, any major anchor (e.g., Woolworths, Coles) renegotiating lease terms or vacating would materially affect portfolio income and valuations.

## Invalidation Condition
Exit position if reported portfolio gearing breaches 40% for two consecutive half-year reporting periods, or if FY27 or FY28 DPU guidance is formally reduced below 7.5 cpu (signalling coverage below 1.0x AFFO), or if HDN announces a dilutive equity raise at a price more than 10% below prevailing NTA without a clearly accretive acquisition rationale from an independent sponsor pipeline.
