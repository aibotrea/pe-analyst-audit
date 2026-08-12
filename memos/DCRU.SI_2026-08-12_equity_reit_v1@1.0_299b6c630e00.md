# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-12_equity_reit_v1@1.0_299b6c630e00`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT (DCRU.SI) is a USD-denominated data centre REIT listed on SGX, sponsored by Digital Realty Trust, undergoing a significant strategic pivot: the announced sale of US$315.9M of North American assets to fund its first Singapore data centre entry and Japan expansion marks a structural shift toward APAC alignment. The trailing total distribution yield of 7.2% (at USD 0.50) provides a meaningful income base, though approximately 49% of H1 2026 distributions comprised capital returns rather than income, which is a material sustainability concern that constrains conviction. Beta of 0.34 versus IASP.L (currency-basis caveat applies) implies below-average correlation to the broader APAC REIT index. An OU Monte Carlo PGain of 72.7% supports a moderate conviction rating, tempered by high annualised volatility of 23.5% and near-term execution risk from the portfolio restructuring currently in progress.

## Quantitative Chain

- E(R): 0.0970
- Std dev: 0.1596
- P-gain: 0.7267
- CAPM alpha: 0.0869
- Beta: 0.3369
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Portfolio transaction fails to complete or is significantly dilutive (assets sold at discount to book, new APAC assets acquired at compressed yields); capital distribution component of DPU eliminated causing DPU to fall 40%+; AI infrastructure spending slowdown reduces data centre demand; cap rate expansion of 50bps in both NA and APAC markets; gearing breaches 45% MAS regulatory limit requiring equity issuance. Annualised income yield collapses to ~2.0% with no multiple support.
- **base**: E(R)=0.0970
  - Central case as built: total distribution yield 7.20% (including 0.88c capital distribution component), forward DPU growth 2.0%, +0.5% multiple expansion on APAC pivot. Portfolio transaction completes as announced; Singapore and Japan assets begin contributing income from H2 2026; occupancy stable across retained portfolio; gearing within regulatory limits.
- **bull**: E(R)=0.2200
  - APAC data centre assets acquired at yields exceeding 6.5%, immediately accretive to DPU; capital distribution component replaced by income distribution as Singapore and Japan assets ramp occupancy to 98%+; Digital Realty injects further pipeline at favourable terms; APAC data centre valuations re-rate upward on sustained AI hyperscaler demand driving 20%+ NAV uplift; gearing falls below 35% on asset revaluation; income DPU grows 8%+ in 12 months.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.072 (Cat A) — H1 2026 total distribution of 1.80 US cents per unit (comprising 0.92c tax-exempt income + 0.88c capital distribution), annualised to 3.60c, divided by closing price of USD 0.50 per unit as of 2026-08-12. Source: DCRU.SI 2026-07-29 CACT filings (Capital Distribution and Cash Dividend/Distribution announcements). Total yield 3.60/50.0 = 7.20%.
- `income_vs_capital_distribution_split` = 0.489 (Cat A) — Capital distribution component represents 0.88c of 1.80c total H1 2026 distribution (48.9%). Income distribution is 0.92c per unit. Annualised income yield is only 3.68%. This split raises distribution sustainability concerns and is a primary driver of the qualitative gate override. Source: DCRU.SI 2026-07-29 Capital Distribution filing.
- `dpu_growth_forward` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed. Data centre sector benefits from structural AI/cloud demand tailwinds. Portfolio pivot to APAC (Singapore debut, Japan expansion) announced 2026-08-12 (DCRU.SI Asset Acquisitions and Disposals filing) should provide incremental income contribution. Growth constrained by ongoing capital distribution component and portfolio transition uncertainty. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple expansion assumed. APAC-heavy portfolio pivot post the US$315.9M North America asset sale may attract a modest re-rating as DCRU aligns more closely with Asian data centre market multiples. Assumes no material cap rate expansion. Category C — highly uncertain, depends on deal completion and market reception.
- `portfolio_transaction_2026_08_12` = disclosed (Cat B) — On 2026-08-12, DCRU.SI announced a major portfolio transaction: sale of stakes in three North American data centres back to Digital Realty for US$315.9M, with proceeds to fund entry into Singapore and expansion in Japan. Source: DCRU.SI 2026-08-12 Asset Acquisitions and Disposals filing and corroborated by multiple news sources (Business Times, IPE Real Assets, Data Center Dynamics, 2026-08-12). Transaction introduces execution risk and interim DPU dilution during transition. Treated as Category B — headline confirmed but full financial terms pending attachment review.
- `sponsor_quality` = Digital Realty Trust (DLR) (Cat A) — Digital Realty Trust (NYSE: DLR) is the external manager and sponsor. The 2026-08-12 portfolio transaction is a sponsor-driven asset swap, demonstrating active pipeline involvement. DLR is one of the largest global data centre REITs by AUM, providing credible pipeline and operational expertise.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP, as well as the indirect USD/SGD currency basis (DCRU trades on SGX in USD). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- High capital distribution component (49% of H1 2026 DPU): if income generation does not ramp from APAC assets, total distributions may be cut materially, compressing the effective income yield from 7.2% to ~3.7%
- Portfolio transaction execution risk: completion delays, pricing disappointments, or acquisition of APAC assets at inadequate yields could be dilutive to NAV and DPU on a 12-month view
- Elevated volatility (23.5% annualised): DCRU has traded in a relatively narrow USD 0.47–0.52 range recently but the major transaction announcement on 2026-08-12 signals elevated near-term price volatility
- Leverage uncertainty: the aggregate leverage ratio post-transaction is not yet determinable from available filings; if gearing rises above the MAS 45% limit (or 50% with shareholder approval), a dilutive equity raise may be required
- AI/data centre sentiment risk: if AI infrastructure spending expectations are revised downward, data centre cap rates could expand meaningfully, reducing NAV and suppressing the unit price irrespective of income delivery

## Invalidation Condition
Exit the position if: (1) the announced US$315.9M North America asset sale fails to complete or completes at a price more than 10% below announced consideration; (2) H2 2026 DPU falls below 0.80 US cents per unit (implying annualised income DPU <1.60c, a >10% cut from H1 run-rate), indicating deteriorating income coverage; (3) aggregate leverage ratio breaches 45% MAS limit requiring an unplanned equity issuance at a discount to NAV; or (4) Digital Realty materially reduces its sponsor commitment or ceases to serve as external manager of DCRU.
