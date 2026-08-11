# Specialist Memo — DXI.AX

**Memo ID**: `DXI.AX_2026-08-11_equity_reit_v1@1.0_c30902fdc84e`
**Ticker**: DXI.AX (Dexus Industria REIT)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-08-11
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Dexus Industria REIT offers high-quality Australian industrial and logistics exposure at a 6.64% distribution yield backed by near-perfect occupancy of 99.7% and upgraded FY26 guidance released 2026-08-11. The CAPM alpha of 9.1% against a declining IASP.L benchmark reflects the structural re-rating premium for well-leased Australian industrial assets relative to broader APAC REITs. Beta of 0.47 versus IASP.L (currency-basis caveat applies) indicates meaningfully lower co-movement risk than the peer universe. The OU Monte Carlo (10,000 iterations) generates an 80.5% probability of positive return over 12 months, supporting an above-average conviction rating at the current entry price of AUD 2.46.

## Quantitative Chain

- E(R): 0.0914
- Std dev: 0.1056
- P-gain: 0.8053
- CAPM alpha: 0.0910
- Beta: 0.4719
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - Occupancy drops to 94% due to tenant non-renewal or warehouse market softening; cap rates expand 30-50bps as RBA holds higher-for-longer or external rate shock, compressing NTA; DPU coverage falls below 1.0x AFFO requiring a distribution cut; AUD/GBP FX movement amplifies benchmark beta noise. Gearing rises toward 38% if asset values decline.
- **base**: E(R)=0.0900
  - Distribution yield 6.64%, DPU growth 2.5%, cap rates stable, occupancy ~99.7%, gearing ~33%. RBA eases modestly, supporting cap-rate stability. OU Monte Carlo sim return 9.1%.
- **bull**: E(R)=0.1900
  - RBA cutting cycle accelerates, cap rates compress 25-30bps adding multiple expansion ~5%; DPU growth exceeds 3.5% driven by rent escalations at lease renewal; Dexus Funds Management injects accretive acquisitions at 6%+ yield; occupancy sustained at 99%+.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0664 (Cat A) — Trailing DPU yield of 6.64% sourced from Kalkine/Google News report dated 2026-07-20 referencing DXI's published distribution. Observed public figure; consistent with AUD 2.46 unit price as of 2026-08-11.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth assumption of 2.5% p.a. based on: (1) 99.7% portfolio occupancy (near-full) per Kalkine report 2026-08-03 referencing upgraded FY26 guidance; (2) industrial lease structures with annual CPI/fixed-rent-review escalators typically 3-4%; (3) offset by limited near-term acquisition pipeline upside given gearing discipline. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Assumed neutral cap-rate/multiple change over 12-month horizon. Industrial cap rates in Australia broadly stabilised post 2023-24 repricing cycle. Upside in bull case; compression risk in bear. No active guidance from FY26 results (body unavailable as filing released intraday 2026-08-11).
- `portfolio_occupancy` = 0.997 (Cat A) — 99.7% occupancy reported in news coverage (Kalkine 2026-08-03) citing Dexus Industria upgraded FY26 guidance announcement. Published issuer-disclosed figure.
- `gearing_estimate` = 0.33 (Cat B) — Estimated gearing of ~33% based on analyst coverage noting manageable leverage and upgraded guidance. FY26 annual report filed 2026-08-11 (body capture pending/unavailable for intraday filing); estimated below the Australian A-REIT 40% convention threshold. Category B pending confirmed figure from annual report.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis adds noise to the 0.472 beta estimate. Treated as Category B input. CAPM alpha inherits the same noise from the IASP.L currency basis.

## Key Risks
- Higher-for-longer RBA cash rate compressing the AUD yield spread and driving industrial cap rate expansion, reducing NTA and distribution sustainability
- Softening Australian industrial/warehouse demand as e-commerce growth normalises, risking occupancy deterioration from the current 99.7% peak level
- Dexus parent (DXS.AX) balance sheet pressures from office portfolio headwinds potentially constraining pipeline injection capacity into DXI
- AUD/GBP currency basis embedded in the IASP.L beta estimate may overstate or understate true property-market co-movement, impacting CAPM alpha reliability
- FY26 annual report body capture failed for intraday filing (ASX body-capture limitation); gearing and DPU coverage figures are Category B estimates pending confirmed disclosure

## Invalidation Condition
Exit position if portfolio occupancy falls below 93% for two consecutive reporting periods, or if confirmed FY26/FY27 gearing breaches the 40% Australian A-REIT convention threshold, or if DPU is formally cut by more than 10% from the FY26 declared level, or if the Dexus parent formally reduces or suspends its asset pipeline commitment to DXI as manager.
