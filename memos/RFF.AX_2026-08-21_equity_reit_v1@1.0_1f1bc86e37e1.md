# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-08-21_equity_reit_v1@1.0_1f1bc86e37e1`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agricultural/Farmland
**As of**: 2026-08-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Rural Funds Group offers differentiated exposure to Australian agricultural real estate — a sector with strong inflation-linkage via CPI-based rent escalators and structural tailwinds from global food-security demand. The trailing distribution yield of ~5.30% at AUD 2.09 provides a meaningful spread over the 3.71% risk-free rate, with FY26 results (released 21 Aug 2026) confirming earnings growth momentum and $255.6M of strategic asset divestments demonstrating active portfolio management. Beta of 0.45 against IASP.L (with AUD/GBP currency-basis caveat) indicates moderate co-movement with the APAC REIT universe, and the OU Monte Carlo simulation returns a PGain of 71.2% at a 12-month horizon, supporting an above-average conviction score. The primary risk is weather and climate-driven disruption to agricultural cash flows, though lease structures and tenant diversification across cropping types provide partial mitigation.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1297
- P-gain: 0.7116
- CAPM alpha: 0.0725
- Beta: 0.4484
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Australian drought conditions or adverse weather events reduce agricultural output, triggering tenant rent relief requests and DPU cut; distribution yield compresses to 3.5% effective on lower DPU; cap rate expansion of 50bps on farmland valuations following RBA rate increases; divestment proceeds deployed sub-optimally into lower-yielding assets. Bear case also captures a rate-shock scenario where RBA raises cash rate materially above current levels, compressing REIT multiples sector-wide.
- **base**: E(R)=0.0730
  - Central case as built in quantitative chain: distribution yield 5.30%, DPU growth 2.0% via CPI-linked rent escalators, zero multiple change, divestment proceeds redeployed at comparable yields. FY26 earnings growth sustained into FY27 at low-single-digit rate.
- **bull**: E(R)=0.1800
  - Farmland values re-rate upward on increased institutional demand for real assets and food-security themes; DPU growth accelerates to 4%+ as divestment proceeds reinvested accretively; multiple expansion of 5-8% as yield compression tightens with RBA easing cycle; strong FY26 results trigger analyst upgrades and sector re-rating for Australian agricultural REITs.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.053 (Cat A) — Trailing distribution yield of ~5.30% sourced from Kalkine (05 Aug 2026) at current market price of AUD 2.09 (trade date 2026-08-21). Consistent with historically published DPU figures and current price observation.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% per annum assumes CPI-linked rent reviews on agricultural leases (historically CPI or fixed 2-3% escalators per RFF's lease structure) partially offset by portfolio changes post-$255.6M divestments (Jul 2026). Conservative relative to prior 2-3% range given portfolio recycling uncertainty. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change assumed at base case. Price of AUD 2.09 represents material recovery from Jan 2025 lows (~AUD 1.48) and is approaching 2-year highs; limited further re-rating uplift expected. FY26 results released today — market reaction embedded in current price.
- `expected_return_buildup` = 0.073 (Cat B) — E(R) = distribution yield (5.30%, Category A) + DPU growth (2.0%, Category C) + multiple change (0.0%, Category C) = 7.3%. Category B overall as derived from one Category A and two Category C inputs.
- `risk_free_rate_source` = 0.0371 (Cat A) — US 3-Month T-Bill rate (DTB3) from FRED as of 2026-08-20: 3.71%. Used as risk-free proxy given IASP.L benchmark is USD/GBP cross-listed; AUS domestic equivalent (RBA cash rate) not available from stored APAC rates at this as_of date.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Beta = 0.448, correlation = 0.273 over 257 observations.
- `divestment_program` = 255.6M_AUD (Cat A) — $255.6M asset sales secured per Finance News Network (10 Jul 2026), confirmed as price-sensitive ASX announcement in RFF FY26 results context (2026-08-21). Proceeds expected to support balance sheet and/or reinvestment; exact deployment not confirmed at as_of date.
- `filing_body_availability` = unavailable (Cat A) — ASX filing body capture for RFF.AX returned 0 records from stored filings (Phase 01 v3.3 §4 — body capture for ASX is parked). DPU coverage, gearing ratio, WALE, and occupancy figures sourced from news headlines only. Material uncertainty exists around AFFO coverage and leverage metrics.

## Key Risks
- Climate and weather risk: prolonged drought, flooding, or adverse seasonal conditions reducing agricultural productivity and triggering tenant rent-relief arrangements, directly impairing DPU coverage
- Interest rate sensitivity: RBA tightening or higher-for-longer rates compressing the yield spread and applying downward pressure on farmland asset valuations and REIT multiples
- Divestment reinvestment risk: $255.6M proceeds from FY26 asset sales may be redeployed into lower-quality or lower-yielding assets, diluting DPU accretion versus the divested portfolio
- Filing body unavailability: ASX body capture is parked under Phase 01 v3.3 §4, preventing direct verification of gearing ratio, WALE, AFFO coverage, and top-tenant concentration — key leverage and coverage metrics rely on headline news only
- Commodity price pass-through: tenant profitability depends on agricultural commodity prices (beef, almonds, sugar); a sustained commodity down-cycle could impair lease renewal terms and rental growth

## Invalidation Condition
Exit or downgrade conviction if DPU is cut by more than 10% in any single distribution announcement, or if gearing ratio rises above 40% LVR (Australian REIT convention limit), or if more than two major agricultural tenants representing more than 20% of rental income enter formal rent-relief or default arrangements, or if the RBA cash rate rises above 5.5% compressing the yield spread below 100bps on a sustained basis for two consecutive quarters.
