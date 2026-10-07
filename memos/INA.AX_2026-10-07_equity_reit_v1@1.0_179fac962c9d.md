# Specialist Memo — INA.AX

**Memo ID**: `INA.AX_2026-10-07_equity_reit_v1@1.0_179fac962c9d`
**Ticker**: INA.AX (Ingenia Communities Group)
**Market**: Australia
**Sector**: Land-Lease Communities / Lifestyle REIT
**As of**: 2026-10-07
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Ingenia Communities Group is a high-growth Australian lifestyle REIT with structural tailwinds from an ageing population seeking affordable land-lease housing. At AUD 4.70 the stock trades at an approximate 10.5% discount to the Warburg Pincus indicative offer of AUD 5.25, providing partial downside support; however, the board's repeated rejection of non-binding bids while simultaneously pursuing the dilutive Peet acquisition raises material capital allocation concerns. Elevated one-year annualised volatility of 31.1% and a moderate PGain of 62.8% from the OU Monte Carlo support a cautious position size. The management alignment gate failure (board prioritising empire-building over value realisation) reduces conviction by one step to Low (2), reflecting the binary risk of the current corporate action environment overshadowing the otherwise attractive land-lease fundamentals.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.2115
- P-gain: 0.6279
- CAPM alpha: 0.0945
- Beta: 0.6992
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1800
  - Warburg Pincus withdraws takeover interest entirely; Peet acquisition completes at elevated cost and proves dilutive, pushing gearing above 40% regulatory convention; RBA maintains restrictive rates compressing land-lease cap rates; occupancy in holiday parks falls materially due to consumer spending weakness; DPU cut forced by rising interest costs and integration charges. Bear case also encompasses a scenario where the Peet deal collapses mid-execution, triggering break fees and reputational damage.
- **base**: E(R)=0.0700
  - Central case as built: distribution yield ~3.1%, DPU growth 4.0% from organic site additions and CPI-linked rent escalation, near-flat multiple change. Peet transaction remains under review with uncertain outcome; Warburg Pincus bid optionality provides partial price floor at AUD 5.25 but no certainty of completion. Gearing stays within the AU REIT convention of <40%.
- **bull**: E(R)=0.2200
  - Warburg Pincus raises offer to AUD 5.50+ and board recommends; or Peet acquisition completes and proves significantly accretive (>6% yield-on-cost for development sites); RBA cuts rates materially in 2H-2026, compressing cap rates and re-rating INA.AX multiple; occupancy in land-lease communities reaches full capacity; DPU growth accelerates to 6%+ driving further multiple expansion.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.031 (Cat B) — Estimated trailing DPU yield of ~3.1% derived from publicly known FY2025 DPS of approximately AUD 14.5c annualised divided by current market price of AUD 4.70. Ingenia is a growth-oriented land-lease REIT with lower current-income yield offset by development-driven capital growth. No INA.AX-specific filing body was successfully matched by the ASX pipeline at as_of date (cross-contamination noted); yield estimate uses external public knowledge of Ingenia's distribution history.
- `dpu_growth_3yr` = 0.04 (Cat C) — Forward DPU growth assumption of 4.0% p.a. reflecting: (1) organic rent escalation in land-lease communities (CPI-linked plus site additions); (2) development completions from Ingenia's active greenfield pipeline; (3) partially offset by integration uncertainty from the proposed Peet (ASX: PPC) acquisition announced August 2026 per ASX headline (INA.AX ASX announcement 'Ingenia Communities proposes to acquire Peet, boosting growth', 2026-08-26). Sensitivity: bear case 0%, bull case 6%.
- `multiple_change` = -0.001 (Cat C) — Assumed near-flat multiple change of -0.1%. The current price of AUD 4.70 partially prices in M&A optionality (Warburg Pincus further revised bid at AUD 5.25, reported 2026-09-30). Board rejection of bids (INA.AX headlines: 'Ingenia Rejects Non-Binding Indicative Offer' 2026-09-06, 'Ingenia Rejects Revised Non Binding Indicative Offer' 2026-09-20) creates residual M&A premium balanced against Peet acquisition dilution risk. Net multiple change assumed approximately zero in the base case.
- `ma_optionality` = disclosed (Cat B) — Warburg Pincus has submitted multiple non-binding indicative offers for INA.AX, with the most recent at AUD 5.25/share (approximately 11.7% premium to current price of AUD 4.70 as of 2026-10-07). Board has rejected all offers. An 'Update on Further Revised Non-Binding Indicative Offer' was released 2026-10-04 (price_sensitive=True per ASX announcement record). M&A optionality is treated as a qualitative tailwind partially embedded in the current price but not added to E(R) due to low deal-closure probability given repeated board rejections.
- `rba_policy_rate` = 4.35 (Cat A) — RBA cash rate as of 2026-09-24 per BIS CBPOL data (observation_date 2026-09-24, age_days 13). Relevant to AUD funding costs and distributable income headwinds.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The currency basis means measured beta of 0.699 may overstate or understate true property-market sensitivity. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Peet acquisition proves dilutive and gearing rises above 40%, triggering investor re-rating and potential equity raise at a discount.
- Warburg Pincus withdraws all takeover interest, removing the current price floor and returning INA.AX toward pre-bid levels (~AUD 3.57 seen in early September 2026).
- Higher-for-longer RBA cash rate (currently 4.35%) sustains elevated AUD borrowing costs, compressing distributable income and NAV.
- Consumer discretionary weakness reduces demand for Ingenia's holiday and tourist parks segment, which generates a meaningful share of revenue.
- Integration execution risk from concurrent Peet deal and organic development pipeline strains management bandwidth and balance sheet.

## Invalidation Condition
Exit if Warburg Pincus formally withdraws all takeover proposals AND the Peet acquisition reaches binding agreement at terms that push pro-forma gearing above 38% LVR, or if DPU is cut by more than 10% in any reported half-year relative to the prior corresponding period, or if INA.AX price breaks below AUD 3.80 on high volume indicating market loss of confidence in the strategic direction.
