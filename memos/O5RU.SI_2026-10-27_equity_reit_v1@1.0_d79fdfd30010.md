# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-10-27_equity_reit_v1@1.0_d79fdfd30010`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-10-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers a high trailing distribution yield of about 7.1%, a spread of roughly 3% over the 4.05% T-bill. The yield rests on 1H FY2027 DPU of 4.908 cents, up 4% y-o-y, as reported by The Edge Singapore. The OU Monte Carlo gives a 12-month expected return of about 8.0% with PGain of 76.8% and a low beta of 0.32 (currency-basis caveat applies). The numeric chain supports conviction 4 (Above average). I apply a one-step gate override to conviction 3 (Moderate) because AFFO coverage, gearing and asset concentration could not be verified from the filing bodies available, and because CEO and CFO transitions coincide with a roughly 10% price decline since end-August.

## Quantitative Chain

- E(R): 0.0810
- Std dev: 0.1100
- P-gain: 0.7678
- CAPM alpha: 0.0675
- Beta: 0.3156
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Stagflation or higher-for-longer rate pathway. SGD and USD rates stay elevated and cap rates expand 25-50bps. AFFO coverage falls below 1.0x as refinancing costs rise, and DPU is cut about 5%. The leadership transition disrupts execution, and the yield multiple contracts a further 5%.
- **base**: E(R)=0.0810
  - Central case as built in the chain: 7.1% distribution yield, 2% DPU growth, 1% multiple contraction. Occupancy is stable, cap rates are flat, and the new CEO delivers continuity.
- **bull**: E(R)=0.1700
  - Singapore and US rates ease and the yield spread compresses, with about 5% multiple expansion. DPU growth reaches 4% on acquired-asset contributions and positive rental reversions, and refinancing is completed at lower cost via the enlarged debt programme.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 1.35 (Cat A) — SGX closing price SGD 1.35 on 2026-10-27 (get_price).
- `distribution_yield` = 0.071 (Cat B) — 1H FY2027 DPU of 4.908 cents (+4% y-o-y) per The Edge Singapore on 2026-10-15, annualised to about 9.8 cents, divided by a price of about SGD 1.35-1.37. This gives roughly 7.1-7.3%, in line with the 7.1% yield in a Longbridge note dated 2026-10-26. The yield is derived from press-reported DPU. I could not read the DPU figure in the O5RU.SI 2026-10-15 half-yearly results filing, whose body only lists attachments. The same day's distribution announcement (O5RU.SI 2026-10-15 CACT) shows a declared rate of SGD 0.0016 for 01/07/2026-30/09/2026, which I could not reconcile with the 4.908c figure because the body was truncated. I treat the headline DPU as the basis and flag the discrepancy.
- `dpu_growth` = 0.02 (Cat C) — Forward DPU growth assumption: 1H FY27 DPU growth of 4% y-o-y, haircut to 2% for a full 12 months. Reasons for the haircut are fading contributions from acquired assets, CEO/CFO transition risk, and higher refinancing cost. Sensitivity is tested in scenario_analysis.
- `multiple_change` = -0.01 (Cat C) — Assumed 1% yield-multiple contraction over 12 months. A 3-month T-bill rate of 4.05% (DTB3 2026-10-26) limits room for yield compression, and the price has fallen from about SGD 1.49 on 2026-08-31 to SGD 1.35. Sensitivity is tested in scenario_analysis.
- `expected_return_build` = 0.081 (Cat C) — E(R) = yield 7.1% (B) + DPU growth 2.0% (C) + multiple change -1.0% (C) = 8.1%.
- `risk_free_rate` = 0.0405 (Cat A) — FRED DTB3 3-month T-bill rate of 4.05% observed 2026-10-26.
- `expected_market_return` = -0.045 (Cat B) — Trailing ~5.17-year annualised log return of IASP.L (1260 trading days) is -4.5%. The figure is GBP-denominated, so it absorbs FX co-movement. A negative Rm makes the CAPM required return low, which inflates alpha.
- `management_transition` = CEO and CFO transition (Cat A) — O5RU.SI 2026-10-01 ANNC: Lim Joo Lee (previously head of finance, capital markets and investor relations) appointed CEO effective 2026-10-01. A 2026-10-01 announcement also covers CEO and CFO appointment updates. News dated 2026-07-23 reported that the prior CEO, Russell Ng, would step down.
- `debt_programme` = S$2.0bn (Cat A) — O5RU.SI 2026-09-18 ANNC: multicurrency debt issuance programme limit raised from S$750m to S$2.0bn. This adds financing flexibility. It does not by itself indicate drawn leverage.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Unverified gate inputs: filing bodies did not provide gearing, AFFO coverage, occupancy, WALE or top-asset concentration. The DPU figure comes from press reports, and the SGD 0.0016 declared-rate field was not reconciled. Gate statuses are therefore marked info.
- Leadership transition: the new CEO and the CFO changes may disrupt execution, capital management and investor confidence. The price has fallen about 10% since end-August 2026.
- Higher-for-longer rates: the 4.05% T-bill narrows the yield spread, and refinancing at higher cost or cap rate expansion would pressure DPU and NAV.
- Currency-basis and benchmark noise: IASP.L is GBP-denominated with a negative 5-year return of -4.5%, and the correlation to O5RU is only 0.24. Beta and CAPM alpha are therefore low-reliability, and alpha is likely overstated. PGain is the primary metric.
- Live-mode analysis, not point-in-time backtest: this is a directional signal with no vintage discipline. News headlines were used and could not all be verified. The 2026-10-21 price series shows a discontinuity, possibly a distribution or adjustment effect.

## Invalidation Condition
Exit if AFFO distribution coverage falls below 1.0x or DPU is cut in the next half-year result, if reported gearing rises above about 42% (approaching the 45% Singapore regulatory cap) without a credible deleveraging plan, if portfolio occupancy drops materially for two consecutive periods, or if the new management team signals a dilutive acquisition or equity raise at a deep discount to NAV.
