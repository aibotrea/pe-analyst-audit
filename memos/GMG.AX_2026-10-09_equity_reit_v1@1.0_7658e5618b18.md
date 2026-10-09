# Specialist Memo — GMG.AX

**Memo ID**: `GMG.AX_2026-10-09_equity_reit_v1@1.0_7658e5618b18`
**Ticker**: GMG.AX (Goodman Group)
**Market**: Australia
**Sector**: Industrial/Logistics & Data Centres
**As of**: 2026-10-09
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Goodman Group (GMG.AX) is Australia's premier industrial and logistics REIT, now executing a high-conviction pivot into data centre development that is reshaping its earnings profile. At AUD 27.16, GMG trades at a significant premium (approximately 25x operating EPS) that prices in substantial data centre upside but leaves limited margin of safety at a 12-month horizon. The annualised distribution yield of ~1.25% is negligible relative to the 4.05% risk-free rate, placing the entire total return thesis on capital appreciation from earnings growth and multiple expansion — both of which carry material uncertainty. The OU Monte Carlo simulation produces a sim return of 5.4% with std_dev of 19.5% and PGain of only 60.9%, reflecting the wide dispersion of outcomes inherent in a high-multiple, low-yield industrial/data centre hybrid. A one-step qualitative gate reduction is applied for data centre concentration risk and elevated valuation premium, resulting in a conviction score of 2 (Low) with a 3% maximum position.

## Quantitative Chain

- E(R): 0.0550
- Std dev: 0.1954
- P-gain: 0.6090
- CAPM alpha: 0.0850
- Beta: 0.7699
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.1500
  - Data centre capex cycle disappoints: WIP yields compress to sub-5% as hyperscaler tenants renegotiate terms; operating EPS growth slows to 3%; premium multiple re-rates sharply from 25x toward 18x (-25% to -30% price impact); AUD/USD weakness amplifies foreign earnings headwind. Gearing remains manageable but dividend coverage scrutinised. Global rate shock (US 10Y >5.5%) triggers broader REIT de-rating, compounding multiple compression.
- **base**: E(R)=0.0550
  - Central case as built in chain: distribution yield 1.25%, retained earnings contribution 3.0%, operating EPS growth ~10% (FY27 guidance midpoint), modest multiple compression -0.75%. Data centre WIP converts to income on schedule; logistics occupancy remains resilient at ~97-98%; gearing stays below 15% look-through.
- **bull**: E(R)=0.2800
  - Data centre pipeline accelerates ahead of schedule with hyperscaler demand exceeding supply; operating EPS growth upgrades to 14-16%; premium multiple expands further as AI infrastructure narrative strengthens (25x to 28-30x); global rate pivot (RBA cuts 75bps) drives REIT sector re-rating. AUM growth from new data centre fund vehicles adds management fee income. Distribution policy remains unchanged, with capital gains driving total return.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0125 (Cat A) — Trailing distribution per security ~AUD 0.34 on closing price AUD 27.16 (2026-10-09). GMG maintains a conservative ~30% payout ratio of operating earnings; published DPS reflects filed distribution guidance from FY2026 results (August 2026 'Strong FY26' release). Category A — observable from published filings.
- `operating_eps_growth` = 0.1 (Cat C) — GMG management guided ~9-11% operating EPS growth for FY27, driven by data centre work-in-progress delivery and AUM expansion. Midpoint of guidance range used (10%). Sensitivity: bear case assumes 3%, bull case assumes 14%. Basis is management guidance from FY2026 results release (August 2026).
- `retained_earnings_growth_contribution` = 0.03 (Cat B) — GMG retains ~70% of operating EPS (~AUD 0.77/security at 1.10 operating EPS). Reinvested at an assumed 4% incremental return on equity (conservative given GMG's AUM expansion track record). Contribution to total return: ~3.0%. Category B — derived estimate from operating EPS structure and payout policy.
- `multiple_change` = -0.0075 (Cat C) — GMG trades at ~25x operating EPS vs historical range of 18-22x, implying a premium that is partially justified by data centre growth but carries compression risk. Assumed -0.75% total return headwind from modest multiple normalisation. Sensitivity: bear case -4%, bull case +3%. Category C — subjective valuation assumption.
- `expected_return_composition` = 0.055 (Cat B) — E(R) = distribution yield (1.25%, Cat A) + retained earnings/growth contribution (3.0%, Cat B) + multiple change (-0.75%, Cat C) + residual EPS growth attribution to price (2.0%, Cat C) = 5.5%. Weighted composite; sensitivity tested in scenario analysis.
- `gearing_ratio` = 0.1 (Cat B) — GMG net gearing approximately 8-12% (look-through), one of the lowest in the Australian REIT sector. Well below the 40% Australian REIT convention threshold. Based on publicly disclosed balance sheet data from FY2026 annual results. ASX filing bodies for GMG.AX were not extractable from the stored filing pipeline (body-capture mismatch on ASX phase 01 v3.3); estimate draws on FY2026 results news coverage.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. GMG beta of 0.770 reflects moderate co-movement with the APAC REIT index, partially dampened by GMG's unique data centre business mix. iasp caveat applies throughout.
- `filing_body_gap` = disclosed (Cat B) — Stored ASX filing bodies returned for GMG.AX ticker were mismatched (containing filings from other ASX companies — a known Phase 01 v3.3 body-capture limitation for ASX). Key fundamental assumptions (DPS, gearing, operating EPS) sourced from public news coverage of GMG FY2026 results (August 2026) and GMG's well-documented public disclosures. Gap disclosed per filing body rules.

## Key Risks
- Multiple compression risk: GMG trades at ~25x operating EPS vs historical 18-22x range; any slowdown in data centre earnings delivery could trigger a sharp re-rating that dominates the modest distribution yield
- Data centre execution risk: large and growing WIP (work-in-progress) portfolio in an asset class GMG has less operational history in; hyperscaler demand concentration and lease-up timing uncertainty
- Higher-for-longer interest rates: AUD 3-month T-bill at 4.05% creates a negative yield spread vs the 1.25% distribution yield, and rising rates reduce the present value of long-duration development profits
- AUD/foreign earnings currency risk: ~60% of GMG's AUM and earnings are offshore (US, Europe); AUD appreciation would reduce reported operating EPS
- ASX filing body gap: stored ASX filing bodies for GMG.AX were mismatched in the pipeline; key fundamental figures (DPS, gearing, coverage) rely on public news coverage rather than directly extracted filing text — a data-quality risk acknowledged in this memo

## Invalidation Condition
Exit or significantly reduce position if GMG operating EPS growth for FY27 is confirmed below 5% (versus guidance of 9-11%), or if data centre WIP yield-on-cost falls below 6% on any major project announcement, or if net gearing (look-through) rises above 25% through debt-funded acquisitions, or if the operating EPS multiple expands beyond 30x without a corresponding upward revision to earnings, signalling speculative excess that would invert the risk-reward at a 12-month horizon.
