# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-07-23_equity_reit_v1@1.0_0c45c9cb8899`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-07-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
AIMS APAC REIT offers direct Singapore industrial and logistics exposure with a compelling FY2026 distribution yield of ~5.97% (DPU 9.85 cents, +2.6% y-o-y) underpinned by resilient occupancy and positive rental reversions in the Singapore business park and warehouse segment. The July 2026 announcement of a maiden Perth freehold acquisition (A$42.7M) extends geographic diversification and provides incremental DPU accretion, consistent with management's active capital-recycling strategy presented at the JP Morgan Real Assets Forum. Beta of 0.25 against IASP.L (currency-basis caveat applies) reflects a lower-volatility profile relative to the broader APAC REIT universe, while a CAPM alpha of 6.5% signals meaningful excess return above the risk-implied hurdle despite a negative 5-year benchmark return. The OU Monte Carlo PGain of 79.5% at a 12-month horizon supports above-average conviction, with E(R) of 8.5% offering a 470bp spread over the 3.75% T-bill rate.

## Quantitative Chain

- E(R): 0.0847
- Std dev: 0.1023
- P-gain: 0.7949
- CAPM alpha: 0.0652
- Beta: 0.2530
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Singapore industrial occupancy falls to 90% on weaker manufacturing and logistics demand; DPU coverage drops below 1.0x AFFO; Perth acquisition integration disrupted by AUD/SGD depreciation and single-tenant vacancy risk; MAS raises macro-prudential limits forcing deleveraging; cap rate expansion of 50bps compresses NAV by ~8%.
- **base**: E(R)=0.0840
  - Central case as built in chain: DPU growth 2.5%, distribution yield 5.97%, occupancy stable at ~93-95%, cap rates flat, Perth acquisition completes on disclosed terms at A$42.7M, gearing remains below 40%.
- **bull**: E(R)=0.1800
  - Singapore industrial rental reversions accelerate to 5%+ driven by e-commerce and supply-chain reshoring; DPU growth exceeds 4%; Perth asset stabilises above 6% yield; price-to-NAV re-rating narrows 5–8% discount; AIMS Financial Group injects additional pipeline assets at accretive yields.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0597 (Cat A) — FY2026 full-year DPU of SGD 0.0985 (reported 2.6% y-o-y growth per The Edge Singapore, 07 May 2026) divided by closing price of SGD 1.65 on 2026-07-23. Observed published number.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% p.a.: conservative relative to trailing FY2026 actual of 2.6% (H2 DPU +4.1% per Business Times, 07 May 2026). Organic rental reversions in Singapore industrial market plus incremental contribution from Perth acquisition (A$42.7M freehold, announced 09 Jul 2026). Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Assumed zero multiple change (price-to-NAV expansion/contraction) over 12-month horizon. O5RU.SI trades at broadly stable levels (SGD 1.58–1.67 range over 60-day window). Flat assumption is conservative; upside scenario allows for modest re-rating.
- `perth_acquisition` = disclosed (Cat A) — Proposed acquisition of freehold industrial properties at 398 Bushmead Road and 286 Stirling Crescent, Hazelmere, Perth WA for A$42.7M. Announced SGX filing 09 Jul 2026 (O5RU.SI ANNC). Maiden Australian industrial exposure; single-tenant concentration risk noted.
- `leverage_gearing` = 0.35 (Cat B) — Estimated aggregate leverage of approximately 35% based on AIMS APAC REIT's historical gearing range (~33–37%) and incremental debt expected from Perth acquisition. No current period balance sheet available in retrieved filings; derived from prior public disclosures and management commentary. Below MAS 45% statutory limit.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer SGD interest rates compressing the DPU yield spread versus T-bill and increasing financing costs on variable-rate debt
- Single-tenant concentration risk at the newly acquired Perth freehold site (398 Bushmead Road / 286 Stirling Crescent); tenant default or non-renewal could impair Australian DPU contribution
- AUD/SGD currency translation risk on Australian asset valuations and income, with AUD weakness reducing SGD-denominated distributions
- Singapore industrial cap rate expansion driven by global rate re-pricing compressing NAV and price-to-book multiple
- Macro data (FEDFUNDS, credit spreads) absent from stored series at this as_of date; supporting macro signals relied on live T-bill rate and trailing benchmark return only

## Invalidation Condition
Exit if portfolio occupancy falls below 91% for two consecutive quarters, or if DPU coverage drops below 1.0x AFFO in any reported period, or if aggregate leverage breaches 42% (approaching MAS 45% limit) following the Perth acquisition and subsequent debt drawdown, or if AIMS Financial Group materially reduces its sponsor pipeline commitment or sells down its unitholding below 10%.
