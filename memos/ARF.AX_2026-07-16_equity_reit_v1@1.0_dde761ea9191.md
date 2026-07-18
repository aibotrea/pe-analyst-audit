# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-07-16_equity_reit_v1@1.0_dde761ea9191`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Social Infrastructure / Childcare & Healthcare
**As of**: 2026-07-16
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Arena REIT (ARF.AX) offers defensive, long-duration social infrastructure exposure through a portfolio of early learning centres and healthcare properties under triple-net, CPI-linked leases with WALEs exceeding 15 years and near-100% occupancy. A trailing distribution yield of approximately 5.1% at the current AUD 3.30 price provides a meaningful income base, with 2.0% p.a. DPU growth expected from embedded lease escalators and a modest development pipeline. Beta of 0.525 versus IASP.L (currency-basis caveat applies) indicates below-average market co-movement relative to broader APAC REITs. The OU Monte Carlo PGain of 69.3% at a 12-month horizon supports a moderate conviction rating, tempered by elevated historical volatility of 19.1% and an unfavourable CAPM benchmark environment where IASP.L has delivered a negative 5-year trailing return.

## Quantitative Chain

- E(R): 0.0660
- Std dev: 0.1297
- P-gain: 0.6930
- CAPM alpha: 0.0670
- Beta: 0.5251
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA holds cash rate higher for longer, driving 50bps cap rate expansion and a 8-10% decline in NTA. Childcare sector demand softens due to government subsidy policy changes or falling birth rates, pushing occupancy below 97%. DPU coverage drops below 1.0x AFFO if development pipeline is delayed or over-capitalised. This bear case also captures a stagflation or rate-shock scenario where rising inflation is accompanied by sustained monetary tightening, materially compressing REIT multiples across the ASX.
- **base**: E(R)=0.0660
  - Central case as built in chain: distribution yield ~5.1%, DPU growth 2.0% from CPI-linked escalators, modest -0.5% multiple headwind. Occupancy remains near 100%. Gearing stays ~28%, within regulatory limit. RBA begins easing gradually, providing mild tailwind to REIT multiples in H2 2026.
- **bull**: E(R)=0.1800
  - RBA cuts cash rate by 75bps+ in 2026, driving multiple re-rating across A-REITs. Arena secures accretive development completions at 6%+ yields, lifting DPU growth to 4%+ p.a. Childcare policy tailwinds (increased government subsidies boosting occupancy and operator credit) support premium valuations. Cap rate compression of 25-30bps drives ~10% NTA uplift.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.051 (Cat A) — Trailing annualised DPU of approximately AUD 0.168/unit implied by publicly declared quarterly distributions, divided by last traded price of AUD 3.30 on 2026-07-16. Distribution announcement headline confirmed via ASX filing dated 2026-06-18 (DISTRIBUTION ANNOUNCEMENT, Quarterly distribution, price_sensitive=True). Body capture failed for that filing; yield inferred from last-known published DPU and current market price.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. underpinned by CPI-linked rent escalators embedded in long-dated childcare and healthcare leases (WALE typically >15 years for Arena REIT), combined with modest external growth from development pipeline. Sensitivity tested across bear/base/bull scenarios. Higher-than-CPI growth would require accretive acquisitions at scale.
- `multiple_change` = -0.005 (Cat C) — Assumed modest cap rate expansion of ~5bps (translating to -0.5% multiple headwind) reflecting Australian rate environment where RBA has held cash rate elevated, compressing REIT multiples modestly from peak. Central case holds multiples broadly flat with a slight negative tilt.
- `gearing_level` = 0.28 (Cat B) — Arena REIT's gearing estimated at approximately 28% (look-through NTA basis) based on historically disclosed balance sheet structure. Australian A-REIT regulatory convention sets a practical ceiling of ~40%. Well within limit. Filing body for June 2026 quarterly report unavailable (body_unavailable=True); estimate based on prior-period disclosures and market commentary.
- `occupancy` = 1.0 (Cat B) — Arena REIT has consistently reported near-100% occupancy across its early learning centre and healthcare portfolio, driven by long-term triple-net leases. Kalkine article dated 2026-05-13 references 'high-occupancy' status. Direct filing confirmation unavailable due to ASX body capture failures on recent periodic reports.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Higher-for-longer RBA cash rate compressing AUD REIT multiples and widening the risk premium required by investors, reducing NTA and total return.
- Government policy changes to childcare subsidies in Australia that could impair operator profitability, tenant credit quality, and ultimately occupancy or lease renewal rates.
- Development pipeline execution risk: cost overruns or completion delays on new childcare centres could dilute DPU and compress AFFO coverage below 1.0x.
- Sector concentration: 100% exposure to early learning and healthcare social infrastructure creates idiosyncratic risk if that subsector experiences a regulatory or demand shock.
- ASX filing body capture failures limited direct verification of June 2026 quarterly distribution quantum and market update disclosures — key_assumptions sourced from prior-period data carry higher estimation uncertainty.

## Invalidation Condition
Exit or reduce position if occupancy falls below 97% for two consecutive quarterly reporting periods, or if DPU coverage drops below 1.0x AFFO for two consecutive periods, or if gearing exceeds 35% of total assets without a credible deleveraging plan, or if the Australian government announces material cuts to childcare subsidy programmes that are likely to impair Arena REIT's tenant base credit quality and lease renewal profile.
