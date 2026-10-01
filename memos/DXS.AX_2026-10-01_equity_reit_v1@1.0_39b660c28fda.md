# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-10-01_equity_reit_v1@1.0_39b660c28fda`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Office/Diversified
**As of**: 2026-10-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus offers a 6.3% distribution yield at AUD 5.58, providing a meaningful income return in a higher-rate environment, with an active unit buy-back providing NTA support. However, the portfolio remains heavily weighted toward CBD office assets facing structural demand headwinds from hybrid work patterns, and the funds management and industrial pivot is still in early innings. Beta of 0.60 versus IASP.L (AUD/GBP currency basis caveat applies) reflects moderate market sensitivity, while annualised volatility of 20.8% and a PGain of 63% from the OU Monte Carlo support only a low conviction stance after a one-step downward gate override for office concentration risk. CAPM alpha of 6.2% is positive but inherits significant currency noise from the GBP-denominated benchmark.

## Quantitative Chain

- E(R): 0.0480
- Std dev: 0.1412
- P-gain: 0.6313
- CAPM alpha: 0.0617
- Beta: 0.5967
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office occupancy falls further as hybrid-work structural demand destruction accelerates; DPU cut by 3%+ as AFFO coverage drops below 1.0x; RBA holds rates above 4.25% for the full year driving cap rate expansion of 25-50bps; NTA compression of 8-12%; buy-back suspended due to balance sheet caution. Macro bear case includes a global credit tightening episode compressing property multiples across APAC.
- **base**: E(R)=0.0470
  - Central case as built in the quantitative chain: distribution yield of ~6.34%, DPU growth of -1.0%, modest negative multiple change of -0.5%. Office occupancy stable but not improving; funds management and industrial pivot provides partial earnings offset; buy-back continues at moderate pace.
- **bull**: E(R)=0.1700
  - RBA begins cutting rates, compressing cap rates and lifting NTA; office leasing demand recovers ahead of expectations with positive re-leasing spreads; DPU grows +1.5% driven by industrial ramp-up and funds management fee income; buy-back accelerates at meaningful NTA discount; Allan Gray and other value investors catalyse a re-rating of office REITs.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0634 (Cat A) — H1 FY26 estimated distribution of 17.7 cents per security declared by Dexus (sourced: Kalkine/Google News, 23 Jun 2026 reporting). Annualised full-year estimate of ~35.4 cps divided by closing price of AUD 5.58 on 2026-10-01 yields 6.34%. Semi-annual distribution confirmed as an issuer-declared figure.
- `dpu_growth_rate` = -0.01 (Cat C) — Negative DPU growth of -1.0% assumed over the 12-month horizon. Office market structural headwinds (hybrid work, sub-lease supply, cap rate expansion in CBD assets) are expected to modestly compress distributable income. Partially offset by incremental contribution from industrial assets and funds management earnings. Sensitivity tested: bear case -3.0%, bull case +1.5%.
- `multiple_change` = -0.005 (Cat C) — Modest negative multiple change of -0.5% assumed. Ongoing unit buy-back programme (confirmed active via ASX notifications, Sep-Oct 2026) provides partial NTA support, but office cap rate headwinds from higher-for-longer RBA rate environment (4.35% as of Sep 2026) are expected to produce modest NTA compression. Net assumed at -50bps of price return contribution.
- `rba_cash_rate` = 0.0435 (Cat A) — RBA policy rate 4.35% as observed from BIS data, observation date 2026-09-17, age 14 days. Used as domestic rate context for yield spread analysis.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP currency basis. Treated as Category B input. CAPM alpha inherits the same noise.
- `gearing_estimate` = within_convention (Cat B) — DXS gearing estimated within the Australian REIT convention of <40% based on publicly known capital structure. Ongoing buy-back programme (multiple ASX notifications Sep-Oct 2026) confirms balance sheet headroom. No specific gearing figure sourced from a DXS-specific filed annual report at this as_of date — treated as Category B derived estimate.

## Key Risks
- Prolonged office cap rate expansion driven by higher-for-longer RBA rates compressing NTA and distribution capacity
- Structural decline in CBD office demand from hybrid work adoption reducing occupancy and effective rents across core holdings
- Slower-than-expected progress on the industrial and funds management diversification pivot, leaving DXS earnings disproportionately exposed to office
- Distribution coverage falling below 1.0x AFFO if office income deteriorates faster than industrial/FUM fee income can offset
- Currency-basis noise in beta and CAPM alpha estimates (IASP.L is GBP-denominated) reduces precision of CAPM-derived signals

## Invalidation Condition
Exit position if DXS portfolio office occupancy falls below 90% for two consecutive reporting periods, or if the board formally suspends or reduces the distribution by more than 10% in any single half-year announcement, or if disclosed gearing breaches the 40% Australian convention threshold — any of which would signal a material deterioration in the fundamental income and balance sheet thesis underpinning the position.
