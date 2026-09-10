# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-09-10_equity_reit_v1@1.0_f7c213d82807`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-10
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Keppel DC REIT is Singapore's leading listed data centre REIT, backed by the Keppel conglomerate sponsor with a demonstrated pipeline of hyperscale assets. The September 2026 acquisition of two hyperscale colocation data centres in Inzai City, Greater Tokyo — funded by a well-structured S$625M equity placement at SGD 2.10/unit — is strategically sound, adding geographic diversification and exposure to Japan's undersupplied data centre market. At the current price of SGD 2.15, the estimated forward yield of ~5.2% offers a meaningful spread of ~140bps over the 3.81% T-bill rate. The OU Monte Carlo simulation returns a PGain of 77.9% at a 12-month horizon, while a CAPM alpha of 6.1% (Category B; currency-basis caveat applies) confirms expected excess return. The combination of structural AI/cloud demand tailwinds, a low beta of 0.26 relative to IASP.L, and active sponsor pipeline supports an above-average conviction score of 4.

## Quantitative Chain

- E(R): 0.0770
- Std dev: 0.0996
- P-gain: 0.7790
- CAPM alpha: 0.0610
- Beta: 0.2557
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Japan hyperscale data centre acquisition encounters integration delays or tenant pre-commitment fails to materialise, causing DPU accretion to disappoint and post-placement DPU to fall to ~10.0 cents annualised. Simultaneously, SGD interest rates remain elevated and rate-sensitive investors exit data centre REITs, compressing multiples by 10–15%. Global AI/cloud capex slowdown reduces demand for new colocation capacity. Gearing creeps toward 40% if asset values soften.
- **base**: E(R)=0.0770
  - Central case as modelled: forward annualised DPU ~11.2 cents, yield ~5.2%, DPU growth 2.5%, zero multiple change. Japan assets stabilise within 12 months at ~6% NPI yield, offsetting placement dilution. Occupancy across portfolio remains above 95%. Gearing within 35–38% post-acquisition. SGD T-bill rate stable near 3.8%.
- **bull**: E(R)=0.1800
  - AI-driven hyperscale demand accelerates, pushing colocation rental reversion sharply upward. Japan data centres ramp faster than expected and DPU accretion exceeds placement dilution, lifting annualised DPU to ~12.5 cents. Multiple expansion of 5–8% driven by re-rating of Singapore data centre REITs as a scarce-asset class. Keppel sponsor injects additional pipeline assets at accretive yields. SGD interest rates ease, reducing financing costs.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0521 (Cat B) — Forward annualised DPU estimated at ~11.2 cents/unit (post-placement dilution). H1 2026 DPU of 5.714 cents (annualised 11.428 cents) sourced from AJBU.SI 2026-07-23 CACT filing; adjusted downward ~2% for dilution from 297.62M new units issued at SGD 2.10 per unit (AJBU.SI 2026-09-01 REPL placement results filing), partially offset by income from Japan hyperscale data centre acquisition. Divided by current price SGD 2.15 (2026-09-10 close). Category B as forward DPU requires analyst derivation.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumed: acquisition of two hyperscale colocation data centres in Inzai City, Greater Tokyo (AJBU.SI 2026-09-01 asset acquisition announcement) funded by S$625M equity placement at ~6%+ NPI yield provides modest accretion. Near-term dilution from new units partially offsets. 2.5% reflects organic rent escalation (CPI-linked and fixed-step leases typical for DC REITs) and stabilisation of Japan assets. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Zero multiple change assumed for base case. Current price SGD 2.15 is 2.4% above the placement price of SGD 2.10 (AJBU.SI 2026-09-01 placement results), suggesting the market has digested the equity raise. AI/cloud demand tailwind supports data centre premiums but is already reflected in current pricing. No meaningful re-rating assumed at 12-month horizon.
- `placement_dilution` = 0.1215 (Cat A) — Private placement issued 297,620,000 new units at SGD 2.10/unit, increasing unit count from 2,447,605,207 to 2,745,225,207 — a 12.15% unit base expansion. Sourced from AJBU.SI 2026-09-01 REPL placement results filing (capital amount-new SGD 4,013,311,441).
- `h1_2026_dpu` = 0.05714 (Cat A) — H1 2026 DPU of 5.714 cents per unit for the period 1 January to 30 June 2026, comprising taxable income 4.838 cents, tax-exempt income 0.358 cents, and capital distribution 0.518 cents. Sourced from AJBU.SI 2026-07-23 CACT capital distribution filing.
- `capital_distribution_component` = 0.00518 (Cat A) — Capital distribution component of H1 2026 DPU is 0.518 cents out of 5.714 cents total (~9.1%), indicating partial return of capital rather than purely distributable income. Sourced from AJBU.SI 2026-07-23 CACT filing. This flags potential AFFO coverage monitoring requirement.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Post-placement DPU dilution risk: 297.62M new units represent a 12.15% unit base expansion; if Japan assets underperform expected 6%+ NPI yield, per-unit DPU could disappoint, pressuring the unit price below the SGD 2.10 placement price.
- Capital distribution component (~9.1% of H1 2026 DPU) signals partial return of capital rather than purely income-backed distributions; if AFFO coverage falls below 1.0x, the framework requires a downward conviction override on re-assessment.
- Hyperscale tenant concentration: colocation data centres in Inzai, Greater Tokyo likely serve one or two anchor hyperscale tenants; any early lease exit or renegotiation could materially impair income.
- SGD/JPY currency risk: Japan assets generate JPY income; unhedged or partially hedged JPY/SGD exposure introduces FX volatility into SGD distributions.
- Interest rate sensitivity: data centre REIT valuations are long-duration; a re-acceleration of SGD or global rates would compress multiples and widen the cost of future debt refinancing, currently a tailwind at ~35–38% gearing.

## Invalidation Condition
Exit position if post-acquisition annualised DPU falls below 10.5 cents per unit for two consecutive semi-annual reporting periods (indicating placement dilution is not being offset by Japan asset income), or if portfolio gearing rises above 42% without a corresponding equity raise, or if Keppel Ltd formally reduces its strategic ownership stake in Keppel DC REIT Management Pte. Ltd. below a controlling threshold, signalling diminished sponsor support for the pipeline.
