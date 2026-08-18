# Specialist Memo — O5RU.SI

**Memo ID**: `O5RU.SI_2026-08-18_equity_reit_v1@1.0_9bbba8378c55`
**Ticker**: O5RU.SI (AIMS APAC REIT)
**Market**: Singapore
**Sector**: Industrial/Logistics
**As of**: 2026-08-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
AIMS APAC REIT offers Singapore-Australia industrial and logistics exposure at a compelling trailing yield of ~6.3% at the current depressed price of SGD 1.49, which has re-rated approximately 10% lower since mid-July 2026 primarily due to equity fund raising dilution and the S$250M perpetual securities redemption announcement. The perp redemption removes expensive 5.375% hybrid capital and, combined with the accretive Hazelmere, Perth industrial acquisition completed August 2026, positions the portfolio for improving DPU coverage over the next 12 months. Beta of 0.264 versus IASP.L (currency-basis caveat applies) indicates lower-than-average co-movement with the broader APAC REIT universe, providing defensive characteristics. A PGain of 76.2% from the OU Monte Carlo and CAPM alpha of +5.7% (both Category B due to IASP.L currency basis) support above-average conviction at a 12-month horizon, with E(R) of 7.3% providing a meaningful 357bp spread over the 3.72% T-bill rate.

## Quantitative Chain

- E(R): 0.0730
- Std dev: 0.1017
- P-gain: 0.7622
- CAPM alpha: 0.0574
- Beta: 0.2639
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Equity raise dilution is more severe than modelled, DPU falls >8% as Hazelmere acquisition proves dilutive at acquisition price, occupancy softens below 93% in Singapore industrial segment due to slowing tech-tenant demand, perp redemption triggers unexpected refinancing cost at higher rate, and Singapore industrial cap rates expand 25-50bps as higher-for-longer global rates compress REIT multiples.
- **base**: E(R)=0.0730
  - Central case: distribution yield 6.3%, DPU growth 1.5% driven by rental escalations and accretive Hazelmere acquisition contribution, occupancy stable at 95-96%, gearing ~37% within regulatory limits, perp redemption accretive to financial flexibility, modest multiple headwind of -0.5% from equity raise overhang dissipates over 12 months.
- **bull**: E(R)=0.1750
  - Hazelmere Perth acquisition delivers above-forecast yield (>6.5%), DPU growth accelerates to 3%+ from tight Australian industrial market rental reversions, equity raise overhang clears rapidly, perp redemption triggers meaningful re-rating as balance sheet quality recognised by market, Singapore industrial occupancy improves toward 98%, and IASP.L benchmark recovery drives sector re-rating tailwind.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat A) — Trailing annualised DPU estimated at approximately SGD 0.094/unit based on FY2026 published distributions; at current price of SGD 1.49 (18-Aug-2026 closing) this implies a yield of ~6.3%. Slightly haircut from headline to reflect near-term dilution from the equity fund raising completed Aug 2026 (O5RU.SI 2026-08-05 ANNC: Use of Proceeds from Equity Fund Raising).
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed: built-in rental escalations of 2-3% for Singapore industrial assets and Australian leases partially offset by unit-count dilution from recent equity raise. Hazelmere, Perth acquisition (O5RU.SI 2026-08-05 ANNC: Completion of Acquisition) expected to be yield-accretive but takes 1-2 quarters to contribute fully. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Modest negative multiple change assumption of -0.5% reflecting: (1) equity raise dilution pressure on near-term unit price; (2) partial offset from balance sheet quality improvement following redemption of S$250M 5.375% Perpetual Securities (O5RU.SI 2026-07-31 CACT: Issuer's Early Redemption). Net multiple change treated as near-neutral with slight headwind.
- `perp_redemption_balance_sheet` = positive (Cat A) — AIMS APAC REIT exercised early redemption call on S$250M 5.375% Subordinated Perpetual Securities, pay date 1-Sep-2026 (O5RU.SI 2026-07-31 CACT). Removes expensive hybrid capital; modestly reduces interest cost burden and improves financial flexibility. Category A as the redemption notice is a published corporate action.
- `leverage_gearing` = 0.37 (Cat B) — Estimated aggregate leverage of approximately 37% based on publicly available FY2026 annual report and 1Q FY2027 business update (O5RU.SI 2026-07-30 ANNC: First Quarter FY2027 Business Update). Body detail unavailable in extracted text; estimate derived from company track record of operating at 34-40% gearing. Well within Singapore's 50% regulatory limit. Category B as derived from published filings without full body extraction.
- `occupancy_rate` = 0.956 (Cat B) — Portfolio occupancy estimated at approximately 95-96% based on AIMS APAC REIT's track record of high occupancy across its Singapore-Australia industrial portfolio. 1Q FY2027 Business Update (O5RU.SI 2026-07-30 ANNC) confirms operational stability but full body text of presentation not available in extraction. Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Low beta of 0.264 reflects both genuine defensive industrial REIT characteristics and partial SGD/GBP currency basis dampening.

## Key Risks
- Near-term DPU dilution from equity fund raising exceeds current estimates if Hazelmere acquisition yield proves lower than anticipated, compressing the distribution yield signal.
- Higher-for-longer global interest rates causing Singapore industrial cap rate expansion of 25-50bps, which would compress NAV and price multiples.
- Australian dollar / SGD currency risk on Australian assets (Hazelmere, Perth), as AUD weakness would reduce SGD-equivalent income contribution from the growing Australian portfolio.
- Sponsor concentration risk: AIMS Financial Group and MacarthurCook are less capitalised than larger Singapore REIT sponsors (e.g. CapitaLand, Mapletree), limiting pipeline depth and potential for large-scale value-accretive acquisitions.
- Occupancy softening in Singapore industrial segment if technology sector demand weakens, as Macquarie Park assets have historically carried tech-adjacent tenants with shorter-lease characteristics.

## Invalidation Condition
Exit position if portfolio occupancy falls below 92% for two consecutive quarterly business updates, or if the forward DPU run-rate (annualised post-equity-raise) declines by more than 8% versus FY2026 actuals for two consecutive quarters, or if aggregate gearing exceeds 43% following any further debt-funded acquisition, or if AIMS Financial Group materially reduces its unitholding or pipeline commitment to AIMS APAC REIT.
