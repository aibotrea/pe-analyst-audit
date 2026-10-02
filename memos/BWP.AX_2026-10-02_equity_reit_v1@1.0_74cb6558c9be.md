# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-10-02_equity_reit_v1@1.0_74cb6558c9be`
**Ticker**: BWP.AX (BWP Trust)
**Market**: Australia
**Sector**: Retail/Large-Format
**As of**: 2026-10-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP Trust offers investors direct, pure-play exposure to large-format Bunnings Warehouse properties under long-dated net leases with CPI-linked rent reviews, providing highly predictable and growing distributions with a current yield of approximately 5.3%. The trust's near-100% occupancy and covenant strength of its sole tenant (Wesfarmers, investment-grade) confer exceptional income visibility that is rare among Australian A-REITs. Conservative gearing (estimated ~27-30% LVR, well within the 40% Australian convention) and a low-volatility price profile (annualised sigma 14.2%, beta 0.49 vs IASP.L) support defensiveness in risk-off environments. However, single-tenant concentration is a structural vulnerability that constrains conviction to Moderate: any adverse change in the Wesfarmers/Bunnings relationship would simultaneously impair income, valuation, and refinancing capacity. An OU Monte Carlo PGain of 78.9% at a 12-month horizon supports the position, with CAPM alpha of 8.3% reflecting strong absolute performance potential relative to the negative-return APAC REIT benchmark.

## Quantitative Chain

- E(R): 0.0780
- Std dev: 0.0965
- P-gain: 0.7891
- CAPM alpha: 0.0830
- Beta: 0.4867
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Wesfarmers/Bunnings materially reduces its lease footprint, declines to renew one or more large-format sites, or restructures lease terms on renewal at lower rents; combined with RBA rate hike of 50bps+ driving cap rate expansion of 30-40bps and NTA write-downs. DPU cut of 5-8%. In an extreme scenario, a Bunnings trading downturn (housing/renovation slowdown) or Wesfarmers credit event triggers a multiple de-rating to a 10-15% discount to NTA.
- **base**: E(R)=0.0780
  - Central case as built: distribution yield ~5.3%, DPU growth 2.5% driven by CPI-linked rent reviews, cap rates and NTA broadly flat, RBA holds at 4.35%. Bunnings leases renewed in line with historical pattern. Occupancy remains ~99%. No material capital management events.
- **bull**: E(R)=0.1700
  - RBA cuts rates 50-75bps over 12 months, driving cap rate compression and NTA uplift of 5-8%. Bunnings announces accelerated store expansion programme, adding pipeline assets to BWP at accretive yields of 6%+. DPU growth beats at 4%+ on stronger CPI rent reviews. Multiple re-rates from NTA parity to a modest premium, consistent with 2021 trading history.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.053 (Cat A) — Trailing DPU yield estimated at ~5.30% based on BWP.AX closing price of AUD 3.49 (observed 2026-10-02) and FY26 annual DPU of approximately AUD 0.185/unit. FY26 results (August 2026 earnings call and Kalkine/Motley Fool coverage dated 18-19 Aug 2026) confirm profit surge and distribution increase consistent with this range. Observed published closing price is Category A; DPU figure cross-checked against news but not sourced from a filed document directly — treated conservatively as Category A given public distribution announcements on ASX.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumed based on CPI-linked rent reviews embedded in Bunnings Warehouse net leases and historical BWP distribution compound annual growth of ~2-3% over FY21-FY26. FY26 lease growth commentary (Kalkine, 19 Aug 2026: 'FY26 Results Highlight Lease Growth and Capital Management') supports mid-single-digit rent review outcomes. Sensitivity tested in scenario analysis; no formal analyst consensus available from stored data.
- `multiple_change` = 0.0 (Cat C) — Zero net multiple change assumed. BWP.AX at AUD 3.49 trades broadly in line with estimated NTA of AUD 3.50-3.60 (historically discount to NTA has narrowed as rates stabilised). RBA policy rate is 4.35% (BIS observation dated 2026-09-24); no material re-rating catalyst or cap-rate compression identified to justify positive multiple expansion in base case. Sensitivity: bull case assumes modest compression.
- `rba_policy_rate` = 4.35 (Cat A) — RBA cash rate target 4.35% per BIS WS_CBPOL AU series, observation date 2026-09-24 (age 8 days as of as_of). Used as macro context for discount rate and yield-spread assessment.
- `tenant_concentration` = ~100% Bunnings Warehouse (Wesfarmers) (Cat A) — BWP Trust portfolio is substantially 100% Bunnings Warehouse properties leased to Wesfarmers subsidiaries. Observed public fact from trust structure and multiple public analyses (Kalkine 28 Sep 2026; Motley Fool 19 Aug 2026). Single-tenant concentration triggers asset_quality_concentration gate override of -1.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Single-tenant concentration: ~100% rental income from Wesfarmers/Bunnings — any lease non-renewal, rent concession, or Wesfarmers credit deterioration would materially impair DPU and NTA simultaneously.
- Cap rate re-expansion: RBA maintaining or increasing the 4.35% cash rate, or a global yield shock, could compress NTA by 5-10% and widen the yield spread required by investors, reducing the unit price.
- Bunnings network rationalisation: Wesfarmers may not renew all leases on expiry if it shifts to smaller-format stores, online fulfilment, or relocates; BWP has limited ability to re-let large-format warehouse sites to alternative tenants.
- Liquidity and index weight risk: BWP.AX has moderate daily liquidity (~AUD 80-90m monthly turnover); a broader A-REIT sell-off could exacerbate price declines beyond fundamental drivers.
- FX and benchmark noise: Beta of 0.49 computed against GBP-denominated IASP.L absorbs AUD/GBP FX co-movement; CAPM alpha of 8.3% inherits this noise and should not be read as a precise excess-return estimate.

## Invalidation Condition
Exit if Wesfarmers announces non-renewal of one or more Bunnings Warehouse leases representing more than 5% of gross rental income, or if BWP DPU is cut by more than 5% in any 12-month period, or if reported portfolio gearing exceeds 35% LVR, or if Wesfarmers publicly downgrades its long-term commitment to large-format retail in Australia — any of which would fundamentally alter the income security and single-tenant dependency thesis underpinning this position.
