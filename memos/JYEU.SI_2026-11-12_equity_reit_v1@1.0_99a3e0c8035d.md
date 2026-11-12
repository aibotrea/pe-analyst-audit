# Specialist Memo — JYEU.SI

**Memo ID**: `JYEU.SI_2026-11-12_equity_reit_v1@1.0_99a3e0c8035d`
**Ticker**: JYEU.SI (Lendlease Global Commercial REIT)
**Market**: Singapore
**Sector**: Retail/Commercial
**As of**: 2026-11-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Lendlease Global Commercial REIT offers a Singapore-centred retail and office portfolio with about 94% committed occupancy and an estimated 5.7% distribution yield. That is a 1.6pt spread over the 4.12% T-bill rate. The OU Monte Carlo gives a 12-month simulated return of 6.6% with a PGain of 70%, and CAPM alpha is 5.1% on a beta of 0.30 (currency-basis caveat applies). The numeric chain supports a base score of 4. I applied a one-step gate override to 3 because the DPU/coverage and gearing inputs could not be verified from available filings, and the units are small-cap, illiquid and about 18% volatile.

## Quantitative Chain

- E(R): 0.0670
- Std dev: 0.1244
- P-gain: 0.7034
- CAPM alpha: 0.0510
- Beta: 0.2980
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Stagflation/higher-for-longer rate pathway: SGD rates stay elevated and cap rates expand 25-50bp. Committed occupancy falls below 92%, DPU coverage drops below 1.0x and DPU falls about 3%. The sponsor reduces its support and the units de-rate to a wider yield spread.
- **base**: E(R)=0.0670
  - Central case as built in the chain: 5.7% yield, 1% DPU growth, flat multiple, occupancy stable around 94%, gearing stable and no equity raising.
- **bull**: E(R)=0.1700
  - Rate cuts compress yields. Singapore retail rental reversions are positive, and accretive capital recycling and Orchard/Jem asset enhancement lift DPU about 4%. Units re-rate toward book NAV.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `price` = 0.54 (Cat A) — Latest SGX close of SGD 0.54 on 2026-11-12 from get_price.
- `distribution_yield` = 0.057 (Cat B) — Estimated trailing DPU yield of about 5.7% (roughly 3.1 cents DPU on a SGD 0.54 price). This is my recollection of published FY2025/FY2026 DPU, not read from a stored filing. The 1Q FY2027 business update body (JYEU.SI 2026-10-30 ANNC) was unavailable (body_unavailable=True), and the FY2026 annual report announcement (2026-10-01) carries only a PDF attachment. It should be verified against the filed DPU.
- `dpu_growth` = 0.01 (Cat C) — Forward DPU/NAV growth assumption of 1.0%. This reflects modest Singapore retail rental reversions and no assumed acquisitions. It is not based on consensus. Sensitivity is covered in the bear case (-3%) and the bull case (+4%).
- `multiple_change` = 0.0 (Cat C) — Assumes no change in yield/P-NAV multiple over 12 months (cap rates and unit yield flat). A 25bp yield expansion would cost roughly 4-5% of price, which is reflected in the bear case.
- `expected_return_build` = 0.067 (Cat B) — E(R) = yield 5.7% + growth 1.0% + multiple change 0.0% = 6.7%. This is a derived estimate. The yield component is Category B, and the growth and multiple components are Category C.
- `portfolio_committed_occupancy` = 0.944 (Cat B) — Committed occupancy of 94.4% for 1Q FY2027, taken from a news headline (Yahoo Finance Singapore, 2026-10-29). The underlying filing body was unavailable, so this is secondary-source data.
- `risk_free_rate` = 0.0412 (Cat A) — FRED DTB3 3-month T-bill rate of 4.12% on 2026-11-10 from get_tbill_rate (USD rate, used as the platform Rf convention).
- `expected_market_return` = -0.0432 (Cat B) — Trailing 5.18-year annualised log return of IASP.L (GBP-denominated), 1260-day lookback. It is negative, which mechanically flatters CAPM alpha at low beta.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. This is a currency-basis caveat; the correlation is only 0.19, so the beta of 0.298 is statistically weak.
- `manager_fee_in_units` = observed (Cat A) — JYEU.SI 2026-10-12 ANNC reports payment of acquisition fees by way of issuance of units. The filing body only lists a PDF attachment, so the amount is not captured. Fees paid in units are a mild alignment positive but cause dilution.
- `leverage_gearing` = unverified (Cat C) — Aggregate leverage was not retrieved from any available filing body. I assume it sits within the MAS 50% limit, as is typical for this REIT, but this is not verified. The perpetual securities (4.28% and 4.75%, SGD 120M each, per the 2026-10-01 trustee ANNC) add to financial obligations.

## Key Risks
- Distribution coverage and gearing are unverified because the 1Q FY2027 update body was unavailable. A coverage shortfall or higher refinancing costs could pressure DPU.
- Higher-for-longer rates or a stagflation scenario could widen cap rates and compress the yield spread over the 4.12% T-bill, with a negative-NAV effect on a small-cap REIT.
- Asset concentration in a few Singapore retail and office assets (Jem, 313@somerset, Paragon/Sky Complex exposure), plus overseas Milan office exposure, adds tenant and cap-rate risk. Sponsor Lendlease's pipeline support is uncertain, and the manager chairperson changed in October 2026.
- The beta (0.30, correlation 0.19) is statistically weak because of IASP.L currency basis. The negative trailing benchmark return flatters CAPM alpha, so alpha should be treated as low-reliability.
- Live-data analysis uses single-point price and news-derived inputs. The yield figure is a Category B recollection rather than a parsed filing, so the E(R) build carries estimation error.

## Invalidation Condition
Exit if committed occupancy falls below 92% for two consecutive quarterly updates, if DPU coverage falls below 1.0x AFFO or reported DPU is cut more than 5% year-on-year, if aggregate leverage approaches the MAS 50% limit, or if Lendlease signals a material reduction in its sponsor stake or pipeline commitment.
