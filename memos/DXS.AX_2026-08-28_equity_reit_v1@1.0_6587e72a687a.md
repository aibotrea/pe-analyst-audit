# Specialist Memo — DXS.AX

**Memo ID**: `DXS.AX_2026-08-28_equity_reit_v1@1.0_6587e72a687a`
**Ticker**: DXS.AX (Dexus)
**Market**: Australia
**Sector**: Diversified
**As of**: 2026-08-28
**Framework**: equity_reit_v1@1.0
**Conviction score**: 2/5 (Low)
**Max position**: 3.0%

## Thesis
Dexus (DXS.AX) is Australia's largest diversified office-focused REIT with a current distribution yield of ~6.3%, representing a meaningful spread over the 3.69% US T-bill proxy. However, the elevated annualised volatility of ~20% and news-flagged debt strain on the cash backstop limit upside confidence. Beta of 0.55 versus IASP.L (currency-basis caveat applies) suggests moderate co-movement with the APAC REIT index. The OU Monte Carlo assigns a 63.6% probability of positive return over a 12-month horizon, reflecting the tension between a high starting yield and the structural headwinds facing CBD office assets. An on-market buyback provides partial downside support, but FY26 DPU is held rather than growing, and further valuation write-downs remain a risk in the current rate environment.

## Quantitative Chain

- E(R): 0.0480
- Std dev: 0.1359
- P-gain: 0.6363
- CAPM alpha: 0.0567
- Beta: 0.5511
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Office occupancy deteriorates to below 88%, DPU cut by 5% as AFFO coverage slips below 1.0x, gearing breaches 40% covenant triggering asset sales at distressed cap rates (cap rate expansion 50bps), and AUD weakens further compressing NTA. Debt refinancing at materially higher spreads amplifies the downside; buyback suspended.
- **base**: E(R)=0.0470
  - Central case as built: distribution yield 6.3%, DPU growth -1.5%, zero multiple change. Gearing stays below 38%, occupancy holds at ~91%, on-market buyback continues providing modest per-unit DPU support. RBA easing cycle provides modest tailwind to valuations.
- **bull**: E(R)=0.1800
  - RBA easing triggers cap rate compression of 25bps, office occupancy recovers to 93%+, DPU growth turns positive at +2%, and price-to-NTA discount narrows from ~0.68x to ~0.80x driven by institutional re-rating of Australian office REITs. Debt costs decline materially, lifting FFO and DPU coverage above 1.05x AFFO.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.063 (Cat A) — Trailing distribution yield of ~6.3% confirmed by Kalkine media analysis of DXS.AX FY2026 results (20 Aug 2026). Current unit price AUD 5.80 as at 2026-08-28 (observed closing price); annualised distribution approximately AUD 0.365/unit implied. Consistent with Dexus FY26 results guidance delivery noted in market commentary.
- `dpu_growth` = -0.015 (Cat C) — Negative DPU growth assumption of -1.5% p.a.: office market headwinds, ongoing valuation write-downs in CBD office assets, and debt strain noted by Simply Wall St (21 Aug 2026) are expected to erode FFO marginally. Partially offset by on-market buyback (announced via ASX, multiple update notices Aug 2026) which reduces unit count and provides modest per-unit support. Sensitivity tested in scenario analysis — bear case assumes -5% DPU, bull case assumes +2%.
- `multiple_change` = 0.0 (Cat C) — Zero multiple expansion assumed. DXS trades at a material discount to NTA (~0.65-0.70x estimated), which offers re-rating potential, but this is offset by persistent office sector discount and elevated interest costs. In the absence of confirmed cap rate compression or a significant portfolio repositioning event, no multiple change is modelled in the base case.
- `leverage_gearing` = elevated_flagged (Cat B) — Simply Wall St (21 Aug 2026) flagged debt as straining the cash backstop. Dexus historically operates at ~30-35% gearing (within Australian <40% convention), but current elevated debt costs and office valuations under pressure raise concern. Precise FY2026 gearing figure not extractable from available filings within the analysis window; classified Category B (derived estimate). Applied as a qualitative gate override of -1 step.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise.
- `rba_cash_rate` = 0.035 (Cat B) — RBA cash rate approximated at ~3.5% based on publicly available RBA policy trajectory as at mid-2026. Live APAC rates tool returned empty data; estimate based on known RBA easing cycle from 4.35% peak. Relevant as context for AUD funding costs and yield spread assessment; does not directly enter the quantitative chain (US T-bill used as risk-free rate per framework).

## Key Risks
- Debt strain and elevated interest costs compress FFO coverage and may force asset sales at unfavourable cap rates, particularly for secondary office assets
- Prolonged weakness in Sydney and Melbourne CBD office vacancy rates structurally depresses NTA and re-rating potential
- RBA cash rate remaining higher-for-longer than consensus extends the period of elevated AUD funding costs and delays cap rate compression
- Absence of an external sponsor pipeline means DXS relies on accretive recycling and third-party fund management fees, both of which are cyclically sensitive
- Backtest calibration limitation: quantitative chain based on live data as at 2026-08-28; vintage discipline (Phase 5) not yet implemented — forward estimates carry model risk

## Invalidation Condition
Exit position if DXS gearing ratio rises above 40% (Australian regulatory convention) for one reporting period, or if DPU is formally cut by more than 5% relative to the FY26 declared distribution of approximately AUD 0.365/unit, or if CBD office occupancy across the portfolio falls below 88% on the next semi-annual update, signalling structural rather than cyclical demand impairment.
