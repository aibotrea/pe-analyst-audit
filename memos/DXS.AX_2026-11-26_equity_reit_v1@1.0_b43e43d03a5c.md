# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-11-26_equity_reit_v1@1.0_b43e43d03a5c`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified/Office
**As of**: 2026-11-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
DXS offers an ~8% forward distribution yield, about 380bps above the 4.18% T-bill, and the 12-month OU Monte Carlo gives a 6.4% expected return. PGain is 67% with a wide 14.6% dispersion. The beta of 0.54 versus IASP.L (currency-basis caveat applies) and the negative trailing benchmark return flatter CAPM alpha of 6.8%, so alpha is weak evidence. Management signals lower FY27 earnings while holding distributions, which points to a payout above what recurring cash earnings cover. An interim CFO appointment on the analysis date adds governance uncertainty, and I could not verify gearing or NTA from filings. I therefore apply a one-step conviction reduction to a Low rating with a small position size.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1458
- P-gain: 0.6705
- CAPM alpha: 0.0676
- Beta: 0.5402
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation-style rate shock: RBA and long-end yields rise, office cap rates expand 50bps and valuations fall about 5%. FFO declines more than guided, the distribution is cut about 10% to restore coverage, and the yield falls to ~7%. A weaker multiple and negative growth outweigh the yield.
- **base**: E(R)=0.0650
  - Central case as built in the chain: ~8.0% yield, -1.5% growth from lower FY27 earnings, no multiple change, and distributions held near current levels.
- **bull**: E(R)=0.1700
  - Office valuations stabilise and rates ease, narrowing the discount to NTA by about 8%. Capital recycling and the buy-back are accretive, and FFO surprises positively so the distribution is maintained with improved coverage.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_price` = 5.99 (Cat A) — DXS.AX closing price AUD 5.99 on 2026-11-26 from get_price.
- `distribution_yield` = 0.08 (Cat B) — Forward cash distribution of ~48c per security divided by AUD 5.99 price. The 'steady distributions' headlines (Kalkine 2026-09-15 and 2026-11-04) indicate guidance is held. I could not retrieve the filed FY26 result. The DPS level is my estimate from prior published guidance, not a verified current filing.
- `earnings_growth` = -0.015 (Cat C) — Kalkine 2026-11-04 headline says Dexus expects lower FY27 earnings. I assume a -1.5% annual drag on distributable value, from FFO decline and a refocus on core property. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating or de-rating assumed. I could not verify NTA or the discount to NTA from retrieved data, so no credit is taken for discount narrowing.
- `expected_return_build` = 0.065 (Cat C) — E(R) = yield 8.0% + growth -1.5% + multiple change 0.0% = 6.5%. The yield is Category B and the growth and multiple components are Category C.
- `risk_free_rate` = 0.0418 (Cat A) — FRED DTB3 3-month US T-bill 4.18% on 2026-11-24 via get_tbill_rate. This is a USD rate used as the model risk-free rate for an AUD asset.
- `expected_market_return` = -0.0404 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (GBP-denominated), 1,305 observations, from calculate_benchmark_return. The return is negative, which flatters CAPM alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_gap` = disclosed (Cat B) — ASX body capture is parked. The stored DXS.AX filing bodies returned in this session (2026-10-28 to 2026-11-26) contained text from unrelated issuers (e.g. Sovereign Metals, Papyrus, GWA). They were disregarded as mis-attributed. Fundamentals such as gearing, AFFO coverage, occupancy and WALE could not be sourced from issuer filings.
- `interim_cfo_event` = Appointment of Interim CFO (Cat A) — DXS ASX announcement dated 2026-11-26 headline 'Appointment of Interim CFO'. Body unavailable, so the reason for the change is unknown. Treated as a governance flag.
- `buyback_active` = disclosed (Cat A) — DXS ASX 'Update - Notification of buy-back' announcements dated 2026-10-29, 2026-11-08 and 2026-11-09 show an on-market buy-back is active. Bodies were unavailable or mis-attributed, so size and pace are unverified.

## Key Risks
- Distribution sustainability: lower FY27 earnings with steady DPS implies a payout above AFFO. A distribution cut would hit both income and the share price.
- Office cap-rate expansion or a higher-for-longer Australian rate path would erode NTA and the multiple.
- Governance and execution: the interim CFO appointment on 2026-11-26 and the active buy-back create uncertainty over reporting continuity and capital allocation. The reason for the CFO change is undisclosed.
- Data limitations: ASX filing bodies were unavailable or mis-attributed, so gearing, AFFO coverage, occupancy and WALE are unverified. The qualitative gates are therefore mostly 'info'.
- Beta and the market return are measured against GBP-denominated IASP.L (currency basis), and the benchmark's negative 5-year return inflates alpha. Rf is a USD T-bill rate applied to an AUD asset.

## Invalidation Condition
Exit if Dexus cuts its distribution guidance or reports AFFO payout persistently above 110% for two consecutive half-years. Also exit if gearing rises above roughly 40%, if office occupancy falls materially below current levels with further portfolio devaluations of 5% or more, or if the interim CFO change proves linked to an earnings restatement or accounting issue.

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
