# Specialist Memo — CNI.AX

**Memo ID**: `CNI.AX_2026-07-15_equity_reit_v1@1.0_42f7a90d8e9e`
**Ticker**: CNI.AX (Centuria Capital Group)
**Market**: Australia
**Sector**: Diversified Property Funds Management
**As of**: 2026-07-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Centuria Capital Group (CNI.AX) is a diversified Australian property funds manager with exposure to industrial (CIP.AX) and office (COF.AX) REITs. At A$1.72, the stock trades near a 12-month low following a recently completed retail entitlement offer (July 2026), which introduces dilution uncertainty. Estimated distribution yield of ~5.2% provides a modest spread of ~140bps over the RBA cash rate, but this spread is thin relative to CNI's elevated 12-month historical volatility of 33.9%. PGain of 60.4% from the OU Monte Carlo and positive CAPM alpha of 7.6% (noting IASP.L currency-basis caveat) are directionally supportive, but the high sigma and pending confirmation of post-dilution DPS coverage constrain conviction to Low.

## Quantitative Chain

- E(R): 0.0620
- Std dev: 0.2301
- P-gain: 0.6044
- CAPM alpha: 0.0756
- Beta: 0.7181
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - AUM contraction driven by cap rate expansion in industrial and office sectors; management fee income falls 15%+; entitlement offer proceeds fail to reduce gearing materially; RBA lifts cash rate to 4.35% compressing property valuations; distribution cut to A$0.06 DPS; AUD weakens, amplifying FX-basis noise in beta.
- **base**: E(R)=0.0610
  - Central case as built in chain: distribution yield 5.2%, DPS growth 1.5%, -0.5% multiple compression. RBA holds at 3.85%. CIP and COF occupancy stable. Post-entitlement dilution absorbed within 12 months. Volatility mean-reverts modestly.
- **bull**: E(R)=0.2200
  - RBA pivots to easing cycle; cap rates compress, lifting AUM valuations and management fee base; CNI raises new capital vehicles or acquires third-party AUM; distribution reinstated at A$0.10+ DPS; price recovers toward pre-entitlement offer level of A$2.25+.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=fail [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.052 (Cat B) — Estimated trailing distribution yield derived from current price of A$1.72 and estimated FY2026 DPS of approximately A$0.09 per share (consensus range A$0.08–A$0.10). Body capture for the July 2026 entitlement offer filing (CNI.AX 2026-07-10 ISSUED_CAPITAL) is pending, so the post-dilution DPS has not been confirmed from primary source. Classified Category B as a derived estimate with disclosed methodology.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward distribution growth assumption of 1.5% p.a. reflects modest AUM expansion across managed vehicles (CIP.AX, COF.AX, healthcare funds) offset by higher debt costs and post-entitlement-offer dilution drag. No filed forward guidance confirmed from primary sources at as_of date. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% multiple contraction reflecting higher-for-longer AUD interest rate environment (RBA cash rate ~3.85%) and elevated property sector discount-to-NTA dynamics. Cap rate expansion risk in managed industrial and office portfolios applies indirect pressure on CNI's management fee base and AUM valuation.
- `rba_cash_rate` = 0.0385 (Cat C) — RBA cash rate assumed at 3.85% based on publicly known RBA policy rate for mid-2026. FRED RBAAONBIS series returned error; APAC rates tool returned no data for AU at as_of. Used as qualitative context for spread analysis only; US T-bill rate (3.71%) used as Rf in CAPM.
- `entitlement_offer_dilution` = disclosed (Cat A) — ASX announcement 2026-07-10 (CNI.AX ISSUED CAPITAL): 'Successful Completion of Retail Entitlement Offer'. Body capture pending; headline confirms dilutive capital event completed in early July 2026. This reduces per-share distributions and may affect short-term NTA. Incorporated as a negative adjustment to distribution growth and multiple.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Post-entitlement offer dilution reducing per-share distributions below A$0.09 DPS; filing body capture for the July 2026 capital raise is pending and primary-source confirmation is unavailable at as_of
- Higher-for-longer RBA rates compressing the distribution yield spread and pressuring NTA in managed vehicles (CIP, COF), reducing management fee income and AUM base
- Cap rate expansion in Australian industrial and office sectors reducing valuations across Centuria-managed portfolios, triggering covenant pressure or forced asset sales
- Elevated share price volatility (annualised 33.9%) — significantly above typical A-REIT peers — reflects binary capital structure risk and limits position sizing
- CAPM alpha and beta are computed against GBP-denominated IASP.L; AUD/GBP currency basis inflates apparent alpha and distorts beta reliability

## Invalidation Condition
Exit position if post-entitlement-offer DPS guidance falls below A$0.07 per share on an annualised basis (confirming >22% distribution cut), or if CNI announces a second dilutive equity raise within 12 months of the July 2026 entitlement offer, or if aggregate gearing across managed REITs (CIP, COF) breaches the 50% Australian regulatory convention threshold for two consecutive quarterly reports, or if AUM under management declines more than 10% year-on-year.
