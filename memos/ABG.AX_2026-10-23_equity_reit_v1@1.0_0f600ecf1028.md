# Specialist Memo — ABG.AX

**Memo ID**: `ABG.AX_2026-10-23_equity_reit_v1@1.0_0f600ecf1028`
**Ticker**: ABG.AX (Abacus Group)
**Market**: Australia
**Sector**: Office/Diversified Commercial
**As of**: 2026-10-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
ABG is a de-rated Australian commercial REIT that is moving to a focused office and commercial strategy after its Storage King transaction. It trades at a large discount to NTA, and its unit price is down about 28% over 11 months. The assumed yield of about 9% (unverified) sits well above the 4.04% T-bill, and the OU Monte Carlo gives a 12-month expected return of 6.9% and a PGain of 66.5%. Beta of 0.58 against IASP.L is low, but correlation is only 0.28 and the currency-basis caveat applies. Annualised volatility of 23.9% is high for a REIT, and the persistent price decline suggests the market doubts distribution coverage and balance-sheet quality. The numeric chain would support a score of 3, which I cut one step because key balance-sheet and coverage data could not be verified. The result is Low conviction with a small position.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1625
- P-gain: 0.6650
- CAPM alpha: 0.0797
- Beta: 0.5785
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - Distribution is rebased 20-25% because AFFO coverage falls below 1.0x. Office valuations soften with 25-50bp of cap-rate expansion, and gearing moves above the 40% convention as covenants tighten. A stagflation or higher-for-longer rate path widens the discount to NTA, and the unit price falls about 25% against a roughly 7% yield.
- **base**: E(R)=0.0700
  - Central case as built in the chain: yield about 9%, distribution drift of -2%, no multiple change. Valuations stay flat, refinancing is manageable and the distribution is broadly held.
- **bull**: E(R)=0.2800
  - Asset sales and the Storage King transaction proceeds cut debt and lift sentiment. Distribution is maintained with coverage at or above 1.0x, and rate cuts or cap-rate compression narrow the discount to NTA by about 15-20%, adding to the yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `closing_price` = 0.805 (Cat A) — ABG.AX last close AUD 0.805 on 2026-10-23 (get_price). The price is down about 28% from about AUD 1.11 in Nov-2025 (get_history monthly closes).
- `distribution_yield` = 0.09 (Cat C) — I could not retrieve the published FY26 DPS or the FY27 guidance through the tools. News headlines (Kalkine, Aug-2026) say ABG held its distribution at the FY26 result. The 9.0% yield assumes a DPS of about 7.2-7.5c on the AUD 0.805 price. The yield is an unverified estimate, not an observed figure. Sensitivity: each 1c of DPS is about 1.2pts of yield.
- `dpu_growth` = -0.02 (Cat C) — I assume a 2% annual drag on distributions. The drivers are refinancing at higher rates, a soft office-market backdrop, the loss of income from asset recycling, and the 'cost cuts' narrative in the Aug-2026 headlines. Sensitivity is tested in the bear and bull cases.
- `multiple_change` = 0.0 (Cat C) — I assume no re-rating or de-rating over 12 months. Headlines say ABG trades at a large discount to NTA, but I did not verify the NTA figure and I give no credit for closing the discount. I treat that as bull-case upside only.
- `expected_return_build` = 0.07 (Cat C) — E(R) = yield 9.0% + growth -2.0% + multiple change 0.0% = 7.0%. Each component is classified above.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill at 4.04% on 2026-10-22 (get_tbill_rate). The rate is USD-based and is applied to an AUD asset as a framework convention.
- `expected_market_return` = -0.046292 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (1260-day lookback). The benchmark is GBP-denominated, so the return absorbs FX co-movement. A negative Rm inflates CAPM alpha mechanically.
- `historical_volatility` = 0.239039 (Cat B) — Annualised volatility from 262 observations over a 252-day lookback (calculate_historical_volatility).
- `filing_data_gap` = disclosed (Cat B) — The stored filings returned for ABG.AX (2026-10-09 to 2026-10-23) have bodies that belong to other issuers (Antilles Gold, IVE Group, Metallium, a securitisation note deed). They carry no ABG financial data and were disregarded. Gearing, AFFO coverage, NTA, occupancy and WALE were not verified from filings. The affected gates are marked info and a one-step precautionary override is applied.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Distribution coverage and balance-sheet metrics (gearing, AFFO cover, NTA, ICR) were not verified from ABG filings, because the stored filing bodies belonged to other issuers. The yield input is an unverified Category C estimate.
- Office-sector valuation and cap-rate risk under higher-for-longer rates, with a downtrend in the units (-28% over 11 months) and volume rising on declines, which signals persistent selling pressure.
- A distribution rebase or covenant pressure if AFFO coverage falls below 1.0x. Execution risk on asset recycling and on the roughly AUD 340m Storage King decision.
- Currency-basis noise: IASP.L is GBP-denominated, correlation is only 0.28, and the negative 5-year benchmark return (-4.6%) inflates CAPM alpha mechanically. Alpha is a weak supporting input.
- Management succession and governance changes, and the high volatility of 23.9%, which give a wide outcome range (OU std dev 16.2%). The OU simulation is a directional signal, not a formal backtest.

## Invalidation Condition
Exit if ABG cuts its distribution below the FY26 level, or if reported AFFO coverage falls below 1.0x for two consecutive half-year reporting periods. Also exit if gearing rises above 40% or covenant headroom tightens materially, or if office valuation write-downs push NTA down by more than 10% while the unit price keeps making new lows below AUD 0.775. Any of these would show that the thesis of a held distribution and a discount to NTA that can narrow no longer applies.
