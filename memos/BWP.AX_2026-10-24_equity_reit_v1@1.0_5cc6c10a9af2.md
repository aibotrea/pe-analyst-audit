# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-10-24_equity_reit_v1@1.0_5cc6c10a9af2`
**Ticker**: BWP.AX (BWP Trust)
**Market**: Australia
**Sector**: Retail/Large-Format (Bunnings-anchored)
**As of**: 2026-10-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP Trust offers Australian large-format retail property exposure underpinned by Bunnings, a Wesfarmers subsidiary, and a low-gearing balance sheet. The estimated distribution yield of about 4.9% plus modest rent growth gives a 7% expected return. The OU Monte Carlo simulation gives a 12-month mean of 6.95%, a standard deviation of 9.9% and a PGain of 75.8%. Beta of 0.51 against IASP.L (currency-basis caveat applies) and 14.6% volatility indicate defensive behaviour. Conviction starts at 4 and is cut one step to 3 because of single-tenant concentration and because fundamentals could not be verified from filings.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.0992
- P-gain: 0.7584
- CAPM alpha: 0.0737
- Beta: 0.5090
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0700
  - Higher-for-longer rates, or an inflation and rate shock in the stagflation pathway, push cap rates out by 40-50bps and widen the yield to roughly 5.5%. Rent growth falls to about 1%. Bunnings lease renewals or rent resets come in weak, and valuations fall about 7%.
- **base**: E(R)=0.0700
  - Central case as built in the chain: yield about 4.9%, rent growth about 2.5%, small -0.4% multiple drift, low gearing, Bunnings tenancy stable and cap rates broadly flat.
- **bull**: E(R)=0.1700
  - RBA easing and falling bond yields compress cap rates by about 25bps, supporting a 4-5% revaluation uplift. Rent reviews run at 3.5% or more, and accretive acquisitions or developments add to DPU growth.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 3.55 (Cat A) — Latest close AUD 3.55 on 2026-10-23 from get_price.
- `distribution_yield` = 0.049 (Cat B) — Approximate trailing distribution of ~17.4c per unit divided by the AUD 3.55 price. The DPU comes from my recollection of BWP's recent distributions, not a retrieved filing. The stored ASX filings returned for this ticker were off-topic bodies from other issuers, so the figure could not be verified. Treated as a derived estimate.
- `dpu_growth` = 0.025 (Cat C) — Assumes rent growth of about 2.5%. This reflects Bunnings leases with CPI-linked or fixed reviews plus market reviews, and modest valuation-driven income growth with no major acquisitions. It is not based on consensus. Scenario analysis tests it.
- `multiple_change` = -0.004 (Cat C) — Small allowance for yield or cap-rate drift. The Australian risk-free rate is elevated (US 3M T-bill 4.04%), and BWP's yield spread to the risk-free rate is thin or negative. Sensitivity is tested in the bear case.
- `expected_return_build` = 0.07 (Cat C) — E(R) = yield 4.9% + growth 2.5% + multiple change -0.4%, rounded to 7.0%.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill at 4.04% on 2026-10-22. It is a USD rate used as a proxy for the AUD risk-free rate, which is an additional basis mismatch.
- `expected_market_return` = -0.0463 (Cat B) — IASP.L trailing 5.17-year annualised log return from calculate_benchmark_return (1260-day lookback). It is GBP-denominated and absorbs FX co-movement. The negative value makes CAPM alpha mechanically large and positive, so alpha should be read with caution.
- `leverage_gearing` = low (not verified) (Cat C) — BWP is understood to run low gearing, around 20% or below, well inside the AU <40% convention. No filing body was retrievable to confirm this. Assumption only.
- `tenant_concentration` = high (not verified) (Cat C) — BWP is understood to derive the large majority of rental income from Bunnings Warehouse, a Wesfarmers subsidiary. Wesfarmers is also a significant unitholder and the sponsor. No retrievable filing confirms current percentages.
- `filing_data_gap` = disclosed (Cat B) — The get_stored_filings results for BWP.AX contained unrelated issuer content (ALI, Korvest, Energy Action, Manuka, Syntara, Xenitra, Arena REIT, Avita). They were treated as untrusted and off-topic, and no facts were extracted. Fundamental inputs (DPU, gearing, WALE, occupancy, AFFO coverage) are therefore not sourced from filings.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Extreme single-tenant concentration in Bunnings/Wesfarmers means lease renewal terms or a change in Wesfarmers' property strategy would directly affect income and valuations.
- Thin yield spread to the 4.04% risk-free rate (USD T-bill proxy) leaves the unit price exposed to rising AU bond yields and cap-rate expansion.
- Fundamental inputs (DPU, gearing, WALE, AFFO coverage) are not verified against filings, because stored filing bodies were off-topic. The E(R) build rests on recalled figures and Category C assumptions.
- The IASP.L benchmark is GBP-denominated, so beta and the negative -4.6% trailing market return carry currency-basis noise. The resulting CAPM alpha is mechanically inflated and only a supporting input.
- Live-mode trailing statistics are a directional signal only, not a formal backtest. The 252-day volatility and beta are sensitive to the window chosen.

## Invalidation Condition
Exit if Wesfarmers/Bunnings announces material lease non-renewals, rent resets materially below passing rent, or a strategic shift away from leasing from BWP. Also exit if gearing rises above 30%, if DPU coverage falls below 1.0x for two consecutive half-years, or if a sustained rise in Australian bond yields pushes valuation yields out by more than 50bps.
