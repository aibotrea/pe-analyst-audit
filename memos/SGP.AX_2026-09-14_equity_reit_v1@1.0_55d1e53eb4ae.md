# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-09-14_equity_reit_v1@1.0_55d1e53eb4ae`
**Ticker**: SGP.AX (Stockland Group)
**Market**: Australia
**Sector**: Diversified REIT (Residential Communities / Logistics / Retail Town Centres)
**As of**: 2026-09-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Stockland (SGP.AX) is Australia's largest diversified REIT, with exposure across residential land communities (~50% of earnings), logistics/industrial (~25%), and retail town centres (~25%), providing a rare combination of cyclical recovery optionality and income stability. At AUD 4.21 the stock trades on an estimated FY2026 distribution yield of ~6.8% — a material spread of ~330bps over the RBA cash rate and ~290bps over the 3-month T-bill — supported by a top-end FFO result confirmed by the high-volume price re-rating on 2026-08-19. With gearing of ~27% (well within the Australian convention of <40%), internally managed structure, and residential volumes recovering in an RBA easing cycle, the E(R) of ~10.3% per annum is well-supported. The OU Monte Carlo simulation yields a PGain of 70% at a 12-month horizon with an annualised std_dev of 19.3%, consistent with above-average conviction.

## Quantitative Chain

- E(R): 0.1027
- Std dev: 0.1933
- P-gain: 0.7008
- CAPM alpha: 0.1453
- Beta: 0.9171
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Residential settlement volumes fall 20%+ as construction sector stress intensifies; DPU cut to AUD 0.26 (yield 6.2% on bear-case price); cap rates expand 25bps as global rate fears re-emerge; gearing drifts toward 33%; logistics vacancy rises as supply overtakes demand. Bear case also captures a stagflation or rate-shock scenario in which the RBA is forced to pause or reverse its easing cycle, combined with AUD depreciation compressing asset values.
- **base**: E(R)=0.1027
  - Central case as built: FY2026 DPU AUD 0.285 (yield 6.77%), 3.0% forward DPU growth, +50bps multiple contribution from mild cap-rate compression, gearing stable at ~27%, RBA easing continues, residential volumes recover modestly, logistics rent reversion ~3%.
- **bull**: E(R)=0.2200
  - RBA delivers two additional rate cuts accelerating residential demand; Stockland upgrades FY2027 DPU guidance to AUD 0.305+ (yield lifts on earnings, price re-rates toward AUD 5.00+); logistics cap rates compress 30bps supported by infrastructure spending; town centres benefit from tourism-driven specialty sales growth; multiple expansion adds 150bps. Gearing remains disciplined at ~25%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0677 (Cat B) — Derived from estimated FY2026 DPU of AUD 0.285 per unit divided by closing price of AUD 4.21 on 2026-09-14. DPU estimate is Category B: top-end FFO result confirmed by large-volume price spike on 2026-08-19 (46.9M shares; SimplyWall.st 2026-08-19 headline 'Stockland Shares Eye Rerating After Top End FFO Print') supports guidance uplift from FY2025 base of ~AUD 0.280. Filed actuals not yet available via stored filings pipeline.
- `dpu_growth_forward` = 0.03 (Cat C) — Three-year forward DPU growth assumption of 3.0% per annum. Driven by: (i) residential communities volume recovery as RBA easing cycle continues; (ii) logistics rental reversion ~3-4% on lease expiry; (iii) town centre rents indexed to CPI. Conservative relative to Kalkine commentary (Sep 2026) on SGP as yield favourite and asset-class tailwinds. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest cap-rate compression assumption of +50bps contribution to total return. Rationale: RBA easing cycle expected to support property capitalisation rate tightening; however, partially offset by elevated US Treasury yields and AUD/USD currency uncertainty. Conservative relative to bull-case scenario. Sensitivity tested.
- `stockland_gearing` = 0.27 (Cat B) — Estimated gearing of approximately 27% on NTA basis, consistent with Stockland's disclosed range of 25-30% across FY2023-FY2025 reporting periods. FY2026 actuals not retrievable from stored filings pipeline (ASX body capture returned cross-contaminated filings); estimate based on prior disclosed balance sheet trajectory and management guidance to maintain investment-grade discipline.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise. The benchmark annualised return of -5.0% over the trailing 5 years (driven partly by GBP/AUD basis) produces an anomalously high CAPM alpha; alpha should be treated as supporting context only, not as the primary investment signal.
- `rba_cash_rate` = 0.035 (Cat B) — RBA cash rate estimated at approximately 3.5% as of September 2026, reflecting the easing cycle that commenced in early 2025. Live APAC rates API returned empty data; stored APAC rates returned no rows. Estimate based on publicly disclosed RBA policy trajectory and news context. Used as qualitative context for spread analysis only; Rf is sourced from US DTB3 per methodology.

## Key Risks
- Residential settlement volumes may disappoint if construction cost inflation or builder insolvencies delay project completions, compressing the ~50% residential earnings contribution.
- Higher-for-longer global rates (particularly US Treasury yields) could prevent AUD cap-rate compression, neutralising the multiple-change component of E(R) and potentially driving mild multiple expansion.
- AUD/USD and AUD/GBP currency movements introduce beta noise versus the GBP-denominated benchmark IASP.L; reported alpha of 14.5% is materially inflated by the 5-year negative benchmark return and should not be relied upon as a precision signal.
- Retail town centre segment faces secular headwinds from e-commerce penetration, with any deterioration in specialty retail sales growth reducing rental reversion assumptions.
- Calibration limitation: this analysis uses live tools in non-backtest mode; the OU Monte Carlo is a directional signal only, not a formally calibrated backtest. Phase 5 vintage discipline has not been applied.

## Invalidation Condition
Exit or materially reduce position if: (i) Stockland reports FY2027 residential lot settlements more than 15% below guidance for two consecutive half-years, indicating structural demand destruction; or (ii) NTA-basis gearing breaches 35% signalling balance sheet stress; or (iii) DPU is cut by more than 10% from the FY2026 base level of approximately AUD 0.285 per unit, indicating AFFO coverage has deteriorated below 1.0x; or (iv) the RBA unexpectedly reverses to a tightening cycle, materially compressing the distribution spread.
