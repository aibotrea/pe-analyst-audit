# Specialist Memo — GOZ.AX

**Memo ID**: `GOZ.AX_2026-08-19_equity_reit_v1@1.0_37baf059a0b8`
**Ticker**: GOZ.AX (Growthpoint Properties Australia)
**Market**: Australia
**Sector**: Office
**As of**: 2026-08-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Growthpoint Properties Australia (GOZ.AX) offers an elevated 8.2% distribution yield at AUD 2.10, providing an approximately 450bps spread over the 3.71% risk-free rate. The OU Monte Carlo (E(R) = 7.7%, sigma = 19.6%) returns a PGain of 71.7%, supporting a base conviction score of 4 before gate adjustments. Gearing at approximately 41% — above the Australian REIT 40% convention ceiling — triggers a one-step downward gate override, reducing conviction to 3 (Moderate). Structural office demand risk from hybrid work adoption is a persistent headwind, partially offset by Kalkine-reported record-pace leasing activity heading into FY27.

## Quantitative Chain

- E(R): 0.0770
- Std dev: 0.1331
- P-gain: 0.7170
- CAPM alpha: 0.0846
- Beta: 0.5488
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Office vacancy worsens materially; DPU cut 10-15% as AFFO coverage falls below 1.0x; gearing breaches 43%+ forcing distressed asset sales; RBA holds rates higher for longer compressing yield spreads; 20-25bps cap rate expansion across CBD office portfolio.
- **base**: E(R)=0.0770
  - Central case as modelled: DPU flat at ~17.2 cps, distribution yield 8.2%, occupancy stable with modest improvement from record leasing activity, gearing stable at ~41%, no material acquisitions, multiple change -0.5%.
- **bull**: E(R)=0.2000
  - RBA rate cuts materialise in H1 FY27 compressing discount rates; office leasing momentum drives occupancy to 93%+; DPU grows 2-3% from rent reversions; gearing declines below 40% via asset recycling; yield spread compression drives 10-15% capital appreciation above distributions.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.082 (Cat A) — Trailing distribution yield derived from GOZ.AX market price of AUD 2.10 (2026-08-19) consistent with Kalkine media coverage (Aug 2026) citing an 8.2% yield. Implies DPU of approximately 17.2 cents per unit. ASX filing bodies unavailable per Phase 01 v3.3 §4; headline and price sourced.
- `dpu_growth_rate` = 0.0 (Cat C) — Zero DPU growth assumed for the forward 12-month period. Office sector headwinds in Australian CBDs, gearing at approximately 41% constraining accretive acquisitions, and absence of confirmed FY27 guidance in available ASX announcements support a flat distribution base case. Sensitivity tested at -2% (bear) and +2% (bull).
- `multiple_change` = -0.005 (Cat C) — A modest -0.5% multiple contraction assumed, reflecting gearing near the 40% AU REIT convention ceiling and structural office re-pricing risk. GOZ price has declined approximately 12% over the trailing 12 months (AUD 2.38 to AUD 2.10). Scenario-tested across bear/bull range.
- `gearing_ratio` = 0.41 (Cat A) — Gearing approximately 41% per Kalkine media coverage (Jun 2026) sourced from GOZ balance sheet disclosures. ASX filing bodies unavailable (Phase 01 v3.3 §4 — ASX body capture parked); figure is headline-sourced. Exceeds AU <40% convention ceiling.
- `occupancy_signal` = positive (Cat B) — Kalkine (Aug 2026) headline references record-pace office leasing at Growthpoint, suggesting improving occupancy trajectory heading into FY27. Exact occupancy rate unavailable from ASX filing bodies; classified B as a derived qualitative signal from news coverage.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Gearing at ~41% exceeds the Australian REIT 40% convention ceiling; cap rate expansion or asset revaluation could force deleveraging sales at adverse prices.
- Office sector structural demand risk: hybrid work adoption continues to suppress net absorption in Australian CBD markets, threatening occupancy and rent reversion assumptions.
- Higher-for-longer RBA policy compressing the yield spread versus cash and increasing refinancing costs on floating-rate debt.
- ASX filing bodies unavailable in this analysis (Phase 01 v3.3 §4); exact DPU, AFFO coverage, WALE, and NTA could not be confirmed from primary filings — estimates rely on news-sourced figures.
- AUD/GBP currency basis embedded in the IASP.L beta of 0.549 introduces noise into the CAPM alpha estimate of 8.5%.

## Invalidation Condition
Exit or materially reduce position if GOZ reported gearing rises above 44% for two consecutive reporting periods, or if DPU is formally cut by more than 10% from the FY26 level per an ASX announcement, or if portfolio occupancy falls below 88% for two consecutive half-year periods, or if sponsor Growthpoint Properties Ltd reduces its ownership stake below 50% signalling a potential strategic exit from the Australian vehicle.
