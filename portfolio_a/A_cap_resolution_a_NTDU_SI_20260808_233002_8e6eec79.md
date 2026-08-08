# Track A Decision — NTDU.SI

**Decision ID**: `A_cap_resolution_a_NTDU_SI_20260808_233002_8e6eec79`
**Flow context**: cap_resolution_a
**Decided at**: 2026-08-08T23:30:02.178677+00:00
**Decided by**: gp
**GP cycle**: `A_cycle_2026-08-08T23:30:02.178677+00:00_2869cc7b`

## Action

- **Action**: `partial_dispose`
- Executed size: 1.50%
- Binding constraint: `total_invested_cap`

## Reasoning

**Reason class**: `cap_resolution`

NTDU.SI is a newly added Phase A ticker (conviction 3, Data Centre, Singapore) at 5.0 pct. While it does not directly address Japan or Diversified caps, it is a significant contributor to the total_invested_pct overage. Trimming to 1.5 pct frees approximately 3.5 pct of invested weight, helping close the remaining leverage excess after the Japan disposes. As a new position with conviction score of only 3 and no established PnL track record, it is the weakest Singapore add and the most appropriate lever to pull for leverage relief without disrupting incumbents with positive returns.

## Dispose List
- `NTDU.SI` (partial): NTDU.SI is a newly added Phase A ticker (conviction 3, Data Centre, Singapore) at 5.0 pct. While it does not directly address Japan or Diversified caps, it is a significant contributor to the total_in

## Post-Decision Exposures

- Total invested: 103.03%
- Country: `{"Australia": 32.04, "Singapore": 31.29, "Japan": 39.7}`
- Sector: `{"Retail": 19.55, "Diversified": 33.26, "Healthcare": 5.03, "Office": 11.04, "Industrial/Logistics": 22.6, "Residential": 7.04, "Data Centre": 4.51}`
