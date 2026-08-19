# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-19_equity_reit_v1@1.0_dd1a8ddeaba1`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-19
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT offers USD-denominated data centre exposure on the SGX, benefiting from AI-driven hyperscaler demand and a credible global sponsor in Digital Realty Trust. The H1 2026 distribution of 1.80 US cents (annualised yield ~6.9% at the current USD 0.52 price) provides an income buffer, though nearly half of the distribution is classified as capital return rather than income, which constrains AFFO coverage sustainability. A transformative portfolio transaction announced on 12 August 2026 — disposing of approximately US$315.9M of North American assets and pivoting into the Singapore data centre market — introduces meaningful near-term execution risk that limits conviction. With a PGain of 68.7%, a CAPM alpha of +7.1% (currency-basis caveat applies), and an active unit buy-back cancellation programme, the risk/return profile is positive but not yet sufficiently de-risked to warrant above a low conviction stance pending completion of the portfolio repositioning.

## Quantitative Chain

- E(R): 0.0792
- Std dev: 0.1608
- P-gain: 0.6872
- CAPM alpha: 0.0709
- Beta: 0.3534
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - North America asset disposal executes below book value, redeployment into Singapore assets is delayed or dilutive, resulting in a 12-month distribution cut. DPU coverage falls further as capital distribution component is withdrawn. Interest rate shock causes cap rate expansion of 50bps on data centre assets, compressing NAV. Hyperscaler tenant does not renew on key North American asset, occupancy drops to below 90%. Overall yield compression and re-rating of data centre risk premium.
- **base**: E(R)=0.0785
  - Central case as modelled: annualised DPU of 3.60 US cents at yield 6.92%, DPU growth of 1.5%, portfolio transition drag of -0.5%. North America disposal completes at announced terms; Singapore entry accretive at 6%+ NPI yield. Distribution coverage improves modestly as capital distribution component stabilises. Unit buy-back continues, providing partial downside support. Cap rates flat.
- **bull**: E(R)=0.2200
  - AI infrastructure demand accelerates, driving hyperscaler lease renewals at higher rents across the residual portfolio. Singapore data centre entry proves highly accretive (NPI yield above 7%), DPU growth re-rates to 4%+. Capital distribution component converted fully to income distribution reflecting improved AFFO coverage. Unit buy-back programme accelerates, reducing float significantly. Multiple expansion of 1.5x on strengthened cash flow outlook. Leverage falls below 35% post disposal proceeds.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0692 (Cat A) — H1 2026 DPU of 1.80 US cents per unit (filed DCRU.SI 2026-07-29 CACT), annualised to 3.60 US cents. Divided by closing price of USD 0.52 (2026-08-19). Trailing annualised yield = 3.60/52.0 = 6.92%.
- `capital_distribution_proportion` = 0.489 (Cat A) — H1 2026 distribution of 1.80 US cents comprises 0.92 cents tax-exempt income and 0.88 cents capital distribution (48.9% capital return), per DCRU.SI 2026-07-29 CACT filing. This implies income-only DPU coverage is structurally constrained and approximately 51% of the distribution is income-derived.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. reflects AI/hyperscaler-driven data centre demand tailwinds, partially offset by near-term distribution dilution from the North America asset disposal (US$315.9M transaction announced 2026-08-12) and Singapore market entry reducing near-term distributable income. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — A -0.5% multiple change drag applied to reflect portfolio repositioning execution risk from the US$315.9M North America disposal and simultaneous Singapore data centre acquisition announced 2026-08-12. Near-term NAV basis risk and redeployment timing uncertainty reduce the implied multiple slightly. Sensitivity tested in scenario analysis.
- `portfolio_transaction_context` = disclosed (Cat A) — Digital Core REIT announced a major portfolio transaction on 2026-08-12 (SGX filing DCRU.SI 2026-08-12 ANNC): proposed disposal of North American assets valued at approximately US$315.9M and entry into the Singapore data centre market. Trading was halted on 2026-08-11 and lifted 2026-08-12. This is the most material recent corporate event influencing the investment case.
- `unit_buyback_programme` = active (Cat A) — Active unit buy-back and cancellation programme with mandate for up to 129,602,591 units, ongoing since 15 April 2026. Daily buy-back notices filed through August 2026 (DCRU.SI 2026-08-19 ANNC, 2026-08-18 ANNC, 2026-08-14 ANNC), including 2,000,000 units cancelled on 19 Aug 2026. Signal of management confidence at current price levels.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU trades in USD on SGX). Treated as Category B input. CAPM alpha inherits the same currency and iasp benchmark noise.

## Key Risks
- Execution risk on the US$315.9M North America asset disposal: if proceeds are below announced terms or redeployment into Singapore takes longer than expected, DPU will be diluted and the capital distribution component may be further relied upon.
- Structural distribution sustainability concern: 48.9% of H1 2026 DPU is capital return rather than income, indicating AFFO coverage of income distributions alone is sub-1.0x; any deterioration in operating cash flow could force a distribution cut.
- Data centre single-tenant concentration risk: DCRU's relatively small portfolio (~10 assets) means loss or non-renewal of a major hyperscaler tenant could materially impair occupancy and income.
- Interest rate sensitivity: DCRU reports and pays distributions in USD; any rise in US rates or widening of REIT risk premia would compress valuation multiples and increase refinancing costs.
- Currency basis in CAPM inputs: beta (0.353) and IASP.L market return (-4.43%) both incorporate USD/GBP FX movements, introducing noise in the CAPM alpha signal; this limits precision of the quant chain.

## Invalidation Condition
Exit or reduce position if: (1) the North America asset disposal is announced to have failed, been materially repriced downward, or withdrawn; (2) the H2 2026 DPU is cut below 1.50 US cents per unit (>17% reduction from H1 2026 annualised run-rate); (3) aggregate leverage rises above 42% post-transaction, approaching the 45% MAS regulatory limit; or (4) a major hyperscaler tenant representing more than 20% of gross revenue provides formal notice of non-renewal.
