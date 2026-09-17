# Specialist Memo — WPR.AX

**Memo ID**: `WPR.AX_2026-09-17_equity_reit_v1@1.0_3724d383315e`
**Ticker**: WPR.AX (Waypoint REIT)
**Market**: Australia
**Sector**: Retail/Petrol Station (Net-Lease)
**As of**: 2026-09-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Waypoint REIT offers an attractive gross distribution yield of approximately 7.6% underpinned by long-dated NNN petrol station leases with Viva Energy as the dominant tenant. The Ornstein-Uhlenbeck Monte Carlo simulation returns a 76.1% probability of positive return over 12 months (PGain), and the CAPM alpha of 8.1% reflects strong expected outperformance versus a negative IASP.L benchmark (currency-basis caveat applies). However, extreme single-tenant concentration on Viva Energy (>90% of income), the absence of a traditional sponsor pipeline, and gearing approaching the 40% Australian REIT convention limit constrain the conviction score to 2 (Low) after two qualitative gate overrides. The position sizing of 3.0% reflects the asymmetric downside risk from any adverse Viva Energy lease renegotiation.

## Quantitative Chain

- E(R): 0.0760
- Std dev: 0.1063
- P-gain: 0.7613
- CAPM alpha: 0.0806
- Beta: 0.4979
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Viva Energy exercises lease break options or renegotiates at materially lower rents on key sites; RBA delays rate cuts, causing cap rate expansion of 50bps; gearing breaches 40% covenant threshold forcing an equity raise at a dilutive price. Distribution cut of 15-20% is likely under this scenario, with DPU falling to ~14c annualised.
- **base**: E(R)=0.0760
  - Central case as built in chain: annualised DPU of ~17c, yield 7.62%, 1.5% organic DPU growth from CPI-linked reviews, cap rates flat to marginally expanding (-1.5% multiple drag). Occupancy stable across the petrol station portfolio. RBA delivers one 25bps cut in H1 2027.
- **bull**: E(R)=0.1800
  - RBA accelerates easing cycle by 75bps in 2026-2027, compressing REIT yields and driving multiple re-rating; Viva Energy locks in long-dated lease extensions at CPI-plus rents; WPR executes accretive portfolio bolt-on acquisitions at 7%+ cap rates, driving DPU growth of 3-4%. Yield spread to cash rate widens attracting institutional inflows.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=fail [override_applied=-1]
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0762 (Cat B) — Computed from 1H26 declared distribution of AUD 0.0425 per unit (WPR.AX 2026-08-26 PERIODIC REPORTS/DISTRIBUTION ANNOUNCEMENT), extrapolated to a quarterly cadence of 4.25c × 4 = 17c annualised, divided by current price AUD 2.23. Classified B as cadence assumption (semi-annual vs quarterly) carries estimation uncertainty; cross-checked against Kalkine news report of 6.87% yield at marginally higher July 2026 price.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. Waypoint REIT's lease structure with Viva Energy is NNN with CPI-linked rent reviews typically capped at 3% annually. Assumed conservative 1.5% net growth given potential lease renewal risk and cap rate headwinds. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.015 (Cat C) — Assumed -1.5% contribution from slight cap rate expansion pressure in the Australian petrol station net-lease sector, given rates remaining elevated in H2 2026. Partially offset if RBA eases; tested across scenarios.
- `expected_return_build` = 0.076 (Cat B) — E(R) = distribution yield (7.62%, Cat B) + DPU growth (1.50%, Cat C) + multiple change (-1.50%, Cat C) = 7.62%. Rounded to 7.6%.
- `viva_energy_tenant_concentration` = high (Cat A) — Viva Energy Group is the anchor tenant across WPR.AX's petrol station and convenience retail portfolio, representing the dominant income source (publicly disclosed portfolio composition). Concentration risk drives qualitative gate override.
- `gearing_level` = 0.4 (Cat B) — WPR.AX gearing estimated at approximately 40% based on publicly available 1H26 results; approaching the Australian REIT convention limit of 40%. Classified B as precise figure subject to 1H26 report confirmation (body capture unavailable for primary filing).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Single-tenant concentration: Viva Energy dominates WPR income, and any deterioration in Viva's credit quality, EV transition impact on petrol station volumes, or lease non-renewal materially impairs distributable earnings.
- Cap rate re-expansion: Prolonged higher-for-longer RBA cash rate environment keeps property capitalisation rates elevated, compressing NTA and limiting unit price recovery.
- Gearing headroom: Balance sheet gearing approaching the 40% convention limit restricts acquisition-led growth and could trigger covenant discussions if property valuations decline.
- EV transition risk: Accelerated uptake of electric vehicles structurally reduces petrol station throughput, potentially impairing Viva Energy's ability to maintain lease obligations at current rental levels over the medium term.
- Backtest calibration limitation: Phase 2 calibration is directional only; Phase 5 vintage discipline not yet applied. PGain and conviction scores should be interpreted as indicative rather than formally backtested.

## Invalidation Condition
Exit or reduce the position if Viva Energy announces non-renewal, material rent reduction, or closure of more than 5% of WPR's petrol station sites; or if WPR.AX gearing exceeds 42% for two consecutive reporting periods; or if annualised DPU falls below AUD 0.14 per unit (a decline of more than 18% from the 1H26 run-rate), signalling distributable earnings deterioration beyond the base case.
