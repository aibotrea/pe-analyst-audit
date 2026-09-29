# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-09-29_equity_reit_v1@1.0_c0f075892c1c`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-29
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Keppel DC REIT (AJBU.SI) is Singapore's largest listed data centre REIT, offering structurally differentiated exposure to AI and cloud infrastructure demand through a diversified portfolio of ~25+ data centres across Singapore, Australia, Europe, Malaysia, China, and now Japan. Q1 2026 DPU growth of 13.2% YoY and H1 2026 earnings confirming stronger performance validate the portfolio's income growth trajectory. The trailing forward yield of ~5.37% at SGD 2.11 offers a meaningful spread over the 4.1% T-bill rate, supported by a strong Keppel Ltd sponsor with an active pipeline. PGain of 85.4% from the Ornstein-Uhlenbeck Monte Carlo simulation and CAPM alpha of 8.28% support above-average conviction, with a one-step qualitative override applied reflecting limited AFFO coverage disclosure in available filings.

## Quantitative Chain

- E(R): 0.1040
- Std dev: 0.0983
- P-gain: 0.8539
- CAPM alpha: 0.0828
- Beta: 0.2173
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Occupancy declines on hyperscaler lease non-renewals or data centre oversupply in Singapore/Europe; DPU growth flat (0%) or negative; cap rate expansion of 50bps compresses NAV; SGD strength and higher-for-longer US rates pressure refinancing costs; Japan acquisitions delayed or dilutive; gearing approaches 43% limiting future capital deployment.
- **base**: E(R)=0.1040
  - Central case as built in chain: distribution yield 5.37%, DPU growth 5.0% supported by AI/cloud demand and Japan acquisitions, flat multiple, gearing ~38%, occupancy stable above 95%.
- **bull**: E(R)=0.2200
  - DPU growth accelerates to 10%+ driven by hyperscaler demand surge and accretive Japan/European acquisitions; cap rate compression on data centre scarcity premium; multiple expansion as AI infrastructure cycle intensifies; dividend yield rerates toward 4.5% (price ~S$2.52); gearing managed below 37%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0537 (Cat A) — Q1 2026 actual DPU of S$0.02833 (announced April 2026; +13.2% YoY). Annualised to S$0.1133/unit. Divided by closing price SGD 2.110 on 2026-09-29 gives trailing forward yield of 5.37%. Observed published quarterly DPU figure.
- `dpu_growth_3yr` = 0.05 (Cat C) — Forward DPU growth assumed at 5.0% p.a. Basis: Q1 2026 DPU grew 13.2% YoY; H1 2026 earnings call confirmed stronger performance; two Japan data centre acquisitions announced September 2026 expected to be yield-accretive; AI/cloud structural tailwinds supporting data centre leasing demand. Sensitivity tested in scenario analysis (bear: 0%, bull: 10%).
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumption. Data centre REITs trade at a premium to broad S-REIT universe; with sector already pricing in AI tailwinds and price near short-term lows (SGD 2.11), assumption is flat cap rate / flat P/NAV multiple over 12 months. Sensitivity in scenario analysis.
- `gearing_estimate` = 0.38 (Cat B) — Estimated aggregate leverage ~38% based on historical Keppel DC REIT reported gearing (~35-40% range) and active refinancing activity (loan facilities + green bonds announced 21-Sep-2026 and 29-Sep-2026, AJBU.SI filings dated 2026-09-21 and 2026-09-29). Below Singapore regulatory threshold of 45% (with credit rating) / 50% (with credit rating and no deterioration). Category B as exact current gearing not confirmed in available filing bodies.
- `affo_coverage` = estimated_above_1x (Cat B) — Distribution coverage estimated above 1.0x AFFO based on data centre REIT sector norms and Q1 2026 DPU growth of +13.2% implying growing income base. Specific AFFO figure not available in retrieved filing bodies; distribution_coverage gate set to info with one-step override applied as data-gap precaution.
- `japan_acquisitions` = two_data_centres_accretive (Cat B) — Keppel DC REIT announced acquisition of two data centres in Japan (news dated 2026-09-01). Assets expected to be yield-accretive and expand the geographic diversification of the portfolio. Specific acquisition yield not confirmed in retrieved filings; treated as a positive qualitative signal for DPU growth.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Computed beta of 0.217 implies low co-movement with the broader APAC REIT index, consistent with data centre REIT differentiated demand drivers.

## Key Risks
- Higher-for-longer global interest rates compressing the yield spread and increasing refinancing costs on debt renewed in 2026-2027
- Hyperscaler customer concentration risk — loss or non-renewal of a major tenant (e.g. large cloud provider) could cause material DPU shortfall
- Data centre oversupply risk in Singapore (power cap uncertainty) or European markets could compress occupancy and rental reversions
- Japan data centre acquisitions executing at unfavorable yields or facing integration delays, diluting short-term DPU
- AFFO coverage data gap — specific coverage ratio not confirmed in available filing bodies; adverse AFFO disclosure would trigger reassessment

## Invalidation Condition
Exit position if Keppel DC REIT reports portfolio occupancy below 93% for two consecutive quarters, or announces DPU for any half-year period that implies annualised DPU below S$0.10 (implying yield coverage erosion), or if aggregate leverage is disclosed above 43% without a clear deleveraging plan, or if Keppel Ltd formally reduces its strategic commitment to the data centre REIT platform through a sponsored divestiture of majority stake in the manager.
