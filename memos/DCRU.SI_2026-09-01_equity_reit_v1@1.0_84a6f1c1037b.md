# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-09-01_equity_reit_v1@1.0_84a6f1c1037b`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-09-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT offers a 7.1% USD-denominated distribution yield supported by a portfolio of freehold and long-leasehold data centres across North America and Europe, sponsored by Digital Realty Trust (NYSE: DLR). The active unit buy-back programme — commencing April 2026 and cancelling repurchased units — provides per-unit DPU accretion and signals management confidence at current price levels. H1 2026 DPU of US$0.018 was flat year-on-year, reflecting financing cost headwinds, but the conservative leverage profile (~33%, well inside the 50% regulatory cap) preserves balance sheet flexibility. The OU Monte Carlo generates a simulated 12-month return of 7.6% with PGain of 67.8%, supporting moderate conviction; the principal risk is the sustained USD rate environment compressing the yield spread and potential cap-rate expansion in the data centre sub-sector.

## Quantitative Chain

- E(R): 0.0763
- Std dev: 0.1637
- P-gain: 0.6778
- CAPM alpha: 0.0685
- Beta: 0.3506
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - US Federal Reserve resumes rate hikes or holds higher-for-longer, compressing DCRU's USD spread to risk-free rate to near zero. Occupancy slips below 90% due to hyperscale tenant consolidation (e.g. Microsoft or Meta non-renewal), DPU cut to US$0.030 annualised (yield 5.9% at entry), leverage rises toward 40% if asset valuations decline. Cap rate expansion of 75bps drives NAV erosion of ~15%. Unit buyback programme suspended due to liquidity constraints. This scenario is also consistent with a broader AI spending retrenchment where hyperscaler capex budgets are cut and data centre demand growth stalls.
- **base**: E(R)=0.0760
  - Central case: annualised DPU stable at US$0.036, distribution yield ~7.1% at entry price. DPU growth of +1.0% from buyback accretion. Cap rate/multiple drag of -0.5%. Occupancy broadly stable at ~95%. Leverage maintained at ~33%. Unit buyback programme continues at current pace throughout H2 2026.
- **bull**: E(R)=0.2200
  - AI and cloud infrastructure demand accelerates sharply, driving data centre rental reversion and occupancy above 97%. Digital Realty executes an accretive ROFR asset injection at 6.5%+ NPI yield, delivering DPU uplift. US rates ease 50-75bps, compressing cap rates by 25bps and driving NAV expansion. DPU improves to US$0.040 annualised (yield ~7.9% on cost), and the market re-rates DCRU toward 1.0x P/NAV from current discount. Buyback programme exhausted early due to strong price performance.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0713 (Cat A) — H1 2026 DPU of US$0.018 per unit (Business Times, 29 Jul 2026), annualised to US$0.036. Divided by closing price of US$0.505 on 2026-09-01. Observed published DPU and market price.
- `dpu_growth` = 0.01 (Cat C) — Forward DPU growth assumption of +1.0%: H1 2026 DPU was flat year-on-year at US$0.018, implying zero organic growth in the near term. A 1.0% estimate reflects modest accretion from the ongoing unit buy-back programme (mandate from 15 April 2026, units cancelled upon repurchase) partially offsetting revenue headwinds from elevated financing costs. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.5% cap-rate/multiple drag over the 12-month horizon reflecting persistent elevated US interest rates and continued USD-denominated financing cost pressure on data centre REITs. Partially offset by structural AI/cloud demand tailwinds. Sensitivity tested in scenario analysis.
- `leverage_ratio` = 0.33 (Cat B) — Estimated aggregate leverage of ~33%, derived from Digital Core REIT's publicly reported balance sheet positioning as of H1 2026. DCRU has historically maintained leverage in the 31-35% range, well within the 50% Singapore REIT regulatory limit. Exact figure subject to H2 2026 results.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP, as well as currency translation between SGD (listing currency) and GBP. Treated as Category B input. CAPM alpha inherits the same noise.
- `sponsor_pipeline` = Digital Realty Trust (DLR) (Cat A) — Digital Realty Trust is the external manager and sponsor of DCRU, with a global data centre portfolio offering ROFR assets. Sponsor commitment evidenced by ROFR structure and ongoing management. Publicly disclosed in DCRU offering documents and annual reports.
- `unit_buyback_programme` = active (Cat A) — Daily unit buy-back notices filed on SGX from 24 Aug to 1 Sep 2026 (e.g. DCRU.SI 2026-09-01 ANNC), with mandate start date 15 April 2026. Maximum authorised buyback: 129,602,591 units. Purchased units are cancelled, providing per-unit NAV and DPU accretion.

## Key Risks
- Higher-for-longer US interest rates compressing the USD yield spread to the risk-free rate, reducing the attractiveness of the 7.1% distribution yield relative to T-bills at 3.78%.
- Hyperscale tenant concentration risk: significant lease non-renewals by anchor tenants (Microsoft, Meta, IBM) could reduce occupancy below 90% and necessitate a DPU cut.
- Data centre cap rate expansion driven by rising global rates or a retrenchment in AI/cloud infrastructure spending, eroding NAV and price-to-book multiple.
- USD/SGD currency mismatch: DCRU distributes and reports in USD but is listed on SGX, creating FX exposure for SGD-based investors and benchmark currency-basis noise in beta computation.
- Macro data availability gap: FRED macro series (FEDFUNDS, credit spreads) were not incorporated as supporting signals in this analysis; their absence is a minor analytical limitation disclosed per framework requirements.

## Invalidation Condition
Exit DCRU.SI if annualised DPU falls below US$0.030 (representing a distribution cut of more than 16% from current run-rate) for two consecutive semi-annual periods, or if aggregate leverage breaches 42% (indicating a structural deterioration in asset valuations), or if Digital Realty Trust formally withdraws or materially reduces its ROFR pipeline commitment to Digital Core REIT, or if occupancy across the portfolio declines below 88% for two consecutive reporting periods.
