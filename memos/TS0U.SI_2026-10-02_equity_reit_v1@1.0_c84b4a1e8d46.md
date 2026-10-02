# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-10-02_equity_reit_v1@1.0_c84b4a1e8d46`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified (Commercial/Hospitality)
**As of**: 2026-10-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
OUE REIT offers a diversified Singapore commercial and hospitality portfolio with an attractive trailing yield of ~7.3% supported by a strong 1H 2026 DPU outcome (+28.6% YoY). The low beta of 0.26 versus IASP.L (currency-basis caveat applies) signals lower systemic co-movement with the broad APAC REIT universe, while a CAPM alpha of 6.7% suggests meaningful excess return over the required rate at current pricing. The OU Monte Carlo at a 12-month horizon produces a PGain of 72.2%, supporting moderate conviction. The key offset to a stronger conviction score is the uncertainty introduced by the EGM-approved disposal whose scope and value impact are not fully visible in available filings, creating asymmetric downside risk to forward DPU if proceeds are not efficiently redeployed.

## Quantitative Chain

- E(R): 0.0830
- Std dev: 0.1399
- P-gain: 0.7220
- CAPM alpha: 0.0666
- Beta: 0.2559
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - EGM disposal proves value-destructive, reducing income-generating AUM by a meaningful portion; DPU falls below 1H 2026 annualised run-rate; Singapore office vacancies rise and hospitality RevPAR declines on slowing regional tourism. Cap rate expansion of 50bps compresses NAV; yield spread to T-bill narrows. Rate shock scenario where MAS keeps policy tight and SGD strength further pressures tourist arrivals drives occupancy to below 88%.
- **base**: E(R)=0.0830
  - Central case as built in the quantitative chain: annualised DPU yield ~7.3%, sustainable forward DPU growth of 2.0%, and modest -1.0% multiple contraction. Singapore office occupancy stable at ~90-92%, hospitality assets deliver steady RevPAR. Disposal proceeds deployed or returned to unitholders at fair value. Gearing remains within MAS 45% limit.
- **bull**: E(R)=0.1900
  - Disposal proceeds are recycled into higher-yielding acquisitions, OUE sponsor injects additional pipeline assets accretively above 6% cap rate. Singapore commercial rents see positive reversion on tight Grade A supply; Hilton Orchard occupancy recovers to cycle highs. Rate expectations ease in 2H 2026, compressing cap rates and supporting NAV re-rating. DPU growth exceeds 5% YoY on accretive deployment.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.073 (Cat A) — Annualised DPU of SGD 0.0252 (2x 1H 2026 DPU of 1.26 cents as reported 22 Jul 2026) divided by closing price of SGD 0.345 on 2026-10-02. Both DPU and price are observed public data.
- `dpu_growth_3yr` = 0.02 (Cat C) — 1H 2026 DPU of 1.26 cents was +28.6% YoY (reported 22 Jul 2026), but the elevated figure is partly attributed to post-restructuring and disposal-related income. Forward sustainable DPU growth estimated at +2.0% p.a., reflecting modest organic rental reversion in Singapore commercial and hospitality assets. The EGM disposal (TS0U.SI 2026-08-13 ANNC) introduces downside risk; sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Assumed -1.0% multiple contraction contribution given OUE REIT continues to trade at a discount to NAV, higher-for-longer rate environment in Singapore, and AUM headwinds from the EGM-approved disposal (TS0U.SI 2026-08-13 ANNC). Scenario-tested in bear and bull cases.
- `egm_disposal_event` = disclosed (Cat B) — EGM held 4 September 2026 (minutes filed TS0U.SI 2026-10-02 ANNC) convened for, inter alia, a disposal resolution ('Despa...' text truncated in circular TS0U.SI 2026-08-13 ANNC). The nature and proceeds of the disposal are not fully visible from the truncated filing body, creating uncertainty around forward DPU and gearing. This uncertainty is reflected in a -1 gate override on distribution_coverage.
- `gresb_rating` = 88.7 (Cat A) — OUE REIT retained Four-Star GRESB rating with a record score of 88.7 in 2026, as announced TS0U.SI 2026-10-01 ANNC. Supports ESG quality assessment under asset_quality_concentration gate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- EGM-approved disposal (TS0U.SI 2026-08-13 ANNC) reduces AUM and DPU if proceeds are not quickly redeployed at equivalent or better yields
- Higher-for-longer SGD interest rates compressing yield spreads and increasing refinancing costs on OUE REIT's debt stack
- Singapore office market softening and/or hospitality RevPAR decline on weaker regional tourism reducing NPI for commercial and hotel assets
- OUE Limited sponsor capacity constraints — OUE is a smaller sponsor relative to Tier-1 peers, limiting pipeline injection optionality
- Elevated unit-level volatility (20.6% annualised) relative to the yield received creates unfavourable risk-adjusted return if macro conditions deteriorate

## Invalidation Condition
Exit or reduce position if OUE REIT announces post-disposal DPU guidance more than 15% below the annualised 1H 2026 run-rate of SGD 0.0252 per unit, or if aggregate leverage as reported in the next semi-annual financial statements breaches 42% (signalling limited headroom to the 45% MAS regulatory limit), or if Singapore Grade A office occupancy across the OUE commercial portfolio falls below 88% for two consecutive reporting periods without a credible reversion plan disclosed by management.
