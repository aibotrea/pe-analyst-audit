# Specialist Memo — CQE.AX

**Memo ID**: `CQE.AX_2026-09-05_equity_reit_v1@1.0_be54a6f9f3e6`
**Ticker**: CQE.AX (Charter Hall Social Infrastructure REIT)
**Market**: Australia
**Sector**: Social Infrastructure / Healthcare & Education
**As of**: 2026-09-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Charter Hall Social Infrastructure REIT offers exposure to long-WALE, government and community-anchored assets (childcare, healthcare, social services) with near-100% occupancy and CPI-linked rental escalators, providing a resilient income stream. At AUD 2.40, the trailing distribution yield of ~6.8% is materially above the 3.75% T-bill rate, offering a real yield spread of ~305bps to compensate for duration and asset risk. FY26 earnings and distributions were lifted, and FY27 guidance was reaffirmed in August 2026, supporting DPU growth continuity. The OU Monte Carlo simulation returns a 72.2% probability of positive 12-month return (pgain 0.72), with a CAPM alpha of ~11% relative to the IASP.L benchmark — though this alpha inherits AUD/GBP currency-basis noise and should be interpreted cautiously. Conviction is held at Moderate (3) given persistent rate headwinds, a 13% price decline from Sep 2025 peaks, and the negative 5-year IASP.L trailing return (-4.6% p.a.) signalling structural macro pressure on APAC REIT valuations.

## Quantitative Chain

- E(R): 0.0930
- Std dev: 0.1571
- P-gain: 0.7215
- CAPM alpha: 0.1096
- Beta: 0.6449
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds rates higher-for-longer into 2027 triggering further cap-rate expansion of 40–50bps; CQE unit price retreats to AUD 2.00–2.10. DPU growth stalls at 0% as childcare operators face cost pressures and one or more anchor tenants exit on lease expiry. Gearing drifts toward 38% LVR reducing refinancing flexibility. Distribution yield spread over risk-free rate compresses materially. This scenario also captures a macro rate-shock or stagflation pathway where both real assets and risk assets reprice simultaneously.
- **base**: E(R)=0.0930
  - Central case as built: trailing yield ~6.8%, DPU growth 2.5% from CPI-linked escalators, flat cap rates. FY27 guidance reaffirmed; occupancy remains near 99%; Charter Hall pipeline supports modest AUM growth. RBA commences gradual easing in H1 2027, providing mild multiple expansion tailwind.
- **bull**: E(R)=0.2200
  - RBA pivots earlier than expected; cap rates compress 25–30bps driving NTA uplift. Sponsor Charter Hall injects accretive pipeline assets at 6.5%+ initial yield. DPU growth accelerates to 4–5% as childcare sector demand outpaces supply. Price re-rates toward AUD 2.80–3.00, recapturing Aug 2026 post-results level and approaching Sep 2025 highs.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.068 (Cat A) — Trailing distribution yield derived from current traded price of AUD 2.40 (2026-09-04 close from stored prices) and published FY26 DPU. News sources (Kalkine, Jun–Aug 2026) report yield between 6.24% and 6.49% at higher price levels; at AUD 2.40 the implied trailing yield on published DPU rounds to ~6.8%. Treated as Category A (observed price and published DPU).
- `dpu_growth_3yr` = 0.025 (Cat C) — Forward DPU growth of 2.5% p.a. assumes continuation of CPI-linked lease escalators across social infrastructure portfolio (childcare, healthcare, government-tenanted assets) consistent with FY27 guidance reaffirmed in ASX Progress Report 2026-08-10 (Tenant Update and FY27 Guidance Reaffirmed). No external consensus DPU forecast available; assumption is internally derived and subject to sensitivity analysis.
- `multiple_change` = 0.0 (Cat C) — Flat cap-rate and multiple assumption in base case. Rate pressure persisting (Kalkine, 10 Aug 2026) limits scope for multiple expansion. Price has retreated ~13% from Sep 2025 highs (~AUD 3.24) to AUD 2.40, suggesting cap-rate expansion is partly embedded. Zero multiple change is a conservative base; tested in scenario analysis.
- `leverage_gearing` = ~33% LVR (estimated) (Cat B) — CQE historically operates with LVR in the 30–35% range, well within the Australian REIT convention of <40%. FY26 Annual Report announced 2026-08-20 (body capture mismatched in pipeline); estimate based on prior disclosed gearing and sector norms. No FY26 audited figure captured — disclosed as an estimate.
- `occupancy_wale` = ~99% occupancy, WALE >10 years (estimated) (Cat B) — CQE's social infrastructure assets (childcare centres, healthcare facilities, government-tenanted properties) carry near-100% occupancy and long WALE by sector convention. Specific FY26 figures not directly captured from filed body (ASX body pipeline mismatch noted); estimate drawn from sector knowledge and prior period disclosures.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis introduces noise into the beta estimate and CAPM alpha. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Higher-for-longer RBA rates compressing the yield spread and driving further cap-rate expansion, with unit price at risk of re-testing AUD 2.10–2.20 support levels.
- Childcare sector structural headwinds: government subsidy reform, cost inflation among childcare operators, or tenant attrition on lease expiry could impair DPU coverage.
- Gearing creep if asset valuations decline further; a move above 35% LVR would narrow the buffer to the Australian REIT convention threshold of 40%.
- Beta estimate (0.645 vs IASP.L) absorbs AUD/GBP FX co-movement — true property-market beta and CAPM alpha are uncertain; the quantitative conviction signal may overstate alpha.
- Absence of confirmed FY26 AFFO coverage ratio from captured filings introduces uncertainty on distribution sustainability; payout ratio assumed adequate based on 'lifted earnings' headline but not independently verified.

## Invalidation Condition
Exit the position if CQE's annualised DPU declines more than 5% from FY26 actuals for two consecutive half-year periods, or if reported LVR exceeds 38% (approaching the 40% Australian REIT convention limit), or if occupancy falls below 97% for two consecutive reporting periods — any of which would indicate deterioration in the core income and asset-quality pillars underpinning the investment thesis.
