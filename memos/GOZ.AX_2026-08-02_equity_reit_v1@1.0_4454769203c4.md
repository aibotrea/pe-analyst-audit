# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-08-02_equity_reit_v1@1.0_4454769203c4`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Diversified Office/Industrial
**As of**: 2026-08-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Growthpoint Properties Australia offers an elevated trailing distribution yield of approximately 8.48% at the current AUD 2.23 price, providing a meaningful income return well above the 3.69% risk-free rate. The OU Monte Carlo simulation (12-month horizon) produces a simulated return of 8.9% with a PGain of 74.8%, supporting a positive return expectation. However, gearing at approximately 41% exceeds the Australian A-REIT convention of sub-40%, and structural office demand headwinds introduce meaningful downside risk to DPU sustainability, warranting a one-step conviction downgrade to Moderate. The CAPM alpha of 9.25% versus the IASP.L benchmark (currency-basis caveat applies) is strongly positive, though this partly reflects the negative trailing benchmark return over the 5-year window rather than pure stock-level outperformance.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1337
- P-gain: 0.7482
- CAPM alpha: 0.0925
- Beta: 0.5638
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office vacancy accelerates materially, DPU cut of 10-15% as AFFO coverage drops below 1.0x, cap rate expansion of 50bps in office assets, gearing rises above 45% forcing dilutive equity raise. Bear case also encompasses a sustained higher-for-longer RBA rate environment compressing yield spreads and a sharper AUD/GBP depreciation amplifying benchmark currency basis noise.
- **base**: E(R)=0.0900
  - Central case as built in quantitative chain: distribution yield 8.48%, DPU growth 1.5% p.a. reflecting industrial reversion offsetting office drag, -1.0% multiple compression from gearing overhang, gearing stable at 41%, RBA on easing path providing modest support.
- **bull**: E(R)=0.2200
  - RBA eases 75-100bps, cap rates compress, office demand recovers as return-to-work trends solidify, gearing reduced below 40% via accretive asset disposals, DPU growth re-rates to 3-4% p.a., price-to-NAV discount closes driving 5-8% multiple expansion.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0848 (Cat A) — Implied trailing distribution yield of ~8.48% based on ASX-observed close price of AUD 2.23 (2026-07-31) and FY26 Final Distribution announcement filed 2026-06-21. Corroborated by Kalkine news report (20 Jul 2026) citing 8.48% yield. Category A as both price and distribution headline are publicly observed.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed reflecting modest organic rental reversion on industrial/logistics assets partially offset by structural headwinds in office. Growthpoint Jun-2026 trading update notes continuing leasing momentum (body unavailable, headline only). Conservative relative to Australian CPI given office vacancy drag. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% multiple contraction over 12 months reflecting gearing at 41% (above AU REIT convention of <40%), ongoing structural demand uncertainty for office assets, and elevated base rates environment. Category C model assumption; scenario analysis tests +/- outcomes.
- `gearing_ratio` = 0.41 (Cat A) — Gearing of approximately 41% referenced in Kalkine media report (Jun 2026) citing GOZ balance sheet data derived from publicly filed accounts. Exceeds Australian A-REIT convention threshold of <40%, triggering a one-step conviction override.
- `rba_cash_rate` = 0.04 (Cat C) — RBA cash rate assumed at ~4.0% as live APAC rate data unavailable at query time. Consistent with publicly reported RBA settings in mid-2026. Used as contextual input only; T-bill rate (3.69%) is the primary risk-free input.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. This currency and IASP basis noise means the beta of 0.564 should be treated as a directional estimate only. CAPM alpha inherits the same noise. Treated as Category B input throughout.

## Key Risks
- Gearing at ~41% exceeds AU A-REIT convention (<40%), limiting balance sheet flexibility and potentially triggering covenant scrutiny if valuations decline further.
- Structural office demand headwinds — persistent work-from-home trends and sublease supply — could suppress occupancy and compel DPU reductions, with FY26 distribution coverage data unavailable to assess AFFO buffer.
- Higher-for-longer RBA cash rate compresses the yield spread, reduces refinancing capacity, and may trigger further cap rate expansion on office assets.
- AUD/GBP currency basis introduces noise into the IASP.L-derived beta (0.564) and CAPM alpha, limiting precision of CAPM-based risk attribution.
- Phase 2 calibration is directional only; vintage discipline not formalised until Phase 5, and absence of macro series (FEDFUNDS, T10Y2Y) at this as_of date limits macro-overlay rigour.

## Invalidation Condition
Exit if reported gearing breaches 45% for any reporting period, or if DPU is formally cut by more than 10% relative to FY26 guidance, or if portfolio occupancy falls below 90% for two consecutive reporting periods, or if Growthpoint Properties Ltd undertakes a dilutive equity raise at a material discount to prevailing NAV estimates.
