# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-09-04_equity_reit_v1@1.0_483884c3090e`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified Office/Hospitality
**As of**: 2026-09-04
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
OUE REIT offers exposure to Singapore CBD office and hospitality assets at a meaningful discount to estimated NAV, with a distribution yield of approximately 5.0% that provides a spread over the 3.75% T-bill rate. However, an active EGM-linked corporate action (likely an asset disposal), combined with news coverage flagging DPU risk from asset sales, clouds the near-term distribution outlook and warrants caution. Beta of 0.26 versus IASP.L (currency-basis caveat applies) implies lower systematic risk relative to the APAC REIT benchmark, and CAPM alpha of 2.4% is modest but positive. An OU Monte Carlo PGain of 61% — just above the random-walk threshold — combined with elevated annualised volatility of 20.7% reflects the asymmetric risk profile; conviction is calibrated at Low pending resolution of the disposal corporate action.

## Quantitative Chain

- E(R): 0.0400
- Std dev: 0.1407
- P-gain: 0.6101
- CAPM alpha: 0.0244
- Beta: 0.2614
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1000
  - Asset disposal is executed at a material discount to book value, triggering a write-down; DPU is cut by 15-20% due to loss of NPI from divested asset and distributable income shortfall. Singapore CBD office vacancy rises as tech sector contracts, compressing occupancy at OUE Downtown and One Raffles Place below 90%. Cap rate expansion of 25-50bps driven by higher-for-longer SGD SORA rates narrows the NAV and pressures the unit price toward SGD 0.28-0.30.
- **base**: E(R)=0.0400
  - Central case as modelled: distribution yield ~5.0%, DPU growth -1.0% reflecting modest NPI headwind from asset portfolio repositioning, multiple flat. Office occupancy stable at 93-95% across Singapore properties. Gearing remains within regulatory limit (~38%). SORA rates stabilise, yield spread versus risk-free narrows marginally.
- **bull**: E(R)=0.1800
  - Asset disposal completes at or above book value, proceeds used to reduce debt; lower gearing enhances DPU coverage and signals balance sheet discipline. Singapore CBD office demand strengthens driven by financial services and family office activity. OUE Mandarin hospitality assets benefit from sustained tourist arrivals. Unit price re-rates toward SGD 0.40-0.42, delivering ~16-18% total return including distribution yield.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.05 (Cat B) — Estimated trailing distribution yield derived from current unit price of SGD 0.355 and estimated annualised DPU of approximately SGD 0.0178/unit for FY2025, consistent with historical OUE REIT payout range. Classified Category B as DPU figure is an analyst estimate; no published FY2025 full-year DPU figure was available in the retrieved filings. Filing bodies retrieved from SGX for TS0U.SI (2026-07-27 to 2026-08-25) contained only corporate governance and engagement announcements with no DPU or financial metrics.
- `dpu_growth_assumption` = -0.01 (Cat C) — Negative 1.0% DPU growth assumed over 12-month horizon. Rationale: (1) News headline (Jul 2026) identified OUE REIT among Singapore REITs selling assets that may impact dividends; (2) an EGM was convened in August 2026 whose circular referenced a 'Despa...' (likely disposal) corporate action; (3) asset divestments typically reduce NPI contribution even if gearing benefits partially offset. Sensitivity: in bull case, disposal proceeds reduce debt and DPU stabilises flat.
- `multiple_change` = 0.0 (Cat C) — No re-rating assumed at the 12-month horizon. OUE REIT is trading in the SGD 0.35-0.37 range, broadly consistent with its recent 6-month trading band. Without a confirmed disposal price or accretive acquisition pipeline, no justified basis for NAV multiple expansion or compression beyond ±5%.
- `egm_disposal_risk` = disclosed (Cat B) — EGM convened 13 August 2026 (TS0U.SI 2026-08-13 ANNC) with circular referencing what appears to be a disposal resolution (body_truncated=True; full text reads '4. Announcement on Despa...'). SIAS Q&A responses published 28 August 2026 (TS0U.SI 2026-08-13 REPL filing). Nature and completion of the asset disposal is not confirmed from available filing bodies; treated as a qualitative risk in gate assessment and bear scenario.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. The currency basis between SGD and GBP introduces noise into the beta estimate and, by extension, into the CAPM alpha. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Asset disposal completing below book value, triggering NAV write-down and DPU cut that reduces yield support at current unit price.
- Higher-for-longer Singapore SORA rates compressing the yield spread and increasing refinancing costs on OUE REIT's floating-rate debt tranche.
- Singapore CBD office demand softening as financial sector or tech-tenant demand moderates, particularly impacting One Raffles Place and OUE Downtown occupancy.
- Concentrated hospitality exposure (Mandarin Orchard/Gallery) to discretionary tourism and MICE demand, which is susceptible to geopolitical disruption or FX headwinds to inbound arrivals.
- Corporate governance uncertainty: EGM convened August 2026 with SIAS Q&A required, and OUE Limited changes in substantial unitholder interest, indicate active sponsor activity that may not align with minority unitholder interests.

## Invalidation Condition
Exit position if: (1) the asset disposal announced via EGM is confirmed at a price more than 5% below independently appraised book value, or (2) DPU for any semi-annual period falls more than 15% below the prior corresponding period without explicit disclosure of an offsetting AUM growth catalyst, or (3) aggregate leverage ratio breaches 42% of deposited property value on a sustained basis, or (4) OUE Limited reduces its unitholding below 30% without a credible pipeline commitment replacing its sponsor role.
