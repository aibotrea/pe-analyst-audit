# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-09-23_equity_reit_v1@1.0_ba29a91074bd`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Office/Diversified
**As of**: 2026-09-23
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus (DXS.AX) offers a headline distribution yield of approximately 6.1% at the current AUD 5.56 price, providing a positive spread over the 3-month T-bill rate of 4.0%. However, the trust's heavy CBD office concentration (~70% of portfolio) remains a material structural risk in an environment of normalised hybrid work patterns and uncertain office demand recovery. The OU Monte Carlo simulation yields a 66.9% probability of positive return over 12 months (PGain), reflecting the income cushion against meaningful downside volatility (σ=20.3%). CAPM alpha of 7.2% versus the negative-returning IASP.L benchmark is encouraging but inherits currency-basis noise. The active on-market buyback and portfolio reset strategy provide some support, but the asset concentration gate override reduces conviction to Low (score 2), warranting a maximum 3% portfolio position until office fundamentals show clearer stabilisation.

## Quantitative Chain

- E(R): 0.0610
- Std dev: 0.1380
- P-gain: 0.6691
- CAPM alpha: 0.0721
- Beta: 0.5732
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1200
  - Australian CBD office vacancy continues to rise toward 20%+, driven by hybrid work adoption and lease expiry concentration. DPU cut of 15-20% as FFO coverage deteriorates below 1.0x AFFO. Cap rate expansion of 50-75bps triggers NTA writedowns of 10-15%. Rate environment remains elevated (RBA holds above 3.5%), compressing yield spread to near zero. Portfolio reset fails to execute accretive divestments, leaving balance sheet gearing above 35%.
- **base**: E(R)=0.0610
  - Central case as built in the quantitative chain: distribution yield 6.10%, DPU growth +0.50%, cap rate drag -0.50%. CBD office occupancy stabilises around 90-92% in premium-grade assets. On-market buyback provides modest price support. Portfolio recycling progresses at book value. Gearing held within 28-32%. RBA continues measured easing.
- **bull**: E(R)=0.2200
  - RBA accelerates easing cycle, driving 10-year Australian bond yields below 3.5% and cap rate compression of 25-50bps. Office demand recovers as employers reinforce return-to-office mandates, lifting CBD occupancy toward 94-95% and enabling rental reversion. Dexus executes accretive asset recycling into logistics/industrial at 6%+ yields, lifting FFO growth to 3-5% p.a. Buyback enhances per-unit NTA. Market re-rates toward NAV, currently implying a 15-20% discount.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=fail [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.061 (Cat B) — Implied trailing distribution yield derived from Kalkine-cited 6.42% yield at ~AUD 5.73 (late July 2026), adjusted to AUD 5.56 closing price as of 2026-09-23. Implied DPS ~AUD 0.34 per unit. Downward-adjusted to 6.10% to reflect portfolio reset headwinds and conservative treatment of FY2026 distribution guidance uncertainty. Category B — derived estimate from observed analyst commentary and current market price.
- `dpu_growth` = 0.005 (Cat C) — Forward DPU growth of +0.50% p.a. assumed for base case. Reflects modest organic income growth from industrial and logistics assets partially offsetting declining office rental income. Dexus's CBD office exposure (~70% of portfolio by value) faces structural headwinds from hybrid work normalisation. Growth capped near zero; upside contingent on asset recycling into higher-yielding sectors. Sensitivity tested across scenarios.
- `multiple_change` = -0.005 (Cat C) — Assumed -0.50% multiple/cap rate drag reflecting ongoing cap rate uncertainty for Australian CBD office, persistent higher-for-longer rate environment, and re-rating pressure from structural office demand concerns. Partially offset by buyback support (on-market buy-back active as of September 2026 per ASX announcements). Sensitivity tested across scenarios.
- `rba_cash_rate` = 0.035 (Cat C) — RBA cash rate estimated at approximately 3.50% as of September 2026. Live APAC rate retrieval returned no data; this is a documented assumption based on RBA easing cycle that commenced in early 2025. Used for qualitative context only (yield spread analysis); not directly embedded in CAPM chain, which uses DTB3 US T-bill as risk-free rate per framework methodology.
- `gearing_assumption` = 0.3 (Cat B) — Dexus gearing ratio estimated at approximately 28-32% of total assets based on historical disclosures and publicly available FY2025 annual report data (DXS.AX has historically reported look-through gearing in this range). No current ASX filing body confirmed specific FY2026 figure (ASX filing body capture returned cross-contaminated content from other issuers). Assessed against the AU A-REIT convention of <40% by the framework.
- `office_concentration` = 0.7 (Cat B) — Dexus CBD office exposure estimated at approximately 65-75% of portfolio by value based on Dexus investor presentations and FY2025 portfolio composition. Portfolio reset announced in 2026 involves capital recycling but the majority of income remains office-derived. This concentration underpins the asset_quality_concentration qualitative gate override.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The IASP.L/AUD currency basis introduces noise into the 0.573 beta estimate, which may understate true AUD-denominated REIT-market sensitivity. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Structural decline in Australian CBD office demand from hybrid work normalisation, leading to sustained vacancy above 15% and downward rental reversion pressure
- Higher-for-longer interest rate environment compressing yield spread and triggering cap rate expansion, causing NTA writedowns and increased cost of debt on refinancing
- Distribution cut risk if FFO/AFFO coverage falls below 1.0x — ASX filing bodies for DXS.AX were unavailable via the stored reader (cross-contamination), preventing confirmation of current AFFO coverage ratio
- Portfolio recycling execution risk: divestment of office assets into a thin transaction market may realise below-book values, crystallising losses and reducing distributable income
- AUD/GBP currency basis embedded in the IASP.L beta (0.573) may understate true market sensitivity; actual drawdown correlation with APAC REIT sell-offs may be higher than the coefficient implies

## Invalidation Condition
Exit the position if Dexus reports two consecutive half-year periods with office portfolio occupancy below 88%, or if the trust announces a distribution per unit reduction exceeding 15% from the FY2026 base, or if look-through gearing rises above 38% of total assets, or if management formally abandons the portfolio recycling program without an alternative capital deployment strategy that preserves distributable income above 1.0x AFFO coverage.
