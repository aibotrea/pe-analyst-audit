# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-09-30_equity_reit_v1@1.0_1e3bf09f62e6`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Digital Core REIT is executing a material strategic pivot — disposing of three North American data centres for US$315.9M and entering the Singapore market — while its unit price has de-rated to USD 0.455, approximately half its IPO price, creating a potential valuation opportunity. The estimated distribution yield of ~6.5% provides a spread over the 4.07% risk-free rate, and the active unit buy-back cancellation programme (~1M units per trading day) is modestly accretive to per-unit distributions. Beta of 0.34 versus IASP.L (currency-basis caveat: USD/GBP noise applies) reflects low co-movement with the APAC REIT benchmark, while a PGain of 67.2% from the OU Monte Carlo supports a positive skew to outcomes. Conviction is constrained to Low (score 2) by elevated annualised volatility (24.6%), near-term distributable income uncertainty during the portfolio transition, and post-disposal asset concentration risk ahead of the Q3 2026 operational update due 27 October 2026.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.1671
- P-gain: 0.6716
- CAPM alpha: 0.0640
- Beta: 0.3364
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - North America asset disposal fails to close or renegotiates at material discount, DPU cut 20-30% during transition income gap, gearing remains elevated near 42%, Singapore market entry delayed or executed at dilutive yields, cap rate expansion of 50bps from rate shock or recession, occupancy falls below 90% at residual assets, multiple contraction -5%.
- **base**: E(R)=0.0740
  - Central case: US$315.9M disposal closes as announced, proceeds deployed into Singapore data centre at accretive yield, DPU supported by ongoing unit buy-back (unit count reduction ~3-4% annualised), distribution yield ~6.5%, organic DPU growth 1.5%, minor multiple compression -0.5%, gearing falls to ~35-38% post-disposal.
- **bull**: E(R)=0.2000
  - Disposal closes above book value, Singapore acquisition delivers yield above 7%, AI-driven hyperscale demand drives full occupancy with rental escalations, DPU raised 10-15%, multiple re-rates as market recognises strategic transformation value, gearing falls below 35%, Digital Realty sponsor injects further pipeline assets at accretive terms.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat C) — Estimated trailing distribution yield of ~6.5% based on current unit price of USD 0.455 and peer data centre REIT yield benchmarks (~5.9% avg SGX REIT sector; data centre premium assumed). No Q3 2026 DPU disclosure available at as_of (Q3 update due 27 Oct 2026 per DCRU.SI 2026-09-30 ANNC). Sensitivity: bear -1.5pp, bull +0.5pp.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumes modest organic uplift from remaining portfolio and gradual Singapore market entry following the US$315.9M North America asset disposal announced Aug 2026. Growth is constrained by near-term income gap during portfolio transition. Sensitivity tested plus or minus 1.5pp in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Slight multiple contraction of -0.5% assumed to reflect execution risk during the strategic pivot (3 North American asset disposals; new Singapore market entry). Price declined from ~USD 0.505 to USD 0.455 through September 2026 (~10% intra-month trend), suggesting continued de-rating pressure. Sensitivity: 0 in base; -2% in bear; +1.5% in bull.
- `north_america_asset_disposal` = US$315.9M (Cat A) — Digital Core REIT proposed sale of three North American data centres for US$315.9M announced August 2026 (Business Times and Singapore Business Review, 12 Aug 2026). Proceeds expected to reduce gearing and fund Singapore market entry. Category A: publicly announced transaction price.
- `unit_buyback_programme` = 1000000_units_per_day_cancelled (Cat A) — Active daily unit buy-back programme purchasing 1,000,000 units per trading day throughout September 2026, all units cancelled (DCRU.SI SGX ANNC filings 2026-08-31 through 2026-09-04). Maximum authorised buy-back 129,602,591 units. Unitholder-friendly capital return reduces unit count by approximately 3-4% annualised.
- `leverage_post_disposal` = estimated_below_40pct (Cat C) — Pre-disposal gearing estimated ~38-42% based on sector comparables and 1Q2026 update reference (DCRU.SI 2026-04-22 ANNC). US$315.9M disposal proceeds expected to reduce aggregate leverage materially below Singapore's 45% regulatory limit. Post-disposal leverage is a Category C estimate pending Q3 2026 disclosure (due 27 Oct 2026).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (DCRU trades in USD on SGX). Currency and iasp basis noise treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Execution risk on US$315.9M North America asset disposal — delayed close or price renegotiation would leave gearing elevated and DPU under pressure during the transition period.
- Singapore market entry risk — acquiring data centre assets in a new geography at potentially compressed yields could be dilutive if pricing is aggressive or operational ramp-up is slower than expected.
- Higher-for-longer US interest rates (Rf 4.07%) compressing the yield spread, with DCRU's USD-denominated distributions exposed to US rate dynamics despite SGX listing.
- Post-disposal asset concentration risk: remaining portfolio more geographically concentrated, amplifying single-market and single-tenant event risk before new Singapore assets are fully income-producing.
- Calibration limitation: this analysis is a directional signal only; Phase 2 calibration is not a formal backtest (vintage discipline arrives in Phase 5), and macro credit-spread signals are not incorporated due to availability constraints at this as_of date.

## Invalidation Condition
Exit or reduce position if any of the following occur: (1) the US$315.9M North America asset disposal is formally cancelled or renegotiated to a price more than 10% below announced consideration; (2) annualised DPU is cut by more than 20% in the Q3 2026 disclosure or subsequent quarter; (3) aggregate leverage is reported above 45% (Singapore MAS regulatory limit) for two consecutive reporting periods without a credible and time-bound de-leveraging plan disclosed; or (4) Digital Realty Trust as sponsor materially reduces its commitment evidenced by withdrawal of pipeline support, reversal of any fee waiver, or public statements distancing from the REIT's Singapore expansion strategy.
