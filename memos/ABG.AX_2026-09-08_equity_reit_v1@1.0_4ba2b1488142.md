# Specialist Memo — ABG.AX

**Memo ID**: `ABG.AX_2026-09-08_equity_reit_v1@1.0_4ba2b1488142`
**Ticker**: ABG.AX (Abacus Group)
**Market**: Australia
**Sector**: Office
**As of**: 2026-09-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Abacus Group is a pure-play Australian commercial (office) REIT following the demerger of Abacus Storage King (ASK.AX), currently trading at AUD 0.84 — a ~17% drawdown from mid-June 2026 levels — implying a trailing distribution yield of approximately 9.34%. The quantitative chain returns a PGain of 77.0% and CAPM alpha of +11.6% against a negative-returning IASP.L benchmark, supporting the statistical case for a positive 12-month return. However, qualitative gate reviews apply two downward overrides reflecting: (1) uncertain AFFO distribution coverage given the absence of filing body data and structural office sector pressures, and (2) concentration risk in Australian commercial office, a sector facing persistent hybrid-work headwinds. Conviction is capped at Low (2) with a 3% maximum position, reflecting the balance between a meaningful yield cushion and material execution risk in ABG's post-demerger strategic repositioning.

## Quantitative Chain

- E(R): 0.1130
- Std dev: 0.1520
- P-gain: 0.7701
- CAPM alpha: 0.1161
- Beta: 0.4746
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Office vacancies accelerate materially as hybrid work demand weakens further; RBA holds rates higher-for-longer compressing valuations; NTA write-downs force distribution cuts reducing DPU coverage below 1.0x AFFO; leverage breaches 40% LVR covenant triggering equity raising at a discount; Storage King divestiture proceeds disappoint, removing a value catalyst and exacerbating the discount to NTA.
- **base**: E(R)=0.1130
  - Central case as built in chain: distribution yield 9.34%, DPU growth 1.0%, modest multiple expansion 1.0% on RBA rate cuts beginning to materialise; occupancy stable in the low-90% range; leverage within regulatory limits; commercial REIT repositioning on track following Storage King demerger.
- **bull**: E(R)=0.2800
  - RBA delivers meaningful rate cuts accelerating property re-rating; ABG executes accretive office asset recycling at 6%+ yield-on-cost; NTA discount closes substantially as market regains confidence in pure-play commercial REIT strategy; occupancy improves above 95%; DPU growth exceeds 3% p.a. on positive rent reversion in core CBD markets.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0934 (Cat A) — Implied trailing distribution yield of ~9.34% at current price AUD 0.84, consistent with FY26 Fund Payment Notice (ASX announcement 2026-08-31) and corroborated by Kalkine media coverage dated 2026-08-14. Observed public market data.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. assumed. ABG is repositioning as a pure commercial (office) REIT following the demerger of Abacus Storage King (ASK.AX). Office sector in Australia faces structural headwinds from hybrid work; modest positive organic rent reversion assumed against cost pressures. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.01 (Cat C) — Modest mean-reversion multiple expansion of 1.0% assumed. ABG has re-rated downward ~17% over June-September 2026 and is likely trading at a discount to NTA given the Storage King divestiture overhang and market uncertainty around office REIT strategy. A partial re-rating toward NTA is the base-case assumption. Rate-easing expectations in Australia provide a supportive tailwind.
- `leverage_ratio` = estimated_35_40pct (Cat B) — No ASX filing body available (body capture parked for ASX as of Phase 01 v3.3 §4). Leverage estimated at 35-40% LVR based on sector norms for Australian commercial REITs and announced corporate strategy post-demerger. Assumed within the AU convention threshold of <40%. If confirmed above 40%, a further gate override may apply.
- `rba_cash_rate` = unavailable (Cat C) — RBA cash rate not available from stored APAC rates at as_of 2026-09-08. News headlines reference shifting rate expectations in Australia as a tailwind for property. No stored macro rate available; treated as supporting context only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Structural office demand decline from hybrid-work adoption compresses occupancy and rent reversion, impairing DPU coverage and triggering distribution cuts.
- Higher-for-longer Australian interest rates maintain pressure on property valuations and NTA, widening the discount to book and constraining capital recycling options.
- Post-demerger leverage uncertainty: without confirmed FY26 balance sheet data (ASX filing body unavailable), gearing may be approaching or breaching the 40% LVR convention, limiting financial flexibility.
- Storage King divestiture overhang: market uncertainty around transaction proceeds, timing of capital return, and reinvestment strategy may weigh on sentiment and price.
- Calibration limitation: Phase 2 calibration is directional only; vintage point-in-time discipline arrives in Phase 5, so backtest-mode scenario accuracy is not formally validated.

## Invalidation Condition
Exit position if FY26 or interim results confirm DPU coverage falls below 1.0x AFFO for two consecutive reporting periods, or if aggregate leverage (LVR) is disclosed above 42% without a credible deleveraging plan, or if ABG management announces a further material strategic pivot — such as re-entering self-storage or undertaking a dilutive equity raising — that undermines the pure-play commercial REIT thesis underpinning the yield and multiple-expansion assumptions.
