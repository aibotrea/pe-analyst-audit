# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-07-13_equity_reit_v1@1.0_b3f8bb211c4f`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics
**As of**: 2026-07-13
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Goodman Group is the highest-quality integrated industrial property and fund manager in the Asia-Pacific, with a rapidly scaling data centre development pipeline that differentiates it from traditional REIT peers. At AUD 29.92 (as of 2026-07-13), GMG offers a modest distribution yield of ~1% but compensates with ~9% operating EPS growth underpinned by hyperscaler demand for purpose-built data centre facilities and resilient logistics fundamentals. The CAPM alpha of 11.5% — acknowledging the AUD/GBP currency-basis noise embedded in the IASP.L beta of 0.79 — signals meaningful outperformance potential versus the benchmark required return. However, at ~35x forward earnings, GMG carries significant valuation risk: the OU Monte Carlo produces a PGain of 68.5% and 1-year simulated standard deviation of 18.5%, consistent with a Moderate (3/5) conviction score and a 5% maximum position size.

## Quantitative Chain

- E(R): 0.0900
- Std dev: 0.1851
- P-gain: 0.6850
- CAPM alpha: 0.1148
- Beta: 0.7931
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Data centre leasing velocity disappoints materially — hyperscalers delay commitments amid AI capex pullback or interest rate re-escalation. Development margins compress, FY26 EPS growth falls to ~3% vs. 9% guidance. Multiple contracts by 5-6 turns on a 35x base, implying ~15% multiple headwind. Logistics vacancy rises in Australia and Japan. AUD depreciates further, reducing offshore earnings value. Total return -12% under this bear/rate-shock pathway.
- **base**: E(R)=0.0890
  - Central case as modelled: 1.0% distribution yield, 9.0% EPS growth per FY26 guidance, -1.0% multiple contraction reflecting elevated entry valuation. Occupancy stable across logistics portfolio (~97-98%). Data centre pipeline delivers on schedule. AUD/USD broadly stable. Total return ~9%.
- **bull**: E(R)=0.2800
  - Data centre pre-leasing accelerates — GMG secures additional hyperscaler commitments pushing FY26 EPS growth toward 12-13%. RBA cuts rates 75bp, compressing cap rates and supporting multiple expansion of 2-3 turns. AUM surpasses AUD 100bn milestone, driving performance fee crystallisation. Multiple expansion adds ~+5% to total return. Strong logistics fundamentals underpin organic rental growth of 5%+. Total return ~28%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.01 (Cat A) — Trailing distribution of AUD 0.30/share (FY25 actuals, publicly filed) divided by closing price of AUD 29.92 on 2026-07-13. Observed market price and published distribution figure.
- `dpu_eps_growth` = 0.09 (Cat B) — GMG guided ~9% operating EPS growth for FY26 in its HY26 results presentation (Feb 2026). The Q3 FY26 Operational Update (ASX 2026-05-25) confirmed FY26 guidance; body unavailable under Phase 01 v3.3 §4 ASX body-capture limitation. Estimate treats guidance as disclosed methodology, hence Category B. Sensitive to development margin realisation and data centre leasing velocity.
- `multiple_change_assumption` = -0.01 (Cat C) — GMG trades at approximately 35x forward earnings — a significant premium to sector peers driven by the data centre development narrative. A -1% multiple contraction is assumed over the 12-month horizon, reflecting the risk of valuation re-rating if interest rates stay elevated or data centre leasing lags expectations. Sensitivity tested in scenario analysis: bull (+2%) and bear (-5%).
- `data_centre_pipeline_contribution` = material (Cat B) — GMG has pivoted significantly toward data centre development, with management commentary indicating a pipeline of hyperscaler-leased facilities across APAC, Europe and Americas. Exact pipeline quantum not sourced from filing body (unavailable for ASX — Phase 01 v3.3 §4). Contribution embedded in the 9% EPS growth estimate; treated as Category B given management guidance basis.
- `gearing_level` = 0.22 (Cat B) — GMG's look-through gearing has historically been maintained at approximately 20-25% of total assets (well below the 40% Australian convention). Exact FY26 gearing not independently sourced from filing body (body_unavailable for Q3 FY26 Operational Update, ASX 2026-05-25). Estimate based on FY25 statutory accounts and management disclosures; classified Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise. Correlation of 0.34 indicates moderate co-movement with the APAC REIT benchmark.

## Key Risks
- Valuation re-rating risk: GMG trades at a material premium to sector peers (~35x forward earnings); any disappointment in data centre leasing timelines or EPS delivery could trigger a sharp de-rating given the high entry multiple.
- Interest rate sensitivity: Despite low balance-sheet gearing (~22%), the elevated earnings multiple makes GMG highly sensitive to changes in the Australian and global rate environment; a renewed rate-hiking cycle would compress the multiple and increase the cost of development capital.
- Data centre execution risk: The pivot to hyperscaler-focused data centres introduces construction, permitting, and counterparty-concentration risks; delays in power connection or planning approvals could push development earnings into future periods.
- ASX filing body unavailability: Key filings including the Q3 FY26 Operational Update (2026-05-25) and Distribution Announcement (2026-06-16) had body_unavailable=True under Phase 01 v3.3 §4; specific gearing, occupancy, and coverage metrics could not be independently verified from filing text and are based on prior disclosures.
- Calibration limitation: This analysis uses directional Phase 2 calibration signals. Vintage discipline arrives in Phase 5; the conviction score and scenario probabilities should be treated as directional, not formally back-tested.

## Invalidation Condition
Exit position if GMG's FY26 operating EPS growth guidance is formally revised below 5% in any ASX announcement, or if the look-through gearing ratio breaches 35% of total assets for two consecutive reporting periods, or if a major hyperscaler counterparty cancels or materially delays a signed data centre pre-lease commitment representing more than 10% of the development work-in-progress book, or if the closing price sustains a decline below AUD 24.00 (approximately -20% from current levels) for five consecutive trading days without a corresponding improvement in fundamentals.
