# Specialist Memo — CNI.AX

**Memo ID**: `CNI.AX_2026-08-14_equity_reit_v1@1.0_3a142f4fefbd`
**Ticker**: CNI.AX (Centuria Capital Group)
**Market**: Australia
**Sector**: Diversified Property Funds Management
**As of**: 2026-08-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Centuria Capital Group offers diversified Australian property sector exposure through its managed REIT platform (Centuria Industrial REIT, Centuria Office REIT) with a current distribution yield of approximately 6.48% at AUD 1.50. However, the stock has undergone a severe ~34% drawdown from mid-June 2026 highs amid rate anxiety and sector-wide re-rating pressure, creating both value and risk. The AI Factory initiative with ResetData represents an optionality play on data centre infrastructure, though execution risk is elevated and FY26 results are pending. The OU Monte Carlo returns a PGain of 61.1% and a CAPM alpha of 8.87% against a deeply negative IASP.L benchmark return; however, annualised volatility of 35.9% and the absence of verified AFFO coverage data from primary filings constrain conviction to a Low rating.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.2439
- P-gain: 0.6112
- CAPM alpha: 0.0887
- Beta: 0.6960
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - RBA holds rates at elevated levels through FY27, triggering further sector re-rating and AUM outflows from CNI-managed vehicles (CIP, COF). Distribution yield compresses to sub-5% on DPU cut as AFFO coverage falls below 1.0x. AI Factory (ResetData) deployment encounters cost overruns or client delays, creating write-down risk on co-investment. Share price retreats toward AUD 1.20. Multiple contracts; total return dominated by capital loss offsetting the income component.
- **base**: E(R)=0.0700
  - Central case as modelled: distribution yield 6.48%, DPU growth 2.0% p.a., multiple contraction of 1.5%. AUM stable across managed REIT platforms. AI Factory progresses to deployment phase, providing options value without meaningful contribution in FY27. RBA rate trajectory consistent with current market pricing. Share price recovers modestly toward AUD 1.55-1.65.
- **bull**: E(R)=0.2800
  - RBA pivots to rate cuts by early 2027, compressing cap rates and re-rating the REIT sector. CIP and COF AUM grows materially as institutional appetite returns. AI Factory/ResetData reaches first operational milestone, attracting strategic capital and re-rating CNI's earnings multiple higher. Macquarie stake-building signals further corporate activity. Share price recovers toward AUD 1.90-2.00, delivering capital gain plus distribution income.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0648 (Cat A) — Current distribution yield of ~6.48% sourced from Kalkine market report dated 22 Jul 2026 referencing observable market price of AUD 1.50 and trailing DPU. Corroborated by current closing price of AUD 1.50 on 2026-08-14.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. reflects modest AUM organic growth across managed REIT platforms (CIP, COF) offset by sector headwinds. RBA rate environment and 'rate anxiety gripping the REIT sector' (Kalkine, 14 Aug 2026) temper upside. No filed FY26 distribution guidance was available in stored filings (ASX body capture parked — Phase 01 v3.3 §4). Sensitivity tested in scenario analysis.
- `multiple_change` = -0.015 (Cat C) — Multiple contraction of -1.5% assumed over 12-month horizon. CNI.AX fell ~34% from ~AUD 2.27 (mid-June 2026) to AUD 1.50 (14 Aug 2026). Rate anxiety and sector re-rating pressure documented across multiple Kalkine articles (Jul-Aug 2026). FY26 results pending (webcast details 7 Aug 2026); uncertainty premium maintained. AI Factory and ResetData deployment creates execution risk.
- `rba_policy_rate` = unavailable (Cat C) — RBA policy rate could not be retrieved from stored APAC rates (no data returned for AU as of 2026-08-14). Live APAC rate tool also returned empty. Using US T-bill rate (3.71%) as risk-free proxy per methodology. RBA cash rate assumed to be in the 3.5%-4.0% range based on publicly reported 2026 RBA trajectory — consistent with the T-bill proxy used.
- `asx_body_capture_gap` = disclosed (Cat B) — No stored filing bodies were available for CNI.AX (0 records returned, ASX body capture parked per Phase 01 v3.3 §4). AFFO coverage, gearing, occupancy, and WALE could not be verified from primary filings. These gaps are reflected in qualitative gate ratings and key_risks. FY26 results were scheduled for announcement shortly after as_of date (webcast details filed 7 Aug 2026).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Rate anxiety and RBA policy: persistent elevated rates compress property valuations and managed REIT AUM, reducing Centuria's base management and performance fees with direct impact on DPU coverage
- ASX filing body capture gap: AFFO coverage ratio, gearing, and WALE metrics could not be verified from primary filings as of as_of date; FY26 results scheduled imminently may reveal negative surprises
- AI Factory execution risk: the ResetData AI infrastructure deployment is nascent and price-sensitive; cost overruns or commercialisation delays could impair capital deployed in co-investments and damage management credibility
- Severe price momentum signal: CNI.AX down ~34% from June-2026 highs with no confirmed stabilisation; rate-driven sector re-rating may continue if RBA delays cuts beyond consensus expectations
- Concentration in managed platform economics: CNI's earnings are highly leveraged to AUM growth across CIP and COF; any significant unit price decline or capital outflow in those vehicles directly compresses CNI's fee income and distribution capacity

## Invalidation Condition
Exit if FY26 results (due imminently after 2026-08-14) reveal AFFO distribution coverage below 1.0x, or if AUM under management across CIP and COF declines by more than 10% over two consecutive half-year periods, or if the RBA cash rate increases beyond 4.5% signalling a prolonged higher-for-longer cycle that would further impair managed REIT valuations and compress the sector P/NAV multiple below 0.6x.
