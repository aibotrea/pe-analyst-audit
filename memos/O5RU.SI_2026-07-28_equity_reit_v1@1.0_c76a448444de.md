# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-07-28_equity_reit_v1@1.0_c76a448444de`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-07-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers Singapore and Australian industrial/logistics exposure at a trailing distribution yield of ~6.0% on FY2026 DPU of 9.85 cents, providing a meaningful 220bp spread over the current 3.82% T-bill rate. NPI growth of 5.7% in FY2026 and ongoing positive rental reversions underpin a 2.5% forward DPU growth assumption. The OU Monte Carlo simulation at 12 months generates a sim return of 8.5% with a PGain of 79.7%, supporting moderate conviction. The primary near-term overhang is the CEO departure effective 30 September 2026 with no incoming successor yet disclosed, which introduces execution and capital allocation uncertainty and drives a one-step downward gate override from the base quantitative score.

## Quantitative Chain

- E(R): 0.0854
- Std dev: 0.1022
- P-gain: 0.7970
- CAPM alpha: 0.0646
- Beta: 0.2439
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Occupancy falls to 90% as industrial demand softens amid macro slowdown; DPU cut 8-10% as debt refinancing costs spike on higher-for-longer rates; cap rate expansion of 50bps compresses NAV; Australian acquisition proves dilutive due to AUD/SGD weakness; CEO transition disrupts capital allocation strategy.
- **base**: E(R)=0.0850
  - Central case: DPU grows 2.5%, occupancy holds at ~94-95%, cap rates flat, Australian acquisition (Hazelmere, Perth) closes accretively at ~6% yield, CEO transition orderly with new appointment by end-Q3 2026.
- **bull**: E(R)=0.1900
  - Positive rental reversions of 8-10% across Singapore industrial portfolio; Australian acquisition accretive at >6.5% NPI yield; S-REIT sector re-rating on SGD rate cuts compresses cap rates by 25bps; new CEO announcement catalyses investor confidence; DPU grows 4%+ on stronger NPI.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0604 (Cat A) — FY2026 full-year DPU of S$0.0985 (9.85 cents, as reported by The Edge Singapore and Singapore Business Review on 07-May-2026 for the financial year ended 31 March 2026) divided by closing price of SGD 1.63 on 2026-07-28. Observed published number.
- `dpu_growth_forward` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. anchored to: (i) 9M FY2026 DPU up 2.5% YoY (Business Times, 05-Feb-2026); (ii) FY2026 NPI growth of 5.7% providing headroom; (iii) accretive Australian industrial acquisition at Hazelmere, Perth WA announced 09-Jul-2026 (O5RU.SI SGX filing, 2026-07-09, ANNC). Sensitivity tested ±1.5% in scenarios.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumed. Price has rallied ~6.5% from May 2026 lows to SGD 1.63, suggesting market has partially re-rated. No catalyst for material cap rate compression or expansion in the 12-month horizon beyond baseline. Tested at +50bps expansion (bear) and -25bps compression (bull).
- `fy2026_dpu` = 0.0985 (Cat A) — FY2026 full-year DPU of 9.85 cents (financial year ended 31 March 2026), reported up 2.6% year-on-year. Source: The Edge Singapore and Singapore Business Review, 07-May-2026.
- `gearing_leverage` = 0.35 (Cat B) — Estimated aggregate leverage of ~35% based on AIMS APAC REIT's publicly known historical gearing range of 33-37% and no filing-based evidence of breach. MAS regulatory limit for Singapore REITs is 45% (50% with credit rating). No adverse leverage news observed in 365-day filings review. Treated as Category B pending full FY2026 balance sheet confirmation.
- `ceo_transition_risk` = flagged (Cat A) — CEO Russell Ng Keh Yang announced cessation effective 30 September 2026 (O5RU.SI SGX filing 2026-07-24, ANNC). Incoming CEO identity not disclosed in available filings. Creates near-term management transition uncertainty.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. The low beta of 0.244 and low correlation of 0.191 partly reflect the currency basis between SGD and GBP, not just genuine low market sensitivity. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- CEO transition risk: Russell Ng stepping down 30 September 2026 with no disclosed successor; execution of the Australian acquisition pipeline and AUM growth strategy may be disrupted during the handover period.
- Higher-for-longer SGD interest rates compressing the yield spread versus T-bills and increasing refinancing costs on floating-rate debt.
- AUD/SGD FX risk from the growing Australian portfolio (Hazelmere, Perth acquisition); currency weakness could reduce SGD-equivalent distributions.
- Industrial demand slowdown in Singapore if global trade volumes contract, potentially pressuring occupancy rates and rental reversions.
- Aggregate leverage may increase post-Australian acquisition; if gearing rises above 40%, headroom to the 45% MAS limit narrows significantly.

## Invalidation Condition
Exit if: (i) disclosed aggregate leverage exceeds 42% following the Australian acquisition close, reducing headroom to the 45% MAS regulatory cap; or (ii) FY2027 DPU guidance or Q1 FY2027 quarterly DPU (for the period ended 30 June 2026, due ~August 2026) implies full-year DPU below 9.50 cents, indicating distribution coverage deterioration; or (iii) the incoming CEO appointment is delayed beyond December 2026 or accompanied by a material change in investment mandate or capital recycling strategy unfavourable to unitholders.
