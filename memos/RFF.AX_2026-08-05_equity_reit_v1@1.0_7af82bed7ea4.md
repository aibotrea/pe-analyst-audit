# Specialist Memo — RFF.AX

**Memo ID**: `RFF.AX_2026-08-05_equity_reit_v1@1.0_7af82bed7ea4`
**Ticker**: RFF.AX (Rural Funds Group)
**Market**: Australia
**Sector**: Agricultural/Farmland REIT
**As of**: 2026-08-05
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Rural Funds Group provides exposure to Australian agricultural land — a scarce, inflation-linked asset class with structural demand tailwinds from food security themes and water entitlement appreciation. The trailing distribution yield of 5.36% at AUD 2.20 offers a 162bp spread over the 3.74% US T-bill proxy, underpinned by long-dated CPI-linked agricultural leases. The $255.6M asset sales announced in July 2026 signal active portfolio management, though near-term AUM compression constrains DPU growth to an estimated 1.5% p.a. Beta of 0.46 versus IASP.L (currency-basis caveat applies) indicates below-market co-movement, supporting the portfolio diversification thesis for a 12-month hold. PGain of 70.3% from the OU Monte Carlo simulation supports moderate conviction, with the -1 gate override reflecting unconfirmed distribution coverage pending FY26 results.

## Quantitative Chain

- E(R): 0.0686
- Std dev: 0.1275
- P-gain: 0.7031
- CAPM alpha: 0.0652
- Beta: 0.4569
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Asset sale proceeds fail to be redeployed accretively; DPU cut of 5-10% as agricultural income contracts under drought or commodity price shock; cap rate expansion of 50bps compresses NAV; RBA rate cuts slower than expected keeping funding costs elevated; gearing rises back toward 38% if asset impairments materialise. Bear case also captures a global macro downturn / AUD depreciation scenario pressuring land valuations.
- **base**: E(R)=0.0680
  - Central case as built in quantitative chain: distribution yield 5.36%, DPU growth 1.5% from CPI-linked lease escalation, neutral multiple change, gearing ~30% post-asset sales, AUD stable versus trading partners.
- **bull**: E(R)=0.1800
  - Asset sale proceeds redeployed into higher-yielding agricultural assets at 6%+ cap rates; DPU growth accelerates to 3% on strong soft commodity prices and water entitlement value uplift; market re-rates agricultural REIT sector upward as institutional ESG demand for farmland increases; gearing remains <28%; RBA rate cuts provide yield-spread tailwind.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=info
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0536 (Cat A) — Trailing distribution yield of 5.36% confirmed by Kalkine analysis (July 2026) at market price AUD 2.20 as of 2026-08-05, implying annualised DPU ~AUD 0.118 per unit. Consistent with observed price series from stored prices.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth assumption of 1.5% p.a.: RFF's lease structures include CPI-linked rent escalation clauses on agricultural leases (typically 2-3% p.a.), offset by AUM reduction following the announced $255.6M asset sales (Finance News Network, 10 July 2026). Net growth estimate below historical 2% p.a. guidance, reflecting portfolio contraction. Sensitivity tested in scenario analysis.
- `multiple_change` = 0.0 (Cat C) — Neutral multiple change assumption (0% cap rate expansion/compression). Asset sales suggest capital recycling without immediate redeployment signal; market pricing broadly reflects agricultural land values. No re-rating catalyst identified within 12-month horizon.
- `gearing_estimate` = 0.3 (Cat B) — RFF has historically reported gearing of approximately 30-35% (LVR basis). The $255.6M asset sale proceeds (ASX announcement, RFF.AX, 2026-07-10, ASSET ACQUISITION & DISPOSAL) are expected to reduce leverage. Exact post-sale gearing not confirmed via filed documents (body_unavailable for FY26 financial results); estimated at ~30% post-sale, within AU REIT convention of <40%. Category B given derivation from public announcement without full balance sheet confirmation.
- `distribution_coverage_status` = unconfirmed (Cat B) — DPU coverage by AFFO could not be confirmed from filed documents; body capture failed for three recent filings including the 2026-05-31 distribution announcement (filing_text_status=failed). RFF's agricultural lease income is generally pass-through and well-covered historically. Treated as Category B pending FY26 full results scheduled for reporting (ASX announcement, RFF.AX, 2026-08-05, PERIODIC REPORTS — FY26 reporting date and webinar).
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. The AUD/GBP cross introduces additional noise beyond agricultural REIT sector fundamentals. Treated as Category B input. CAPM alpha inherits the same currency and iasp benchmark noise.

## Key Risks
- Distribution coverage unconfirmed — FY26 financial results pending; if AFFO payout ratio exceeds 1.0x, DPU sustainability is at risk and conviction would be reduced further
- Asset sale proceeds redeployment risk — $255.6M in divestments reduces income-generating AUM; failure to reinvest at equivalent or better yields would compress DPU
- Agricultural concentration and climate risk — drought, flood, or pest events could impair farm operating performance and reduce rental income from agricultural tenants
- RBA interest rate trajectory — while rate cuts are anticipated, any higher-for-longer scenario increases RFF's weighted average cost of debt and compresses the yield spread
- Calibration limitation — Phase 2 calibration is directional only; vintage discipline is not formally implemented until Phase 5, and point-in-time macro data availability may affect backtest reproducibility

## Invalidation Condition
Exit position if RFF announces a DPU reduction exceeding 5% on a trailing twelve-month basis, or if reported gearing (LVR) rises above 38% following any debt-funded acquisition, or if the $255.6M asset sale proceeds remain undeployed for more than 18 months causing annualised DPU to fall below AUD 0.110 per unit, or if occupancy or lease renewal rates on core agricultural properties decline materially for two consecutive half-year reporting periods.
