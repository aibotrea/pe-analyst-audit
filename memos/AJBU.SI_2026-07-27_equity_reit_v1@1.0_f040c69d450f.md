# Specialist Memo — AJBU.SI

**Memo ID**: `AJBU.SI_2026-07-27_equity_reit_v1@1.0_f040c69d450f`
**Ticker**: AJBU.SI (Keppel DC REIT)
**Market**: Singapore
**Sector**: Data Centre / Digital Infrastructure
**As of**: 2026-07-27
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Keppel DC REIT (AJBU.SI) is Singapore's largest listed data centre REIT, offering structural exposure to AI-driven demand growth across a multi-geography portfolio spanning Singapore, Australia, and Europe. The 1H 2026 declared DPU of 5.714 cents (annualised ~11.4 cents) translates to a 5.1% distribution yield at current price of SGD 2.24, providing a meaningful premium over the 3.81% T-bill rate. A low IASP.L-computed beta of 0.28 (currency-basis caveated) reflects the defensive, long-leased nature of data centre cashflows and supports a CAPM alpha of 6.3%. The OU Monte Carlo simulation generates a PGain of 80.3%, supporting above-average conviction at a 12-month horizon, with E(R) of ~8.1% anchored by yield plus a conservative 3.0% DPU growth assumption driven by organic rent escalation and Keppel's demonstrable sponsor pipeline.

## Quantitative Chain

- E(R): 0.0810
- Std dev: 0.0945
- P-gain: 0.8031
- CAPM alpha: 0.0633
- Beta: 0.2801
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - DPU growth flat at 0% (no escalation, hyperscaler churn); yield compresses as T-bill rates stay elevated, driving cap rate expansion of 30-50bps across portfolio; gearing approaches 42-44% constraining acquisition capacity; capital distribution component grows as operating income coverage weakens; potential rate-shock scenario (global central bank re-tightening) further pressures valuations and refinancing costs.
- **base**: E(R)=0.0810
  - Central case as built in quantitative chain: annualised DPU ~11.4 cents, distribution yield 5.1%, DPU growth 3.0% driven by rent escalation and Keppel sponsor pipeline, cap rates flat, gearing stable at ~37%, occupancy above 95%.
- **bull**: E(R)=0.1800
  - AI-driven demand surge accelerates colocation pricing power to 5%+ DPU growth; accretive acquisitions from Keppel sponsor pipeline at 6%+ NPI yield; modest multiple re-rating as global REIT sentiment improves with rate cuts; occupancy exceeds 97% across key Singapore and Australian assets; FX tailwind from stronger EUR/SGD for European portfolio.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.051 (Cat A) — 1H 2026 DPU of 5.714 cents per unit declared and filed on SGX (AJBU.SI 2026-07-23 CACT/ANNC). Annualised to 11.428 cents. Divided by closing price of SGD 2.24 on 2026-07-27 = 5.10% distribution yield. DPU is issuer-published; price is an observed closing quote.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth of 3.0% per annum assumed over the analysis horizon. Basis: (i) structural data centre demand driven by AI/cloud workload expansion; (ii) organic rent escalation clauses (typical 2-3% CPI-linked step-ups in colocation and hyperscaler leases); (iii) Keppel sponsor pipeline providing inorganic growth optionality. Sensitivity tested across bear (0%), base (3%), bull (5%) cases. No published consensus estimate was available from the news or filings corpus.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumption: current price-to-NAV broadly in line with historical average for Singapore data centre REITs. No re-rating catalyst assumed in base case; upside scenario allows modest expansion. Sensitivity tested in scenario analysis.
- `capital_distribution_component` = 0.00518 (Cat A) — 1H 2026 distribution includes a capital distribution of 0.518 cents per unit (AJBU.SI 2026-07-23 CACT filing). This represents return of capital rather than operating income, marginally reducing sustainable income coverage. Flagged as a monitoring item in the distribution_coverage qualitative gate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. Low beta of 0.28 is consistent with KEPPEL DC REIT's defensive, long-leased data centre cashflows but should not be read as a precise measure of systematic risk.

## Key Risks
- Higher-for-longer interest rates compressing the yield spread versus SGD T-bill, increasing refinancing costs on existing floating-rate debt facilities
- Hyperscaler demand concentration risk: loss of one or more large colocation clients could materially reduce occupancy and DPU coverage
- Power supply constraints and energy price inflation across key markets (Singapore, Germany, UK) increasing operating costs and limiting data centre expansion capacity
- Capital distribution component (0.518 cents of 5.714 cents 1H 2026 DPU) represents return of capital rather than operating income, indicating current operating income may not fully support the declared distribution level
- SGD/GBP and SGD/EUR currency basis risk for European portfolio assets; FX hedging costs may compress distributable income if EUR weakens materially

## Invalidation Condition
Exit if reported gearing breaches 45% aggregate leverage for two consecutive half-yearly reporting periods, or if DPU falls below 10.0 cents annualised (a 12% cut from current run-rate) for two consecutive distributions, or if portfolio occupancy declines below 90% for any single reporting period, or if Keppel Limited materially reduces its unitholding or publicly signals withdrawal of sponsor pipeline support to Keppel DC REIT.
