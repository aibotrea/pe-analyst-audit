# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-08-30_equity_reit_v1@1.0_f7b31ca67e46`
**Ticker**: SGP.AX (Stockland Group)
**Market**: Australia
**Sector**: Diversified REIT (Residential Development / Retail / Logistics / Workplace)
**As of**: 2026-08-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Stockland Group delivered FY26 FFO at the top end of guidance (AUD 892m post-tax), driven by a development surge that lifted earnings approximately 10% year-on-year, validating management's capital recycling strategy across its diversified residential, logistics, retail, and workplace platform. FY27 FFO guidance of 38-39 cents per security implies a forward distribution yield of approximately 6.7% at the current AUD 4.31 price, providing a meaningful spread above the 3.69% T-bill rate. Beta of 0.96 against IASP.L (currency-basis caveat applies — AUD/GBP co-movement absorbed into the coefficient) indicates SGP tracks the broader APAC REIT universe closely, with an OU Monte Carlo producing an estimated 12-month return of 9.1% and a 67.8% probability of a positive outcome. The primary risk to the thesis is Australian residential demand softening under prolonged RBA restriction, which could pressure settlement volumes and FFO delivery, warranting a Moderate conviction score at a 5% max position.

## Quantitative Chain

- E(R): 0.0920
- Std dev: 0.1970
- P-gain: 0.6781
- CAPM alpha: 0.1346
- Beta: 0.9608
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA maintains restrictive policy through FY27, driving cap-rate expansion of 30-50bps and NAV write-downs across commercial and retail assets. Residential settlement volumes fall 15-20% due to affordability constraints and mortgage stress, causing FFO to miss the 38-39c FY27 guidance range. DPU coverage falls toward 1.0x, prompting a distribution cut or DRP uplift. Multiple compresses a further 8-10% from current levels. Gearing creeps toward 32-35% as asset values decline.
- **base**: E(R)=0.0920
  - Central case as built in quantitative chain: FY27 FFO lands at mid-guidance 38.5c, 75% payout ratio delivers ~28.9c DPS, forward yield 6.7% at AUD 4.31. DPU growth 3.0% p.a. from pipeline settlements and logistics rent reversions. Gearing stable at ~27%. Cap rates flat with mild 0.5% multiple headwind from rate environment. OU Monte Carlo produces sim return 9.1%, std_dev 19.7%, pgain 67.8%.
- **bull**: E(R)=0.2200
  - RBA cuts rates 50-75bps through FY27, triggering cap-rate compression and NAV re-rating. Residential settlement volumes accelerate as housing affordability improves, pushing FFO toward the top of or above 39c guidance. DPU lifted 5-6%, distribution yield re-rates to 5.5-6.0% implying price appreciation toward AUD 4.80-5.00. Development pipeline conversion accelerates. Multiple expands 8-12% as the market prices in the interest rate tailwind and Stockland's diversified platform at a tighter discount to NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.067 (Cat B) — FY27 FFO guidance mid-point of 38.5c per security (Kalkine/Investing.com coverage of SGP FY26 results announcement, ASX filing 2026-08-18, headline 'Stockland FY27 FFO Guidance Set at 38-39c'). Assumed ~75% payout ratio yields ~28.9c DPS; divided by last trade price of AUD 4.31 (2026-08-28) = 6.7% forward yield. Payout ratio is a derived estimate (Category B) as FY27 DPS not yet formally declared.
- `dpu_growth_3yr` = 0.03 (Cat C) — Three-year forward DPU growth assumption of 3.0% p.a. reflecting active residential development pipeline delivering incremental FFO, disciplined capital recycling in logistics and retail, and steady-state organic rent growth. FY26 development-driven earnings lifted FFO ~10% y/y (Motley Fool Australia, 2026-08-19). Growth rate is a forward-looking analyst assumption; sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — A modest -0.5% multiple change (mild cap-rate compression headwind) is assumed over the 12-month horizon, reflecting the still-elevated RBA rate environment relative to pre-2022 norms and ongoing NAV discount uncertainty. This is a conservative assumption; upside scenario assumes flat to positive re-rating.
- `fy26_ffo` = 892000000.0 (Cat A) — Post-tax FFO of AUD 892m for FY26, reported at top end of guidance per ASX price-sensitive announcement 'Stockland delivers FY26 result at top end of guidance' (filing_date 2026-08-18, source asx). Supporting news coverage: Kalkine 2026-08-18, Investing.com 2026-08-19.
- `gearing_assumption` = 0.27 (Cat B) — Stockland's regulatory gearing is estimated at ~27% based on historical AREIT disclosures and the 'Stockland Property Portfolio as at 30 June 2026' filing (ASX, 2026-08-18). Specific gearing figure not confirmed from filing body (ASX body capture provided cross-contaminated documents). Assumed to be well within the Australian 40% convention maximum.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP is a persistent source of noise in this coefficient. Treated as Category B input. CAPM alpha inherits the same noise. IASP.L 5-year trailing annualised return of -4.58% reflects both APAC REIT fundamentals and the AUD/GBP cross during that period.

## Key Risks
- RBA higher-for-longer rate policy compressing residential settlement volumes and widening cap rates on commercial assets, potentially causing FY27 FFO to undershoot the 38-39c guidance range
- High historical volatility of 28.9% (annualised) and a 19.7% OU Monte Carlo std_dev imply significant return dispersion; a 1-sigma downside implies ~-11% 12-month return
- Beta of 0.96 against GBP-denominated IASP.L absorbs AUD/GBP FX basis noise; true property-market beta is uncertain and CAPM alpha of 13.5% inherits this noise
- Development pipeline execution risk: cost overruns, planning delays, or subdued housing demand could defer FFO crystallisation from residential settlements into FY28+
- ASX filing body capture for SGP returned cross-contaminated documents from other issuers; gearing, WALE, and distribution coverage figures could not be confirmed from primary filing text and rely on public news synthesis

## Invalidation Condition
Exit the position if FY27 FFO guidance is formally revised below 36 cents per security (implying more than a 5% miss to the low end of the 38-39c range), or if reported gearing exceeds 35% in the FY27 interim results, or if residential settlement volumes in two consecutive half-year periods decline more than 20% year-on-year, signalling structural demand deterioration in the core development earnings engine.
