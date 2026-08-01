# Specialist Memo — TS0U.SI

**Memo ID**: `TS0U.SI_2026-07-28_equity_reit_v1@1.0_4eda51144bae`
**Ticker**: TS0U.SI (OUE REIT)
**Market**: Singapore
**Sector**: Diversified (Office/Hospitality)
**As of**: 2026-07-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
OUE REIT is executing a meaningful portfolio simplification via the proposed divestment of Crowne Plaza Changi Airport at a modest premium to valuation, with proceeds earmarked for deleveraging and a SGD 20m special distribution to unitholders. The post-divestment portfolio concentrates in Singapore office (OUE Downtown 1 & 2) and hospitality (Hilton Singapore Orchard), providing a cleaner income profile at a declared 1H 2026 DPU of 1.26 cents/unit. A forward recurring yield of approximately 6.1% — net of the hotel contribution to be divested — provides a meaningful 228bps spread over the 3.82% T-bill rate, supporting income-oriented positioning. Beta of 0.27 versus IASP.L (currency-basis caveat applies) indicates low co-movement with the broader APAC REIT benchmark. PGain of 70.8% from the OU Monte Carlo simulation at a 12-month horizon supports moderate conviction, tempered by a one-step qualitative override reflecting post-divestment asset concentration in two primary properties.

## Quantitative Chain

- E(R): 0.0840
- Std dev: 0.1525
- P-gain: 0.7076
- CAPM alpha: 0.0650
- Beta: 0.2692
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Crowne Plaza divestment delayed or fails to complete, leaving gearing above 45% regulatory threshold and triggering mandatory deleveraging via equity issuance. Office occupancy at OUE Downtown 1 & 2 falls to below 88% as Singapore CBD office demand softens amid global macro slowdown or trade-shock scenario. DPU cut to ~1.0 cent/unit annualised (from ~2.52 cents), yield support collapses. Cap rate expansion of 30-40bps on Singapore commercial real estate driven by higher-for-longer US rate environment feeding into SGD SORA.
- **base**: E(R)=0.0830
  - Central case: Crowne Plaza Changi Airport divestment completes in 2H 2026 reducing gearing to ~38-40%. Recurring DPU ~2.14 cents/unit annualised (post-CPCA removal), recurring yield ~6.1% at SGD 0.357. Special distribution of SGD 20m (~0.4 cents/unit) adds one-off uplift. Organic office growth +1.0%. Slight multiple re-rating of +0.5% as balance sheet improves.
- **bull**: E(R)=0.2200
  - Crowne Plaza divestment completes promptly with additional capital recycling into higher-yielding Singapore office or mixed-use assets. Gearing falls to ~35%, enabling debt-funded accretive acquisition from OUE Limited sponsor pipeline. Singapore CBD office demand strengthens on financial sector expansion. DPU recovers to ~2.8-3.0 cents/unit annualised. NAV discount narrows materially as institutional investors re-rate the cleaner, lower-leverage portfolio. Cap rates stable or compress 10-20bps.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.061 (Cat A) — Annualised DPU derived from declared 1H 2026 distribution of SGD 0.0126 per unit (TS0U.SI 2026-07-22 CACT filing), annualised to SGD 0.0252 and divided by closing price SGD 0.357 = 7.06% gross. A Category C haircut of ~15% applied to strip out Crowne Plaza hotel contribution post-divestment (announced 2026-06-25), yielding a forward recurring yield of ~6.1%. Declared 1H DPU per unit is Category A; post-divestment haircut is Category C.
- `dpu_growth_rate` = 0.01 (Cat C) — Organic DPU growth of +1.0% p.a. assumed for remaining office portfolio (OUE Downtown 1 & 2, Hilton Singapore Orchard). Divestment proceeds from Crowne Plaza Changi Airport (~SGD 500m, TS0U.SI 2026-06-25 announcement) applied to deleverage, partially offsetting smaller income base. Net growth sensitive to lease renewal outcomes; sensitivity tested in scenario analysis.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% positive multiple re-rating assumed as gearing declines post Crowne Plaza Changi Airport divestment. OUE REIT trades at a discount to NAV consistent with Singapore diversified REITs. Category C assumption with high sensitivity to interest rate trajectory and Singapore commercial real estate cap rates.
- `special_distribution_contribution` = 0.008 (Cat B) — SGD 20m special distribution announced in connection with Crowne Plaza Changi Airport divestment (TS0U.SI 2026-06-25 filing). Estimated ~0.4 cents/unit based on ~4.8bn units outstanding. Pro-rated at ~0.8% contribution to 12-month E(R). Category B: unit count derived from manager fee-in-units filings and disclosed capitalisation; exact unit count not confirmed from available truncated filings.
- `gearing_post_divestment` = elevated_reducing (Cat B) — Gearing not explicitly stated in available 1H 2026 filing body (TS0U.SI 2026-07-22 Half Yearly Results — body text not parsed beyond headline). Crowne Plaza divestment at ~SGD 500m above book (1.3% premium per news, 2026-06-24) is explicitly for deleveraging. Expected to reduce below Singapore 45% regulatory guidance post-completion. Treated as Category B pending confirmed gearing number.
- `manager_fee_in_units` = positive_alignment (Cat A) — Manager base fee paid by way of issue of new units in OUE REIT (TS0U.SI 2026-07-27 ANNC filing). This conserves cash for distribution and aligns manager incentives with unit price performance. Minor dilutive effect on per-unit metrics.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same currency and iasp noise.

## Key Risks
- Crowne Plaza Changi Airport divestment delay or failure to complete would leave gearing elevated above 45% regulatory comfort, requiring equity issuance and DPU dilution
- Post-divestment concentration in OUE Downtown 1 & 2 creates significant single-market (Singapore CBD office) exposure; any step-down in occupancy or renewal rents materially impairs DPU
- Higher-for-longer global interest rates feeding through SGD SORA compress the yield spread and could trigger cap rate expansion on the remaining commercial assets
- Manager base fee paid in units creates ongoing dilution to per-unit DPU, mildly offsetting income return over time
- OUE Limited sponsor IPT transactions (e.g., Healthway Medical lease renewal) require ongoing unitholder scrutiny to ensure arm's-length pricing and absence of value transfer to related parties

## Invalidation Condition
Exit position if: (1) the Crowne Plaza Changi Airport divestment is formally terminated or materially restructured below SGD 480m net proceeds, preventing targeted deleveraging; (2) reported gearing rises above 45% in the 1H 2026 financial statements without a credible timeline to reduce below 42% within two quarters; (3) annualised DPU for FY2026 falls below 2.0 cents/unit on a recurring basis excluding one-off special distributions, implying a yield of less than 5.6% at current price; or (4) OUE Downtown portfolio committed occupancy falls below 88% for two consecutive reporting periods.
