# Specialist Memo — ABG.AX

**Memo ID**: `ABG.AX_2026-11-05_equity_reit_v1@1.0_e7721ec90e73`
**Ticker**: ABG.AX (Abacus Group)
**Market**: Australia
**Sector**: Office/Commercial
**As of**: 2026-11-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
ABG is an ASX-listed commercial REIT that has reset its payout, cut costs and agreed to sell its Storage King stake, and now trades at 0.86 AUD. An assumed forward yield of about 7% plus a small re-rating gives an E(R) of 8%, compared with a 4.03% T-bill. Beta is 0.56 against IASP.L (currency-basis caveat applies), but volatility is high at 24%. The OU Monte Carlo gives a PGain of 68%, which is moderate. I applied a one-step downward gate on distribution coverage because I could not verify DPS, AFFO coverage or gearing, and because the payout was recently cut. That gives low conviction and a small position.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1649
- P-gain: 0.6846
- CAPM alpha: 0.0855
- Beta: 0.5608
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - A stagflation or higher-for-longer rate pathway pushes AU cap rates out by 50bps or more and office valuations fall. Occupancy declines and the distribution is cut again, so yield falls to about 5%. The multiple de-rates by 15% or more, and the Storage King proceeds do not offset the NTA decline.
- **base**: E(R)=0.0800
  - Central case as built in the chain: yield of about 7.0% on a reset payout, flat growth, and a 1% re-rating. Gearing stays in range and occupancy is broadly stable.
- **bull**: E(R)=0.2200
  - RBA easing compresses cap rates, and Storage King proceeds are used for debt reduction and buybacks. The distribution is covered at a comfortable FFO payout, and the stock re-rates 10% or more toward NTA.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 0.86 (Cat A) — ABG.AX last close 2026-11-05 in AUD from get_price.
- `distribution_yield` = 0.07 (Cat C) — I could not retrieve the exact FY26 or FY27 DPS. The ASX filing bodies returned for ABG.AX were mismatched documents from other issuers, so I ignored them. Headlines from Investing.com (2026-08-24) and Kalkine (2026-08-03) say the FY26 results reset and cut the payout while holding the distribution. I assumed a forward yield of about 7.0%, equal to roughly 6.0c DPS on 0.86 AUD. Sensitivity: each 1pt change in yield moves E(R) by 1pt.
- `dpu_growth_12m` = 0.0 (Cat C) — I assumed flat distribution and NTA growth over 12 months. The company has cut costs and is refocusing on commercial property, with offsetting office valuation and rate risk. The Storage King stake sale (reported at about A$284m, Capital Brief 2026-09-18) is assumed to be neutral to the distribution after debt paydown.
- `multiple_change` = 0.01 (Cat C) — I assumed a modest 1% re-rating, based on a likely discount to NTA and a stronger balance sheet after the Storage King proceeds. NTA was not verified. Sensitivity is shown in the bear and bull cases.
- `expected_return_build` = 0.08 (Cat C) — E(R) = 7.0% yield + 0.0% growth + 1.0% multiple change = 8.0%. The components are C, C and C.
- `risk_free_rate` = 0.0403 (Cat A) — FRED DTB3 3-month T-bill 4.03% on 2026-11-04. It is a USD rate used as a proxy and is not AUD-matched.
- `expected_market_return` = -0.0414 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return, in GBP terms. It absorbs currency effects.
- `historical_volatility` = 0.2426 (Cat B) — Annualised volatility from 252 days of stored daily prices (262 observations).
- `beta` = 0.5608 (Cat B) — 252-day beta against IASP.L. Correlation is low at 0.277, so the estimate is statistically weak.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `leverage_data_gap` = not_verified (Cat C) — I could not retrieve gearing, ICR, AFFO coverage or NTA from the filings or news available. I assumed gearing is within the AU convention of below 40% after the Storage King sale proceeds. This is unverified.

## Key Risks
- Distribution inputs (DPS, AFFO coverage, gearing, NTA) were not verified from the filings available. The yield assumption is Category C, and if the actual yield is lower, E(R) and PGain are overstated.
- Office and commercial valuation risk if AU cap rates widen, with higher-for-longer rates and a stagflation pathway the main drivers.
- Execution risk on the Storage King stake sale, on use of proceeds, and on the managing director succession and strategy refocus.
- The beta is statistically weak, with correlation of 0.28 against a GBP-denominated benchmark. The 5-year benchmark return is negative (-4.1%), so CAPM alpha is inflated and unreliable.
- The risk-free rate is a USD T-bill proxy rather than an AUD rate. The OU Monte Carlo with 24% volatility gives a wide outcome range (std dev about 16.5%).

## Invalidation Condition
Exit if a further distribution cut takes the forward yield below about 5.5%, if reported AFFO or FFO payout coverage falls below 1.0x, or if gearing rises above 40% because the Storage King sale fails to complete or its proceeds are not applied to debt reduction. Also exit if office valuation write-downs push NTA down more than 10% or occupancy deteriorates materially.
