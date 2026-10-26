# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-10-26_equity_reit_v1@1.0_3812c214d468`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agriculture/Specialty
**As of**: 2026-10-26
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
RFF is an Australian agricultural REIT (farmland, water, cattle and cropping assets) offering an estimated forward yield of about 6.0% against a 4.04% T-bill. FY26 coverage points to higher earnings, stable distributions and lower gearing after asset divestments. The 12-month OU Monte Carlo gives an expected return of about 6.9% with a 13.5% standard deviation, a PGain of about 70% and a CAPM alpha of about 7.5%. Beta of 0.54 against IASP.L is low, but the currency-basis caveat applies and correlation is only 0.32, so the alpha figure is noisy. Conviction is moderate because AFFO growth is stalling, the yield spread over Rf is modest, and gate evidence could not be confirmed from primary filings.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1350
- P-gain: 0.6963
- CAPM alpha: 0.0747
- Beta: 0.5352
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Higher-for-longer rates and a stagflation-type shock push Australian bond yields up. Agricultural cap rates expand by 25-50bps and the price de-rates. AFFO stays flat and coverage slips below 1.0x. Water or farmland valuations are written down, and further asset sales fail to cut gearing. The distribution is held flat in nominal terms and the multiple falls about 12%.
- **base**: E(R)=0.0700
  - Central case as built in the chain: yield about 6.0%, DPU growth about 1%, no multiple change. Gearing stays lower after the FY26 divestments. Lease escalators offset cost pressure and AFFO is roughly stable.
- **bull**: E(R)=0.1700
  - Divestments are completed at or above book value and proceeds are recycled accretively. AFFO growth resumes and distribution growth reaches 3-4%. Falling AUD rates narrow the discount to NTA, adding a multiple re-rating of about 7%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `share_price` = 1.955 (Cat A) — RFF.AX last close on 2026-10-26 (AUD 1.955) from get_price/get_stored_prices.
- `distribution_yield` = 0.06 (Cat B) — Estimated forward yield of about 6.0%, derived from an assumed FY26 distribution near 11.7 cents per unit divided by the AUD 1.955 price. The 11.7c figure is not verified in a retrieved filing. News coverage of the FY26 result (Kalkine, Sharecafe, 2026-08-21) describes distributions as stable, and one July 2026 Kalkine headline cites a 5.36% yield. Treat as an estimate, not an observed published DPU.
- `dpu_growth_12m` = 0.01 (Cat C) — Assumed 1% annual distribution growth. Contractual rent escalators and the lower gearing after FY26 divestments are offset by AFFO that headlines describe as stalling (Simply Wall St, 2026-08-22). Sensitivity is shown in the bear and bull scenarios.
- `multiple_change` = 0.0 (Cat C) — No P/AFFO or NTA-discount re-rating assumed over 12 months. The price has traded in a tight AUD 1.85-1.96 range over the last 30 days.
- `expected_return_build` = 0.07 (Cat B) — E(R) = yield 6.0% + growth 1.0% + multiple change 0.0% = 7.0%.
- `risk_free_rate` = 0.0404 (Cat A) — FRED DTB3 3-month T-bill at 4.04% on 2026-10-23. It is a USD rate used as the platform's standard Rf, which adds a basis mismatch against an AUD asset.
- `expected_market_return` = -0.0438 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (GBP-denominated), computed with calculate_benchmark_return. A negative market return makes the CAPM required return slightly below Rf and flatters alpha.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_gap` = disclosed (Cat B) — The stored RFF.AX filing bodies returned by get_stored_filings contained text from unrelated issuers (Kuniko, Block, Siren Gold, L1 Capital, Serko, H3 Energy). They were ignored as off-topic. Gearing, AFFO coverage, WALE and tenant concentration were not extracted from primary filings. Gate assessments rely on headline-level news and are provisional.

## Key Risks
- Higher Australian and global rates widening agricultural cap rates and compressing the yield spread over a 4.04% risk-free rate
- AFFO growth stalling, with distribution coverage possibly near or below 1.0x, and limited visibility without primary-filing confirmation
- Asset concentration in a small number of agricultural tenants and operators, plus commodity, weather and water-market exposure
- Externally managed structure with related-party dealings and a divestment programme whose pricing against book value is unproven
- Data limitations: beta and market return use a GBP benchmark (currency noise, correlation 0.32), the benchmark's negative 5-year return flatters alpha, the stored filing bodies were mismatched, and E(R) inputs are partly Category B and C estimates

## Invalidation Condition
Exit if FY27 half-year results show AFFO per unit below the distribution per unit (coverage under 1.0x) or a distribution cut. Also exit if gearing rises back above roughly 35% after divestments, if independent valuations imply a write-down of more than 5% in NTA, or if the share price falls more than 20% from AUD 1.955 without a matching improvement in fundamentals.
