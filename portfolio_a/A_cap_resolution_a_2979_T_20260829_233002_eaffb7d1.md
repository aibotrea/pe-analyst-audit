# Track A Decision — 2979.T

**Decision ID**: `A_cap_resolution_a_2979_T_20260829_233002_eaffb7d1`
**Flow context**: cap_resolution_a
**Decided at**: 2026-08-29T23:30:02.060762+00:00
**Decided by**: gp
**GP cycle**: `A_cycle_2026-08-29T23:30:02.060762+00:00_e3d7676b`

## Action

- **Action**: `partial_dispose`
- Executed size: 0.08%
- Binding constraint: `country_cap`

## Reasoning

**Reason class**: `cap_resolution`

2979.T is the worst-performing Japan holding by blended PnL at -4.85% with unrealised loss of -14,748.96 USD, the largest unrealised loss in the portfolio. Trimming from 2.99% to 0.08% (retaining only the tiny position_id 171 leg) reduces Japan exposure by ~2.91% and total invested by ~2.91%, addressing residual Japan cap excess after removing 3281.T and residual total_invested_cap excess. Among all Japan holdings, 2979.T has the worst momentum and loss profile, making it the clear candidate for the deepest trim to restore compliance.

## Dispose List
- `2979.T` (partial): 2979.T is the worst-performing Japan holding by blended PnL at -4.85% with unrealised loss of -14,748.96 USD, the largest unrealised loss in the portfolio. Trimming from 2.99% to 0.08% (retaining only

## Post-Decision Exposures

- Total invested: 105.06%
- Country: `{"Singapore": 36.32, "Japan": 37.01, "Australia": 26.73, "HongKong": 5.0}`
- Sector: `{"Healthcare": 8.08, "Office": 13.99, "Diversified": 27.26, "Retail": 22.82, "Residential": 3.26, "Industrial/Logistics": 22.1, "Data Centre": 7.55}`
