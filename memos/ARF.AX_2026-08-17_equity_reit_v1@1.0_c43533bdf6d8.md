# Specialist Memo — ARF.AX

**Memo ID**: `ARF.AX_2026-08-17_equity_reit_v1@1.0_c43533bdf6d8`
**Ticker**: ARF.AX (Arena REIT)
**Market**: Australia
**Sector**: Social Infrastructure/Childcare
**As of**: 2026-08-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Arena REIT is a specialist Australian childcare-focused REIT under acute stress following a rent relief request by Edge Early Learning — one of its key tenants — which triggered a ~28% share price decline over 10-11 August 2026 and a postponement of FY2026 annual results. At AUD 2.34, the stressed distribution yield of approximately 6.4% (based on a haircut DPU estimate) offers nominal income compensation, but significant binary uncertainty remains over the final settlement terms, the depth of any DPU cut, and broader childcare sector financial health. The OU Monte Carlo simulation produces a PGain of 60.0% but at a simulation standard deviation of 22.9%, reflecting elevated dispersion of outcomes; two qualitative gate failures on distribution_coverage and tenant concentration drive the conviction score to 1 (Speculative), capping maximum position at 1.0% pending FY2026 results resolution.

## Quantitative Chain

- E(R): 0.0590
- Std dev: 0.2291
- P-gain: 0.5998
- CAPM alpha: 0.0714
- Beta: 0.6165
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.2500
  - Edge Early Learning enters administration rather than a negotiated settlement; Arena must re-tenant 10-15% of GLA at below-market initial rents; FY2026 DPU cut exceeds 25% to ~12.5 cpu; cap rates expand 50bps driving NTA write-downs; gearing rises toward 33%; contagion risk from other childcare operators compounds the stress.
- **base**: E(R)=0.0590
  - Negotiated rent relief reduces DPU ~12% to ~15.0 cpu; FY2026 results released late August 2026 with revised guidance; price stabilises near AUD 2.30-2.40; cap rates flat; 1% organic DPU growth from remainder of portfolio; no further tenant defaults.
- **bull**: E(R)=0.2200
  - Edge Early Learning rent relief resolves as short-term deferral with near-full income recovery; FY2026 DPU maintained near ~16.5 cpu; market re-rates to AUD 2.80-3.00; childcare sector demand remains structurally supported by Australian government subsidies; development pipeline resumes accretive growth.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0641 (Cat B) — Stressed DPU estimate of ~15.0 cpu applied to current price of AUD 2.34 (observed closing price 2026-08-17), reflecting an approximate 12% haircut to FY2025 consensus DPU of ~17.0 cpu. Haircut reflects Edge Early Learning rent relief request (ASX price-sensitive announcement 2026-08-09). Derivation is analyst estimate; Category B.
- `dpu_growth_3yr` = 0.01 (Cat C) — Minimal 1.0% p.a. organic DPU growth assumed given unresolved Edge Early Learning rent relief and postponed FY2026 results. Upside scenario assumes swift resolution restoring near-full DPU; bear case assumes further deterioration. Sensitivity tested across all three scenarios.
- `multiple_change` = -0.015 (Cat C) — Slight negative multiple change of -1.5% applied as cap rate expansion assumption. Reflects ongoing uncertainty from postponed FY2026 results (ASX announcement 2026-08-17 revised reporting date) and potential for further DPU guidance downside. A 50bps cap rate move changes E(R) by approximately 1.5%.
- `edge_el_tenant_event` = material_negative (Cat A) — Edge Early Learning confirmed as key childcare tenant requesting rent relief; FY2026 annual results postponed per ASX price-sensitive announcement 2026-08-09. Stock declined ~28% over 10-11 August 2026 from ~AUD 3.28 to ~AUD 2.24; observable public announcement and price action classified Category A.
- `gearing_ratio` = 0.25 (Cat B) — Estimated gearing ~25% based on Arena REIT's historically conservative balance sheet profile. Exact FY2026 figure unavailable as results are postponed; ASX filing body capture unavailable (ASX Phase 01 v3.3 §4 — body capture parked). Classified Category B pending confirmed FY2026 disclosure.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same iasp currency noise.

## Key Risks
- Edge Early Learning enters administration requiring re-tenanting of a material portfolio share at reduced initial rents, with prolonged income drag
- FY2026 DPU guidance reveals a cut deeper than the ~12% stressed assumption, triggering renewed price de-rating
- Childcare sector contagion: other operators in Arena's tenant base face similar financial stress from subsidy changes or sector overcapacity
- Higher-for-longer Australian interest rates widen funding spreads and elevate refinancing risk as gearing rises
- Elevated 33.7% historical volatility (incorporating the crash event) amplifies downside scenario outcomes within the 12-month horizon

## Invalidation Condition
Exit or reduce below 0.5% if Edge Early Learning formally enters voluntary administration without a committed replacement tenant, or if FY2026 DPU guidance confirms a cut exceeding 20% versus FY2025 actuals upon results release, or if gearing on revised FY2026 portfolio valuations is reported above 35%, or if a second top-five tenant requests rent relief or deferral within 90 days of the FY2026 results publication date.
