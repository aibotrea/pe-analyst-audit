# Specialist Memo — NTDU.SI

**Memo ID**: `NTDU.SI_2026-08-08_equity_reit_v1@1.0_028f65d38d32`
**Ticker**: NTDU.SI (NikkoAM-Straits Trading Asia ex Japan REIT ETF)
**Market**: Singapore
**Sector**: Diversified APAC REIT ETF
**As of**: 2026-08-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
NTDU.SI provides diversified exposure to the APAC REIT universe (ex-Japan) via a liquid SGX-listed ETF structure, tracking the FTSE EPRA Nareit Asia ex Japan Net Total Return Index. The estimated distribution yield of ~6.5% delivers a meaningful spread of approximately 275bps over the current 3.74% T-bill rate, supporting the income thesis. Low beta of 0.30 against IASP.L (currency-basis caveat applies) indicates lower co-movement with the broader benchmark, reflecting the ETF's multi-country diversification across Singapore, Australia, Hong Kong and Malaysia. The OU Monte Carlo PGain of 70.7% at a 12-month horizon supports a moderate conviction rating; however, the absence of direct filing data on distribution coverage and the Category C nature of the yield assumption constrain conviction to 3.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.1276
- P-gain: 0.7068
- CAPM alpha: 0.0552
- Beta: 0.2980
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Distribution yield compresses to 5.5% as underlying REIT DPUs are cut amid Hong Kong office and retail vacancy deterioration; APAC cap rates expand 30-50bps driven by a sustained higher-for-longer rate environment or USD strength shock; multiple contraction of -3.0% amplifies price decline; ETF discount to NAV widens on thin liquidity.
- **base**: E(R)=0.0700
  - Central case as constructed in the quantitative chain: distribution yield 6.5%, DPU growth 1.5%, multiple change -1.0%. Singapore and Australia REIT constituents hold occupancy steady; Hong Kong drag is offset by Singapore industrial and Australia diversified exposure.
- **bull**: E(R)=0.1800
  - US Federal Reserve pivots to rate cuts faster than expected, compressing risk-free rates and expanding REIT multiples; APAC REIT distributions grow 3%+ on tight occupancy and positive rental reversions in Singapore logistics and Australian retail; distribution yield re-rates to 5.8% on price appreciation; ETF NAV premium supported by strong inflows.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.065 (Cat C) — Estimated trailing distribution yield of 6.5% for the FTSE EPRA Nareit Asia ex Japan index-tracking ETF. No filing DPU data was retrievable (0 stored filings, SGX lookup unavailable for this ETF). Benchmarked against published NikkoAM product materials and comparable APAC REIT ETF yields for 2025-2026. Sensitivity tested in scenario analysis.
- `dpu_growth` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed, reflecting organic NOI growth across the APAC REIT universe (Singapore, Hong Kong, Australia, Malaysia) underpinned by improving occupancy trends and modest rental reversions. No issuer-specific guidance was available from filings.
- `multiple_change` = -0.01 (Cat C) — Multiple contraction of -1.0% assumed reflecting ongoing rate pressure on APAC REIT valuations, modest USD strength, and subdued sentiment in Hong Kong commercial real estate. IASP.L benchmark posted -3.9% annualised over trailing 5 years, consistent with sector multiple headwinds.
- `etf_structure_note` = disclosed (Cat A) — NTDU.SI is an exchange-traded fund (ETF) managed by Nikko Asset Management Asia Limited, co-sponsored by Straits Trading Company. It tracks the FTSE EPRA Nareit Asia ex Japan Net Total Return Index. The ETF structure means leverage, coverage and asset concentration are properties of the underlying portfolio, not a direct balance sheet. Reported TER ~0.60% p.a. The ETF does not hold property directly; qualitative gates are assessed at the underlying index constituent level.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP (NTDU.SI is USD-denominated on SGX). Treated as Category B input. CAPM alpha inherits the same currency basis noise.

## Key Risks
- Higher-for-longer global interest rates compressing APAC REIT multiples and narrowing the distribution yield spread over T-bills
- Hong Kong commercial real estate weakness (office and retail vacancy) dragging on index constituent distributions and NAV
- USD strength versus SGD, AUD and HKD creating adverse currency translation effects on underlying REIT asset values
- ETF-specific liquidity risk: average daily volume is moderate (~1-4M units), and a market dislocation could widen bid-ask spreads or create NAV discount
- Data limitation: no stored filings or SGX announcement data available for NTDU.SI; the distribution yield assumption (6.5%) is Category C and unverified from primary issuer sources

## Invalidation Condition
Exit position if the trailing 12-month distribution yield falls below 5.0% (implying DPU cuts across the underlying portfolio), or if the ETF begins trading at a persistent NAV discount exceeding 3% for two consecutive months, or if aggregate leverage across the top-10 index constituents rises above 50% on average, signalling regulatory gearing stress across the Singapore and Hong Kong constituent REITs.
