# Specialist Memo — SGP.AX

**Memo ID**: `SGP.AX_2026-08-08_equity_reit_v1@1.0_8349027da370`
**Ticker**: SGP.AX (Stockland Group)
**Market**: Australia
**Sector**: Diversified REIT (Residential/Logistics/Data Centre)
**As of**: 2026-08-08
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Stockland (SGP.AX) is Australia's largest diversified REIT-stapled group, offering a ~6.07% distribution yield underpinned by recovering residential communities, a growing logistics portfolio, and a nascent data centre development pipeline. The stock experienced a severe YTD drawdown to three-year lows in May 2026 before recovering toward AUD 4.30, creating a more attractive entry point relative to fundamental value. CAPM alpha of 12.4% against the IASP.L benchmark (currency-basis caveat applies) and a PGain of 70.4% from the Ornstein-Uhlenbeck Monte Carlo support an above-average conviction at a 12-month horizon. The RBA's easing bias and Stockland's internalized management structure with active capital recycling provide additional valuation support.

## Quantitative Chain

- E(R): 0.0950
- Std dev: 0.1755
- P-gain: 0.7043
- CAPM alpha: 0.1242
- Beta: 0.8765
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA reverses to hiking cycle or keeps rates elevated, cap rates expand 50bps+, residential settlements disappoint materially, DPU coverage falls below 1.0x AFFO, SGP re-tests May 2026 three-year lows at ~AUD 3.72, data centre development delays crystallise with cost overruns, and logistics vacancy rises as tenant demand softens in a broader macro slowdown.
- **base**: E(R)=0.0940
  - Central case as built in chain: distribution yield ~6.07%, DPU growth 2.5%, +1% multiple expansion as RBA easing bias consolidates, occupancy stable across logistics and workplace portfolios, residential settlements track management step-change guidance, data centre pipeline progresses on schedule.
- **bull**: E(R)=0.2200
  - RBA delivers two or more rate cuts, cap rates compress 25-50bps driving NAV re-rating, residential demand surges as housing affordability improves with rate cuts, data centre first assets reach income-producing status earlier than expected at accretive yields (6%+), logistics rental growth accelerates to 5%+, and SGP approaches prior AUD 5.00+ price levels.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=info

## Key Assumptions
- `distribution_yield` = 0.0607 (Cat A) — Trailing distribution yield of ~6.07% referenced by Kalkine media (22 Jul 2026) against current market price AUD 4.30. Stockland 2H26 estimated distribution announcement confirmed via ASX headline (SGP.AX 2026-06-22 DISTRIBUTION ANNOUNCEMENT). Filing body unavailable per ASX body-capture limitation (Phase 01 v3.3 §4); yield derived from price-implied DPU and consistent with news references to reaffirmed distribution guidance.
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% pa. AFR reported Stockland earnings more than doubled in FY2025 on residential recovery (20 Aug 2025). AFR also noted a 'step-change' in housing settlements for FY2026 (16 Feb 2026). Post-recovery normalisation assumed to moderate growth to ~2.5% driven by logistics rental growth, data centre development pipeline, and stabilised residential volumes. Sensitivity tested across scenarios.
- `multiple_change` = 0.01 (Cat C) — Assumed +1.0% contribution from modest multiple expansion. SGP.AX experienced a YTD decline to three-year lows (~AUD 3.72) by May 2026, recovering to ~AUD 4.30 as at as_of date. Rate environment in Australia easing (RBA on-hold to easing bias). Flat-to-modest re-rating assumed as rate expectations normalise. Category C — highly sensitive to RBA trajectory and global cap rate direction.
- `gearing_assumption` = below_40pct (Cat B) — Stockland historically operates at 25-30% look-through gearing, well within the Australian REIT convention of <40% LVR. 3Q26 operational update body unavailable (ASX body capture parked); no adverse leverage signals in publicly available headlines. Treated as Category B derived estimate pending full filing body.
- `data_centre_pipeline` = emerging (Cat C) — Stockland data centre update filed 2026-03-02 (price-sensitive ASX announcement). Filing body unavailable. News flow indicates Stockland is pursuing data centre development as a growth pillar alongside residential and logistics. Accretive yield contribution from this segment is speculative at this stage and not explicitly modelled in the base DPU growth rate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. This currency and IASP basis effect introduces noise into the beta of 0.876 and into CAPM alpha. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer Australian interest rates compressing the distribution yield spread over the 3.74% T-bill rate and delaying the cap rate normalisation thesis.
- Residential settlement volumes disappoint if housing affordability remains stretched or if labour/materials cost inflation erodes development margins.
- Data centre development pipeline execution risk: cost overruns, delays, or failure to attract anchor tenants at underwritten yields could impair NAV.
- Governance transition risk: a new Chairman was appointed in July 2026 — while not flagged as adverse, leadership change during a strategic pivot increases execution uncertainty.
- ASX filing body capture limitation means key operational metrics (gearing, occupancy, DPU coverage) for 3Q26 update and 2H26 distribution could not be independently verified from filing text; analysis relies on news headlines and prior-period consensus.

## Invalidation Condition
Exit or reduce the position if Stockland reports gearing above 38% LVR for two consecutive reporting periods, or if the FY2026 or FY2027 DPU falls more than 10% below the implied level of the 2H26 distribution guidance, or if the RBA resumes a hiking cycle with the cash rate rising above 4.75%, or if the data centre development pipeline is formally wound back or impaired by more than AUD 300 million in a single announcement.
