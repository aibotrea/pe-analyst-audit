# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-09-01_equity_reit_v1@1.0_8e6d3c3de1ff`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics & Data Centres
**As of**: 2026-09-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is Australia's premier industrial-logistics and data centre developer-operator, uniquely positioned at the intersection of e-commerce supply chain demand and hyperscaler-driven data centre expansion. The stock has de-rated ~14% from mid-2026 highs (from AUD 32+ to AUD 27.47), providing a more reasonable entry point despite remaining at a premium multiple. An OU Monte Carlo E(R) of ~9.9% and PGain of 69.5% supports moderate conviction at a 12-month horizon. The high CAPM alpha of 12.5% largely reflects the negative IASP.L benchmark return over the 5-year window (Category B — currency basis caveat applies), rather than a purely fundamental signal. Key risk is the transition from logistics-REIT to data-centre developer which compresses the distribution yield to ~1.1%, making GMG more equity-growth sensitive than a traditional income REIT.

## Quantitative Chain

- E(R): 0.1000
- Std dev: 0.1942
- P-gain: 0.6951
- CAPM alpha: 0.1252
- Beta: 0.7346
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Operating EPS growth decelerates to 5% on data centre pipeline delays and logistics demand softening; cap rate expansion of 50bps compresses NTA; AUD/USD weakens materially reducing offshore earnings translation; global recession scenario pushes gearing above 25% as WIP valuations are marked down; multiple contracts to 18x EPS; higher-for-longer RBA rates amplify refinancing costs.
- **base**: E(R)=0.0990
  - Central case as built in chain: operating EPS growth 11%, distribution yield ~1.1%, modest multiple compression of -2%, gearing stable at ~18%, data centre AUM ramp on track with major hyperscaler tenants, occupancy above 97% across logistics portfolio.
- **bull**: E(R)=0.2800
  - Operating EPS growth accelerates to 18-20% as data centre completions exceed expectations and hyperscaler demand surges; AUM grows to A$130bn+ with management fees re-rated; multiple expansion to 28x EPS on structural data centre premium; RBA rate cuts materialise, compressing cap rates; strong AUD amplifies offshore returns.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.011 (Cat A) — Trailing DPU yield: GMG FY2025 DPS of approximately 30 cpu AUD on closing price of AUD 27.47 as of 2026-09-01. Low yield reflects GMG's capital-light distribution policy with majority of operating earnings retained for development and AUM growth. Observed from published ASX distribution announcements (DISTRIBUTION ANNOUNCEMENT filing 2026-08-26 and 2026-08-24 headlines confirm 30 June 2026 distribution dispatch).
- `operating_eps_growth` = 0.11 (Cat B) — FY2026 operating EPS growth of ~11% derived from published GMG guidance and simplywall.st news (21 Aug 2026) referencing A$2.675b FY2026 profit. Consistent with GMG's multi-year guidance trajectory of 10-15% operating EPS growth underpinned by data centre AUM expansion and development completions. Category B as derived from guidance estimates and external commentary rather than directly filed operating EPS figure.
- `multiple_change` = -0.02 (Cat C) — Net P/E multiple change assumption of -2%: GMG de-rated materially from AUD 32+ (June 2026) to AUD 27.47 (September 2026, ~14% decline), suggesting partial re-rating already occurred. Residual -2% multiple compression assumed over 12-month horizon given elevated premium valuation (implied P/E ~22-24x FY2026 operating EPS) and higher-for-longer Australian rate environment. Category C: model assumption; sensitivity tested in scenarios.
- `gearing_ratio` = 0.18 (Cat B) — Estimated look-through gearing of approximately 18% based on publicly available GMG balance sheet disclosures and historical reporting. Well within the Australian REIT convention of <40%. Category B as approximate point estimate derived from prior disclosures pending FY2026 balance sheet confirmation.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis between AUD and GBP introduces noise that cannot be decomposed without a local-currency benchmark. Treated as Category B input. CAPM alpha inherits the same noise from the IASP.L currency basis.

## Key Risks
- Data centre pipeline execution risk: delays in power procurement, grid connection, or hyperscaler capex cycles could defer AUM growth and compress operating EPS growth below 8%.
- Interest rate sensitivity: RBA maintaining elevated cash rates or a re-steepening of the Australian yield curve would increase development financing costs and further compress GMG's premium multiple.
- FX headwinds: GMG derives substantial earnings from European and US operations; a strengthening AUD would reduce translated earnings and reduce reported DPS.
- Valuation concentration risk: at ~22-24x operating EPS, the stock prices in sustained high-growth; any reduction in hyperscaler capex commitments (e.g., AI demand softening) would cause a sharp multiple de-rating.
- Macro data gap: APAC central bank rate data unavailable for AU at as_of date via stored readers; RBA cash rate used as a supporting qualitative input only. This is a limitation disclosed per backtest calibration conventions.

## Invalidation Condition
Exit position if GMG operating EPS growth guidance is formally reduced below 8% for two consecutive annual periods, or if gearing (look-through) rises above 30% due to WIP write-downs or balance sheet stress, or if any single hyperscaler representing more than 15% of contracted AUM cancels or materially reduces its pipeline commitment, or if the ASX price recovers above AUD 36 without corresponding EPS upgrade (implying >30x multiple, excessive valuation risk).
