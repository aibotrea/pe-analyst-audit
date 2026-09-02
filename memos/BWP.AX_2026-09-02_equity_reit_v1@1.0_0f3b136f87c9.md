# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-09-02_equity_reit_v1@1.0_0f3b136f87c9`
**Ticker**: BWP.AX (BWP Trust)
**Market**: Australia
**Sector**: Large-Format Retail / Industrial
**As of**: 2026-09-02
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP Trust offers stable, Bunnings-anchored large-format retail exposure with a ~5.0% distribution yield at AUD 3.68, CPI-linked rent escalations of ~2% p.a., and a WALE of approximately 7–8 years providing strong income visibility. Low gearing (estimated ~25% LVR, well below the 40% AU convention limit) and the Wesfarmers/Bunnings covenant provide a defensive income floor. The OU Monte Carlo yields a simulated 12-month return of 6.9% with a PGain of 76.2%, supporting a base conviction of 4 before qualitative gate adjustments. A one-step downward override is applied for extreme single-tenant concentration (~96% Bunnings), which, while backed by an investment-grade covenant, represents a structural vulnerability that is partially reflected in the current price discount to sector peers.

## Quantitative Chain

- E(R): 0.0697
- Std dev: 0.0973
- P-gain: 0.7617
- CAPM alpha: 0.0716
- Beta: 0.4731
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - RBA raises cash rate to 4.75%, causing cap rate expansion of 50bps and a 5–8% decline in NTA. Bunnings renegotiates rent on two major sites at renewal, suppressing DPU growth to 0%. Distribution yield rises but unit price falls 10–12%; total return turns negative. Bear case also encompasses a broader rate-shock or stagflation scenario where AUD weakens, input costs for Bunnings rise, and Wesfarmers opts to reduce retail footprint.
- **base**: E(R)=0.0700
  - Central case as built in quantitative chain: distribution yield of ~5.0%, DPU growth of 2.0% (CPI-linked), neutral multiple re-rating, RBA holds rates steady, occupancy at 100%, Bunnings leases renewed on standard terms.
- **bull**: E(R)=0.1600
  - RBA commences rate cut cycle, compressing cap rates by 25–35bps and lifting NTA. Wesfarmers announces new Bunnings sites with BWP acquiring 3–5 assets at 5.5–6.0% yields, immediately accretive. DPU growth accelerates to 3.5% p.a. as CPI-linked rents outperform. Unit price re-rates from ~19x to ~21x forward DPU.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0497 (Cat A) — Trailing annualised DPU of approximately AUD 18.3 cents divided by closing price of AUD 3.68 on 2026-09-02. DPU sourced from BWP AMIT Fund payment notice and distribution announcement filings dated 2026-08-18 (ASX). Price is the observed closing price on the as_of date.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. based on CPI-linked rent escalation clauses in Bunnings Warehouse long-term leases (historically 2–3% CPI escalations). Conservative lower bound applied given elevated rate environment. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple re-rating assumption. BWP trades at ~19x annualised DPU; cap rates in Australian large-format retail have stabilised. No compression or expansion assumed in base case.
- `gearing_lvr` = 0.25 (Cat B) — Estimated LVR of approximately 25%, consistent with BWP Trust's historical gearing range of 20–28%. Derived from most recent annual report disclosures. Materially below the 40% AU REIT convention threshold. Body capture for ASX filings was unavailable in pipeline (cross-contaminated); estimate based on public financial history.
- `tenant_concentration` = 0.96 (Cat A) — Bunnings Warehouse (Wesfarmers subsidiary) represents approximately 96% of net lettable area and income. This is a publicly disclosed and well-known structural feature of BWP Trust. Drives asset_quality_concentration gate override of -1.
- `wale` = 7.5 (Cat B) — Estimated weighted average lease expiry of approximately 7–8 years based on BWP Trust's historical WALE disclosures and the long-term nature of Bunnings leases. Exact figure not available from pipeline body capture; estimate from public record.
- `rba_cash_rate` = 0.04 (Cat B) — Estimated RBA cash rate of approximately 4.0% as of 2026-09-02. Live APAC rate data returned empty for AU; estimate consistent with RBA rate trajectory through 2025-2026. Used as supplementary context only — Rf derived from DTB3 T-bill.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Single-tenant concentration risk: Bunnings Warehouse represents ~96% of income; any strategic shift by Wesfarmers to renegotiate leases, vacate, or not renew at expiry would be materially negative for distributions and asset values.
- Interest rate sensitivity: higher-for-longer RBA cash rates compress the yield spread between BWP's ~5.0% distribution yield and the risk-free rate, weighing on unit price via cap rate expansion.
- Cap rate expansion: Australian large-format retail cap rates could widen if institutional demand for the sub-sector softens, particularly if Bunnings' covenant is perceived to deteriorate.
- Limited growth optionality: BWP's external growth is constrained by the Bunnings acquisition pipeline; the trust has limited ability to diversify tenants or geographies without deviating from its mandate.
- AUD/GBP FX basis in beta calculation: the 0.47 beta against IASP.L absorbs currency co-movement noise, making the CAPM alpha of 7.2% an imprecise signal that may overstate true risk-adjusted outperformance.

## Invalidation Condition
Exit position if Bunnings Warehouse (Wesfarmers) provides formal notice of intent to vacate or not renew any material lease representing more than 10% of NLA, or if BWP Trust's LVR rises above 35% for two consecutive reporting periods signalling a shift in capital management philosophy, or if annualised DPU coverage falls below 0.95x AFFO for two consecutive half-years indicating distribution sustainability concerns.
