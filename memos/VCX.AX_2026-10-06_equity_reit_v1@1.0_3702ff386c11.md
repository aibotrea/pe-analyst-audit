# Specialist Memo — VCX.AX

**Memo ID**: `VCX.AX_2026-10-06_equity_reit_v1@1.0_3702ff386c11`
**Ticker**: VCX.AX (Vicinity Centres)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-10-06
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Vicinity Centres is Australia's second-largest retail REIT with a premium portfolio anchored by Chadstone (50% stake), offering a distribution yield of approximately 5.2% at the current AUD 2.29 price. The CAPM alpha of 8.5% (Category B, subject to AUD/GBP currency basis noise) suggests meaningful excess return relative to the IASP.L benchmark, which has itself returned -5.2% p.a. over five years. However, the OU Monte Carlo PGain of 66.2% and annualised volatility of 21.4% reflect elevated near-term uncertainty, driven by the RBA holding at 4.35% and the stock's ~15.8% drawdown between July and October 2026. The internally-managed structure eliminates fee-alignment risk, but the absence of a sponsor pipeline limits near-term accretive acquisition optionality, supporting a low conviction score pending evidence of earnings stabilisation.

## Quantitative Chain

- E(R): 0.0615
- Std dev: 0.1454
- P-gain: 0.6622
- CAPM alpha: 0.0851
- Beta: 0.6895
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - RBA raises cash rate to 5.0%+ triggering cap rate expansion of 50–75bps; occupancy falls to 94% at sub-regional assets; DPU cut by 8–10%; Australian household consumption contracts sharply under mortgage stress; multiple contraction of -8%; stock re-rates to AUD 1.90–2.00. This pathway also captures a broader rate-shock scenario where global risk-free rates surge and APAC REIT valuations de-rate in parallel.
- **base**: E(R)=0.0610
  - Central case as modelled: DPU growth 1.5%, distribution yield ~5.15%, mild cap rate drag -0.5%, RBA on hold at 4.35%, occupancy stable at ~99% for premium assets, no material acquisitions or disposals.
- **bull**: E(R)=0.2200
  - RBA cuts cash rate by 50–75bps to ~3.6–3.85% driving cap rate compression and NAV uplift; specialty retail spending recovers strongly boosting rental reversion; DPU growth accelerates to 3–4%; premium assets re-rate toward pre-2024 multiples; stock recovers toward AUD 2.65–2.75.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0515 (Cat A) — Estimated trailing DPU of AUD 0.118 per security (mid-point of FY2026 guidance range based on publicly available prior-period actuals of 11.4–11.7 cents and modest organic growth) divided by observed closing price of AUD 2.29 on 2026-10-06. Price is Category A (observed market close); DPU estimate is Category B derived from published filings.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumes modest specialty retail rental reversion and stable occupancy (~99% in premium centres), partially offset by higher interest cost from elevated RBA cash rate (4.35% as of 2026-09-24 per BIS). No material acquisition pipeline assumed given internalised management structure. Sensitivity: bull +1.5pp, bear -2.0pp.
- `multiple_change` = -0.005 (Cat C) — Mild cap rate expansion assumption (-0.5% multiple drag) reflecting Australian risk-free rates remaining elevated (RBA 4.35%). Retail sector re-rating risk is real given the ~15.8% price decline Jul-Oct 2026. Sensitivity: bull +1.0%, bear -3.0%.
- `rba_policy_rate` = 0.0435 (Cat A) — RBA cash rate 4.35% per BIS WS_CBPOL series, observation date 2026-09-24 (age 12 days at as_of). Directly influences Australian property cap rates and REIT funding costs.
- `gearing_estimate` = 0.27 (Cat B) — Estimated balance sheet gearing of ~27%, derived from VCX's historically disclosed gearing range of 25–30% (well within Australian REIT convention of <40%). No current filing body available to verify exact figure at as_of; cross-contaminated stored filings precluded extraction. Gap disclosed in key_risks.
- `management_structure` = internally_managed (Cat A) — VCX internalised management in 2022, eliminating external manager fee drag and conflicts of interest. No traditional sponsor pipeline exists; management incentives aligned with securityholder outcomes.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- RBA higher-for-longer rate environment (4.35% cash rate) compressing retail REIT cap rate spreads and suppressing NAV; any further rate increases would accelerate multiple contraction beyond the -0.5% base assumption
- Retail spending softness driven by Australian household consumption weakness amid mortgage cost pressures, threatening specialty retailer lease renewals and DPU coverage sustainability
- Concentrated exposure to physical retail formats — e-commerce structural headwinds remain, and any deterioration in foot-traffic metrics at sub-regional assets could drive occupancy below 95%
- Filing body cross-contamination in stored data pipeline means exact current gearing, AFFO coverage, and FY2026 DPU have not been independently verified from VCX source documents at as_of; estimates carry elevated Category B/C uncertainty
- Benchmark IASP.L five-year annualised return of -5.25% signals persistent negative sentiment for APAC-listed REITs; a risk-off rotation could amplify VCX's already elevated beta-adjusted drawdown risk

## Invalidation Condition
Exit position if VCX reports occupancy falling below 95% for two consecutive half-year periods, or DPU coverage drops below 0.95x AFFO for two consecutive reporting periods, or gearing breaches 35% of total assets, or the RBA raises the cash rate above 5.0% signalling a sustained higher-for-longer regime materially beyond the current 4.35% base.
