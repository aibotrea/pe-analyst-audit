# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-31_equity_reit_v1@1.0_fff457269485`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-31
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Digital Core REIT is executing a strategic portfolio transformation — divesting US$315.9M of North American data centre assets and redeploying into Singapore and Japan — that positions it as a pure-play APAC data centre REIT with structural demand tailwinds from AI and cloud adoption. At USD$0.505/unit, the trailing yield of ~7% provides a substantial spread of approximately 325bps over the current 3-month T-bill rate of 3.74%, and the active unit buyback programme (up to 129.6M units cancelled) signals management conviction in intrinsic value. Beta of 0.35 versus IASP.L (currency-basis caveat applies) indicates below-benchmark volatility for a data centre REIT, while annualised volatility of 24.1% is moderate for the sector given the high-leverage legacy profile that is now being corrected. The OU Monte Carlo simulation yields a 12-month sim return of 9.2% with a PGain of 71.4%, supporting an above-average conviction score of 4.

## Quantitative Chain

- E(R): 0.0930
- Std dev: 0.1637
- P-gain: 0.7135
- CAPM alpha: 0.0850
- Beta: 0.3495
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - North America asset disposal falls through or closes at a material discount, leaving DCRU over-leveraged above MAS 45% limit and forcing an equity raise at a significant discount. DPU cut of 15–20% as interest costs rise and asset income gap widens during transition. Data centre demand softens on AI capex pullback, occupancy dips to 88%, cap rates expand 50bps. Unit buyback suspended. Bear case also incorporates a rate-shock scenario where US Fed resumes hikes, compressing yield spreads globally and driving further APAC REIT multiple compression of 10–15%.
- **base**: E(R)=0.0930
  - Central case as built in chain: North America disposal closes at announced US$315.9M, proceeds redeployed into Singapore/Japan data centres. Distribution yield of 6.8% sustained with 2.0% DPU growth from rental escalators and accretive APAC acquisitions. Leverage falls to 33–38% post-close, comfortably within MAS limits. Occupancy stable at 95%+, long WALE data centre leases intact. Unit buyback continues providing price support.
- **bull**: E(R)=0.2200
  - Asset sale closes above book value, unlocking a one-off capital gain distribution and accelerating Singapore/Japan portfolio buildout at 7%+ NPI yields. Data centre demand surge from AI infrastructure spending drives occupancy to 98%+ and triggers rental reversion of 10–15%. DCRU re-rates toward peer data centre REIT multiples (Keppel DC REIT, NTT DC REIT) as APAC investor base broadens. DPU growth accelerates to 4–5%, multiple expands 150bps, total return approaches 22%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.068 (Cat B) — Forward DPU yield estimated at 6.8% on current unit price of USD$0.505. Multiple sources (Smart Investor, Beansprout, June–August 2026) cite DCRU at 7%+ trailing yield; a modest discount to 6.8% applied to reflect near-term income dilution during the North America asset disposal (US$315.9M, announced 12 Aug 2026) and redeployment lag into Singapore/Japan data centres. Category B — derived from observable price and publicly cited yield range.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a.: 1.5% from data centre rental escalators (CPI-linked or fixed step-up clauses typical in long-WALE data centre leases) plus 0.5% net contribution from Singapore/Japan asset acquisitions post-disposal. Data centre sector structural demand from AI/cloud supports occupancy. Sensitivity tested in scenario analysis. Category C — model assumption.
- `multiple_change` = 0.005 (Cat C) — Modest positive re-rating of +0.5% assumed as DCRU pivots portfolio toward Singapore and Japan data centres, markets with stronger institutional REIT investor appetite and SGX familiarity. Partially offset by elevated global rate uncertainty. Net contribution conservative. Category C — model assumption.
- `asset_disposal_transition` = US$315.9M North America disposal announced 2026-08-12 (Cat A) — Digital Core REIT proposed sale of North America data centre assets for US$315.9 million, concurrent with acquisitions of Singapore and Japan data centres. Source: The Business Times 2026-08-12. This is a publicly announced proposed transaction (Category A — observed public announcement). Proceeds expected to reduce leverage and be redeployed into APAC assets.
- `unit_buyback_programme` = Up to 129,602,591 units authorised for cancellation, mandate from 2026-04-15 (Cat A) — Active unit buyback programme disclosed in daily SGX filings (DCRU.SI 2026-08-20 to 2026-08-31 ANNC series). Units purchased by market acquisition and cancelled, signal management confidence in intrinsic value. Pace observed at 2,000,000 units per trading day in late August 2026. Category A — disclosed in SGX filings.
- `leverage_estimate` = estimated_below_40pct_post_disposal (Cat B) — Pre-disposal DCRU leverage was estimated at 35–42% (consistent with MAS 45% limit). US$315.9M asset sale is expected to reduce aggregate leverage materially, likely toward or below 35%. Post-disposal leverage estimate is Category B — derived from public asset value disclosure and directional assessment; exact post-close leverage not yet filed.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU is USD-denominated on SGX). Treated as Category B input. CAPM alpha inherits the same currency noise. The IASP benchmark's negative 5-year annualised return (-4.66%) reflects GBP/APAC currency dynamics and broader APAC REIT drawdowns, compressing the CAPM required return and mechanically inflating alpha.

## Key Risks
- Portfolio transition execution risk: the US$315.9M North America disposal may not close on disclosed terms or on schedule, leaving DCRU in a capital limbo with elevated leverage relative to MAS limits and a partially re-invested portfolio during transition.
- Distribution continuity risk: income from divested North American assets may cease before Singapore/Japan acquisitions generate equivalent DPU, creating a temporary earnings gap and potential DPU cut.
- Rate sensitivity: DCRU's USD-denominated distributions are exposed to both USD/SGD FX risk for investors and to US dollar funding costs; a re-acceleration of Fed rate hikes would compress the yield spread and increase refinancing costs.
- Single-sector concentration: 100% data centre exposure means any sector-specific shock (technology demand slowdown, hyperscaler capex cuts, regulatory restrictions on AI infrastructure) would have outsized NAV impact versus diversified REITs.
- CAPM alpha interpretation caveat: the mechanically high alpha of 8.5% is substantially attributable to the IASP.L benchmark's deeply negative 5-year return (-4.66%), which reflects GBP/APAC currency dynamics and broad APAC REIT drawdowns rather than a genuinely low required-return environment; the alpha figure should be weighted accordingly.

## Invalidation Condition
Exit if: (1) the proposed US$315.9M North America disposal is formally terminated, withdrawn, or repriced below 90% of announced consideration, signalling deterioration in asset quality or counterparty failure; (2) aggregate leverage breaches 45% MAS limit for one reporting period without a credible deleveraging plan announced within 30 days; (3) DPU is cut more than 20% from the most recent declared distribution level for two consecutive quarters; or (4) the unit buyback programme is suspended while the unit price trades more than 15% below the NAV per unit disclosed in the most recent quarterly financial statement.
