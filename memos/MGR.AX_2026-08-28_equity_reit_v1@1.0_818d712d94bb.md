# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-08-28_equity_reit_v1@1.0_818d712d94bb`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified REIT / Integrated Property
**As of**: 2026-08-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Mirvac Group offers diversified Australian property exposure across industrial, office and retail assets with an integrated residential development business, currently trading at a substantial discount (~30-35%) to pre-rate-cycle NAV. The FY26 earnings uplift (EPS A$0.172, shares +6.6% on results day) and active on-market buy-back signal improving operational momentum and management confidence at current prices. Estimated distribution yield of ~5.85% provides a meaningful spread over the 3-month T-bill (3.69%) and is supported by a diversified income base, though office portfolio dynamics and residential settlement timing introduce AFFO coverage uncertainty that warrants monitoring. The OU Monte Carlo simulation yields a sim return of 8.3% with a PGain of 70.4% at a 12-month horizon, supportive of a moderate conviction position, with upside contingent on RBA easing and cap rate normalisation.

## Quantitative Chain

- E(R): 0.0835
- Std dev: 0.1542
- P-gain: 0.7043
- CAPM alpha: 0.1100
- Beta: 0.7665
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Office vacancy rises materially (MGR Sydney/Melbourne CBD office occupancy falls below 90%), residential development settlements disappoint driving statutory loss and DPU cut to ~9.0c, cap rates expand 25-30bps amid sticky RBA rates, gearing breaches 36%+ triggering covenant pressure and equity issuance. Stagflation or persistent inflation scenario would amplify this pathway — higher-for-longer rates compress the yield spread and force NAV write-downs.
- **base**: E(R)=0.0830
  - Central case: DPU ~10.5c (+1.5% growth), occupancy stable in industrial (95%+) offsetting office softness, gearing ~32%, cap rates broadly flat with modest compression as RBA eases, active buy-back provides marginal per-security support.
- **bull**: E(R)=0.2200
  - RBA cuts rates 75-100bps by mid-2027, driving 25-30bps cap rate compression and significant NAV recovery toward AUD 2.30-2.40. Residential pipeline settlements accelerate, DPU grows to 11.5c+, buy-back completes at accretive prices, re-rating narrows discount to NAV materially.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0585 (Cat A) — Trailing DPU estimated at ~10.5 AUc/security based on FY26 results announcement (MGR.AX 2026-08-18 PERIODIC REPORTS: MGR FY26 Results Presentation; FY25 DPU was ~10.2c with modest recovery). At current price AUD 1.795, implied yield is 5.85%. Body capture failed on the distribution filing (MGR.AX 2026-06-17 DISTRIBUTION ANNOUNCEMENT, body_unavailable=True); yield cross-checked against news reporting EPS of A$0.172 for FY26.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. reflecting: (1) modest occupancy recovery in industrial/logistics offsetting continued office headwinds; (2) residential development segment earnings variability; (3) active share buy-back (announced 2026-08-18) providing modest per-security uplift. Sensitivity tested in scenario analysis; downside if residential settlements disappoint.
- `multiple_expansion_contraction` = 0.01 (Cat C) — MGR trades at approximately 30-35% discount to pre-rate-cycle NAV (~AUD 2.50-2.60). With RBA cash rate at 4.35% and expectations of easing, modest cap rate compression is plausible. Contribution assumed at +1.0% annualised. Category C: sensitive to RBA trajectory and global cap rate direction.
- `gearing_ratio` = 0.32 (Cat B) — Estimated gearing at ~32% of total assets based on MGR historical disclosures and FY26 results (MGR.AX 2026-08-18 PERIODIC REPORTS: MGR FY26 Additional Information). Body capture returned mismatched content; estimate derived from FY25 gearing (31.5%) and known refinancing activity. Within Australian REIT convention of <40%.
- `rba_cash_rate` = 0.0435 (Cat A) — RBA cash rate 4.35% as at June 2026 (FRED series IRSTCI01AUM156N). Relevant to Australian borrowing costs and cap rate benchmarking for MGR's investment portfolio.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP due to currency basis. Treated as Category B input. CAPM alpha inherits the same noise. With IASP.L's 5-year annualised return at -4.58%, the required return under CAPM is deeply negative, making alpha arithmetic largely mechanical rather than informational.

## Key Risks
- Office vacancy deterioration in Sydney and Melbourne CBDs compressing NOI and driving cap rate expansion in the investment portfolio
- Residential development settlements disappointing (presales volume, project delays or cost overruns) reducing earnings available for distribution
- Higher-for-longer RBA rates maintaining elevated financing costs, compressing yield spread and sustaining NAV discount
- AUD/GBP currency basis noise in beta estimate (Category B caveat) introducing uncertainty in CAPM alpha signal
- Macro data gaps in backtest-era FRED series may affect calibration comparability; Phase 2 calibration is directional, not formally backtested (Phase 5 vintage discipline pending)

## Invalidation Condition
Exit if MGR's portfolio gearing rises above 37% for two consecutive reporting periods, or if FY DPU is cut below 9.5 AUc (implying >10% cut from FY26 base), or if Sydney/Melbourne CBD office occupancy falls below 88% for two consecutive quarters, or if RBA signals further rate increases rather than easing — any of these would invalidate the base-case NAV recovery thesis.
