# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-10-01_equity_reit_v1@1.0_90ee94b90166`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-10-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
AIMS APAC REIT offers a compelling SGD 9.85 cent trailing DPU yield of ~6.9% at the current price of SGD 1.42, backed by a S$2.25B Singapore industrial/logistics portfolio valued as at March 2026. The redemption of the S$250M 5.375% perpetual securities in September 2026 reduces hybrid leverage and improves distributable income quality. Low beta of 0.29 versus IASP.L (SGD/GBP currency-basis caveat applies) implies meaningful defensive characteristics relative to the broader APAC REIT universe, supported by a PGain of 79.7% from the OU Monte Carlo simulation. Conviction is moderated to 3 (Moderate) from the base-case 4 due to the CEO transition effective 1 October 2026, with an internally-appointed successor whose strategic priorities are unproven at this juncture.

## Quantitative Chain

- E(R): 0.0894
- Std dev: 0.1069
- P-gain: 0.7972
- CAPM alpha: 0.0755
- Beta: 0.2915
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Occupancy falls below 90% from softer industrial demand or key-tenant departures; DPU coverage slips below 1.0x AFFO as new CEO re-bases distribution policy; cap rate expansion of 50bps on Singapore industrial assets compresses NAV; aggressive MTN programme deployment at above-market rates pushes aggregate leverage above 42%; CEO transition disruption leads to strategic drift and elevated vacancy.
- **base**: E(R)=0.0890
  - Central case as modelled: FY2026 DPU of 9.85 cents with 2.5% forward growth, distribution yield 6.94%, minor multiple compression of -0.5% due to CEO transition overhang, aggregate leverage ~37%, perpetual redemption eliminates 5.375% coupon cost, MTN programme used prudently for refinancing and selective acquisitions.
- **bull**: E(R)=0.2000
  - New CEO accelerates accretive acquisitions from expanded S$2B MTN programme at 6%+ NPI yields; industrial/logistics occupancy improves to 97%+ on Singapore supply constraints; DPU growth re-rates to 4-5% p.a.; perpetual redemption saving recycled into yield-enhancing acquisitions; cap rate compression on Singapore Grade-A industrial assets drives NAV upward; multiple re-rating toward 1.1x P/NAV.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.0694 (Cat A) — FY2026 DPU of SGD 9.85 cents (published, +2.6% y-o-y per Yahoo Finance Singapore 2026-05-06) divided by closing price SGD 1.42 (O5RU.SI 2026-10-01). Observed Category A input.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% p.a. Anchored to: (i) FY2026 DPU growth of 2.6% y-o-y; (ii) H2 FY2026 DPU of SGD 5.13 cents, +4.1% y-o-y per Business Times 2026-05-07; (iii) 1Q FY2027 distribution of 2.337 cents per unit for Apr-Jun 2026 (O5RU.SI 2026-07-30 CACT filing, annualises to ~9.35 cents if seasonal mix holds, implying modest step-up trajectory). Growth capped at 2.5% reflecting industrial demand uncertainty and CEO transition drag.
- `multiple_change` = -0.005 (Cat C) — Assumed slight negative multiple compression of -0.5% reflecting near-term CEO transition overhang (Russell Ng ceased 30 Sep 2026; Lim Joo Lee appointed 1 Oct 2026 per O5RU.SI 2026-07-24 cessation filing and 2026-10-01 appointment filing). Internal promotion mitigates disruption but transition uncertainty justifies modest discount. Sensitivity: if cap rates tighten, compression reverses.
- `portfolio_valuation` = 2250663400.0 (Cat A) — AA REIT portfolio valuation as at 31 March 2026: SGD 2,250,663,400 (O5RU.SI 2026-05-07 Notice of Valuation of Real Assets filing, Singapore Dollar denomination confirmed).
- `perpetual_securities_redemption` = S$250M 5.375% perp redeemed 01 Sep 2026 (Cat A) — AIMS APAC REIT redeemed its S$250,000,000 5.375% Subordinated Perpetual Securities (Series 003) at 100% on 01 Sep 2026 (O5RU.SI 2026-07-31 CACT filing, confirmed replacement filing dated 2026-09-01). Reduces hybrid leverage and saves ~S$13.4M p.a. coupon, modestly supportive of distributable income; removes perp from capital structure.
- `debt_programme_expansion` = S$750M to S$2B MTN programme (Cat A) — Multicurrency Debt Issuance Programme limit increased from S$750M to S$2B announced 18 Sep 2026 (O5RU.SI 2026-09-18 ANNC filing). Signals balance sheet ambition and acquisition capacity, but adds refinancing and leverage risk if deployed aggressively.
- `leverage_estimate` = 0.37 (Cat B) — Aggregate leverage estimated at ~37% of total assets, derived from: portfolio valuation of S$2.25B (FY2026), historical debt levels for AA REIT (~S$800-850M based on known perpetual S$250M + senior notes), adjusted for perp redemption 01 Sep 2026. Within Singapore MAS regulatory limit of 45% (50% with credit rating). No explicit gearing disclosure in retrieved filing bodies; full financials pending 2Q FY2027 results (results notification filed 01 Oct 2026).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Correlation of 0.222 indicates moderate co-movement with APAC REIT benchmark.

## Key Risks
- CEO transition risk: Russell Ng's departure on 30 Sep 2026 and Ms Lim Joo Lee's first-day appointment introduce strategic uncertainty; new management may re-base DPU policy, alter capital recycling pace, or pursue acquisitions at suboptimal yields
- Aggressive MTN programme expansion (S$750M to S$2B) could push aggregate leverage above the 45% MAS regulatory threshold if deployed rapidly without proportionate equity issuance or asset recycling
- SGD interest rate persistence: higher-for-longer SORA compresses yield spread versus the 4.03% T-bill rate, reducing attractiveness to income-seeking investors and pressuring DPU coverage if floating-rate debt reprices upward
- Singapore industrial cap rate expansion driven by global base rate contagion or a slowdown in data-centre / e-commerce demand would reduce NAV and could trigger book-value impairment
- IASP.L benchmark currency basis: the computed beta of 0.29 and CAPM alpha of 7.55% absorb SGD/GBP FX noise; if sterling strengthens materially the reported alpha overstates true property-market outperformance

## Invalidation Condition
Exit the position if: (1) aggregate leverage (as reported by management) exceeds 43% for two consecutive quarters, signalling aggressive MTN deployment without offsetting equity; (2) FY2027 full-year DPU falls more than 5% below FY2026's 9.85 cents, indicating new CEO has re-based the distribution; (3) portfolio occupancy reported below 90% for two consecutive quarters; or (4) new CEO announces a material strategic pivot — including a large-scale acquisition exceeding 20% of portfolio NAV at a NPI yield below 5.5% — that destroys yield accretion.
