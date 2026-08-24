# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-08-24_equity_reit_v1@1.0_4dd893bb6b24`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Residential/Land-Lease Communities
**As of**: 2026-08-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Ingenia Communities Group operates a structurally supported land-lease and lifestyle community platform with CPI-linked organic rent growth and a development settlement pipeline providing incremental earnings. However, conviction is constrained to Low by a price-sensitive Trading Halt entered on 2026-08-23 whose nature and implications are entirely unknown given ASX body capture failure, compounded by an unexplained prior trading pause and media-speculation response in July 2026. Annualised historical volatility of 24.8% is elevated for a defensive REIT sector, and the OU Monte Carlo PGain of 63.5% reflects only marginal probability of a positive 12-month return under the current uncertainty profile. CAPM alpha of 7.7% is technically positive but is a Category B signal that inherits IASP.L/AUD-GBP currency-basis noise and is treated as supporting context only.

## Quantitative Chain

- E(R): 0.0590
- Std dev: 0.1686
- P-gain: 0.6351
- CAPM alpha: 0.0767
- Beta: 0.6809
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Trading halt resolves with a dilutive equity raise or adverse regulatory or legal finding, DPU cut of 15-20%, gearing rises above 38% due to asset write-downs, development settlements stall in a slowing residential market, and AUD/GBP FX headwinds amplify benchmark underperformance. Cap rate expansion of 25-50bps further erodes NTA.
- **base**: E(R)=0.0580
  - Central case as built in chain: distribution yield 3.4%, DPU growth 3.0%, minor multiple contraction of -0.5%, gearing stable at approximately 34%, trading halt resolves without material adverse outcome, occupancy in lifestyle communities remains above 90%.
- **bull**: E(R)=0.2000
  - Trading halt resolves with an accretive transaction such as a portfolio acquisition or corporate activity at a premium, RBA rate cuts accelerate cap rate compression by 25bps, development pipeline settlements beat guidance, DPU growth upgrades to 5% or above, and re-rating toward sector peers closes a NAV discount.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.034 (Cat A) — Trailing DPU of approximately 14.5 cpu (FY2025 actuals, publicly reported) divided by closing price of AUD 4.26 on 2026-08-24. Observable published figure.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth assumption of 3.0% p.a.: ~2.5% organic CPI-linked rental escalation across land-lease communities plus ~0.5% net contribution from development settlement pipeline (Ingenia Lifestyle new home settlements). Sensitivity tested in scenarios. No filed guidance available as of as_of due to body capture failures for Business Update (2026-06-02) and pending filings.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% multiple contraction to reflect unresolved price-sensitive Trading Halt (2026-08-23) and prior Pause in Trading and Response to media speculation (2026-07-09/10). Body unavailable for all three events. Negative bias applied conservatively.
- `gearing_assumption` = 0.34 (Cat B) — Estimated gearing of approximately 34% based on publicly disclosed FY2025 balance sheet data for Ingenia Communities Group. Within Australian REIT convention limit of less than 40%. No FY2026 filed balance sheet available due to ASX body capture failures.
- `trading_halt_uncertainty` = material_event_unresolved (Cat C) — INA.AX entered a price-sensitive Trading Halt on 2026-08-23, one day prior to as_of. Filing body unavailable. A further price-sensitive Pause in Trading and Response to media speculation occurred on 2026-07-09 to 2026-07-10; both bodies unavailable. Nature of events is unknown. This is the primary source of elevated model uncertainty and the basis for a -1 gate override on management_alignment.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Unresolved price-sensitive Trading Halt (2026-08-23): nature and financial implications entirely unknown; could range from benign corporate activity to material dilution or regulatory action.
- Development pipeline execution risk: earnings increasingly depend on new home settlements, which are sensitive to residential market conditions and construction cost inflation in Australia.
- Interest rate sensitivity: AUD rates remaining higher-for-longer compress the yield spread over the risk-free rate (T-bill 3.72%) and may drive cap rate expansion that erodes NTA.
- Elevated annualised volatility (24.8%) versus typical Australian REIT peers, suggesting persistent market uncertainty that predates the as_of trading halt.
- ASX filing body capture failure across all material announcements in the 180-day lookback window precludes independent verification of gearing, DPU coverage, and management guidance.

## Invalidation Condition
Exit position immediately if the trading halt resolves with a DPU cut exceeding 10%, a dilutive equity raise priced at more than 5% discount to the pre-halt closing price, or reported gearing rising above 38%; additionally exit if two consecutive half-year DPU coverage ratios fall below 1.0x AFFO, or if occupancy across the lifestyle community portfolio declines below 88% for two consecutive reporting periods.
