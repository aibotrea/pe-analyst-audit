# Specialist Memo — SCG.AX

**Memo ID**: `SCG.AX_2026-09-16_equity_reit_v1@1.0_ff7812c7079c`
**Ticker**: SCG.AX (Scentre Group)
**Market**: Australia
**Sector**: Retail/Shopping Centre
**As of**: 2026-09-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Scentre Group offers high-quality exposure to Australia's dominant Westfield shopping centre network, with a distribution yield of ~4.9% providing a meaningful spread above the 3.97% T-bill rate. The REIT is internally managed, with no external fee drag, and demonstrates disciplined capital recycling through the Westfield Mt Gravatt JV transaction completed in August 2026. Gearing of ~32% sits comfortably within the Australian <40% convention, providing balance sheet headroom. The OU Monte Carlo simulation produces a simulated 12-month return of 6.84% with a 71.3% probability of positive return, underpinned by a strong CAPM alpha of 9.2% (Category B, currency-basis caveat applies). The primary risk is rate-driven cap rate expansion in a higher-for-longer environment, though SCG's dominant market position and long WALE provide defensive income characteristics.

## Quantitative Chain

- E(R): 0.0690
- Std dev: 0.1216
- P-gain: 0.7133
- CAPM alpha: 0.0923
- Beta: 0.7021
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Australian consumer spending deteriorates materially; specialty retail sales decline 5%+, occupancy falls toward 97% from ~99%, DPU growth stalls at 0%, cap rates expand 50bps compressing NAV. Rate shock scenario: RBA fails to cut, 10yr Australian bond yield rises to 5.5%, yield spreads widen significantly, re-rating pushes price to ~AUD 3.00. Distribution coverage drops to 1.0x AFFO threshold.
- **base**: E(R)=0.0690
  - Central case as modelled: DPU growth of 2.5% p.a. driven by CPI-linked rent reviews and leasing spread improvement. Occupancy stable at ~99%, gearing ~32%, Westfield Mt Gravatt JV recycling proceeds redeployed at accretive yields. AUD/GBP FX broadly stable. Distribution yield ~4.9% provides spread over risk-free rate.
- **bull**: E(R)=0.1800
  - RBA delivers 75bps+ of rate cuts in the next 12 months, compressing risk-free rate and driving cap rate tightening of 25-35bps. Specialty retail sales accelerate above consensus, supporting DPU growth of 4%+. Westfield Mt Gravatt JV accretive to earnings. Multiple re-rates positively; price target approaches AUD 4.00+. Distribution yield compresses to ~4.3% as price appreciates.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0491 (Cat A) — Trailing DPU of approximately AUD 0.17 per security per annum (H1 2026 distribution of ~AUD 0.085 per security as per SCG.AX 2026-08-25 DISTRIBUTION ANNOUNCEMENT 'SCG Fund Payment Notice', annualised) divided by closing price of AUD 3.46 on 2026-09-16. Observed published figure.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumed on basis of: (1) CPI-linked rent reviews across Westfield portfolio providing ~1.5% organic uplift; (2) specialty retail sales momentum supporting leasing spread improvement of ~1%; (3) Westfield Mt Gravatt JV transaction (2026-08-26 headline) indicates capital recycling into higher-returning assets. Sensitivity tested across scenarios.
- `multiple_change` = -0.005 (Cat C) — Slight negative multiple re-rating of -0.5% applied given elevated Australian interest rates and cap rate pressure on retail assets. RBA cash rate remains above 4% (stored APAC rates returned no data; assumption based on publicly available rate context). Conservative assumption; upside if rate cuts accelerate.
- `gearing_ratio` = 0.32 (Cat A) — SCG's gearing ratio approximately 32% as per most recent half-year financial reports (SCG.AX 2026-08-25 '2026 SGT1, SGT2 and SGT3 Half-Year Financial Reports'). Well within Australian REIT convention of <40%.
- `westfield_mt_gravatt_jv` = disclosed (Cat A) — Westfield Mt Gravatt Transaction Condition Satisfied announced 2026-08-26 (SCG.AX ASX filing 'Westfield Mt Gravatt - Transaction Condition Satisfied'). ART becomes JV partner per 2026-08-24 filing headline 'ART becomes JV partner at Westfield Mt Gravatt'. Asset recycling transaction reduces single-asset concentration and recycles capital at accretive terms.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP due to currency basis inherent in the IASP.L index. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer RBA cash rate compressing the yield spread versus T-bills and expanding retail cap rates, driving NAV and price lower
- Australian discretionary consumer spending slowdown reducing specialty retail tenant sales, pressuring leasing spreads and DPU growth
- Cap rate re-rating risk if global bond yields rise further, with retail sector historically carrying wider cap rates than industrial or office in valuation resets
- Benchmark return signal (IASP.L 5yr trailing: -5.0%) reflects structural headwinds for APAC REITs; AUD/GBP currency basis adds noise to beta and alpha estimates (Category B inputs)
- Concentration risk: portfolio of 42 Westfield centres is geographically concentrated in Australia and New Zealand; a domestic macro shock has outsized impact relative to diversified global peers

## Invalidation Condition
Exit position if SCG's portfolio occupancy falls materially below 97% for two consecutive reporting periods, or if DPU coverage drops below 1.0x AFFO for two consecutive half-years, or if the RBA cash rate rises above 5.5% without a clear easing path, or if Scentre Group announces a dilutive equity raising at a material discount to prevailing NAV that is not offset by commensurate asset accretion at greater than 6% initial yield.
