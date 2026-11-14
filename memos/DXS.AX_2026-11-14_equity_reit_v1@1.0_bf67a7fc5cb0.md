# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-11-14_equity_reit_v1@1.0_bf67a7fc5cb0`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified/Office
**As of**: 2026-11-14
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Dexus is a large Australian office-led diversified REIT trading at AUD 6.00 with an estimated ~6% distribution yield, about 190bp above the US 3M T-bill used as Rf. The 12-month OU Monte Carlo gives a simulated return of 6.4% with a 14.2% standard deviation, which implies a PGain of 67%. Beta of 0.56 versus IASP.L (currency-basis caveat applies) and a negative trailing benchmark return make CAPM alpha of 7.1% look flattering, so I rely mainly on PGain. Ongoing buy-backs and strategic actions are supportive. Office fundamentals, FY27 trading headwinds and the lack of filing-verified fundamentals cap conviction at Moderate.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1420
- P-gain: 0.6748
- CAPM alpha: 0.0707
- Beta: 0.5578
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or higher-for-longer rate path pushes office cap rates out 50bps or more. Office occupancy weakens and incentives rise. Distributions are cut about 5-8% as coverage falls below 1.0x AFFO. Asset sales are forced at a discount to book value and the strategic review fails to close the NAV discount.
- **base**: E(R)=0.0650
  - Central case as built in the chain: ~6.0% yield, +0.5% DPU growth, no multiple change. Cap rates are flat, gearing stays within the sub-40% convention, and the buy-back continues modestly.
- **bull**: E(R)=0.2000
  - RBA easing and tighter cap rates lift valuations. Strategic actions, such as capital partnerships and asset recycling at or above book, plus the buy-back, narrow the NAV discount by 10-15%. Office leasing recovers and distributions grow 3%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `price` = 6.0 (Cat A) — DXS.AX closing price AUD 6.00 on 2026-11-13 from get_price.
- `distribution_yield` = 0.06 (Cat B) — Approximate forward distribution of ~36 cents per security divided by AUD 6.00. The distribution figure comes from my recollection of recent Dexus guidance. I could not verify it against a filing, because the stored DXS filings returned bodies from unrelated issuers. Treat it as an estimate and verify it against the FY26 results.
- `dpu_growth` = 0.005 (Cat C) — Assumes roughly flat distributions with +0.5% organic growth from office rent reversion and development completions. This is offset by funding costs and the FY27 trading headwinds noted in the August 2026 press coverage. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No re-rating assumed. Any discount-to-NAV closure from the ongoing on-market buy-back (ASX notifications Oct-Nov 2026) is treated as upside in the bull case, not in the base case.
- `risk_free_rate` = 0.0414 (Cat A) — US 3M T-bill (DTB3) of 4.14% on 2026-11-12. This is a USD rate used as the CAPM risk-free input per the methodology, not an AUD rate.
- `expected_market_return` = -0.0431 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return (1260-day lookback). It is GBP-denominated, so it absorbs FX noise. The negative market return makes CAPM alpha look mechanically high.
- `filing_body_gap` = disclosed (Cat B) — Stored DXS.AX filing bodies (get_stored_filings, 2026-10-28 to 2026-11-09) contained text from other issuers (GWA, KME, Noumi and others) and no Dexus fundamentals. No filing-sourced facts are used. Gearing, coverage and occupancy are not verified from filings.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Office valuation risk: higher-for-longer rates or cap rate expansion could force write-downs and push gearing up.
- Distribution cut risk if AFFO coverage falls below 1.0x because of leasing incentives, vacancy or higher refinancing costs. FY27 guidance already points to trading headwinds.
- Fundamental data gap: stored filing bodies were unrelated to Dexus, so yield, gearing, coverage and occupancy are unverified estimates.
- Currency-basis and benchmark noise: the GBP-denominated IASP.L gives a low correlation of 0.32 and a negative 5-year return, so beta and CAPM alpha are unreliable.
- Strategic-review execution risk: asset sales or partnerships at a discount to book could destroy NAV and dilute earnings.

## Invalidation Condition
Exit if Dexus cuts distributions below roughly 34 cents per security, or if reported AFFO coverage falls below 1.0x for two consecutive halves. Also exit if aggregate gearing moves above 40%, if office occupancy drops materially below current levels, or if strategic-review asset sales crystallise losses of more than 10% against book value. Any of these would undermine the yield-based thesis and the assumed flat-to-slightly-growing distribution path.
