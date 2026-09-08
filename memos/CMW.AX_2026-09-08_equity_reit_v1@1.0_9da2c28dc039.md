# Specialist Memo — CMW.AX

**Memo ID**: `CMW.AX_2026-09-08_equity_reit_v1@1.0_9da2c28dc039`
**Ticker**: CMW.AX (Cromwell Property Group)
**Market**: Australia
**Sector**: Diversified/Office
**As of**: 2026-09-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Cromwell Property Group offers a nominally high trailing yield (~6.8% at AUD 0.37) but this is substantially offset by a challenging structural backdrop: elevated gearing above the Australian 40% convention, a portfolio concentrated in office assets facing secular hybrid-work headwinds, and an active but uncertain de-risking agenda evidenced by the Chatswood JV exit and ongoing European asset recycling. The OU Monte Carlo (sigma 28.1%, E(R) 4.3%) produces a PGain of only 58.7%, barely above the 50% toss threshold, providing limited statistical conviction. Two qualitative gate failures — leverage and office asset-quality concentration — reduce the mechanically derived conviction score to 1 (Speculative), warranting a maximum 1.0% position. The CAPM alpha of 6.5% relative to the GBP-denominated IASP.L benchmark (currency-basis caveat applies) is a weak positive signal but insufficient to override the high volatility and structural risks.

## Quantitative Chain

- E(R): 0.0430
- Std dev: 0.1913
- P-gain: 0.5871
- CAPM alpha: 0.0647
- Beta: 0.6910
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - Office cap rates expand a further 50bps; AUM declines from additional forced asset sales at below-book prices; DPU cut of 20%+ as AFFO coverage drops below 1.0x; gearing remains above 45% forcing equity raising at a discount; global rate shock (central banks re-tightening) compounds yield spread compression and NAV erosion.
- **base**: E(R)=0.0430
  - Central case as modelled: distribution yield 6.8%, DPU growth -1.5%, cap rate headwind -1.0%. Chatswood exit proceeds reduce gearing modestly. Office occupancy stable but under pressure. No new accretive acquisitions.
- **bull**: E(R)=0.1800
  - RBA rate cuts accelerate materially, compressing office cap rates and re-rating CMW's portfolio NTA upward; successful disposal of European assets at or above book value reduces gearing below 35%; DPU maintained or increased; unit price re-rates toward NTA from a deep discount.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.068 (Cat A) — Trailing DPU yield estimated at ~6.8% at current market price of AUD 0.37. Kalkine (20 Jul 2026) cited a 6.89% yield when CMW traded near AUD 0.44; at AUD 0.37 the implied yield is marginally higher on a stable trailing DPU basis. Filed FY26 Appendix 4E (price-sensitive, 2026-08-26) confirms distribution was declared for the period. Category A: current price is observed; DPU sourced from published trailing figures.
- `dpu_growth` = -0.015 (Cat C) — DPU growth estimated at -1.5% p.a. Cromwell is in active portfolio repositioning — including completion of Chatswood JV exit (July 2026 ASX announcement) and ongoing European asset recycling. Office-dominant exposure and reduced AUM from disposals are expected to suppress distributable income. No explicit FY27 DPU guidance was available from filed headlines. Sensitivity: range -3.5% (bear) to +1.0% (bull).
- `multiple_change` = -0.01 (Cat C) — Cap-rate / multiple assumption: -1.0% contribution from modest cap rate expansion in Australian and European office markets. CMW price fell ~16% from AUD 0.44 to AUD 0.37 between August and September 2026, consistent with ongoing re-rating. Office sector faces structural hybrid-work headwinds. Sensitivity: range -3.0% (bear) to +2.0% (bull).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis is non-trivial given AUD/GBP volatility over the lookback window. Treated as Category B input. CAPM alpha inherits the same noise. IASP.L annualised return of -4.82% over 5 years also absorbs GBP appreciation effects.
- `rba_cash_rate` = not_retrieved (Cat C) — RBA cash rate data was not available via stored APAC rates or live APAC rates API as at 2026-09-08. The RBA easing cycle context (assumed ~4.10% cash rate based on public reporting through mid-2026) is used qualitatively to assess yield spread attractiveness but does not enter the quantitative chain directly.

## Key Risks
- Gearing above Australian REIT convention (~40% LVR) limits financial flexibility; further asset sales at discounts could destroy NAV and trigger a DPU cut.
- Structural office demand decline from hybrid-work adoption reduces long-run occupancy and rental reversion, compressing distributable income below current yield assumptions.
- European asset recycling at below-book values could crystallise losses and impair balance sheet, particularly if EUR/AUD currency moves are unfavourable.
- Shareholder activism or management instability (historical precedent) could distract from capital allocation discipline at a critical portfolio transition stage.
- Phase 2 calibration limitation: this analysis is a directional signal only; formal backtest vintage discipline is pending Phase 5, and macro series (FEDFUNDS, HY spread) were unavailable and omitted.

## Invalidation Condition
Exit or reassess if CMW reports DPU coverage below 1.0x AFFO for two consecutive half-year periods, or if reported gearing (LVR) increases above 48% from any quarter-end filing, or if the European asset disposal programme produces realised losses exceeding 10% of carrying value on more than two assets, signalling systematic book value impairment.
