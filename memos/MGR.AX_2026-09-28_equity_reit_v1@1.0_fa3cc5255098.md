# Specialist Memo — MGR.AX

**Memo ID**: `MGR.AX_2026-09-28_equity_reit_v1@1.0_fa3cc5255098`
**Ticker**: MGR.AX (Mirvac Group)
**Market**: Australia
**Sector**: Diversified REIT / Residential Developer
**As of**: 2026-09-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Mirvac Group is an internally managed ASX-listed stapled trust combining a commercial REIT portfolio (office, industrial, build-to-rent) with a residential development business. Trailing yield of ~5.1% provides a modest spread over the 4.1% US T-bill proxy (noting AUD rates context), while FY2026 earnings rebound and an active buyback programme signal improving capital discipline. However, the stapled developer/REIT hybrid structure introduces earnings lumpiness from residential settlement timing, and annualised historical volatility of 22.8% — well above typical pure-play AREIT peers — reduces conviction. PGain of 67.5% from the OU Monte Carlo is adequate but not compelling, and the -1 distribution coverage gate override reflects uncertainty around AFFO coverage given the unconfirmed DPS assumption and development income variability.

## Quantitative Chain

- E(R): 0.0710
- Std dev: 0.1547
- P-gain: 0.6752
- CAPM alpha: 0.0989
- Beta: 0.7836
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Residential settlement volumes fall 25-30% below guidance, DPS cut to ~7.5 cents (yield ~4.3%), gearing rises toward 36-38% as development WIP is partially impaired. Office vacancy accelerates and cap rates expand 25-40bps, compressing NTA by 8-12%. Higher-for-longer RBA cash rate (terminal ~4.5%) sustains yield-spread compression. Bear case also captures a tail-risk scenario where global macro deterioration (rate shock or recession) simultaneously impairs residential demand and commercial cap rates, consistent with the 2022-2023 AREIT de-rating.
- **base**: E(R)=0.0700
  - Central case as modelled: DPS ~9.0 cents (yield 5.14%), DPU growth 2.0% p.a., cap rates flat, gearing stable at ~30%. Residential settlements recover modestly in line with guidance, BTR portfolio ramps up on schedule, office portfolio holds occupancy at ~93-94%. RBA cuts rates once by year-end, providing mild multiple support.
- **bull**: E(R)=0.2000
  - RBA delivers 75bps of cuts, triggering AREIT sector re-rating and compressing cap rates ~20bps. Residential demand recovers sharply on rate relief, lifting settlement volumes and development earnings. DPS upgraded to ~10.5 cents reflecting higher coverage and special distribution from asset recycling. BTR occupancy ramp exceeds targets, improving recurring income visibility. Industrial sub-portfolio valuation uplift from logistics demand surge.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0514 (Cat B) — Estimated DPS of approximately 9.0 AUD cents against closing price of AUD 1.75 on 2026-09-28. News (SimplyWallSt 2026-09-01; Kalkine 2026-08-31) confirms FY2026 EPS rebound and higher FY2027 payout signal. Exact DPS unavailable from stored filings due to ASX body-capture contamination returning unrelated issuers. Classified Category B pending formal filed-accounts confirmation.
- `dpu_growth_3yr` = 0.02 (Cat C) — 2.0% p.a. forward DPU growth assumption: (i) industrial and build-to-rent rental reversion tailwinds in Mirvac's commercial portfolio; (ii) partial offset from office sector softness; (iii) residential development settlement recovery. Sensitivity tested in bear/bull scenarios. No consensus forecast available from filed documents.
- `multiple_change` = 0.0 (Cat C) — Flat price/NAV multiple assumed over 12-month horizon. RBA cash rate trajectory stabilising supports no further meaningful cap rate expansion, but no re-rating premium assumed given persistent macro uncertainty. Tested in bear/bull scenarios.
- `closing_price` = 1.75 (Cat A) — ASX closing price MGR.AX on 2026-09-28 as observed from live price feed.
- `gearing_estimate` = 0.3 (Cat B) — Mirvac gearing estimated at ~28-33% look-through LTV based on historical FY2024/FY2025 reporting patterns. ASX stored filings returned unrelated issuers (body-capture contamination); no current balance sheet directly extracted. Estimated well within the <40% Australian REIT convention. Requires confirmation from next formal filing.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces noise beyond Australian property fundamentals. Treated as Category B input. CAPM alpha inherits the same noise and should not be read as a clean fundamental outperformance signal.

## Key Risks
- Residential development settlement delays or pricing pressure reducing distributable earnings and pressuring DPS coverage below 1.0x AFFO on a look-through basis
- Office sector continued softness (elevated vacancy, sub-leasing pressure in Sydney/Melbourne CBDs) dragging NPI yields and cap rate valuations on Mirvac's office exposure
- RBA cash rate remaining higher for longer, compressing the AUD distribution yield spread and applying upward pressure on cap rates across the commercial portfolio
- Key-person and execution risk given scale of build-to-rent pipeline ramp-up, with potential cost overruns or leasing underperformance in new BTR assets
- ASX body-capture contamination in stored filings prevented direct extraction of FY2026 balance sheet, DPS, and gearing data; key financial assumptions are Category B estimates that may require revision upon formal results confirmation

## Invalidation Condition
Exit signal triggered if: (i) Mirvac reports DPS coverage below 1.0x AFFO for two consecutive half-year periods, confirming distribution unsustainability; (ii) gearing breaches 38% look-through LTV approaching the 40% Australian REIT convention ceiling; (iii) residential development settlements fall more than 30% below guidance for two consecutive periods, materially impairing stapled trust distributable income; or (iv) office occupancy across Mirvac's commercial office portfolio deteriorates below 88% on a portfolio-weighted basis, indicating accelerating asset-quality erosion beyond current market consensus.
