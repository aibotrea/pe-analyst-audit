# Specialist Memo — SKG.AX

**Memo ID**: `SKG.AX_2026-11-05_equity_reit_v1@1.0_01eb06ec25ea`
**Ticker**: SKG.AX (Storage King Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-11-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Storage King Group is an internalised ASX-listed self-storage platform, formerly Abacus Storage King. Its price is AUD 1.14, and its assumed 6.5% yield plus 2% growth gives a modelled 12-month E(R) of about 8.5%. The OU Monte Carlo gives a PGain of about 70% with a standard deviation of about 16%. That produces a base conviction of 3, and the data gaps lower it to 2. A beta of 0.62 versus IASP.L (currency-basis caveat applies) and a weak correlation of 0.31 mean CAPM alpha is of limited use, especially with a negative trailing benchmark return. The new 19.6% holder Ki Corporation adds takeover optionality that the base case does not capture, but SKG-specific distribution, gearing and coverage figures could not be verified.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1643
- P-gain: 0.6959
- CAPM alpha: 0.0950
- Beta: 0.6156
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation or rate-shock pathway: RBA tightens further from 4.6% and AU cap rates expand by about 50bps. Self-storage rent growth stalls (0% DPU growth) and internalised costs weigh on earnings. Distribution coverage falls below 1.0x and the yield is cut to about 5.5%. A takeover bid does not emerge and the Ki Corporation overhang fades. Security de-rates by about 15%.
- **base**: E(R)=0.0850
  - Central case as built in the chain: 6.5% yield, 2.0% distribution growth and no multiple change. Cap rates are flat, occupancy is stable and the internalised platform delivers its stated cost savings.
- **bull**: E(R)=0.2400
  - Ki Corporation or another strategic bidder drives a control premium or re-rating of about 10-12%. Distribution growth of about 4% from rate growth and new-build or acquisition contributions. Yield holds at 6.5% and RBA easing compresses cap rates.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `last_close_price` = 1.14 (Cat A) — SKG.AX closing price of AUD 1.14 on 2026-11-05 from the live price tool; consistent with stored price history.
- `distribution_yield` = 0.065 (Cat C) — Forward cash distribution yield assumed at 6.5% of price. No usable SKG-specific DPU, FFO/AFFO or gearing filing was available. The stored ASX filing bodies tagged to SKG.AX were for unrelated issuers (energyone, Nyrada, Nanosonics, CuFe, Gold Mountain, Alliance Nickel, Astral, ASX Ltd) and were discarded. The assumption is anchored on the sector's yield range and the internalisation and rebrand reported in news (Inside Self-Storage 2026-05-27, Kalkine 2026-08-14). Sensitivity: each +/-100bps of yield moves E(R) by the same amount. Needs verification against the FY26 results.
- `dpu_growth` = 0.02 (Cat C) — Assumed 2.0% annual growth in distributable earnings per security. This is about CPI-linked rent growth less internalised-platform cost drag. It is an assumption beyond any published consensus. Sensitivity: tested in the bear case (0%) and bull case (about 4%).
- `multiple_change` = 0.0 (Cat C) — Zero net re-rating assumed over 12 months. The unquantified takeover or strategic-interest optionality is not included in the base case. Ki Corporation (the Kirsh vehicle) bought Abacus Group's 19.6% stake for about A$285m in Sep 2026 (Capital Brief and IPE Real Assets, 2026-09-18). The bull case captures that optionality.
- `expected_return_build` = 0.085 (Cat C) — E(R) = 6.5% yield + 2.0% growth + 0.0% multiple change = 8.5%. It is a Category C composite because all three components are assumptions.
- `historical_volatility` = 0.2418 (Cat B) — Annualised volatility from 252-day stored daily prices (262 observations) as of 2026-11-05. The window is short for a security that was recently rebranded and internalised, and it includes the heavy index-related volume on 2026-09-18 (about 132m shares).
- `risk_free_rate` = 0.0403 (Cat A) — FRED DTB3 3-month T-bill rate of 4.03% on 2026-11-04. It is a USD rate used as a proxy and is not an AUD risk-free rate. The BIS RBA policy rate was 4.6% as of 2026-10-22.
- `expected_market_return` = -0.0414 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (1,260 trading days), computed by the tool. This is a backward-looking and negative figure, so it inflates CAPM alpha. Alpha is treated as a weak supporting input only.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Beta is 0.616 with a correlation of only 0.31, so the fit is weak.
- `fundamental_data_gap` = disclosed (Cat C) — No verified DPU, AFFO coverage, gearing, WALE or occupancy figures were obtained. ASX announcements for SKG are non-price-sensitive notices only (AGM notice, sustainability report, securities notifications). The qualitative gates are therefore marked info and a one-step conviction override is applied for unverifiable distribution coverage and leverage.

## Key Risks
- Fundamental data gap: no verifiable DPU, AFFO coverage, gearing or valuation data. The E(R) components are all Category C and could be materially wrong, and the stored filing bodies for SKG.AX were mis-tagged to unrelated issuers.
- Rate and cap-rate risk: the RBA policy rate is 4.6% and the 3-month T-bill is 4.03%, so a thin yield spread and further tightening could compress valuations. An inflation or stagflation regime would hit REIT multiples.
- Post-internalisation execution and governance risk: higher corporate costs, conflicts with a large new holder (Ki Corporation, 19.6%), and potential overhang or block-sale risk if the holder changes its stance.
- Currency-basis and benchmark risk: beta and alpha are measured against a GBP benchmark with a weak correlation of 0.31, and the benchmark's trailing 5-year return is negative, which flatters CAPM alpha. The 252-day volatility window is also short for a recently rebranded entity.
- Limited macro series and calibration caveat: Rf uses the USD T-bill as a proxy for an AUD-denominated security. This is a directional analysis rather than a formal backtest, and vintage discipline is not yet applied.

## Invalidation Condition
Exit if the FY26 or half-year results show distribution coverage below 1.0x AFFO or a cut to the distribution, if gearing rises above roughly 40% (the Australian convention), or if portfolio occupancy and same-store NOI growth turn negative for two consecutive reporting periods. Exit also if Ki Corporation sells down its 19.6% stake without a bid, or if the security falls more than 20% from the current AUD 1.14 on a fundamental deterioration.
