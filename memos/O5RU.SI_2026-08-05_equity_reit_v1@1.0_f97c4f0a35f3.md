# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-08-05_equity_reit_v1@1.0_f97c4f0a35f3`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-08-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT is a Singapore-listed industrial and logistics REIT with a growing Australian presence, offering a trailing annualised DPU yield of ~5.9% at the current price of SGD 1.58. The same-day completion of the Perth industrial acquisition (Bushmead/Stirling Crescent) and the imminent redemption of S$250M in 5.375% perpetual securities represent concrete near-term catalysts for income enhancement. Beta of 0.255 versus IASP.L (currency-basis caveat applies) implies relatively low systematic exposure to the GBP-denominated APAC REIT benchmark, consistent with the REIT's mid-cap industrial focus. The OU Monte Carlo produces a simulated return of 7.86% with a PGain of 77.8%, supporting a base case of moderate conviction; however, a -1 gate override is applied for the imminent CEO transition (Russell Ng ceasing 30 September 2026), constraining the position ceiling to 5% of portfolio.

## Quantitative Chain

- E(R): 0.0791
- Std dev: 0.1027
- P-gain: 0.7781
- CAPM alpha: 0.0607
- Beta: 0.2553
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - CEO transition disrupts execution of Australian growth pipeline; incoming CEO delays or reprices Bushmead/Stirling Crescent assets. Occupancy softens to 91% on Singapore portfolio amid global logistics demand slowdown. SGD rates remain elevated (SORA above 3.5%), compressing yield spread. Cap rates expand 25–30bps. DPU coverage drops below 1.0x AFFO requiring payout cut. Perp redemption proceeds not fully recycled, dilutive to NPI yield.
- **base**: E(R)=0.0790
  - Central case as built: DPU yield 5.91%, growth 2.0% p.a., multiple change flat. Perth acquisition (Bushmead/Stirling Crescent) ramps to full occupancy within 12 months. Perp redemption reduces distribution burden post-Sep 2026. CEO transition orderly with successor named. Singapore occupancy stable at ~95%. Cap rates flat.
- **bull**: E(R)=0.1800
  - New CEO accelerates AIMS sponsor pipeline with accretive acquisitions at 6%+ NPI yields. Perth industrial demand surges on resource-sector tailwinds, driving portfolio revaluation and cap rate compression of 15–20bps. DPU growth beats at 4–5% p.a. Equity re-rating closes discount to NAV, delivering multiple expansion of ~5%. Perp redemption savings fully pass through to DPU uplift in FY2028 guidance.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.0591 (Cat A) — 1Q FY2027 DPU of 2.337 SGD cents (period 1 Apr–30 Jun 2026) filed by AIMS APAC REIT Management Limited on 2026-07-30 (ANNC: First Quarter FY2027 Business Update) and confirmed in CACT scrip/distribution filing SG260730DVOPABD9. Annualised at 4× = 9.348 cents divided by closing price of SGD 1.58 on 2026-08-05 yields 5.91%.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth of 2.0% p.a. assumed, underpinned by: (i) completion of Perth industrial acquisition (398 Bushmead Road and 286 Stirling Crescent, Hazelmere) announced 2026-08-05 adding rental income; (ii) 'steady DPU growth on broad-based basis' per Beansprout/market coverage of 1Q FY2027 update; (iii) partial offset from CEO transition uncertainty (Russell Ng ceasing 30 Sep 2026). Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple-change assumption. Positive catalyst from redemption of S$250M 5.375% perpetual securities (call exercised, pay date 1 Sep 2026, per filing 2026-07-31 CACT) is offset near-term by CEO transition and equity dilution from the preceding fund raising. Cap rate environment assumed flat over 12-month horizon.
- `perp_redemption` = S$250M 5.375% redeemed 2026-09-01 (Cat A) — Mandatory early redemption of AIMS APAC REIT S$250M 5.375% Subordinated Perpetual Securities confirmed in SGX CACT filing dated 2026-07-31 (Reference SG260731MCALFMQ8). Pay date 1 September 2026. Reduces perpetual distribution drag on distributable income post-redemption.
- `ceo_transition` = CEO stepping down 2026-09-30 (Cat A) — Cessation of Russell Ng Keh Yang as CEO of AIMS APAC REIT Management Limited effective 30 September 2026, disclosed in SGX announcement dated 2026-07-24 (Reference SG260724OTHRX8DI). No unresolved board differences noted. Successor appointment disclosed in same filing. Flagged as management transition risk, triggering -1 gate override.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise. Low beta of 0.255 may partly reflect SGD/GBP basis divergence rather than genuine low co-movement with APAC property.

## Key Risks
- CEO transition risk: Russell Ng ceasing as CEO on 30 September 2026; successor execution track record unproven in the near term, particularly for the Australian portfolio expansion strategy.
- Perpetual securities redemption execution: S$250M perp redeemed 1 September 2026 — refinancing or equity recycling at worse-than-expected terms could erode distributable income.
- Australian FX and cap-rate exposure: Perth industrial assets introduce AUD/SGD translation risk and regional cap-rate sensitivity to RBA policy, adding basis to an already GBP-denominated benchmark (IASP.L currency-basis caveat).
- Higher-for-longer SGD/USD rates: SORA elevation compresses the yield spread between O5RU's ~5.9% DPU yield and the 3.74% risk-free rate, reducing relative attractiveness.
- Distribution coverage not fully verified: AFFO coverage ratio not explicitly stated in available truncated filing bodies; risk that payout exceeds sustainable AFFO in a softer NPI environment.

## Invalidation Condition
Exit or reduce position if: (i) DPU coverage falls below 1.0x AFFO for two consecutive quarterly reporting periods; (ii) aggregate leverage ratio breaches 45% of deposited property value (Singapore regulatory limit 50%); (iii) the incoming CEO materially revises the Australian acquisition strategy or disposes of core Singapore assets at below-book values; or (iv) any quarter's DPU is cut by more than 5% year-on-year absent a rights issue or property disposal with explicit reinvestment rationale.
