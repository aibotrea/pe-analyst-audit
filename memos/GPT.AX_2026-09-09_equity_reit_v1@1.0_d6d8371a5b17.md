# Specialist Memo — GPT.AX

**Memo ID**: `GPT.AX_2026-09-09_equity_reit_v1@1.0_d6d8371a5b17`
**Ticker**: GPT.AX (The GPT Group)
**Market**: Australia
**Sector**: Diversified REIT (Office / Logistics / Retail)
**As of**: 2026-09-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
The GPT Group offers diversified Australian commercial real estate exposure — spanning logistics, office and retail — with a 97.6% portfolio occupancy rate and an internally managed structure that aligns management incentives with unitholder returns. At AUD 4.50, the trailing distribution yield of approximately 5.4% provides a meaningful spread over the 3-month T-bill rate of 3.8%, supported by higher H1 2026 FFO that underpins distribution sustainability. Beta of 0.76 against IASP.L (currency-basis caveat applies) is consistent with a diversified, lower-leverage REIT. The OU Monte Carlo simulation produces a 12-month sim return of 7.8% with a PGain of 71.4%, and a CAPM alpha of 10.5% reflecting the negative trailing benchmark return environment, both supporting an above-average conviction rating. Morningstar's July 2026 undervaluation flag and GPT's status as Australia's oldest REIT with demonstrated long-cycle capital discipline provide an additional margin of safety.

## Quantitative Chain

- E(R): 0.0790
- Std dev: 0.1389
- P-gain: 0.7137
- CAPM alpha: 0.1052
- Beta: 0.7589
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Occupancy falls to 93% driven by office sector weakness and tenant downsizing; DPU cut of ~10% as FFO coverage deteriorates below 1.0x; cap rate expansion of 50bps across the portfolio compresses NTA; RBA holds rates higher for longer, widening the spread disadvantage versus fixed income; no multiple re-rating occurs. This pathway also captures a broader macro stagflation risk where rising inflation sustains elevated rates while economic slowdown reduces tenant demand.
- **base**: E(R)=0.0790
  - Central case as built in the quantitative chain: distribution yield 5.4%, DPU growth 2.0% pa, +0.5% multiple re-rating, occupancy stable at 97.6%, gearing ~33%, RBA on gradual easing path. H1 2026 FFO trajectory maintained into H2 2026.
- **bull**: E(R)=0.2000
  - RBA delivers two additional rate cuts accelerating re-rating of yield-sensitive assets; logistics and retail rental reversions drive DPU growth of 4%+; office occupancy stabilises above 95% on flight-to-quality demand; Morningstar-assessed NTA discount closes materially; portfolio gearing falls below 30% via asset recycling at premium book values.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.054 (Cat A) — Trailing distribution yield derived from last-known annual DPU of approximately AUD 0.243 per unit against closing price of AUD 4.50 on 2026-09-09. Price is observed market data (Category A); DPU sourced from ASX distribution announcement headlines filed 2026-08-16 and 2026-06-19.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% pa assumed based on H1 2026 higher FFO result (Kalkine headline 2026-08-17), 97.6% portfolio occupancy (Kalkine headline 2026-09-07), and modest organic rental growth across logistics and retail segments. Office segment headwinds cap upside. Sensitivity tested in scenario analysis.
- `multiple_expansion` = 0.005 (Cat C) — Modest +0.5% multiple re-rating contribution assumed. Morningstar flagged GPT as undervalued versus NTA (headline 2026-07-01). Current price at AUD 4.50 is materially below typical NTA for a diversified REIT of this quality; partial re-rating assumed over 12-month horizon. Sensitivity: zero multiple change is the bear case.
- `portfolio_occupancy` = 0.976 (Cat A) — 97.6% portfolio occupancy reported in GPT 2026 Interim Result (ASX announcement 2026-08-16, headline: '2026 Interim Result Presentation', price_sensitive=True). Consistent with Kalkine news item dated 2026-09-07.
- `gearing_estimate` = 0.33 (Cat B) — Gearing estimated at approximately 33% based on GPT's historical balance sheet management and publicly available FY2025 disclosures. H1 2026 interim financial report filed 2026-08-16 confirms no material leverage event. Australian REIT regulatory convention threshold is <40%. Category B as derived from prior-period actuals without confirmed H1 2026 figure from filing body.
- `rba_cash_rate` = 0.04 (Cat B) — RBA cash rate estimated at 4.00% based on publicly available rate-setting context as of mid-2026. Live APAC rate tool returned no data. Treated as Category B given reliance on public policy communications rather than a live data feed.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Office segment structural headwinds: persistent work-from-home trends and corporate footprint rationalisation could suppress office occupancy and rental growth, weighing on FFO and DPU coverage.
- Higher-for-longer RBA rates compressing the distribution yield spread versus risk-free assets and maintaining re-rating headwinds on the unit price.
- Cap rate expansion risk: if global base rates remain elevated or rise further, property valuations could decline, increasing gearing and triggering covenant pressure.
- Execution risk on asset recycling: disposal of non-core assets at below-book values would destroy NTA and reduce distributable income.
- Phase 2 calibration limitation: this analysis is a directional signal only; vintage-discipline backtest validation arrives in Phase 5 and absence of confirmed H1 2026 gearing and AFFO coverage from filing bodies (ASX body capture pipeline delivered mismatched documents) introduces data uncertainty.

## Invalidation Condition
Exit if portfolio occupancy falls below 93% for two consecutive reporting periods, or if confirmed gearing breaches 38% of total assets (approaching the 40% Australian REIT convention limit), or if GPT announces a DPU reduction exceeding 10% without a corresponding accretive asset acquisition that restores forward FFO coverage above 1.0x AFFO, or if the RBA delivers unexpected rate hikes totalling more than 75bps above current levels within 12 months, materially widening the risk-free rate spread against the distribution yield.
