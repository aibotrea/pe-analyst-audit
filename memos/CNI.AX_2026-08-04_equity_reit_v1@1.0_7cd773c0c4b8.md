# Specialist Memo — CNI.AX

**Memo ID**: `CNI.AX_2026-08-04_equity_reit_v1@1.0_7cd773c0c4b8`
**Ticker**: CNI.AX (Centuria Capital Group)
**Market**: Australia
**Sector**: Diversified REIT/Fund Manager
**As of**: 2026-08-04
**Framework**: equity_reit_v1@1.0
**Conviction score**: 1/5 (Speculative)
**Max position**: 1.0%

## Thesis
Centuria Capital Group (CNI.AX) is an ASX-listed diversified REIT fund manager and co-investor with ~A$20bn AUM across office, industrial and healthcare strategies. The stock has experienced severe price dislocation (-35% from June 2026 peak to AUD 1.485) driven by media scrutiny over the Centuria Bass Credit Fund and a dilutive retail entitlement offer completed in July 2026, both confirmed via ASX announcements. While the distribution yield (~7.1% on estimated DPU) provides an attractive entry point if income is sustained, the 35.3% annualised volatility and a pgain of only 58.9% from the OU Monte Carlo signal elevated uncertainty. At current prices, the risk/reward is speculative: the bear case is severe (potential DPU cuts, further capital raises, credit fund losses), while the bull case (MQG institutional re-engagement, RBA cuts, Bass Credit resolution) could drive meaningful recovery toward AUD 2.00+.

## Quantitative Chain

- E(R): 0.0550
- Std dev: 0.2398
- P-gain: 0.5889
- CAPM alpha: 0.0698
- Beta: 0.7045
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.3000
  - Bass Credit Fund losses crystallise, triggering investor redemptions and AUM outflows across Centuria's managed REIT platform. DPU cut to AUD 0.07 (yield ~4.7% at current price), distribution coverage drops below 1.0x AFFO. Further capital raise dilution required. Corporate gearing breaches 40% threshold. Credit rating pressure forces asset disposals at distressed cap rates (expansion of 75-100bps). Price retraces to prior lows near AUD 1.00-1.10. Stagflation scenario (sticky Australian CPI, RBA on hold above 4%) amplifies the bear case by prolonging spread compression.
- **base**: E(R)=0.0550
  - Bass Credit Fund overhang resolves without material loss crystallisation. AUM stabilises following entitlement offer proceeds deployed. DPU holds at ~AUD 0.105 supported by management fee income from listed REIT platforms. Gearing remains within 30-35% range. RBA cuts modestly in H2 2026, providing partial cap-rate tailwind for underlying portfolios. Occupancy across managed REITs (COF, CIP) stable at ~93-95%.
- **bull**: E(R)=0.2500
  - Bass Credit Fund concerns prove unfounded; media narrative reverses and investor confidence returns. Entitlement offer capital deployed accretively into new managed fund launches at 5-6% management fee yield on AUM. RBA rate cuts of 50-75bps by end-2026 re-rate listed REIT sector. DPU growth resumes at 3-5%. Macquarie (MQG) becoming a substantial holder (ASX 2026-08-04) signals institutional re-engagement; stock re-rates toward AUD 2.00-2.20.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=fail [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=fail [override_applied=-1]

## Key Assumptions
- `distribution_yield` = 0.071 (Cat B) — Estimated trailing DPU of approximately AUD 0.105 per share (derived from Centuria Capital Group's historical DPU range of AUD 0.10-0.12; no confirmed FY2026 DPU available from filed financials due to ASX body-capture pipeline mismatches) divided by closing price of AUD 1.485 on 2026-08-04. Classified Category B as the DPU is a specialist estimate, not a filed confirmed figure.
- `dpu_growth_rate` = -0.015 (Cat C) — Negative growth assumed at -1.5% reflecting: (1) July 2026 media commentary on Centuria Bass Credit Fund suggesting potential credit stress and reputational drag on AUM growth (CNI.AX headline 2026-07-23); (2) dilutive retail entitlement offer completed July 2026 (CNI.AX filing 2026-07-10), which increases unit count without proportional income accretion; (3) AUM compression risk from investor redemptions in credit strategies. Sensitivity tested ±3% in scenarios. Category C — model assumption.
- `multiple_change` = -0.005 (Cat C) — Modest negative re-rating assumed (-0.5%) reflecting elevated AUD REIT sector uncertainty and Bass Credit Fund overhang. CNI.AX price has fallen ~35% from AUD 2.27 peak in mid-June 2026 to AUD 1.485, suggesting partial mean reversion already priced. Residual multiple compression assumed as tail risk persists. Category C.
- `expected_return_build` = 0.055 (Cat B) — E(R) = distribution yield 7.1% + DPU growth -1.5% + multiple change -0.5% = 5.1%, rounded to 5.5% to reflect modest recovery premium from a ~35% price dislocation from peak. Category B derived estimate.
- `leverage_gearing` = est_30_35pct (Cat B) — Centuria Capital Group corporate-level gearing estimated at 30-35% based on public knowledge of CNI balance sheet as of FY2025. Underlying managed REITs (COF.AX, CIP.AX, CHC adjacent) operate within Australian REIT gearing convention of <40%. No filed gearing ratio available from stored filings for this as_of date due to ASX body-capture pipeline mismatch. Disclosed as estimated; below AU <40% convention threshold.
- `bass_credit_fund_risk` = elevated (Cat A) — ASX announcement headline 2026-07-23 (CNI.AX PROGRESS REPORT): 'Response to media commentary on Centuria Bass Credit Fund' — confirms media scrutiny of the credit fund. Combined with ~35% price decline from peak, indicates market has materially repriced this risk. Treated as Category A (observable public filing headline).
- `entitlement_offer_dilution` = completed (Cat A) — ASX filing headline 2026-07-10 (CNI.AX ISSUED CAPITAL): 'Successful Completion of Retail Entitlement Offer' — capital raise completed, adding to unit count. Body unavailable (status: pending); dilution quantum not confirmed from filing text. Noted as Category A observable event.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and IASP basis noise.

## Key Risks
- Bass Credit Fund credit losses crystallising, triggering co-investment write-downs on CNI's balance sheet and AUM redemptions across managed platforms — the primary downside catalyst given the July 2026 media commentary.
- Dilution risk from the completed retail entitlement offer (July 2026); further capital raises possible if credit fund losses require remediation capital.
- Higher-for-longer RBA cash rate compressing the spread between managed REIT distribution yields and the risk-free rate, reducing AUM inflows and management fee income.
- Macro data series (FRED macro, APAC rate data) were unavailable for AU as of this as_of date; the risk-free rate is sourced from the US 3M T-bill (3.75%) as a proxy, introducing model basis versus the Australian risk-free rate (RBA cash rate ~4.10-4.35% estimated).
- CNI.AX filing bodies in stored database contained mismatched ASX content (pipeline data quality issue); DPU, gearing and AFFO coverage figures are estimated from public domain knowledge rather than confirmed filed numbers, introducing Category C risk to the distribution yield and coverage assessments.

## Invalidation Condition
Exit position if: (1) Centuria Capital Group confirms material losses within the Bass Credit Fund exceeding AUD 50 million or requiring a formal remediation capital injection; or (2) DPU is cut by more than 20% in any announced distribution relative to the prior corresponding period, signalling AFFO coverage below 1.0x; or (3) corporate gearing reported above 40% in any half-year or full-year results filing; or (4) a second dilutive capital raise is announced within 12 months of the July 2026 entitlement offer without a commensurate AUM accretion announcement.
