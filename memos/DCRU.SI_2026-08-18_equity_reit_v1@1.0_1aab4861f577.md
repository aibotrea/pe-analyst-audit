# Specialist Memo — DCRU.SI

**Memo ID**: `DCRU.SI_2026-08-18_equity_reit_v1@1.0_1aab4861f577`
**Ticker**: DCRU.SI (Digital Core REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-18
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Digital Core REIT offers direct exposure to AI and cloud-driven data centre demand through a portfolio of hyperscaler-leased facilities sponsored by Digital Realty Trust, one of the world's largest data centre operators. At USD 0.525, the REIT yields approximately 6.9% on an annualised basis (H1 2026 DPU of 1.80 US cents per unit × 2), supported by an active unit buy-back programme that reduces float and is accretive to per-unit distribution metrics. An OU Monte Carlo simulation produces a 12-month sim_return of 9.8% with a PGain of 73%, supporting moderate conviction, tempered by the elevated 23.7% historical volatility and the fact that 49% of the H1 2026 distribution is classified as capital return rather than income. The portfolio transaction announced on 12 August 2026 introduces near-term binary risk but could serve as a positive catalyst if accretive, while the CAPM alpha of 9.1% reflects significant positive idiosyncratic expected return versus the APAC REIT benchmark.

## Quantitative Chain

- E(R): 0.0990
- Std dev: 0.1608
- P-gain: 0.7294
- CAPM alpha: 0.0911
- Beta: 0.3579
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Portfolio transaction (2026-08-12) proves dilutive or increases gearing above 45% MAS threshold; DPU cut as capital distribution ratio rises further and income component cannot sustain current payout; occupancy softens if a hyperscaler tenant reduces footprint; US rate-higher-for-longer scenario keeps cap rates elevated and NAV compressed; DCRU unit price revisits prior lows near USD 0.40.
- **base**: E(R)=0.0980
  - Central case: annualised DPU of USD 0.036 maintained; 3% per-unit growth supported by buy-back accretion and stable data centre demand; portfolio transaction is NAV-neutral or modestly accretive; gearing remains within MAS 45% limit; distribution yield of 6.9% and modest rerating provide ~10% total return.
- **bull**: E(R)=0.2200
  - Portfolio transaction announced 2026-08-12 proves highly accretive (e.g., acquisition of stabilised hyperscaler-leased assets at 7%+ cap rate); DPU grows to USD 0.040+ annualised (>10% growth); income-to-capital distribution ratio improves, enabling full income DPU coverage; sentiment re-rating closes NAV discount; unit buy-back programme continues to reduce float; USD 0.60+ price target implied.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0686 (Cat A) — Annualised DPU of USD 0.036 (2 × H1 2026 DPU of USD 0.0180 per unit) divided by current price of USD 0.525. H1 2026 distribution comprised 0.92 US cents tax-exempt income and 0.88 US cents capital distribution, per DCRU.SI 2026-07-29 capital distribution announcement. Total yield including return-of-capital component used in E(R) numerator; income-only yield is ~3.5%.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU-per-unit growth of 3% p.a. assumed based on: (i) AI/cloud structural demand tailwinds for data centre capacity; (ii) accretive unit buy-back programme (up to 129.6M units to be cancelled) reducing unit count, supporting per-unit metrics; (iii) portfolio transaction announced 2026-08-12 (details pending full filing disclosure). Sensitivity tested in scenario analysis. Basis: analyst assumption — subject to revision upon full H1 2026 results and portfolio transaction detail disclosure.
- `multiple_expansion` = 0.0 (Cat C) — Neutral assumption on price-to-NAV re-rating. DCRU trades at an estimated discount to appraised NAV given elevated volatility and capital distribution component; however, given near-term uncertainty around portfolio transaction (2026-08-12 announcement, details in PDF attachments not yet available in body capture), no multiple expansion credit is assumed. Conservative baseline.
- `income_vs_capital_distribution` = disclosed (Cat A) — H1 2026 distribution of 1.80 US cents per unit comprised 0.92 US cents (51%) tax-exempt income and 0.88 US cents (49%) capital distribution (return of capital), per DCRU.SI 2026-07-29 capital distribution and cash distribution announcements. The high capital distribution component indicates AFFO coverage of pure income DPU may be below 1.0x and warrants a qualitative gate reduction.
- `portfolio_transaction_uncertainty` = disclosed (Cat B) — Digital Core REIT announced a portfolio transaction on 2026-08-12 (trading halt 2026-08-11, lifted 2026-08-12). Full details are in PDF attachments not captured in filing body. This transaction may alter gearing, asset count, and DPU profile materially. Treated as Category B risk — direction uncertain at as_of date. Source: DCRU.SI 2026-08-12 asset acquisitions and disposals announcement.
- `unit_buyback_programme` = disclosed (Cat A) — Active unit buy-back and cancellation programme mandated since 15 April 2026, with maximum authorised units of 129,602,591. Daily buy-backs confirmed on 2026-08-13, 2026-08-14, and 2026-08-18 (2,000,000 units purchased on 2026-08-18 alone), per DCRU.SI 2026-08-18 and 2026-08-14 unit buy-back notices. All repurchased units are cancelled, supporting per-unit DPU metrics.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP given DCRU trades in USD on SGX while the currency basis is USD/GBP. Treated as Category B input. CAPM alpha inherits the same noise. Correlation of 0.178 implies low systematic co-movement, partly attributable to currency basis.

## Key Risks
- Capital distribution intensity: 49% of H1 2026 DPU was return-of-capital rather than income, raising questions about AFFO coverage and long-term distribution sustainability if operational cash flow does not improve.
- Portfolio transaction uncertainty: full details of the 2026-08-12 portfolio transaction (trading halt trigger) are in PDF attachments not captured in filing body — the transaction could alter gearing, NAV, and DPU materially in either direction.
- High unit price volatility (annualised 23.7%) makes the position sensitive to market sentiment shifts, particularly given DCRU's small float and relatively low liquidity on SGX-ST versus US-listed data centre REITs.
- Sponsor Digital Realty Trust's own balance sheet and pipeline prioritisation could affect DCRU's access to third-party acquisition pipeline, particularly in a higher-cost-of-capital environment.
- US Federal Reserve rate trajectory: higher-for-longer rates compress cap rate spreads and keep NAV under pressure, particularly for US-asset-heavy REITs like DCRU that distribute in USD.

## Invalidation Condition
Exit if any of the following is observed: (1) annualised DPU falls below USD 0.030 per unit for two consecutive half-year reporting periods, indicating structural impairment of distributable income; (2) aggregate leverage breaches 45% MAS gearing threshold; (3) the portfolio transaction announced on 2026-08-12 results in a rights issue at a material discount to NAV or increases gearing above 42%; (4) Digital Realty Trust formally reduces sponsor fee subordination or withdraws pipeline access commitments to DCRU; or (5) a major hyperscaler tenant (contributing more than 20% of portfolio revenue) provides formal notice of lease non-renewal.
