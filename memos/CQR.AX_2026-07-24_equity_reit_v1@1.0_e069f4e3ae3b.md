# Specialist Memo — CQR.AX

**Memo ID**: `CQR.AX_2026-07-24_equity_reit_v1@1.0_e069f4e3ae3b`
**Ticker**: CQR.AX (Charter Hall Retail REIT)
**Market**: Australia
**Sector**: Retail/Neighbourhood Shopping Centres
**As of**: 2026-07-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Charter Hall Retail REIT (CQR) offers high-quality Australian neighbourhood shopping centre exposure anchored by Coles and Woolworths, providing defensive, non-discretionary cash flows underpinning a 6.55% trailing distribution yield. The yield spread over Australian equivalents of the US 3-month T-bill (3.81%) remains attractive, and CQR's recovery from AUD 2.86 lows in late 2024 to AUD 3.88 demonstrates resilience in a rate-normalising environment. OU Monte Carlo simulation returns a 12-month sim return of 7.99% with PGain of 74.2%, supporting an above-average conviction rating. Beta of 0.53 versus IASP.L (currency-basis caveat applies) reflects moderate co-movement with the broader APAC REIT universe, and a CAPM alpha of 8.16% signals meaningful expected outperformance against a benchmark that has delivered negative trailing 5-year returns.

## Quantitative Chain

- E(R): 0.0805
- Std dev: 0.1231
- P-gain: 0.7419
- CAPM alpha: 0.0816
- Beta: 0.5344
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA rate cuts stall or reverse; cap rates expand 30-40bps compressing NTA; specialty tenant vacancies rise as discretionary spending weakens; DPU coverage falls below 1.0x requiring a distribution cut; AUD/GBP volatility increases beta noise. Gearing approaching 38% limiting acquisition capacity.
- **base**: E(R)=0.0800
  - Central case as modelled: 6.55% distribution yield sustained, DPU growth 1.5% from CPI-linked anchors and specialty reversion, cap rates flat, occupancy stable >97% for anchors, gearing ~31-33%.
- **bull**: E(R)=0.2000
  - RBA delivers further rate cuts compressing retail cap rates 20-25bps; CPI stays elevated supporting >3% DPU growth via CPI-linked lease reviews; Charter Hall accretive acquisition pipeline materialises; yield spread tightening drives 8-10% price appreciation on top of distributions.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0655 (Cat A) — Trailing distribution yield of 6.55% sourced from Kalkine market commentary dated 20 Jul 2026, consistent with ASX-announced distributions at the observed closing price of AUD 3.88 on 2026-07-24. Treated as Category A as it is derived from published DPU and market price.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed based on CQR's CPI-linked anchor lease structures (Coles/Woolworths) and modest specialty tenant reversion. Below trailing CPI to reflect stabilising retail leasing conditions. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Neutral cap rate assumption: CQR has recovered from Dec-2024 lows (~AUD 2.86) to AUD 3.88; further multiple expansion not assumed at current level. If RBA cuts continue, modest compression possible (captured in bull scenario).
- `gearing_ratio` = ~30-33% (Cat B) — Estimated from CQR historical reporting and H1 FY2026 results headline (2026-02-05 periodic report). Filing body unavailable (ASX body capture Phase 01 v3.3 §4). Consistent with Australian convention limit of <40%. Gap disclosed.
- `rba_cash_rate` = data unavailable (Cat C) — get_stored_apac_rates returned empty for AU as_of 2026-07-24; get_apac_rates live call also returned empty. RBA rate direction is a key valuation input; omission noted in key_risks. Risk-free rate sourced from US T-bill as proxy (3.81%).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- RBA monetary policy path uncertainty: any pause or reversal in rate cuts would sustain or widen cap rates, compressing NTA and limiting price appreciation
- ASX filing body capture unavailable (Phase 01 v3.3 §4): precise DPU, gearing, and AFFO coverage figures could not be verified from filed documents — distribution yield sourced from third-party commentary
- Specialty retail tenant stress: rising retail vacancy or weaker-than-expected specialty rent reversion would reduce DPU growth below the 1.5% base assumption
- AUD/GBP currency basis in beta calculation introduces noise in CAPM alpha; actual property-market beta may differ from the reported 0.53
- Backtest calibration limitation: Phase 2 calibration is directional only; vintage discipline arrives in Phase 5 and conviction score should be read as a relative signal, not a precise probability

## Invalidation Condition
Exit if CQR announces a distribution cut reducing trailing DPU by more than 5% for two consecutive half-year periods, or if reported gearing exceeds 38% of total assets for one or more reporting periods, or if anchor tenant (Coles or Woolworths) vacates more than three centres within a 12-month window, signalling structural deterioration in the neighbourhood centre thesis.
