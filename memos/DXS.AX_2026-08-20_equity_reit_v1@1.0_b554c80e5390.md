# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-08-20_equity_reit_v1@1.0_b554c80e5390`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Office/Diversified
**As of**: 2026-08-20
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus (DXS.AX) is Australia's largest diversified office A-REIT, trading at a significant discount to NTA at AUD 5.89 with a trailing distribution yield of approximately 6.3% — a decade-low entry point that prices in substantial structural pessimism about Australian CBD office demand. The CAPM alpha of 6.5% against a deeply negative benchmark return (-4.4% annualised for IASP.L) reflects genuine excess return potential, but this is partly an artefact of currency and benchmark noise. The OU Monte Carlo assigns a 66.5% probability of a positive 12-month return with a simulated central return of 5.7%, providing a modest but not compelling risk-adjusted case. Distribution coverage uncertainty (AFFO coverage estimated at 0.95-1.0x, with sustainability questioned in the press ahead of FY2026 results) and high historical volatility (19.8% annualised) are the principal constraints on conviction, leaving the score at 2 (Low) after applying one gate override.

## Quantitative Chain

- E(R): 0.0580
- Std dev: 0.1348
- P-gain: 0.6648
- CAPM alpha: 0.0653
- Beta: 0.5505
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - CBD office vacancy rises further as hybrid-work adoption entrenches; DXS occupancy falls below 90%; DPU cut of 10-15% as AFFO coverage breaks below 0.90x; Australian office cap rates expand 25-50bps driven by global risk-off or higher-for-longer RBA rates; gearing drifts toward 33-35% LVR triggering debt covenant scrutiny. Bear case also encompasses a stagflation scenario where RBA is forced to re-hike, AUD weakens sharply, and valuation deratings compound income losses.
- **base**: E(R)=0.0580
  - Central case as built in chain: distribution yield 6.3%, zero DPU growth, -0.5% multiple drag from modest cap-rate drift. Occupancy stable at ~90%, RBA continues gradual easing supporting REIT valuations marginally, gearing stable ~28% LVR.
- **bull**: E(R)=0.1800
  - RBA cuts accelerate, compressing cap rates by 25-40bps and lifting NTA; office leasing demand recovers as corporates mandate return-to-office, driving occupancy above 93%; DPU growth of 3-5% as portfolio income lifts; Dexus funds management platform AUM growth boosts fee income, supporting a valuation re-rate to price/NAV parity from current discount.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat A) — Trailing distribution yield derived from current price AUD 5.89 and FY2026 DPU of approximately AUD 0.37/unit; consistent with Kalkine June 2026 article citing 6.3% yield at a decade low for DXS. Category A: based on published closing price and filed distribution data.
- `dpu_growth` = 0.0 (Cat C) — Zero DPU growth assumed for FY2027. Dexus faces structural headwinds in Australian CBD office from persistent hybrid-work adoption, elevated vacancy in secondary CBD stock, and development capital requirements that compress distributable income. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Modest cap-rate expansion of approximately 5bps assumed, translating to a -0.5% valuation drag. Australian office cap rates have drifted wider since 2022 rate-rise cycle; RBA easing in 2025-26 provides partial offset but structural demand uncertainty limits meaningful cap-rate compression. Sensitivity tested in scenario analysis.
- `expected_return_build` = 0.058 (Cat B) — E(R) = distribution yield (6.3%, Category A) + DPU growth (0.0%, Category C) + multiple change (-0.5%, Category C) = 5.8%. Component-weighted derivation per framework methodology.
- `gearing_ratio` = 0.28 (Cat B) — Dexus FY2025 reported look-through gearing approximately 28% LVR, derived from published annual results. FY2026 figures filed 2026-08-19 (price-sensitive); body not available to this pipeline. Assumed stable at ~28%, within Australian A-REIT convention of <40%. Disclosed as Category B pending FY2026 confirmation.
- `distribution_coverage_status` = uncertain (Cat B) — Kalkine (June 2026) flagged sustainability of DXS 6.3% yield at a decade-low price, raising AFFO coverage questions. FY2026 financial statements filed 2026-08-19 (price-sensitive) but body not accessible in this pipeline. AFFO coverage assumed at approximately 0.95-1.0x — tight but not confirmed below threshold. Disclosed as uncertain; qualitative gate set to info with -1 override.
- `rba_cash_rate_context` = easing_cycle (Cat B) — RBA commenced rate-cut cycle in 2025; stored APAC rate series returned no data for AU at as_of 2026-08-20. RBA cash rate assumed in 3.85-4.10% range based on publicly available RBA guidance. Provides partial support to REIT valuations via lower discount rates, offset by weak office demand fundamentals.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP currency and IASP benchmark returns. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Distribution sustainability: AFFO coverage is tight at approximately 0.95-1.0x; any further income decline from leasing spreads, vacancies, or rising borrowing costs could trigger a DPU cut, causing price re-rating.
- Structural office demand headwind: persistent hybrid-work adoption in Australian CBD markets constrains rent growth and elevates incentive levels, compressing net effective rents and NTA.
- Cap-rate risk: if RBA pauses easing or global rates stay elevated, Australian office cap rates could expand further, generating additional book-value write-downs and eroding NTA-based valuation support.
- FY2026 results uncertainty: 2026 Financial Statements filed 2026-08-19 are price-sensitive; actual gearing, DPU, and AFFO coverage figures were not accessible to this pipeline and could deviate materially from assumptions.
- Benchmark and backtest limitations: IASP.L is GBP-denominated; beta and CAPM alpha absorb AUD/GBP FX noise (Category B). The 5-year benchmark return of -4.4% reflects an adverse macro period for APAC REITs and may not reflect forward expected market returns.

## Invalidation Condition
Exit position if DXS reports two consecutive half-year periods where AFFO distribution coverage falls below 0.90x, or if portfolio occupancy declines below 87% for two consecutive reporting periods, or if reported LVR gearing exceeds 38% of total assets triggering proximity to covenant limits, or if management announces a formal DPU guidance cut of more than 10% from the FY2026 declared level.
