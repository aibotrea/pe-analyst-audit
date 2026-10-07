# Specialist Memo — CLW.AX

**Memo ID**: `CLW.AX_2026-10-07_equity_reit_v1@1.0_ee769998d314`
**Ticker**: CLW.AX (Charter Hall Long WALE REIT)
**Market**: Australia
**Sector**: Diversified/Long-WALE
**As of**: 2026-10-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Charter Hall Long WALE REIT offers a headline distribution yield of approximately 6.91% underpinned by a long-duration lease portfolio (WALE 10+ years) with government and investment-grade tenants, providing structural income resilience. However, management has guided to flat FY27 income despite high occupancy, reflecting headwinds from higher debt costs and limited external growth, which constrains near-term DPU trajectory. The unit price trades below NTA in a rate environment where the RBA policy rate of 4.35% reduces the appeal of property yields on a risk-adjusted basis. The OU Monte Carlo PGain of 68.9% at a 12-month horizon provides only moderate return probability, and the one-step conviction override reflects the flat-guidance risk. A catalyst for re-rating would require confirmed RBA rate cuts or accretive sponsor-pipeline deployment.

## Quantitative Chain

- E(R): 0.0590
- Std dev: 0.1183
- P-gain: 0.6894
- CAPM alpha: 0.0767
- Beta: 0.6261
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - RBA holds rates at 4.35%+ for longer or hikes further, causing cap rate expansion of 30-50bps and NTA erosion; DPU coverage falls below 1.0x as higher floating-rate debt costs bite post-refinancing; occupancy softens in office/industrial sub-sectors; distribution cut risk materialises; de-rating accelerates to -5% multiple contraction.
- **base**: E(R)=0.0590
  - Central case as built: distribution yield 6.91%, DPU growth flat (FY27 management guidance), mild de-rating of -1.0%; $2B refinancing insulates near-term debt costs; occupancy remains high across long-WALE portfolio; RBA holds at 4.35%.
- **bull**: E(R)=0.1700
  - RBA cuts policy rate by 50-75bps in H1 2027; cap rate compression drives NTA recovery and unit price re-rates toward NTA; DPU growth resumes at 2-3% driven by CPI-linked rent escalations; Charter Hall pipeline provides accretive acquisitions above 6% yield; multiple expansion of +3% as spread over risk-free widens attractively.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0691 (Cat A) — Trailing distribution yield of 6.91% sourced from published news coverage referencing CLW's most recently declared distribution at a unit price of AUD 3.25 (Kalkine, July 2026; confirmed by price_sensitive distribution announcement 2026-09-16). Observed public data.
- `dpu_growth_fwd` = 0.0 (Cat C) — Forward DPU growth set at 0.0% for FY27, consistent with management guidance for flat income (Kalkine, 01 Oct 2026: 'Guiding to Flat FY27 Income Despite High Occupancy'). FY26 results confirmed 2% growth with $2B refinancing completed (Investing.com, 12 Aug 2026). Zero growth is the central assumption. Sensitivity tested in scenario analysis.
- `multiple_change` = -0.01 (Cat C) — Mild de-rating assumption of -1.0% applied. CLW trades below NTA (Simply Wall St, 14 Aug 2026); RBA policy rate at 4.35% (BIS, 2026-09-24) sustains competition from fixed income. Prolonged below-NTA discount may persist or widen modestly. Sensitivity tested in scenario analysis.
- `rba_policy_rate` = 4.35 (Cat A) — Reserve Bank of Australia policy rate at 4.35% as of observation date 2026-09-24 (BIS WS_CBPOL series, age 13 days). Relevant for discount rate context and yield spread compression risk.
- `fy26_refinancing` = 2B_AUD (Cat A) — CLW completed approximately AUD 2 billion in debt refinancing at FY26 results (Investing.com, 12 Aug 2026 — 'Charter Hall Long WALE FY26 slides: 2% growth, $2B refinancing'). Supports gearing management and near-term debt maturity risk mitigation.
- `gearing_estimate` = 0.33 (Cat B) — Estimated gearing of ~33% derived from CLW's historically disclosed gearing range of 30–35% and confirmed FY26 $2B refinancing (Investing.com, 12 Aug 2026). Below AU A-REIT convention threshold of <40%. Treated as Category B pending confirmation from FY26 annual report filing (body unavailable for detailed extraction). Leverage gate assessed as pass.
- `wale_profile` = long (Cat B) — CLW is constituted as a Long WALE REIT with historically disclosed WALE of 10+ years across government, social infrastructure, industrial and commercial tenants. Exact WALE for FY26 period derived from prior reporting; not confirmed in captured filing bodies due to ASX pipeline body gaps. Category B estimate consistent with fund mandate.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- RBA holds or raises rates further, sustaining yield compression on REIT sector and widening NTA discount; CLW's cost of debt rises as $2B refinancing matures at higher margins
- Flat FY27 DPU guidance deteriorates into a distribution cut if occupancy softens in industrial or social-infrastructure sub-sectors, triggering further price de-rating
- Cap rate expansion driven by global fixed-income repricing erodes NTA materially, amplifying below-NTA discount and impairing asset-recycling capacity
- Charter Hall manager fee structures (AUM-based) create incentive misalignment if growth-at-any-cost acquisitions dilute distribution coverage
- IASP.L benchmark currency-basis noise inflates beta and alpha estimates; calibration is directional only (Phase 2 limitation) and formal backtesting discipline is absent until Phase 5

## Invalidation Condition
Exit the position if CLW reports two consecutive half-year periods of DPU coverage below 1.0x AFFO, or if gearing breaches 40% (the Australian A-REIT convention threshold), or if Charter Hall Group reduces its direct co-investment in CLW assets below 10%, signalling reduced sponsor alignment. A formal distribution cut announcement or NTA erosion exceeding 15% from the current level would also constitute an immediate invalidation trigger.
