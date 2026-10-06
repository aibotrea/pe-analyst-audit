# Specialist Memo — ABG.AX

**Memo ID**: `ABG.AX_2026-10-06_equity_reit_v1@1.0_4753ad2d6224`
**Ticker**: ABG.AX (Abacus Group)
**Market**: Australia
**Sector**: Office/Commercial
**As of**: 2026-10-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Abacus Group (ABG.AX) is a focused Australian commercial REIT trading at AUD 0.82 with a trailing distribution yield of approximately 9% that has been reset lower entering FY27 following the sale of its Storage King self-storage interest. The post-disposal portfolio concentrates ABG in Australian CBD office — a sector facing structural headwinds from hybrid work adoption and elevated domestic interest rates (RBA 4.35%). Historical volatility of 23.9% reflects elevated price risk relative to diversified A-REITs, and the OU Monte Carlo yields a PGain of 66.5% with a simulated std dev of 16.2%, insufficient to overcome two qualitative gate overrides (distribution coverage uncertainty and office sector concentration). Alpha of 8.3% vs IASP.L is mathematically positive but inherits significant currency-basis noise given the negative 5-year IASP.L benchmark return of -5.2% annualised.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1621
- P-gain: 0.6654
- CAPM alpha: 0.0829
- Beta: 0.5740
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Office vacancy in Australian CBDs rises to 20%+, DPU coverage falls below 1.0x AFFO post-distribution reset, cap rate expansion of 75bps forces NTA write-downs, gearing breaches 40% covenant threshold post asset revaluation, RBA rate remains elevated above 4.0%, and distribution is cut further — compounding the income reset already underway in FY27.
- **base**: E(R)=0.0700
  - Central case as built: forward yield 7.5%, DPU growth 1.0% organic, cap rate flat to modest -1.5% multiple contraction. RBA holds at 4.35%, office occupancy broadly stable, Storage King sale proceeds reduce gearing below 40%, and ABG stabilises as a focused commercial REIT.
- **bull**: E(R)=0.2200
  - RBA cuts rates by 75bps driving cap rate compression, Australian CBD office demand recovers above expectations, DPU growth of 2.5%+ from rental indexation and NLA uplift, Storage King sale proceeds deployed accretively into office assets above 7% yield, NTA re-rates toward AUD 1.10–1.20 from discount to current price.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.075 (Cat C) — Forward distribution yield estimated at 7.5% on current price of AUD 0.82. News sources (Kalkine, Aug-Sep 2026) cited trailing yield of 8.94–9.34%; discounted to 7.5% forward to reflect the FY27 distribution reset announced post-Storage King Group sale (ABG.AX ASX announcement 2026-09-17 'Sale of Interest in Storage King Group'). Category C as forward DPU quantum post-reset is not yet formally published at as_of date.
- `dpu_growth` = 0.01 (Cat C) — DPU growth assumed at 1.0% p.a. reflecting modest organic rental indexation in Australian CBD office assets. Abacus Group enters FY27 as a focused commercial REIT (news: 'Abacus Group Enters FY27 as a Focused Commercial REIT', Aug 2026); structural office vacancy headwinds in Australian CBD markets constrain growth above CPI. Sensitivity: bear case assumes 0% growth, bull case 2.5%.
- `multiple_change` = -0.015 (Cat C) — Multiple contraction of -1.5% assumed reflecting continued cap rate expansion pressure in Australian office sector amid RBA policy rate at 4.35% (BIS observation date 2026-09-24). Office REITs face structural demand headwinds from hybrid work adoption; modest cap rate widening embedded. Sensitivity: bull case assumes flat multiples (+0%), bear case assumes -4% contraction.
- `storage_king_disposal` = completed (Cat A) — ABG.AX ASX announcement 2026-09-17 (price-sensitive): 'Sale of Interest in Storage King Group'. Headline confirms disposal event; body capture was cross-contaminated in pipeline. Disposal creates a focused commercial/office REIT profile, removes self-storage income diversification, and likely reduces gearing post-settlement.
- `rba_policy_rate` = 0.0435 (Cat A) — Reserve Bank of Australia policy rate 4.35%, observation date 2026-09-24 (age 12 days), sourced from BIS WS_CBPOL via get_stored_apac_rates. Represents the domestic discount rate environment for AUD-denominated commercial property.
- `leverage_gearing` = estimated_sub_40pct (Cat C) — Post Storage King sale proceeds, gearing estimated to have declined below 40% (Australian convention threshold). Specific gearing figure not available from accessible filings at as_of date due to ASX body capture cross-contamination in pipeline. Disclosed as uncertainty; if gearing >40% the leverage gate would trigger a further override. Sensitivity tested in bear case.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Correlation of 0.28 indicates moderate co-movement with the APAC REIT universe.

## Key Risks
- FY27 distribution reset magnitude not yet confirmed at as_of date; if forward DPU is materially below trailing figures, the yield-based E(R) assumption deteriorates significantly
- Australian CBD office structural vacancy — hybrid work adoption may permanently impair occupancy rates and rental growth, pressuring NTA and AFFO coverage
- RBA higher-for-longer scenario: 4.35% policy rate sustains or rises, widening cap rates on commercial property and compressing NTA, potentially triggering covenant concerns if gearing drifts above 40%
- Filing body cross-contamination in the ASX pipeline prevented direct verification of gearing, WALE, occupancy and DPU coverage from FY26 annual report; these remain disclosed data gaps
- Concentration risk: post-Storage King disposal, ABG is a single-sector (office) REIT without diversification from the self-storage segment, heightening earnings sensitivity to office market conditions

## Invalidation Condition
Exit if ABG's reported gearing rises above 40% for two consecutive reporting periods, or if the FY27 annualised DPU falls below AUD 0.055 per security (implying coverage below 1.0x AFFO on current estimates), or if Australian CBD office vacancy in ABG's core markets exceeds 20% with no recovery trajectory evidenced within two quarters, or if management confirms no accretive reinvestment plan for Storage King disposal proceeds within 12 months of settlement.
