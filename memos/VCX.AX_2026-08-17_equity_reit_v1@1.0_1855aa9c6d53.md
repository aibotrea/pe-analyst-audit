# Specialist Memo — VCX.AX

**Memo ID**: `VCX.AX_2026-08-17_equity_reit_v1@1.0_1855aa9c6d53`
**Ticker**: VCX.AX (Vicinity Centres)
**Market**: Australia
**Sector**: Retail
**As of**: 2026-08-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Vicinity Centres offers broad exposure to Australian retail real estate via a ~60-centre portfolio anchored by premium DFO outlets, sub-regional centres, and a co-ownership stake in Chadstone. At AUD 2.64, the implied forward distribution yield of ~4.55% on an estimated 12.0 cent FY2026 DPU provides a modest but positive spread over Australian cash rates, with 2.0% organic growth from in-place rent reviews and the recently announced Eastern Creek Quarter acquisition. Annualised volatility of 20.2% and a beta of 0.67 versus IASP.L (currency-basis caveat applies) reflect moderate sensitivity to the broader APAC REIT market. The OU Monte Carlo (PGain 68.1%) supports a moderate conviction positioning, constrained by elevated price-level volatility, uncertainty around the June 2026 chairman transition, and the absence of confirmed FY2026 AFFO coverage data in filed documents.

## Quantitative Chain

- E(R): 0.0655
- Std dev: 0.1376
- P-gain: 0.6814
- CAPM alpha: 0.0826
- Beta: 0.6748
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Australian consumer spending contracts sharply (high-rate or recession scenario), dragging retail sales performance and specialty tenant turnover rent. Occupancy falls to 95% as weaker discretionary tenants vacate. DPU cut to ~11.0 cents (yield ~4.2% at current price), distribution coverage drops below 1.0x AFFO. Cap rates expand 25-50bps in line with a renewed RBA tightening cycle, compressing NTA and price. Eastern Creek Quarter delivers below-proforma returns on integration delays.
- **base**: E(R)=0.0650
  - Central case as modelled: forward DPU ~12.0 cents (yield 4.55%), 2.0% organic DPU growth from rent reviews and Eastern Creek Quarter contribution, cap rates flat, occupancy stable at ~98.5%. RBA on hold, yield spread to cash rate narrows modestly but remains positive. Chairman transition resolves without governance disruption.
- **bull**: E(R)=0.1800
  - RBA eases by 50-75bps, compressing cap rates and expanding REIT multiples sector-wide. DPU rises to ~12.5-13.0 cents on stronger specialty rent uplifts and Eastern Creek Quarter accretion above proforma. Chadstone and DFO premium assets attract institutional re-rating; price-to-NTA premium widens. Occupancy improves to 99%+ with no material tenant failures. Potential accretive acquisition further boosts distribution growth outlook.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0455 (Cat B) — Forward distribution yield estimated as AUD 0.120 DPU (FY2026 consensus estimate, annualised) divided by closing price of AUD 2.64 on 2026-08-17. DPU estimate is Category B — derived from analyst consensus and prior FY2025 actuals of ~12.0 cents. Body capture for most VCX.AX ASX filings failed (ASX body capture parked per Phase 01 v3.3 §4); exact filed DPU unconfirmable from filings in this pipeline run.
- `dpu_growth_3yr` = 0.02 (Cat C) — Organic DPU growth assumption of 2.0% p.a.: ~1.5% from in-place rent reviews and specialty tenant turnover rent uplifts across the ~60-centre portfolio, plus ~0.5% incremental contribution from the Eastern Creek Quarter acquisition announced 2026-05-14 (price-sensitive ASX filing, body unavailable). Sensitivity tested across bear/base/bull scenarios.
- `multiple_change` = 0.0 (Cat C) — Cap rate and price-to-NTA multiple assumed flat over 12-month horizon. SimplyWallSt analysis (June 2026) estimated VCX ~2% above fair value post-board transition, consistent with roughly neutral multiple. Australian cap rate environment assumed stable given RBA holding pattern. Sensitivity tested in scenarios.
- `gearing_ratio` = 0.28 (Cat B) — Estimated gearing of ~28% based on VCX's published historical range of 25-30% look-through gearing. Exact FY2026 figure unavailable due to ASX body capture failure. Well within the Australian A-REIT conventional limit of <40%.
- `occupancy` = 0.985 (Cat B) — Occupancy estimated at ~98.5% based on VCX's historically high occupancy for its CBD and sub-regional centres. March 2026 quarterly update was filed (2026-05-04, price-sensitive) but body capture failed. Best estimate from prior public reporting. Supports distribution coverage assumption.
- `rba_cash_rate` = 0.04 (Cat C) — RBA cash rate assumed ~4.0% based on last publicly available observations. Stored APAC rates returned no data for AU as of 2026-08-17. Used as context for yield spread analysis only; risk-free rate in the CAPM chain uses the US T-bill (DTB3) as a market-convention proxy.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP, and is therefore subject to currency basis noise. Treated as Category B input. CAPM alpha inherits the same noise — the high computed alpha (8.26%) is materially distorted by IASP.L's strongly negative trailing 5-year return (-4.32% annualised in GBP), and should not be interpreted as standalone outperformance signal.

## Key Risks
- Australian consumer spending slowdown reducing specialty tenant turnover rent and putting pressure on lease renewals, particularly in discretionary categories.
- RBA re-tightening or prolonged higher-for-longer rate environment compressing the yield spread and pushing cap rates wider, negatively impacting NTA and price.
- Governance uncertainty from the June 2026 chairman transition (price-sensitive filing); board continuity risk until new leadership is established.
- Concentration risk in the Chadstone co-ownership (~10% of portfolio by value); any underperformance at this asset disproportionately affects DPU and NTA.
- Integration and yield-on-cost risk from the Eastern Creek Quarter acquisition; body capture failed and proforma metrics are unconfirmable from this pipeline run, representing a data gap.

## Invalidation Condition
Exit conviction or reduce position if VCX occupancy falls below 95% for two consecutive reporting periods, or if the FY2026 or FY2027 DPU is cut below 11.0 cents representing a distribution coverage ratio below 1.0x AFFO, or if announced gearing rises above 35% following further debt-funded acquisitions, or if the new chairman introduces a strategy shift toward lower-quality asset classes or dilutive equity issuance that destroys NTA per unit.
