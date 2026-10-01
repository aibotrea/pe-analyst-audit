# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-10-01_equity_reit_v1@1.0_242fdad31160`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics & Data Centre
**As of**: 2026-10-01
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is a globally diversified industrial REIT and data centre developer with a structurally differentiated growth engine driven by hyperscaler demand. Its FY2026 distribution yield of ~1.1% is low for a REIT, but the total return case rests on ~9% forward EPS growth from AUM expansion across its approximately AUD 90bn+ development pipeline. Beta of 0.76 versus IASP.L (currency-basis caveat applies) reflects GMG's meaningful co-movement with the broader APAC REIT index, while its annualised 1-year volatility of 28.5% reflects the premium-growth valuation that makes the security sensitive to rate and growth-expectations changes. The OU Monte Carlo PGain of 68% at a 12-month horizon supports moderate conviction, constrained by elevated starting multiples (~25-26x forward EPS), the RBA rate at 4.35%, and the negative trailing 5-year benchmark return that weighs on CAPM alpha signal reliability.

## Quantitative Chain

- E(R): 0.0910
- Std dev: 0.1935
- P-gain: 0.6792
- CAPM alpha: 0.1196
- Beta: 0.7618
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - EPS growth decelerates to ~3% as hyperscaler capex cycles down and data centre development pipeline is deferred; multiple compresses 8-10% as RBA holds rates above 4% through FY2027 and global rate repricing hits premium-multiple REITs hardest; distribution maintained but market re-rates GMG closer to NTA, implying significant de-rating from current 25x+ multiple. A macro rate shock (e.g. US long-end yields spiking above 5.5%) would accelerate this bear pathway.
- **base**: E(R)=0.0900
  - Central case as built in quantitative chain: FY2027 EPS growth ~9%, distribution yield ~1.1%, -1% multiple compression. RBA begins easing in 1H2027 providing modest relief. Data centre AUM continues expanding on ~AUD 15bn+ work-in-progress. Occupancy stable across logistics portfolio globally.
- **bull**: E(R)=0.2800
  - EPS growth accelerates to 13-15% as hyperscaler demand for data centre capacity exceeds supply; GMG announces additional data centre pre-commitments from major cloud tenants; RBA cuts 50bps in early 2027 reducing cost of capital; multiple expands 3-5% as growth premium is repriced upward. Development completions and AUM fees drive outperformance versus consensus.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0113 (Cat A) — Trailing distribution of ~30 AUD cpu (FY2026 published dispatch announcement GMG.AX 2026-08-26) divided by closing price AUD 26.59 on 2026-10-01. GMG operates a low-payout stapled structure; distribution yield is structurally low relative to peers.
- `eps_growth_forward` = 0.09 (Cat C) — Forward operating EPS growth assumption of ~9% for FY2027, consistent with GMG's publicly communicated medium-term target range of 7-10% driven by data centre AUM expansion, development completions, and management fee income growth. Sensitivity tested: bear 3%, bull 14%.
- `multiple_change` = -0.01 (Cat C) — Assumed -1% negative multiple contribution over 12 months. GMG trades at a substantial premium to book (~25-26x forward EPS) reflecting data centre optionality. Elevated RBA policy rate (4.35% as of 2026-09-17) and higher-for-longer global rate environment create modest P/E compression headwind. Bear: -5%, Bull: +3%.
- `gearing_lvr` = 0.27 (Cat A) — GMG's reported look-through gearing estimated at ~26-28% LVR based on FY2026 results (publicly disclosed balance sheet). Well within the 40% AU REIT convention threshold.
- `rba_policy_rate` = 0.0435 (Cat A) — RBA official cash rate 4.35% per BIS WS_CBPOL_AU, observed 2026-09-17 (age 14 days as of as_of date). Used as context for discount rate and yield-spread assessment.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP currency basis. Treated as Category B input. CAPM alpha inherits the same noise.
- `filing_body_quality` = degraded (Cat A) — Stored filing bodies for GMG.AX returned cross-contaminated content from unrelated ASX entities due to pipeline body-capture matching issues. No reliable body-level financial data extracted. Key assumptions sourced from public knowledge of GMG FY2026 results and news signals. This data gap is disclosed in key_risks.

## Key Risks
- Hyperscaler capex deceleration: Major cloud tenants (Amazon, Microsoft, Google) reducing data centre investment would materially impair GMG's development pipeline and AUM growth narrative.
- Multiple compression from rate persistence: GMG's premium P/E (~25-26x) is vulnerable to sustained higher-for-longer rates; RBA at 4.35% and US long-end rate volatility pose de-rating risk.
- Filing body data gap: ASX pipeline body-capture returned cross-contaminated content for GMG.AX; balance sheet leverage and DPU figures sourced from public knowledge rather than verified filing extraction, introducing Category C uncertainty into Category A assumptions.
- Currency basis in beta and CAPM alpha: Beta computed against GBP-denominated IASP.L absorbs AUD/GBP FX noise; the negative expected market return (-5.0%) likely reflects benchmark-level FX headwinds not fully applicable to AUD-denominated GMG, making CAPM alpha less reliable as a standalone signal.
- Concentration in development-phase assets: A significant share of GMG's AUM is work-in-progress; construction cost inflation, permitting delays, or hyperscaler tenant credit deterioration could defer completions and impair near-term earnings.

## Invalidation Condition
Exit the position if GMG reports two consecutive half-year periods of operating EPS growth below 4% (versus the ~9% base assumption), or if the group formally revises its data centre work-in-progress pipeline downward by more than 20% due to hyperscaler pre-commitment withdrawals or cancellations, or if group look-through LVR breaches 35% (approaching the 40% AU REIT convention threshold), signalling a deterioration in balance sheet headroom that contradicts the current pass on the leverage qualitative gate.
