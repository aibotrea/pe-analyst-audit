# Specialist Memo — SKG.AX

**Memo ID**: `SKG.AX_2026-09-15_equity_reit_v1@1.0_7b5a133d0d30`
**Ticker**: SKG.AX (Storage King Group)
**Market**: Australia
**Sector**: Self-Storage
**As of**: 2026-09-15
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Storage King Group (SKG.AX) is Australia's leading listed self-storage REIT, having completed management internalisation and rebranding in May 2026 — a structurally positive step that eliminates external fee drag and aligns management incentives with unitholders. The stock has declined ~19% from its June 2026 level to A$1.085, pushing the estimated distribution yield to approximately 6.0%, which represents a meaningful spread over the Australian risk-free rate at a time when the RBA easing cycle may provide cap rate tailwinds. Beta of 0.59 against IASP.L (currency-basis caveat applies) indicates moderate co-movement with the broader APAC REIT index. The OU Monte Carlo simulation yields a sim return of 7.4% at 12 months with a PGain of 68.1%, supporting a moderate conviction score of 3, constrained by the high annualised volatility of 23.3% and uncertainty around the FY26 DPU quantum given pipeline body-capture gaps for this ticker.

## Quantitative Chain

- E(R): 0.0750
- Std dev: 0.1581
- P-gain: 0.6807
- CAPM alpha: 0.0887
- Beta: 0.5890
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Australian self-storage demand softens materially as household formation slows and consumers reduce discretionary storage spend in a prolonged higher-rate environment. Occupancy falls 3-5 percentage points below current levels, DPU coverage drops below 1.0x AFFO, and the stock re-rates to a cap rate 50bps wider. RBA holds rates higher for longer or global credit conditions tighten, triggering cap rate expansion across the Australian A-REIT sector. Distribution cut risk emerges.
- **base**: E(R)=0.0740
  - Central case as built in quantitative chain: 6.0% distribution yield, 1.5% organic DPU growth, neutral multiple change. Internalisation cost savings support stable distribution. Occupancy broadly stable. RBA easing modestly supportive of cap rate stabilisation. No material acquisitions or capital events.
- **bull**: E(R)=0.2000
  - Accelerated RBA rate cuts compress storage cap rates and trigger a sector re-rating. Internalisation savings exceed expectations, lifting AFFO coverage and allowing a DPU uplift of 5-8%. Storage demand recovers on renewed household formation and SME expansion. Stock mean-reverts toward pre-FY26 results levels near A$1.30-1.35, implying 20-25% total return including distribution.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.06 (Cat B) — Estimated trailing distribution yield at current price of A$1.085. No confirmed per-unit DPU figure extracted from filed bodies (ASX pipeline body capture returned mismatched issuer content for SKG.AX). Derived from prior Abacus Storage King (ASK) annualised DPU of ~6.5 cents/unit and current price, yielding approximately 6.0%. Treated as Category B given derivation uncertainty.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a. reflecting modest organic revenue growth in Australian self-storage demand, partially offset by moderating occupancy in a higher-rate environment. Internalisation of management (completed May 2026) provides a one-off cost saving that partially supports near-term distribution. Sensitivity: +/- 1% growth shifts E(R) by approximately 100bps. Category C — forward-looking assumption without confirmed guidance.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumed for base case. Stock has declined ~19% from June 2026 levels (A$1.34 to A$1.085), suggesting meaningful re-rating has already occurred post FY26 results. No mean-reversion uplift assumed in base case given continued downward price drift through September 2026. Bull case allows for modest re-rating.
- `internalisation_governance` = positive (Cat A) — SKG.AX (formerly Abacus Storage King, ASX:ASK) completed management internalisation and rebranded to Storage King Group in May 2026 per ASX announcement dated 18 May 2026 (corroborated by Motley Fool Australia and Market Index coverage). Internalisation eliminates external management fees and aligns management incentives with unitholders. Treated as Category A observed public event.
- `fy26_results_price_event` = negative (Cat A) — FY26 results announcement (ASX price-sensitive periodic report filed 2026-08-13) coincided with a ~8.5% single-day decline on 2026-08-14 (volume 9.45M vs ~1M average), with continued drift to A$1.085 by 2026-09-15. FY26 Investor Presentation filed 2026-08-13 flagged as price-sensitive. Body content unavailable due to ASX pipeline mismatch for SKG.AX — assumption gap disclosed.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. currency and iasp basis noise means the 0.589 coefficient reflects both self-storage sector sensitivity and AUD/GBP exchange rate dynamics. Treated as Category B input. CAPM alpha inherits the same noise.
- `rba_cash_rate` = 0.04 (Cat C) — RBA cash rate estimated at approximately 4.0% as of September 2026. Live and stored APAC rate feeds returned no data for AU as of this date. Estimate based on public knowledge of the RBA easing cycle in 2025-2026, with the cash rate assumed to have settled near 4.0% after cuts from the 4.35% peak. Category C given no confirmed live data feed.

## Key Risks
- FY26 DPU and AFFO coverage metrics could not be confirmed from filed bodies due to ASX pipeline content mismatch — actual distribution quantum and coverage ratio remain unverified inputs to this memo.
- Post-FY26 results re-rating has been persistent and sustained (19% decline over ~3 months), suggesting the market has identified a fundamental issue — risk that the stock continues to drift lower if occupancy or DPU guidance disappoints in FY27.
- Self-storage demand is discretionary at the margin; a prolonged consumer spending slowdown in Australia driven by higher-for-longer mortgage rates could reduce occupancy and revenue per available square metre.
- IASP.L benchmark returned -5.1% annualised over the trailing 5 years, making the CAPM market return input deeply negative — this makes CAPM alpha artificially elevated and should be treated as a Category B signal only.
- Internalisation execution risk: while structurally positive, the transition adds operational complexity; any cost overrun or management team instability post-internalisation would pressure the investment thesis.

## Invalidation Condition
Exit position if FY27 interim distribution per unit is cut by more than 10% versus FY26 levels, or if reported gearing exceeds 38% of GAV for two consecutive reporting periods, or if occupancy across the self-storage portfolio falls below 85% for one reporting period, or if management communicates a formal capital raise at a material discount to NAV indicating balance sheet stress.
