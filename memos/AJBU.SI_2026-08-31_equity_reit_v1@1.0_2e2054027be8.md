# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-08-31_equity_reit_v1@1.0_2e2054027be8`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-31
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Keppel DC REIT (AJBU.SI) offers structurally differentiated data centre exposure in Singapore and globally, underpinned by a Keppel Ltd sponsor with a strong pipeline track record and demonstrated capital discipline. The 1H 2026 DPU of 5.714 cents (annualised 11.43 cents) equates to a 5.19% distribution yield on the current SGD 2.20 price, providing a 145bps spread over the 3.74% T-bill rate. An OU Monte Carlo simulation at 12 months generates a PGain of 79.6% and a CAPM alpha of 6.63% versus the IASP.L benchmark, supporting an Above Average conviction score of 4. Near-term risks from a noted occupancy slide and a preferential offering dilution are considered manageable within the 3.0% DPU growth assumption and are explicitly stress-tested in the bear scenario; the low beta of 0.26 relative to the broader APAC REIT index further reduces systematic risk at the portfolio level.

## Quantitative Chain

- E(R): 0.0819
- Std dev: 0.0984
- P-gain: 0.7960
- CAPM alpha: 0.0663
- Beta: 0.2590
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy slide accelerates to portfolio-level vacancy rising above 5%, DPU growth stalls to 0% or turns negative as lease renewals disappoint. Preferential offering proceeds deployed at sub-5% yield, diluting DPU. Cap rate expansion of 50bps driven by a higher-for-longer rate environment (US Fed maintains restrictive policy, SORA remains elevated), compressing NAV by ~8-10%. Distribution yield alone insufficient to offset negative total return.
- **base**: E(R)=0.0819
  - Central case as built in quantitative chain: distribution yield of 5.19%, DPU growth of 3.0% driven by AI/cloud demand, zero multiple change. Preferential offering accretive at data centre yields above cost of capital. Occupancy stabilises in the low-to-mid 90s percent range. No material change in Singapore macro or MAS policy.
- **bull**: E(R)=0.2000
  - AI infrastructure demand surge drives occupancy back to near-full utilisation (>97%), enabling DPU growth of 6-8%. Preferential offering proceeds deployed into high-yielding hyperscaler anchor-tenanted assets. Rate cut cycle materialises (MAS eases, SGD SORA declines), compressing cap rates by 25-50bps and driving NAV re-rating. Multiple expansion of 5-7% on top of elevated yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0519 (Cat A) — 1H 2026 DPU of SGD 0.05714 per unit (taxable 4.838c + tax-exempt 0.358c + capital 0.518c) as declared in AJBU.SI 2026-07-23 Half Yearly Results filing. Annualised DPU of SGD 0.11428 divided by closing price of SGD 2.20 on 2026-08-31 yields 5.19% distribution yield. Price and DPU are both observed public data.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth assumption of 3.0% p.a. Basis: Q1 2026 DPU of 2.833c was +13.2% YoY (Business Times, Apr 2026), indicating strong near-term momentum from AI/cloud-driven data centre demand. However, 1H 2026 results noted an occupancy slide (reitsweek, Jul 2026), and a preferential offering is underway (AJBU.SI 2026-08-31 ANNC) suggesting near-term dilution. 3.0% is a deliberately conservative estimate balancing structural tailwinds against occupancy and dilution headwinds. Sensitivity tested in scenarios.
- `multiple_change` = 0.0 (Cat C) — Assumes zero multiple expansion or contraction over the 12-month horizon. Preferential offering capital deployment and ongoing occupancy stabilisation are assumed to offset any re-rating, netting to flat. This is a simplifying assumption; sensitivity to +/- 100bps cap-rate shift is reflected in bull and bear scenarios.
- `capital_distribution_component` = 0.00518 (Cat A) — 1H 2026 distribution includes a capital distribution component of 0.518 cents per unit, sourced from AJBU.SI 2026-07-23 CACT filing. This represents a partial return of capital rather than income, mildly relevant to distribution sustainability assessment.
- `preferential_offering_dilution` = disclosed (Cat B) — AJBU.SI 2026-08-31 ANNC discloses 'Use of Proceeds from the Preferential Offering', confirming a capital raise is underway. Quantum and dilution impact not quantifiable from filing headline alone; assumed accretive if deployed at data centre yields above cost of capital. Dilution risk is partially offset by AUM growth contribution included in the 3.0% DPU growth assumption.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Occupancy slide in 1H 2026 (flagged by reitsweek, July 2026) may continue if hyperscaler tenants do not renew or expand leases on schedule, pressuring DPU and valuation.
- Preferential offering dilution risk: if proceeds are deployed at data centre yields below the cost of equity (~8%), DPU per unit declines and the yield story weakens.
- Higher-for-longer interest rate environment (US Fed, MAS) compresses the yield spread versus risk-free rates and may trigger cap rate expansion, eroding NAV.
- Currency and IASP.L basis noise in beta estimate (0.26) may understate true systematic risk; actual portfolio correlation with global rate moves is likely higher than the raw beta implies.
- Concentration risk in data centre assets means any structural shift in hyperscaler capex strategy (e.g., insourcing, technology substitution) could impair long-term demand at a portfolio level.

## Invalidation Condition
Exit if portfolio-level occupancy falls below 90% for two consecutive reporting periods (half-yearly), or if DPU coverage by distributable income (excluding capital distributions) drops below 1.0x for two consecutive periods, or if the preferential offering proceeds are confirmed deployed at a blended yield of less than 5.5%, materially diluting existing unitholders without compensating DPU growth. Additionally, exit if Keppel Ltd formally reduces or withdraws its right-of-first-refusal pipeline commitment to the REIT.
