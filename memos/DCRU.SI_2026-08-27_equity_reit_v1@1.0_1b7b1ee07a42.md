# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-27_equity_reit_v1@1.0_1b7b1ee07a42`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT offers exposure to global data-centre infrastructure via a USD-denominated, Singapore-listed vehicle sponsored by Digital Realty Trust, one of the world's largest data-centre operators. The total DPU yield of ~7.3% on a 2026-08-27 price of USD 0.495 is attractive in absolute terms, and the active unit buy-back programme (2M units/day cancelled since April 2026) signals below-NAV pricing and management confidence. The August 2026 portfolio transaction — disposing of US$315.9M in North American assets and entering Singapore — represents a material strategic pivot whose income accretion profile carries near-term uncertainty. Conviction is moderated to 3 (Moderate) by the elevated capital-distribution fraction (49% of H1 2026 DPU), which obscures income coverage and underscores the need for the Singapore acquisition to prove its recurring earnings contribution before the thesis fully crystallises.

## Quantitative Chain

- E(R): 0.0980
- Std dev: 0.1631
- P-gain: 0.7245
- CAPM alpha: 0.0900
- Beta: 0.3508
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Singapore acquisition fails to replace income lost from North America disposal (negative DPU accretion), income DPU coverage falls below 0.9x AFFO as capital distributions cease, occupancy at key hyperscaler tenants weakens amid AI spend rationalisation, cap rates expand 50bps, leverage remains elevated above 42% post-transaction, and rising US rates compress yield spread further. Unit buy-back programme suspended.
- **base**: E(R)=0.0980
  - Central case as built in quantitative chain: total DPU yield 7.27% (annualised from H1 2026 actual), DPU growth 2.0% p.a. via lease escalators and Singapore portfolio contribution, modest +0.5% multiple re-rating from buy-back programme, cap rates flat, leverage declines post-North America disposal, IASP.L benchmark return -4.6%.
- **bull**: E(R)=0.2500
  - Singapore data-centre acquisition is materially accretive at yield on cost above 7%, capital distribution component transitions to income as new assets contribute recurring NPI, sponsor Digital Realty seeds additional pipeline assets into DCRU, data-centre sector re-rates upward on AI infrastructure tailwind, cap rates compress 25bps, leverage falls below 35%, and unit buy-back delivers meaningful NAV per unit uplift.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0727 (Cat A) — Total DPU of USD 1.80 cents per unit for H1 2026 (1 Jan – 30 Jun 2026), annualised to 3.60 US cents, divided by closing price of USD 0.495 as at 2026-08-27. Source: DCRU.SI 2026-07-29 CACT (Capital Distribution) and CACT (Cash Dividend/Distribution) filings on SGX.
- `income_only_yield` = 0.0372 (Cat A) — Tax-exempt income component of H1 2026 DPU: 0.92 US cents per unit, annualised to 1.84 US cents, divided by USD 0.495 closing price. Capital distribution component (0.88 US cents per unit, 49% of total) excluded from income-only yield. Source: DCRU.SI 2026-07-29 CACT filing on SGX.
- `capital_distribution_fraction` = 0.489 (Cat A) — Capital return component (USD 0.0088/unit) as a proportion of total H1 2026 DPU (USD 0.0180/unit) = 48.9%. Sourced from DCRU.SI 2026-07-29 CACT (Capital Distribution) filing on SGX. Elevated capital distribution fraction (funded by disposal proceeds) reduces income DPU coverage visibility.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption: 2.0% p.a. based on (i) CPI-linked or fixed annual escalators typical in data-centre leases (1.0–3.0%), (ii) portfolio repositioning benefit from North America disposal and Singapore market entry (announced 2026-08-12), and (iii) accretive potential from Digital Realty sponsor pipeline. Sensitivity tested in scenario analysis. Uncertainty elevated by post-transaction income mix.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% positive re-rating assumed over a 12-month horizon, premised on: active unit buy-back programme (since 15 Apr 2026, ~2M units/day cancelled per DCRU.SI 2026-08-18 to 2026-08-27 ANNC filings), implying below-NAV pricing; and potential for data-centre sector re-rating as interest rate environment stabilises. Sensitivity: a 25bp cap rate expansion in the new Singapore assets would offset this entirely.
- `portfolio_transaction` = disclosed (Cat B) — On 2026-08-12, Digital Core REIT announced a US$315.9M North America asset disposal and entry into the Singapore data-centre market. Source: DCRU.SI 2026-08-12 ANNC (Asset Acquisitions and Disposals) filing on SGX. Post-transaction leverage, income profile, and WALE are subject to finalisation; treated as Category B given disclosed transaction size but incomplete balance-sheet impact data at filing date.
- `unit_buyback` = active (Cat A) — Unit buy-back programme active since 15 April 2026 under mandate for up to 129,602,591 units. Daily purchases of 2,000,000 units observed 18–21 Aug 2026 with all units cancelled. Source: DCRU.SI 2026-08-18 to 2026-08-27 daily ANNC filings on SGX.
- `leverage_status` = unconfirmed (Cat B) — Full balance-sheet gearing ratio not extractable from truncated filing bodies available at as_of date. Regulatory limit for Singapore REITs is 45% (50% if investment-grade rated). The North America disposal (US$315.9M) announced 2026-08-12 is expected to be deleveraging if proceeds repay debt, but post-transaction leverage is unconfirmed. Treated as Category B pending full 1H2026 financial statements.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU.SI trades and distributes in USD). Treated as Category B input. CAPM alpha inherits the same currency-basis noise. This is the mandatory iasp currency caveat disclosure.

## Key Risks
- High capital-distribution fraction (49% of H1 2026 DPU) reduces income coverage visibility; if disposal proceeds are depleted, total DPU could decline materially in H2 2026 and 2027.
- Post-transaction leverage and balance-sheet gearing unconfirmed at as_of date; if the North America disposal proceeds are not used to repay debt, Singapore REIT regulatory limits (45%/50%) may constrain future acquisitions.
- Singapore data-centre entry introduces new execution risk: asset pricing, development timeline, and yield-on-cost are unconfirmed from available filing bodies; accretion timeline is uncertain.
- Higher-for-longer US interest rates compress the yield spread vs T-bill (3.7%) and increase cost of any floating-rate debt refinancing; income-only yield of ~3.7% offers minimal spread over risk-free.
- IASP.L benchmark data is GBP-denominated; beta and alpha estimates inherit FX co-movement noise between USD and GBP, reducing signal reliability for CAPM inputs.

## Invalidation Condition
Exit if: (i) H2 2026 or FY2026 income DPU (excluding capital distributions) falls more than 20% below the H1 2026 annualised run-rate of USD 1.84 cents per unit for two consecutive reporting periods; (ii) confirmed post-transaction gearing exceeds 45% of total assets; (iii) the Singapore acquisition yield-on-cost is disclosed below 5.5%; or (iv) the unit buy-back programme is formally suspended without explanation, suggesting deteriorating liquidity or a change in management's capital allocation priorities.
