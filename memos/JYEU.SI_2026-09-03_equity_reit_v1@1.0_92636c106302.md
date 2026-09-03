# Specialist Memo — JYEU.SI

**Memo ID**: `JYEU.SI_2026-09-03_equity_reit_v1@1.0_92636c106302`
**Ticker**: JYEU.SI (Lendlease Global Commercial REIT)
**Market**: Singapore
**Sector**: Diversified
**As of**: 2026-09-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Lendlease Global Commercial REIT (JYEU.SI) offers a diversified retail and office portfolio anchored by Paya Lebar Quarter and Jem in Singapore plus Sky Complex in Milan, with an estimated distribution yield of approximately 6.0% at the current SGD 0.55 unit price. The OU Monte Carlo simulation (12-month horizon) produces a simulated return of 6.4% with a PGain of 69.7%, suggesting a moderate probability of positive return. However, CAPM alpha of 5.35% against a deeply negative benchmark return (IASP.L 5-year annualised -4.6%) masks meaningful idiosyncratic risks: elevated gearing (~40%), S$240M perpetual securities adding to cost of capital, and ongoing Lendlease Group sponsor restructuring which reduces pipeline visibility and introduces potential forced-seller dynamics. The -1 gate override on sponsor quality reduces conviction from 3 to 2, warranting an underweight relative to Singapore diversified REIT peers with stronger sponsor backing.

## Quantitative Chain

- E(R): 0.0650
- Std dev: 0.1252
- P-gain: 0.6965
- CAPM alpha: 0.0535
- Beta: 0.3124
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Lendlease Group (sponsor) accelerates asset disposals or withdraws pipeline support; gearing breaches the 40% mark requiring equity issuance at a discount, diluting DPU. Sky Complex (Milan) occupancy deteriorates as European office demand weakens. DPU cut of 15-20% to ~2.7 cents/unit. Cap rate expansion of 50bps across the portfolio drives NAV discount widening. This bear case is also the tail scenario for a broader Singapore rate shock where the 3M SORA rises materially above current levels, compressing the yield spread to near zero.
- **base**: E(R)=0.0650
  - Central case as built in the quantitative chain: FY2026 DPU ~3.30 cents (yield ~6.0%), 1.0% DPU growth from CPI-linked escalations, modest yield expansion of -0.5% from rate environment. Portfolio valuation broadly stable at SGD 4.2B. Gearing remains below MAS 45% limit. SKY Complex maintains near-full occupancy; PLQ retail and Jem perform in line with Singapore suburban retail trends.
- **bull**: E(R)=0.1800
  - Lendlease Group successfully completes its restructuring and reaffirms pipeline commitment to LREIT, restoring sponsor confidence. SGD interest rates ease by 50-75bps, expanding the yield spread and re-rating the unit price toward NAV. DPU grows 3%+ as PLQ office rents step up on lease renewals and Sky Complex benefits from EUR/SGD tailwind. Gearing falls below 38% following asset value appreciation. Multiple compression reverses; unit price recovers toward SGD 0.65-0.70.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=fail [override_applied=-1]
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.06 (Cat B) — Estimated FY2026 full-year DPU of approximately 3.30 cents per unit against a closing price of SGD 0.55 on 2026-09-03. The 2H FY2026 capital distribution component of 0.0681 cents/unit was sourced from JYEU.SI 2026-08-03 CACT filing; full DPU (income + capital) is estimated from that data point and historical FY2025 actuals (~3.5 cents/unit). DPU trimmed modestly to reflect higher interest expense from S$240M perpetual securities (4.75% and 4.28% coupon tranches). Category B as the full DPU is derived, not directly confirmed from the truncated FY2026 filing body.
- `dpu_growth` = 0.01 (Cat C) — Forward DPU growth of 1.0% p.a. assumed based on: (1) CPI-linked rental escalations at Jem and PLQ retail (~2-3% but partially offset by higher costs); (2) Sky Complex (Milan) near full occupancy with limited upside; (3) higher-for-longer financing costs from two perpetual securities (S$120M @ 4.28% and S$120M @ 4.75%) constraining distributable income growth. Sensitivity: +0.5%/-0.5% tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Modest yield expansion assumed (-0.5% contribution to total return) reflecting higher-for-longer SGD interest rate environment and elevated gearing constraining re-rating. Singapore office/retail REITs trade at 5.5-7.0% implied yield range; JYEU.SI at 6.0% implied yield has limited compression room given sponsor uncertainty (Lendlease Group restructuring). Category C model assumption.
- `portfolio_valuation` = 4215600000.0 (Cat A) — Independent valuation of properties as at 30 June 2026 at SGD 4,215,600,000, sourced from JYEU.SI 2026-08-03 ANNC (Notice of Valuation of Real Assets). Stated in Singapore Dollars.
- `perpetual_securities` = 240000000.0 (Cat A) — Two perpetual securities outstanding: S$120M 4.75% (SGXF15973195) and S$120M 4.28% (SGXF14886885), confirmed from JYEU.SI 2026-08-03 ANNC filings. These rank senior to equity distributions and add to effective cost of capital.
- `gearing_level` = 0.4 (Cat B) — Aggregate leverage estimated at ~40% of deposited property value based on publicly disclosed portfolio valuation of SGD 4.22B and known borrowings profile. LREIT has historically maintained gearing in the 38-42% range. Exact FY2026 gearing ratio not available from truncated filing bodies but assumed to remain below Singapore MAS 45% limit. Category B — derived estimate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP, as well as EUR/GBP noise from the Sky Complex (Milan) asset. Treated as Category B input. CAPM alpha inherits the same currency basis noise. The low correlation (0.197) and low beta (0.31) partly reflect the currency basis effect rather than purely lower property-market sensitivity.

## Key Risks
- Lendlease Group sponsor restructuring: formal reduction of pipeline commitment or distressed asset sales could force LREIT into NAV-dilutive equity issuances or trigger re-rating.
- Elevated gearing (~40%) leaves limited headroom to the Singapore MAS 45% aggregate leverage limit; a portfolio devaluation of >10% would require deleveraging measures.
- S$240M perpetual securities (4.28% and 4.75% coupons) rank senior to equity distributions; rising financing costs constrain distributable income and DPU growth.
- Sky Complex (Milan) introduces EUR/SGD currency translation risk; EUR depreciation against SGD reduces the SGD-equivalent income from the Italian asset.
- Concentrated three-asset portfolio (PLQ, Jem, Sky Complex) means any single-asset event — lease non-renewal, vacancy spike, or capex requirement — has an outsized impact on distributable income.

## Invalidation Condition
Exit position if: (1) aggregate leverage is disclosed at or above 43% for any reporting period, reducing headroom to the MAS 45% limit to less than 2 percentage points; or (2) Lendlease Group formally announces disposal of its cornerstone stake in LREIT or withdrawal of identified pipeline assets; or (3) FY2027 DPU guidance or interim DPU is cut more than 15% below the FY2026 baseline (~3.30 cents), indicating structural deterioration in distributable income beyond current model assumptions.
