# Track A Decision — 3282.T

**Decision ID**: `A_cap_resolution_a_3282_T_20261110_233002_fdee10ca`
**Flow context**: cap_resolution_a
**Decided at**: 2026-11-10T23:30:02.128961+00:00
**Decided by**: gp
**GP cycle**: `A_cycle_2026-11-10T23:30:02.128961+00:00_5f87f0e0`

## Action

- **Action**: `partial_dispose`
- Executed size: 2.00%
- Binding constraint: `total_invested_cap`

## Reasoning

**Reason class**: `cap_resolution`

3282.T is the weakest holding: the largest USD unrealised loss in the book (-10.1k, -3.7% blended) with no recovery signal, and a Residential name in a Japan sleeve already at 22.6%. Trimming it by 0.81pp clears the 0.51pp total-invested excess with buffer. Trimming it instead of the freshly added 2979.T (conviction 3) or the profitable names keeps higher-conviction capital in place.

## Dispose List
- `3282.T` (partial): 3282.T is the weakest holding: the largest USD unrealised loss in the book (-10.1k, -3.7% blended) with no recovery signal, and a Residential name in a Japan sleeve already at 22.6%. Trimming it by 0.

## Post-Decision Exposures

- Total invested: 94.70%
- Country: `{"Australia": 33.07, "Singapore": 31.15, "HongKong": 8.72, "Japan": 21.76}`
- Sector: `{"Diversified": 23.68, "Healthcare": 3.5, "Data Centre": 3.07, "Industrial/Logistics": 26.59, "Retail": 19.47, "Residential": 8.41, "Hospitality": 5.97, "Office": 4.01}`
