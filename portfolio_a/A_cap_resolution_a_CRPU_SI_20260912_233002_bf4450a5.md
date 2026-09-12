# Track A Decision — CRPU.SI

**Decision ID**: `A_cap_resolution_a_CRPU_SI_20260912_233002_bf4450a5`
**Flow context**: cap_resolution_a
**Decided at**: 2026-09-12T23:30:02.437489+00:00
**Decided by**: gp
**GP cycle**: `A_cycle_2026-09-12T23:30:02.437489+00:00_bbb634e2`

## Action

- **Action**: `complete_dispose`
- Executed size: 0.00%
- Binding constraint: `total_invested_cap`

## Reasoning

**Reason class**: `cap_resolution`

CRPU.SI is the weakest holding in the post-additive portfolio: it carries the worst blended PnL of any ticker at -6.98%, is a single-leg position with only 0.95% weight offering minimal diversification benefit, and sits in the Retail sector which already has 16.89% exposure. Removing it fully eliminates ~0.95% of invested weight, resolving the 0.21% total_invested_cap breach with margin, while the portfolio retains superior Retail exposure via RGN.AX, SCG.AX, BWP.AX, and HDN.AX with better return profiles.

## Dispose List
- `CRPU.SI` (complete): CRPU.SI is the weakest holding in the post-additive portfolio: it carries the worst blended PnL of any ticker at -6.98%, is a single-leg position with only 0.95% weight offering minimal diversificatio

## Post-Decision Exposures

- Total invested: 94.26%
- Country: `{"Singapore": 27.73, "Japan": 33.02, "Australia": 33.52}`
- Sector: `{"Healthcare": 5.44, "Diversified": 27.89, "Retail": 15.94, "Office": 15.54, "Industrial/Logistics": 19.47, "Data Centre": 8.98, "Residential": 1.0}`
