# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-11-05_equity_reit_v1@1.0_1e1f7d119206`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified/Long-WALE Net Lease
**As of**: 2026-11-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
CLW is a long-WALE (about 9 years), near fully occupied net-lease portfolio sponsored by Charter Hall. It offers an annualised cash yield of about 7.2%, a large spread over the 4.03% US T-bill input. Income growth is guided flat for FY27 and refinancing costs are rising, so expected total return is about 6.5% with 12-month OU simulated PGain of about 70%. Beta of 0.68 against IASP.L carries the currency-basis caveat, and the CAPM alpha of 8.1% is flattered by the negative trailing benchmark return. The numeric chain supports moderate conviction. A one-step downward override is applied because the David Jones administration is a fresh tenant-credit and asset-concentration event at a flagship property, giving conviction 2.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1247
- P-gain: 0.6973
- CAPM alpha: 0.0805
- Beta: 0.6829
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - David Jones administration leads to rent loss or a prolonged re-let on the Elizabeth Street flagship. Valuation writedowns and 25-50bps cap-rate expansion follow. Refinancing of about $2bn reprices at higher margins, so DPU is cut 3-5%. A stagflation-style rate rise widens the yield spread to T-bill and compresses the multiple by 5-8%.
- **base**: E(R)=0.0650
  - Central case as built in the chain. Yield of about 7.2%, flat DPU (FY27 guidance), occupancy near 99%, cap rates broadly stable, and a modest -0.7% multiple drag from the David Jones overhang.
- **bull**: E(R)=0.1700
  - David Jones space is re-let or resolved quickly at or near passing rent. Rate cuts compress cap rates by 25bps and lift the multiple by 4-5%. Rent escalators (CPI-linked) lift DPU about 2-3%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=info

## Key Assumptions
- `price` = 3.54 (Cat A) — Latest close of AUD 3.54 on 2026-11-05 from get_price.
- `distribution_yield` = 0.072 (Cat B) — Annualised from the 6.4c quarterly distribution payable 13 Nov 2026 (news-reported, not verified against an issuer filing). 4 x 6.4c = 25.6c on AUD 3.54 gives about 7.2%. Earlier press cited 6.91% in July at a different price.
- `dpu_growth_12m` = 0.0 (Cat C) — Press reports FY27 income guidance as flat despite about 99.9% occupancy and a roughly 9-year WALE. Assumes 0% DPU growth, with contractual rent escalators offset by higher refinancing costs (about $2bn refinancing per FY26 results slides headline). Tested in the bear and bull scenarios.
- `multiple_change` = -0.007 (Cat C) — Assumes modest 12-month multiple/valuation drag of about 70bps. This reflects the David Jones voluntary administration (CLW holds a 50% interest in the Elizabeth Street store) and a risk of cap-rate drift with T-bill at 4.03%. Offsets part of the yield. Sensitivity covered in the bear case.
- `expected_return_build` = 0.065 (Cat B) — E(R) = yield 7.2% + growth 0.0% + multiple change -0.7% = about 6.5%, rounded from 6.5%. This is a total-return estimate, not a verified forecast.
- `hist_vol` = 0.1835 (Cat B) — 252-day annualised volatility from stored prices (262 observations).
- `risk_free_rate` = 0.0403 (Cat A) — FRED DTB3 3-month T-bill rate on 2026-11-04 (4.03%). This is a US rate used as the platform risk-free input, not an AUD rate.
- `expected_market_return` = -0.0414 (Cat B) — IASP.L trailing 5.18-year annualised log return (1260-day lookback). It is negative and GBP-denominated, so it absorbs FX effects. CAPM alpha is mechanically inflated by this weak market return.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_gap` = disclosed (Cat B) — The stored filing bodies returned for CLW.AX (2026-10 to 2026-11) were mismatched. They contained other issuers' documents (e.g. mining and bank notices), and ASX body capture is parked. These were ignored. Fundamentals (gearing, AFFO coverage, occupancy, WALE) rest on news headlines only and are unverified against CLW filings.

## Key Risks
- David Jones voluntary administration: CLW holds a 50% interest in the Elizabeth Street store, creating possible rent loss, vacancy and valuation writedowns on a flagship asset.
- Refinancing and higher-for-longer rates: about $2bn of debt refinancing could lift interest costs and compress DPU or valuations. Flat FY27 income guidance leaves little buffer.
- Unverified fundamentals: gearing, AFFO coverage and management-fee alignment were not confirmed from CLW filings, because stored filing bodies were mismatched. Those gates are marked info.
- Currency/benchmark noise: beta (correlation 0.45) and the negative IASP.L 5-year return are GBP-based, so CAPM alpha is unreliable and likely overstated.
- Valuation and yield spread: the 7.2% yield is derived from a news-reported quarterly distribution. Cap-rate expansion would hurt NAV even if distributions hold.

## Invalidation Condition
Exit if Charter Hall Long WALE REIT's David Jones exposure results in confirmed lease termination or rent loss with no credible re-letting plan, or if reported aggregate gearing rises above about 40% (or covenant headroom narrows materially) after the refinancing. Also exit if distribution coverage falls below 1.0x AFFO or DPU is cut beyond the flat FY27 guidance for two consecutive periods, or if portfolio occupancy drops below 97%.
