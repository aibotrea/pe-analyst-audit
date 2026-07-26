# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-07-23_equity_reit_v1@1.0_f043546bd138`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-07-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Keppel DC REIT (AJBU.SI) is Singapore's largest pure-play data centre REIT, offering investors direct exposure to secular AI and cloud-driven demand across 9 countries. The H1 2026 DPU of 5.714 cents per unit (annualised ~4.97% yield at SGD 2.30) provides a meaningful income return, supported by a high-quality sponsor in Keppel Corporation with a demonstrated pipeline of data centre assets. Beta of 0.29 versus IASP.L (currency-basis caveat applies) reflects lower volatility than the broader APAC REIT universe, and the OU Monte Carlo simulation yields a PGain of 78.6% over a 12-month horizon. CAPM alpha of 5.75% versus the negative benchmark return environment further supports above-average conviction, with E(R) of ~7.47% underpinned by a resilient income base and modest growth assumptions.

## Quantitative Chain

- E(R): 0.0747
- Std dev: 0.0936
- P-gain: 0.7863
- CAPM alpha: 0.0575
- Beta: 0.2858
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - DPU growth stalls at 0% as data centre oversupply emerges in key European markets, occupancy slips to 90-92%, cap rates expand 50bps on higher-for-longer global rates, gearing approaches 42-44% requiring dilutive equity raise; SGD/EUR FX headwinds further compress income. Bear case also captures potential rate-shock scenario where MAS tightening compresses yield spread.
- **base**: E(R)=0.0747
  - Central case as built in quantitative chain: H1 2026 DPU of 5.714c annualised at 11.428c, yield of 4.97%, DPU growth 2.5%, cap rates flat, occupancy stable above 95%, gearing within 36-40% range, SGD broadly stable.
- **bull**: E(R)=0.1800
  - AI-driven data centre demand accelerates, Keppel Corporation injects accretive pipeline assets at 6%+ NPI yield, DPU growth reaches 5%, occupancy pushes to 98%+, multiple re-rates as investors price in scarcity premium for high-quality APAC data centre assets, gearing reduced via asset recycling.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0497 (Cat A) — H1 2026 DPU of 5.714 cents per unit (taxable 4.838c + tax-exempt 0.358c + capital 0.518c) declared in AJBU.SI 2026-07-23 CACT filing. Annualised DPU of 11.428c divided by SGD 2.30 closing price = 4.97% trailing yield. Capital distribution component (0.518c per half) noted but included in full yield for E(R) building purposes.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% per annum assumed, reflecting structural demand for data centre space driven by AI workloads and cloud adoption in APAC, partially offset by FX headwinds from European and multi-market assets, and higher financing costs in a sticky-rate environment. Sensitivity tested in scenario analysis: 0% in bear, 2.5% in base, 5.0% in bull.
- `multiple_expansion` = 0.0 (Cat C) — Neutral multiple change assumed. Keppel DC REIT trades near estimated NAV; no material re-rating catalyst or de-rating risk incorporated at the base case. Sensitivity tested across scenarios.
- `leverage_gearing` = ~36-38% (Cat B) — Estimated gearing based on Keppel DC REIT's publicly reported historical range. Full 1H 2026 financial statements filed 2026-07-23 (AJBU.SI ANNC: Half Yearly Results) but detailed leverage ratio not captured in available filing body. Gearing estimated below Singapore MAS 50% regulatory limit.
- `capital_distribution_component` = 0.00518 (Cat A) — Capital distribution of 0.518 cents per unit for H1 2026 period from AJBU.SI 2026-07-23 CACT filing. Represents return of capital, not income; included in total DPU but noted as a coverage risk factor.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input due to currency basis noise inherent in comparing a SGD-denominated REIT against a GBP IASP index. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer global interest rates increasing financing costs on debt refinancing and compressing the yield spread versus the 3.75% T-bill rate
- Capital distribution component (0.518c/unit per half-year) in H1 2026 DPU indicates partial return-of-capital funding of distributions, which may signal income coverage pressure if unaddressed
- Foreign exchange headwinds: multi-currency income from European and Asian data centres creates SGD translation risk that can erode DPU when SGD strengthens
- Data centre oversupply risk in key markets (Frankfurt, Amsterdam, Dublin) as hyperscaler capex drives new supply, potentially compressing rental rates on lease renewals
- Concentration risk: Singapore assets represent a significant share of portfolio value; any regulatory changes to data centre development in Singapore could disproportionately impact NAV

## Invalidation Condition
Exit position if annualised DPU falls below SGD 0.10 per unit (implying a greater than 12% DPU cut from the H1 2026 run-rate of 11.428 cents annualised), or if aggregate leverage ratio breaches 42% for two consecutive reporting periods signalling elevated refinancing risk, or if Keppel Corporation formally reduces or withdraws its pipeline commitment to AJBU.SI, or if portfolio occupancy falls below 90% for two consecutive quarters.
