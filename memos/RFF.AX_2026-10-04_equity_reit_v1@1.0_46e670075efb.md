# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-10-04_equity_reit_v1@1.0_46e670075efb`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agricultural/Farmland REIT
**As of**: 2026-10-04
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Rural Funds Group offers exposure to Australian agricultural land — a scarce real asset with long-WALE leases (typically 10-12 years) providing cash flow visibility. At AUD 1.885, the trailing distribution yield of ~6.2% sits 185bps above the RBA cash rate, offering a modest but real income spread. The OU Monte Carlo produces a simulated 12-month return of 7.1% with a PGain of 70.5% and a positive CAPM alpha of 7.9% against the IASP.L benchmark (currency-basis caveat applies). Conviction is set to Moderate (3/5) reflecting AFFO stalling flagged post-FY26 results, limiting near-term DPU growth optionality, and the absence of a large institutional sponsor pipeline to drive inorganic growth.

## Quantitative Chain

- E(R): 0.0720
- Std dev: 0.1326
- P-gain: 0.7049
- CAPM alpha: 0.0787
- Beta: 0.5054
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA maintains restrictive rates above 4.5% compressing farmland cap rates further; AFFO coverage drops below 1.0x forcing a DPU cut; drought conditions materially impair tenant rental capacity; gearing rises above 35% on land revaluation declines; multiple contracts 10% from current levels.
- **base**: E(R)=0.0720
  - Central case as built in chain: distribution yield 6.22%, DPU growth 1.0%, multiple change flat. Gearing stays ~30%, occupancy/rental collection stable. RBA holds rates steady.
- **bull**: E(R)=0.1900
  - RBA pivots to rate cuts in H1 2027, compressing farmland cap rates and expanding NAV; DPU growth accelerates to 3% via new property acquisitions; AFFO coverage recovers above 1.1x; price re-rates back toward AUD 2.20 pre-results levels, adding ~17% capital gain on top of yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0622 (Cat A) — Trailing DPU of approximately 11.73 cpu annualised (FY26 stable distributions per ASX announcement headline 2026-08-31 and 2026-08-21 FY26 financial results summary), divided by closing price AUD 1.885 on 2026-10-02.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth set at 1.0% p.a. reflecting conservative organic rental indexation on long-WALE agricultural leases. Downside reflects AFFO stalling flagged by Simply Wall St (22 Aug 2026) and Kalkine FY26 results analysis. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — No multiple expansion assumed over 12-month horizon. RFF re-rates with farmland sentiment and RBA rate trajectory; with RBA cash rate at 4.35% (BIS, 24 Sep 2026), cap rate compression is unlikely in the near term.
- `gearing_estimate` = 0.3 (Cat B) — Estimated gearing approximately 30% derived from ASX FY26 results headline (2026-08-21) noting 'lower gearing'. Below AU conventional 40% limit. Filing body capture was mismatched in the pipeline (body_unavailable effective for this filing); exact figure sourced from headline only and classified Category B.
- `rba_cash_rate` = 0.0435 (Cat A) — RBA policy rate 4.35% per BIS WS_CBPOL AU series, observation date 2026-09-24, age 10 days as of as_of date.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- AFFO stalling: if adjusted funds from operations do not recover, DPU sustainability comes into question, as flagged by market commentary following FY26 results (Aug 2026)
- RBA higher-for-longer rate environment compresses farmland cap rate and NAV, reducing any prospect of multiple expansion and widening the yield gap needed to attract buyers
- Agricultural weather risk: drought or flood events affecting tenant farming operations could impair rent collection on structurally long-dated leases, particularly in water-dependent almond and macadamia operations
- Illiquidity and thin trading: average daily volume is modest, and the August 2026 post-results sell-off (from ~AUD 2.22 to ~AUD 1.93) demonstrated limited market depth under selling pressure
- Currency basis noise in beta estimate: beta of 0.505 is computed against IASP.L (GBP-denominated) and absorbs AUD/GBP FX co-movement; true property market beta may differ materially

## Invalidation Condition
Exit if RFF announces a DPU reduction of 5% or more from the current annualised rate of approximately 11.73 cpu, or if AFFO coverage is reported below 0.95x for two consecutive semi-annual periods, or if reported gearing rises above 38% of total assets, or if RBA increases the cash rate above 5.0% without a corresponding farmland rent escalation clause triggering, any of which would materially impair the income thesis underpinning this position.
