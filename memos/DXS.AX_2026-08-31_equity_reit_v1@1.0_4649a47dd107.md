# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-08-31_equity_reit_v1@1.0_4649a47dd107`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified Office/Industrial
**As of**: 2026-08-31
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Dexus offers an approximately 6.3% trailing distribution yield at the current AUD 5.78 unit price, providing a meaningful income component against the 3.74% risk-free rate, with an active on-market buy-back providing downside price support. Beta of 0.561 versus IASP.L (currency-basis caveat: AUD/GBP co-movement absorbed in coefficient) implies moderate market sensitivity, and CAPM alpha of 8.8% indicates expected outperformance relative to the CAPM required return on a deeply negative-returning APAC benchmark. However, the structural challenge of Australian CBD office vacancy, AFFO distribution coverage uncertainty flagged by market commentary, and a historically high volatility of 20% justify a moderate rather than above-average conviction stance. The OU Monte Carlo simulation produces a 12-month simulated return of 7.7% with a standard deviation of 13.6%, yielding a PGain of 71.6% — a positive but not high-confidence outcome.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.1359
- P-gain: 0.7155
- CAPM alpha: 0.0877
- Beta: 0.5607
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Australian office vacancy accelerates to 18%+ in CBD markets; Dexus DPU cut by 10-15% as tenant departures and lease incentive costs weigh on AFFO; cap rate expansion of 50bps erodes NTA, pushing unit price toward AUD 4.80; buy-back paused to preserve balance sheet; RBA rate-cutting cycle stalls or reverses, eliminating yield compression tailwind; gearing rises toward 38-39% as asset values fall.
- **base**: E(R)=0.0770
  - Distribution yield stable at ~6.3%; DPU growth +1.0% on modest rent reviews and stable occupancy; cap rates broadly flat with modest multiple re-rating (+0.5%) from buy-back support and early-cycle RBA easing; office occupancy stabilises around 92-93%; industrial and healthcare segments provide partial income offset; gearing maintained 30-35%.
- **bull**: E(R)=0.2200
  - RBA delivers 75-100bps of rate cuts through 2026-27, compressing office cap rates and re-rating REITs materially; return-to-office momentum strengthens CBD leasing demand; DPU growth +3.5% driven by rent reviews and industrial platform expansion; multiple expansion of +2.5% as unit price re-rates toward NTA; buy-back accretion supplements distribution; total return driven by yield plus capital appreciation.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat B) — Trailing distribution yield of approximately 6.3% cross-referenced from Kalkine media analysis (June 2026) at the prevailing AUD 5.78 unit price as at 2026-08-31, implying an annualised DPS of approximately AUD 0.364. Classified Category B as derived from published distribution and observed market price; exact FY2026 annual DPS confirmation pending full annual report but consistent with 30 June 2026 distribution payment confirmed via ASX announcement 2026-08-28.
- `dpu_growth_3yr` = 0.01 (Cat C) — Forward DPU growth of +1.0% p.a. assumed for the base case. Dexus faces structural office demand headwinds from hybrid working adoption and rising Australian office vacancy rates in Sydney and Melbourne CBD. Partial offset from Dexus's industrial and healthcare real estate exposure and active capital recycling. Growth assumption is conservative relative to pre-COVID history (~2-3% p.a.) given ongoing income compression risk. Sensitivity tested in scenario analysis; bear case assumes -1% (DPU decline), bull case assumes +3.5%.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple expansion assumed over 12 months, reflecting potential benefit from RBA rate easing cycle (if it materialises), active on-market buy-back support confirmed via multiple ASX notifications (2026-08-23 through 2026-08-27), and DXS trading at a meaningful discount to historical NAV. Downside risk: office cap rate expansion could negate any multiple expansion. Scenario analysis stress-tests -1.5% (bear) and +2.5% (bull) multiple change.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise. Beta of 0.561 computed over 252 trading days to 2026-08-31 with 256 observations; correlation 0.322 indicates moderate co-movement with the APAC REIT universe.
- `rba_cash_rate` = unavailable_from_stored_data (Cat C) — RBA cash rate not returned from stored APAC rates as at 2026-08-31 (get_stored_apac_rates returned empty; get_apac_rates returned empty for AU). Publicly available RBA data suggests the cash rate was in a declining cycle through mid-2026 from a peak of ~4.35%. Exact current rate not confirmed; treated as a supporting qualitative input only. Key risk: if RBA pauses or reverses, yield compression thesis weakens.
- `office_vacancy_risk` = elevated (Cat C) — Australian CBD office vacancy remains structurally elevated by historical standards due to post-pandemic hybrid work adoption. DXS derives the majority of its income from office assets in Sydney and Melbourne CBD. This is a Category C input used to calibrate the conservative DPU growth assumption and distribution coverage gate.

## Key Risks
- Australian CBD office vacancy remaining elevated or worsening due to structural hybrid-working adoption, compressing net operating income and DPU coverage below 1.0x AFFO
- RBA rate-cutting cycle failing to materialise or reversing, reducing the yield spread attractiveness of the 6.3% distribution and widening office cap rates, depressing NTA
- Cap rate expansion in the office and industrial segments forcing downward asset revaluations, pushing gearing above the 40% Australian REIT convention threshold and constraining distribution capacity
- Elevated annualised price volatility (~20%) reflecting continued uncertainty in the Australian listed REIT sector; the APAC REIT benchmark (IASP.L) has returned -4.7% annualised over 5 years, indicating persistent sector headwinds
- Backtest calibration limitation: Phase 2 calibration is a directional signal only; vintage discipline arrives in Phase 5. Absence of real-time RBA cash rate confirmation means the rate-sensitivity thesis relies on Category C assumptions

## Invalidation Condition
Exit position if Dexus reports two consecutive half-year periods of DPU decline exceeding 5% relative to the prior corresponding period, or if portfolio occupancy falls below 88% for two consecutive quarters, or if look-through gearing is reported above 40% of asset values, or if the on-market buy-back is suspended without a capital management alternative announced, signalling management no longer views the unit price as offering value.
