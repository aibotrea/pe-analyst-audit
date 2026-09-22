# Specialist Memo — NTDU.SI

**Memo ID**: `NTDU.SI_2026-09-22_equity_reit_v1@1.0_19103d4c0c33`
**Ticker**: NTDU.SI (NTT DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-22
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
NTT DC REIT offers Singapore-listed exposure to a globally significant data centre portfolio backed by NTT Ltd, one of the world's premier data centre operators, providing a strong sponsor pipeline and long-WALE hyperscale leases that underpin distribution stability. At a current price of USD 0.945, the estimated trailing distribution yield of approximately 5.5% delivers a meaningful spread of approximately 150bps over the prevailing 3-month T-bill rate of 4.02%, supported by a constructive AI-driven demand environment for colocation and hyperscale capacity. Beta of 0.25 against IASP.L (currency-basis caveat applies: NTDU is USD-denominated) indicates low co-movement with the broader APAC REIT index, providing some portfolio diversification benefit. The OU Monte Carlo simulation returns a 12-month sim return of 8.4% with a PGain of 73.8%, supporting a moderate conviction rating; conviction is constrained to 3 by a one-step downward gate override reflecting the REIT's short post-IPO track record, absence of verified filed financial statements in the stored database, and limited disclosure on AFFO coverage. As filed results and distribution track record accumulate, conviction could be upgraded.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1328
- P-gain: 0.7375
- CAPM alpha: 0.0676
- Beta: 0.2542
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Data centre demand softens due to AI capex pullback by hyperscalers; DPU coverage falls below 1.0x AFFO; US Federal Reserve resumes rate hikes, pushing T-bill above 5% and compressing DC REIT multiples by 50bps cap rate expansion; gearing approaches 40% requiring equity dilution; occupancy dips from stabilised levels as a lease expires without immediate re-letting; USD weakness vs SGD adds FX headwind for SGD-reporting investors.
- **base**: E(R)=0.0840
  - Central case as built in quantitative chain: trailing DPU yield ~5.5%, DPU growth 3.0% from CPI-linked escalators, zero multiple change, gearing stable ~33%, occupancy maintained at near-full with NTT Ltd anchor tenancies, rate environment stable with T-bill ~4%.
- **bull**: E(R)=0.2000
  - NTT Ltd exercises ROFR pipeline to inject additional stabilised data centre assets at accretive yields (>6%), driving DPU growth above 5%; Federal Reserve cuts rates materially, compressing cap rates and expanding DC REIT multiples; AI-driven hyperscale demand sustains near-100% occupancy with lease renewals at premium rents; USD strengthens providing additional total return for non-USD investors.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.055 (Cat B) — Estimated trailing DPU yield of ~5.5% derived from IPO prospectus-guided FY1 DPU of approximately USD 0.052/unit (annualised) divided by current market price of USD 0.945. No filed annual/interim reports captured in the stored database as of 2026-09-22; yield is a Category B estimate based on IPO disclosure and observed market price. Sensitivity: ±0.5% yield materially affects E(R).
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth of 3.0% p.a. assumed based on CPI-linked rent escalators typical of long-WALE data centre NNN/triple-net leases. NTT DC REIT holds hyperscale and enterprise-grade data centre assets with lease structures common to the NTT Global Data Centers platform. No published management guidance or filed financials available to anchor this estimate. Sensitivity: a 1% reduction in growth drops E(R) to 7.5%.
- `multiple_change` = 0.0 (Cat C) — Zero multiple expansion/compression assumed at base case. DC REIT sector has faced re-rating pressure from elevated global rates; however, spread to T-bill for NTT DC is approximately 150bps, providing some cushion. Rate normalisation could drive modest positive re-rating; conversely, further rate rises could compress multiples. Assumption tested in scenario analysis.
- `gearing_estimate` = 0.33 (Cat C) — Gearing estimated at approximately 33% based on typical Singapore-listed data centre REIT IPO capital structures and NTT DC REIT's stated focus on maintaining leverage well within MAS 50% regulatory limit. No filed financial statements captured in stored database; estimate is Category C until confirmed by filed accounts.
- `sponsor_commitment` = NTT Ltd (NTT Global Data Centers) (Cat B) — Sponsor is NTT Ltd, a subsidiary of Nippon Telegraph and Telephone Corporation, one of the world's largest data centre operators. Sponsor has a substantial global pipeline of data centre assets providing right-of-first-refusal (ROFR) potential for acquisitive growth. Assessment based on public knowledge of NTT Global's platform; filed ROFR agreement details unavailable in stored filings.
- `new_listing_risk` = disclosed (Cat B) — NTT DC REIT listed on SGX approximately August 2025 (first price observation in stored data). As a new listing with fewer than 14 months of trading history, track record of DPU delivery, AFFO coverage, and management execution is unverified. No filed annual report or semi-annual results available in stored database. This uncertainty contributed to a one-step downward gate override in conviction scoring.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. NTDU.SI is USD-denominated, so the currency basis includes both SGD/GBP and USD/GBP components. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Absence of verified filed annual or semi-annual financial statements means AFFO coverage, actual gearing, and occupancy are unconfirmed; any material deviation from IPO projections would be a significant negative surprise.
- Higher-for-longer US interest rates compressing the distribution yield spread and potentially triggering multiple de-rating in USD-denominated data centre REITs.
- Hyperscaler capex moderation or AI infrastructure build-out slowdown reducing near-term colocation demand, which could impair re-leasing economics at expiry.
- New listing with limited secondary market liquidity (daily traded volumes relatively thin vs established S-REITs), amplifying price volatility beyond the 19.5% historical sigma.
- Currency basis risk: NTDU is USD-denominated and SGX-listed, creating a USD/SGD FX exposure for SGD-based investors that is separate from, and additive to, the property-market risk.

## Invalidation Condition
Exit if any of the following are confirmed: (1) filed semi-annual or annual DPU coverage falls below 1.0x AFFO for one reporting period, indicating distribution is not fully supported by operating cash flow; (2) aggregate leverage breaches 40% (regulatory limit is 50% but early breach of 40% signals structural over-gearing for a new listing); (3) NTT Ltd formally reduces or withdraws its ROFR pipeline commitment to NTDU.SI; or (4) occupancy at any single asset falls below 90% without immediate replacement tenant identified.
