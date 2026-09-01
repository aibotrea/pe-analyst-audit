# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-09-01_equity_reit_v1@1.0_9a081f27a32d`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Office
**As of**: 2026-09-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus (DXS.AX) is Australia's largest pure-play office REIT offering a ~4.5% distribution yield at current prices, supported by an active on-market buy-back programme and an internally managed structure with disciplined balance sheet (gearing ~37%, within the AU A-REIT <40% convention). The OU Monte Carlo simulation (annualised sigma 20.1%, 12-month horizon) produces a simulated return of 5.4% and PGain of 65.5%, indicating a marginally positive but uncertain expected outcome at the 12-month horizon. CAPM alpha of +6.5% versus IASP.L appears favourable but is materially distorted by the benchmark's own -4.8% annualised 5-year return and AUD/GBP currency basis noise, and is treated as a supporting rather than primary input. Asset quality concentration risk in Australian CBD office — a sector facing persistent structural WFH-driven vacancy headwinds — triggers a one-step conviction downgrade, resulting in a Low conviction score of 2 with a maximum position size of 3.0%.

## Quantitative Chain

- E(R): 0.0550
- Std dev: 0.1365
- P-gain: 0.6548
- CAPM alpha: 0.0646
- Beta: 0.5537
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1000
  - CBD office vacancy rises materially as WFH norms entrench and large tenant expiries are not renewed; DPU cut of approximately 15% as AFFO coverage falls below 1.0x; RBA holds cash rate above 4.0% compressing the yield spread; cap rate expansion of 50bps forces further NTA write-downs pushing look-through gearing above 40%; potential capital raising or DRP dilution required.
- **base**: E(R)=0.0550
  - Central case as built in chain: 4.5% distribution yield, 1.5% DPU growth, -0.5% multiple drag; occupancy stable at approximately 93%, gearing approximately 37%, RBA easing modestly through 2026-2027 providing modest cap-rate relief; on-market buy-back continues accretively.
- **bull**: E(R)=0.1800
  - RBA cuts accelerate compressing risk-free rates and supporting cap rate tightening; premium office leasing demand surges from financial services and technology sector re-occupation; DPU growth 3.5% p.a., occupancy improves above 95%, NAV re-rating closes discount to book value; buy-back at accretive prices amplifies per-unit DPU.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.045 (Cat A) — Trailing DPU yield estimated from publicly announced 30 June 2026 distribution payment (ASX filing 2026-08-28, DISTRIBUTION ANNOUNCEMENT) and market price of AUD 5.89 on 2026-09-01. DXS pays semi-annual distributions; FY2026 full-year DPU estimated at approximately 26.5 cpu yielding approximately 4.5% at current price.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed based on modest Australian premium office market recovery: CBD vacancy stabilisation, positive leasing spreads on renewals in Sydney and Melbourne, and partial offset from assets under repositioning. Sensitivity: bear -2.0% p.a., bull +3.5% p.a. No consensus Bloomberg forecast was available at as_of date.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% contribution from multiple compression reflecting: RBA cash rates remaining elevated versus pre-2022 levels, structural WFH demand headwinds on office cap rates, partially offset by on-market buy-back providing per-unit DPU accretion. Cap rate sensitivity is primary risk to this assumption.
- `gearing_ratio` = 0.37 (Cat A) — Dexus FY2026 gearing publicly disclosed at approximately 37% look-through basis, within the Australian A-REIT convention limit of less than 40%. Active on-market buy-back programme confirmed via ASX announcements for DXS on 2026-08-27 and 2026-08-31, consistent with balance-sheet confidence.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same iasp and currency noise and should not be used as a standalone conviction signal.

## Key Risks
- Structural work-from-home demand destruction causing persistent CBD office vacancy, impairing leasing spreads and pushing DPU AFFO coverage below 1.0x for multiple consecutive periods.
- Cap rate expansion driven by elevated RBA cash rates or global real estate re-pricing, leading to further NTA write-downs and potential covenant stress if look-through gearing breaches 40%.
- Tenant concentration risk: loss of a major anchor tenant in a flagship Sydney or Melbourne CBD asset could materially impair occupancy and income within a single reporting period.
- AUD/GBP currency basis noise embedded in computed beta (0.554) against the IASP.L benchmark renders the CAPM alpha estimate unreliable as a standalone conviction input.
- Development and repositioning pipeline execution risk: delays or cost overruns in Dexus's active development book could impair near-term FFO and temporarily increase leverage beyond the 40% convention limit.

## Invalidation Condition
Exit position if DXS reported portfolio occupancy falls below 90% for two consecutive half-year reporting periods, or if DPU coverage on an AFFO basis falls below 1.0x for two consecutive periods, or if look-through gearing rises above 40% without a credible publicly disclosed deleveraging plan, or if Dexus announces suspension or a material reduction (greater than 15%) of the semi-annual distribution without a specific asset-disposal recovery pathway.
