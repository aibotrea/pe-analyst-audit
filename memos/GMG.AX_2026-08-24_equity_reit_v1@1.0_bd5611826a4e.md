# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-08-24_equity_reit_v1@1.0_bd5611826a4e`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics & Data Centres
**As of**: 2026-08-24
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is undergoing a strategic transformation from a pure-play APAC industrial REIT to a global integrated industrial and data centre developer-manager, with over AUD 80 billion in assets under management. FY2026 results confirmed A$2.675 billion in profit and a 20-year logistics lease signed at Tsukuba (Greater Tokyo), demonstrating strong long-duration demand across both sub-sectors. At AUD 27.55 following a ~13.5% post-results pullback, the entry point is more compelling than the prior 52-week highs, though a modest premium valuation multiple compression (-1.5%) remains a headwind. The OU Monte Carlo produces a 12-month simulated return of 8.5% with a 67% probability of a positive outcome, and a strong CAPM alpha of 10.5% (noting the IASP.L currency-basis caveat); conviction is moderate given elevated annualised volatility of 28.5% that tempers the otherwise high alpha signal.

## Quantitative Chain

- E(R): 0.0860
- Std dev: 0.1940
- P-gain: 0.6696
- CAPM alpha: 0.1054
- Beta: 0.7014
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Operating EPS growth slows to 3% as hyperscaler demand for data centre space weakens (AI capex cycle pause or power grid constraints), DPU growth stalls, and the market de-rates GMG's premium multiple by an additional 10-15% from current levels. Gearing edges toward 30% on partially-committed development spend, raising refinancing concerns. AUD strengthens, compressing offshore earnings. This pathway incorporates a rate-shock scenario where RBA hikes unexpectedly by 50bps, widening cap rates across the industrial/data-centre complex.
- **base**: E(R)=0.0860
  - Central case as built in the quantitative chain: operating EPS growth of 9%, distribution yield of ~1.1%, and modest multiple compression of -1.5%. Data centre AUM continues to grow with existing hyperscaler pre-commitments executing on schedule. Gearing stable at ~24%. 12-month OU simulated return of 8.5% with 67% PGain.
- **bull**: E(R)=0.2800
  - Operating EPS growth accelerates to 15%+ as GMG announces additional large-scale data centre pre-commitments (100MW+ facilities), hyperscaler tenants extend existing leases and expand footprint. Multiple re-rates upward as data-centre developer peers (e.g., DigitalBridge, Prologis) trade at higher multiples, closing the discount versus global peers. AUD depreciation provides a tailwind to offshore earnings translation. Logistics vacancy tightens in key APAC markets (Tokyo, Sydney, Singapore).

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0109 (Cat A) — Trailing DPU of ~AUD 30cps divided by closing price of AUD 27.55 on 2026-08-24. GMG retains ~75% of operating earnings for development; DPU yield is structurally low relative to traditional REITs. Source: GMG ASX Distribution Announcement 2026-08-24 (GMG Taxation Components and Fund Payment Notice) and observed market price.
- `dpu_earnings_growth` = 0.09 (Cat C) — Forward operating EPS growth assumption of 9% p.a. anchored on data-centre AUM expansion (Goodman's data centre pipeline >80bn AUM under management), logistics demand, and FY2026 full-year results confirming A$2.675b profit (headline: GMG 30 June 2026 Full Year Results, ASX 2026-08-19, price_sensitive=True). Sensitivity tested in scenario analysis: bear 3%, base 9%, bull 15%.
- `multiple_change` = -0.015 (Cat B) — Modest multiple compression of -1.5% assumed. GMG trades at a significant premium valuation (~23x trailing operating earnings). Post-FY2026 results price action (GMG fell ~13.5% from AUD 31.9 to AUD 27.55 between 26 Jun and 24 Aug 2026) suggests market is already partially re-rating the premium. Flat-to-slightly-negative multiple change is a conservative assumption; derived from price history in stored prices and news coverage.
- `gearing_level` = 0.24 (Cat A) — GMG reported gearing of approximately 23-25% as at FY2026 based on disclosed balance sheet. Well within ASX REIT convention threshold of 40%. Source: GMG FY2026 Full Year Results ASX filing 2026-08-19.
- `payout_ratio` = 0.25 (Cat A) — GMG's retained-earnings development model targets approximately 25% payout of operating EPS as DPU, retaining the remainder for internal capital recycling into data centre and logistics developments. Disclosed in annual results presentations.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. Beta = 0.701, correlation = 0.287 over 252 trading days to 2026-08-24.

## Key Risks
- Data centre capital intensity: GMG's pivot requires sustained high-capex development commitments; if hyperscaler pre-commitments slow or are cancelled, development yields may disappoint relative to 9% growth assumption.
- Multiple compression risk: GMG's premium valuation (~23x operating EPS) leaves limited margin of safety; any earnings disappointment or risk-off rotation out of growth property stocks could accelerate the re-rating already observed post-FY2026 results.
- AUD/USD and AUD/GBP currency exposure: GMG derives earnings globally (US, Europe, Japan, Australia); AUD weakness benefits offshore earnings but introduces translation risk; beta vs IASP.L absorbs AUD/GBP noise and may understate true market sensitivity.
- Interest rate sensitivity: Higher-for-longer RBA cash rate compresses cap rates and raises GMG's blended cost of debt; gearing at ~24% provides buffer but refinancing risk on long-duration development assets is non-trivial.
- Concentration in data centre supply chains: GMG's data centre thesis depends on AI-driven hyperscaler demand; any demand air-pocket, regulatory intervention on AI infrastructure, or power availability constraint could materially delay development pipeline monetisation.

## Invalidation Condition
Exit or materially reduce position if: (1) GMG's operating EPS growth guidance is revised below 5% for two consecutive reporting periods, signalling data centre pipeline stall; (2) gearing rises above 35% as a result of unhedged development commitments; (3) hyperscaler pre-commitment occupancy of the data centre pipeline falls below 70%; or (4) the CEO Greg Goodman reduces his personal shareholding by more than 20% in any 12-month period, signalling reduced insider conviction in the capital allocation strategy.
