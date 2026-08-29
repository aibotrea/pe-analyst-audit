# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-08-29_equity_reit_v1@1.0_b9537959d1d1`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-29
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Keppel DC REIT (AJBU.SI) is Singapore's largest pure-play data centre REIT, offering structural exposure to AI and cloud-driven demand through a globally diversified colocation portfolio spanning Singapore, Europe, and APAC. The H1 2026 DPU of 5.714 cents per unit (up 11.3% YoY) and an annualised trailing yield of approximately 5.2% at the current SGD 2.20 price provide a meaningful income base, supported by a high-quality sponsor in Keppel Group that has demonstrated alignment via partial management fee payment in units. Beta of 0.26 versus IASP.L (currency-basis caveat applies) reflects the low co-movement of data centre assets with broader APAC REITs, while the OU Monte Carlo generates a PGain of 81% and a CAPM alpha of 7.2% over the 12-month horizon. A one-step gate override is applied to reflect the occupancy slide disclosed in 1H 2026 results and the partial capital distribution component (~9% of DPU) which reduces income quality, resulting in a Moderate conviction score of 3.

## Quantitative Chain

- E(R): 0.0869
- Std dev: 0.0985
- P-gain: 0.8100
- CAPM alpha: 0.0715
- Beta: 0.2594
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy deterioration accelerates across European and APAC colocation assets, DPU falls 10% as capital distribution component is eliminated and income distribution is trimmed, cap rate expansion of 30bps driven by persistent higher-for-longer global rates and risk-off sentiment. SGD appreciates vs USD, pressuring USD-denominated rental income. Management fees revert fully to cash, reducing distributable income further. Bear case incorporates a rate-shock/stagflation pathway where global central banks are forced to re-tighten.
- **base**: E(R)=0.0865
  - Central case as modelled: annualised DPU of 11.4 cents, distribution yield of 5.19%, DPU growth of 3.5% p.a. driven by AI/cloud colocation demand and selective asset enhancement. Occupancy stabilises following 1H 2026 slide, gearing remains within Singapore 50% regulatory limit, cap rates flat. Management fee partly in units.
- **bull**: E(R)=0.2000
  - AI-driven hyperscaler demand accelerates leasing activity across portfolio, occupancy recovers to historical highs (>95%), DPU growth re-accelerates toward 8-10%, Keppel Group injects accretive pipeline assets at above-portfolio yields. Rate cuts by MAS and global central banks compress cap rates by 25bps, driving NAV uplift and meaningful multiple expansion. Capital distribution component replaced by income distribution as earnings quality improves.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0519 (Cat A) — Annualised DPU of SGD 0.11428 (2x H1 2026 DPU of 5.714 cents per unit as declared in AJBU.SI 2026-07-23 CACT filing) divided by closing price of SGD 2.20 as of 2026-08-28. Observed public data.
- `dpu_growth_3yr` = 0.035 (Cat C) — Forward 3-year DPU growth assumption of 3.5% p.a. H1 2026 DPU rose 11.3% YoY (Business Times, 23 Jul 2026), driven by AI/cloud demand and colocation renewals at higher rates. Growth moderated from H1 pace to account for noted occupancy slide (reitsweek, 23 Jul 2026), lease-up risk, and the partial capital distribution component (0.518c of 5.714c total DPU). Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Zero multiple expansion/contraction assumed for 12-month base case. Data centre REIT premium valuations are partially offset by occupancy headwinds and a still-elevated rate environment (SGD SORA remains above 2%). Neutral assumption sensitivity tested in scenarios.
- `capital_distribution_component` = 0.00518 (Cat A) — Capital distribution component of 0.518 cents per unit within H1 2026 total DPU of 5.714 cents (approximately 9.1% of total distribution is return of capital, not income). Sourced from AJBU.SI 2026-07-23 CACT filing. Relevant to sustainability assessment of DPU coverage.
- `management_fee_units` = disclosed (Cat A) — Management fee for 2Q 2026 partially paid via issue of units in Keppel DC REIT (AJBU.SI 2026-08-03 ANNC filing). This signals management alignment with unitholders and reduces cash outflow from distributable income.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Occupancy decline across colocation assets: reitsweek flagged an occupancy slide in 1H 2026 despite rising income; sustained vacancies would pressure future DPU and erode the income-quality thesis.
- Capital distribution sustainability: approximately 9.1% of H1 2026 DPU (0.518 cents) is return of capital rather than income, which may not be sustainable if asset recycling activity slows.
- Higher-for-longer interest rates: Keppel DC REIT carries floating-rate debt exposure; a rate re-tightening cycle would increase interest costs, compress distribution coverage, and widen cap rates.
- Currency risk: a significant portion of rental income is USD- and EUR-denominated; SGD appreciation would reduce SGD-equivalent distributions and NAV.
- Hyperscaler in-sourcing risk: large cloud providers (AWS, Azure, Google) increasingly build proprietary data centres, potentially reducing colocation demand and exerting pricing pressure on renewal leases.

## Invalidation Condition
Exit position if occupancy falls below 90% across the portfolio for two consecutive reporting periods, or if annualised DPU drops more than 15% from the current 11.4 cents level (i.e. below approximately 9.7 cents), or if aggregate leverage breaches the Singapore MAS 50% regulatory threshold, or if Keppel Group materially reduces its ownership stake or pipeline commitment to the REIT without an accretive replacement sponsor identified.
