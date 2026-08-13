# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-08-13_equity_reit_v1@1.0_a305f8e02795`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified
**As of**: 2026-08-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
OUE REIT offers a high trailing distribution yield of ~7.2% at SGD 0.35, underpinned by a recovering hospitality segment (1H 2026 DPU +28.6% YoY) and a stabilising office portfolio including OUE Bayfront and OUE Downtown in Singapore's CBD. The low beta of 0.29 versus IASP.L (currency-basis caveat applies) reflects idiosyncratic exposure to Singapore office and hospitality rather than broad APAC REIT market cyclicality. A CAPM alpha of 7.3% and OU Monte Carlo PGain of 71.8% support a moderate conviction position, tempered by an EGM filed on the analysis date indicating a pending corporate action whose financial impact has not been fully disclosed. The sponsor's partial reduction in unitholding warrants monitoring but is partially offset by the manager's fee-in-units alignment mechanism.

## Quantitative Chain

- E(R): 0.0870
- Std dev: 0.1496
- P-gain: 0.7180
- CAPM alpha: 0.0732
- Beta: 0.2927
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - EGM results in a dilutive acquisition or large equity fundraise; gearing rises above 45% MAS limit forcing deleveraging disposals at distressed prices. Hospitality RevPAR declines 10% on weaker Singapore tourism or global recession. Office occupancy slips to sub-88% on Singapore CBD oversupply. DPU coverage falls below 1.0x AFFO. Cap rate expansion of 50bps across portfolio. Sponsor continues reducing unitholding creating overhang.
- **base**: E(R)=0.0870
  - Central case as modelled: trailing DPU yield of 7.17%, forward DPU growth 2.5%, multiple change -1.0% reflecting EGM uncertainty. Office occupancy stable at ~90%, hospitality RevPAR grows modestly. Gearing remains ~41%, within MAS limits. Sydney acquisition contributes incrementally to income from H2 2026.
- **bull**: E(R)=0.2200
  - EGM approved transaction proves accretive at yield-on-cost above 6%. Hospitality segment maintains strong RevPAR growth driven by Singapore tourism acceleration (F1, major conferences). Singapore office market tightens, pushing office occupancy above 95% and enabling positive rental reversion. Interest rate cuts allow refinancing at lower cost of debt, boosting DPU by an additional 5-8%. OUE Limited sponsor re-rates REIT or adds pipeline assets, compressing yield to 6% implied price re-rating.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info [override_applied=-1]
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0717 (Cat A) — Trailing annualised DPU of SGD 0.0251 (2H 2025: 1.25 cents per news dated 2026-01-26; 1H 2026: 1.26 cents per news dated 2026-07-22) divided by closing price of SGD 0.35 on 2026-08-13. Observed published DPU figures; price observed from live feed.
- `dpu_growth_forward` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumes continued but moderating hospitality recovery and stable office occupancy. 1H 2026 DPU grew 28.6% YoY (base effect from post-COVID hospitality rebound) and 2H 2025 DPU grew 10.6% YoY; forward growth rate is conservatively anchored at 2.5% as peak hospitality uplift normalises. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Modest negative multiple-change assumption of -1.0% reflects corporate event uncertainty from EGM filed 2026-08-13 (TS0U.SI 2026-08-13 ANNC: Extraordinary/Special General Meeting), which references an undisclosed circular to unitholders and a potential asset acquisition/disposal (Rule 706A filing 2026-07-22). Execution risk and dilution risk from corporate action are not yet priced by market.
- `gearing_estimate` = 0.41 (Cat B) — Estimated aggregate leverage ~41% based on known OUE REIT profile and recent Sydney commercial tower stake acquisition (EdgeProp, 2026-04-21). Exact gearing ratio not sourced from a filed financial statement at as_of date; treated as Category B. Within MAS 45% regulatory limit.
- `sponsor_commitment` = reducing (Cat B) — OUE Limited filed a Form 3 (Changes in Interest of Substantial Unitholder) on 2026-07-27 (TS0U.SI 2026-07-27 ANNC). Reduction in sponsor unitholding is a mild negative signal on sponsor commitment to the REIT. Manager fees continue to be paid in units (2026-07-27 fee-in-units filing), which provides partial alignment.
- `ipт_lease_renewal` = disclosed (Cat A) — Interested Person Transaction: lease renewal with Healthway Medical Corporation Limited at OUE Downtown 2 (TS0U.SI 2026-07-28 ANNC). Indicates active lease management at key office asset. This is an IPT subject to SGX disclosure rules; no further financial quantum available from headline.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP currency basis. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- EGM corporate action (2026-08-13) may result in a dilutive equity fundraise or acquisition at sub-optimal yield-on-cost, destroying NAV per unit
- Hospitality RevPAR normalisation as Singapore post-COVID recovery matures, compressing the 28.6% DPU growth trajectory toward mid-single-digits
- OUE Limited sponsor reducing unitholding (Form 3 filing 2026-07-27) signals reduced sponsor commitment and creates unit overhang
- Gearing estimated at ~41% leaves limited headroom below the 45% MAS limit; rising interest rates or asset devaluation could trigger regulatory concerns
- Singapore CBD office supply pipeline and hybrid work adoption risk occupancy and rental reversion for the office sub-portfolio

## Invalidation Condition
Exit if: (1) EGM-approved transaction reveals gearing rising above 45% MAS regulatory limit post-completion, or yield-on-cost below 5% for any acquired asset; (2) two consecutive semi-annual DPU prints show year-on-year declines of more than 10%; (3) OUE Limited's unitholding falls below 30% indicating a structural sponsor exit; or (4) hospitality RevPAR for Hilton Singapore Orchard or Crowne Plaza Changi Airport declines more than 15% for two consecutive reporting periods.
