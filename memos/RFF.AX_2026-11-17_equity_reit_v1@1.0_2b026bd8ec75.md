# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-11-17_equity_reit_v1@1.0_2b026bd8ec75`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agriculture/Specialty
**As of**: 2026-11-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
RFF offers Australian agricultural real asset exposure with a yield of about 6.0%, roughly 1.8 points above the 4.16% T-bill. Beta of 0.51 versus IASP.L is low, though the currency-basis caveat applies and the correlation is only 0.30. FY26 results reportedly met forecasts, with asset sales lifting NAV and reducing gearing. The OU Monte Carlo gives a PGain of 72% and a 7.9% simulated 12-month return, which implies base conviction of 4. I applied a one-step downgrade for external-manager and related-party alignment concerns, which gives a final score of 3.

## Quantitative Chain

- E(R): 0.0800
- Std dev: 0.1356
- P-gain: 0.7208
- CAPM alpha: 0.0807
- Beta: 0.5115
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Higher-for-longer rates and a stagflation-style shock push Australian bond yields up. Agricultural cap rates expand about 50bps, and the unit price discount to NAV widens. Distribution coverage falls below 1.0x AFFO, and a water or commodity downturn stresses tenants. Gearing rises again as asset sales slow and refinancing costs increase.
- **base**: E(R)=0.0800
  - Central case as built in the chain: yield of about 6.0%, distribution growth of about 1%, and partial discount closure of about 1%. Gearing stays below 40% and agricultural valuations hold.
- **bull**: E(R)=0.2000
  - Further asset sales are completed at or above book value and the proceeds are used for debt reduction or buybacks. Distribution growth reaches 2-3% and the NAV discount narrows by more than 10%. Rate cuts compress cap rates.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `share_price` = 1.955 (Cat A) — Latest close on 2026-11-17 from get_price (AUD).
- `distribution_yield` = 0.06 (Cat B) — Estimated at about 11.7 cents per unit annual distribution divided by a 1.955 AUD price. Recent news (Kalkine, Aug 2026) describes FY26 distributions as stable and in line with forecast. I could not confirm the exact DPU from a primary source, because the stored filing bodies returned for this ticker were from unrelated issuers and were discarded.
- `dpu_growth` = 0.01 (Cat C) — Assumes about 1% distribution growth. Fixed and CPI-linked rent reviews on long-dated agricultural leases are offset by flat or near-flat distribution guidance and the effect of asset sales. Sensitivity is covered in the bear and bull scenarios.
- `multiple_change` = 0.01 (Cat C) — Assumes about 1% of price re-rating over 12 months. Units appear to trade at a material discount to reported NAV, and news says asset sales lifted NAV. Only partial discount closure is assumed. Sensitivity is covered in the scenarios.
- `expected_return_build` = 0.08 (Cat C) — E(R) is about 6.0% yield plus 1.0% growth plus 1.0% multiple change, which gives 8.0%.
- `risk_free_rate` = 0.0416 (Cat A) — FRED DTB3 3-month T-bill at 4.16% on 2026-11-16. This is a USD rate used as the platform's standard risk-free input, not an AUD rate.
- `expected_market_return` = -0.04108 (Cat B) — IASP.L trailing 5.18-year annualised log return from calculate_benchmark_return. The figure is GBP-denominated and absorbs FX noise.
- `leverage_assumption` = below 40% AU convention (Cat B) — News on FY26 results reports lower gearing after asset sales. I could not verify the exact ratio from a primary filing, so this is treated as a derived estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- External manager structure with related-party transactions and fee arrangements that may not align with unitholder outcomes
- Distribution coverage is thin, with payout close to 100% of AFFO, and flat distribution guidance limits upside
- Agricultural valuation risk from cap rate expansion, water availability, commodity prices and climate, with concentrated tenants and assets
- Higher-for-longer Australian rates would compress the yield spread and raise refinancing costs
- The distribution yield, gearing and coverage figures are not confirmed from primary filings, because the stored filing bodies were unrelated to RFF, so the memo relies on news summaries and my estimates

## Invalidation Condition
Exit if distribution coverage falls below 1.0x AFFO for two consecutive reporting periods or the distribution is cut. Also exit if gearing rises back above 40% with no credible deleveraging plan. Exit if further asset sales are completed materially below book value, which would undermine the reported NAV and the discount-closure thesis.
