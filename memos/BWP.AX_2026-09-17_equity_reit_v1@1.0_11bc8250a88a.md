# Specialist Memo — BWP.AX

**Memo ID**: `BWP.AX_2026-09-17_equity_reit_v1@1.0_11bc8250a88a`
**Ticker**: BWP.AX (BWP Trust)
**Market**: Australia
**Sector**: Large-Format Retail / Industrial
**As of**: 2026-09-17
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
BWP Trust offers defensive large-format retail income through near-exclusive Bunnings Warehouse tenancy backed by Wesfarmers, one of Australia's highest-quality corporates, providing predictable CPI-linked cash flows and an estimated distribution yield of ~5.1% at the current price of AUD 3.60. Beta of 0.48 versus IASP.L (currency-basis caveat applies) reflects a lower-volatility, income-oriented REIT profile well suited for defensive positioning. The OU Monte Carlo model returns a 12-month simulated return of ~6.1% and a PGain of 73.6%, supporting moderate conviction. Conviction is constrained to 3 from a base of 4 following a one-step qualitative gate reduction for extreme tenant concentration (~97% Bunnings), which represents meaningful single-counterparty risk despite that counterparty's investment-grade quality. FY2026 full-year results (53.8% profit jump) and ongoing portfolio reset toward large-format retail provide incremental fundamental support.

## Quantitative Chain

- E(R): 0.0614
- Std dev: 0.0968
- P-gain: 0.7356
- CAPM alpha: 0.0644
- Beta: 0.4798
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Wesfarmers signals intention to renegotiate Bunnings leases at lower rents at a material proportion of sites upon expiry, combined with RBA holding rates at elevated levels (cash rate 4.25%+), driving cap rate expansion of 50bps and compressing NTA by 8-10%. DPU growth falls to 0% as CPI-linked rent reviews are capped at floor rates. Multiple contraction contribution widens to -3%. Sell-off accelerates from current AUD 3.60 toward AUD 3.20-3.30.
- **base**: E(R)=0.0610
  - Central case as constructed: distribution yield 5.14%, DPU growth 1.5% from CPI-linked rent reviews, multiple change -0.5%, stable Bunnings occupancy, leverage ~32% LVR. RBA eases modestly, providing marginal cap rate support. Portfolio recycling proceeds at or near book value. 12-month total return approximately 6.1%.
- **bull**: E(R)=0.1800
  - RBA cuts cash rate by 75bps+, compressing cap rates and driving NTA uplift of 6-8%. BWP successfully acquires additional large-format retail assets at accretive yields above 6%, boosting DPU growth to 3%+. Wesfarmers extends leases early with above-CPI reviews. Re-rating toward historically observed premium-to-NTA levels pushes unit price back toward AUD 4.00-4.10.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info
- `asset_quality_concentration` — status=info [override_applied=-1]
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0514 (Cat A) — Trailing distribution yield estimated at 5.14% based on current price of AUD 3.60 and trailing DPU of approximately AUD 0.185 per unit. BWP Trust has historically paid semi-annual distributions; the most recent ASX distribution announcement (2026-08-18) confirms ongoing payment. Classified Category A as DPU is an issuer-published figure at the declared rate.
- `dpu_growth_3yr` = 0.015 (Cat C) — Forward DPU growth of 1.5% p.a. assumed, reflecting CPI-linked annual rent reviews under Bunnings Warehouse leases (typically fixed or CPI-linked, capped and collared). News coverage (Kalkine, Sept 2026) confirms large-format retail growth narrative for FY27 but limited acquisition pipeline beyond Bunnings. Sensitivity: if rent-review outcomes fall below CPI (bear), growth narrows to 0%; if portfolio recycling delivers accretive yield (bull), growth widens to 3%+.
- `multiple_change` = -0.005 (Cat C) — Modest cap rate compression headwind assumed at -0.5% contribution from multiple change, reflecting the recent 10% price decline from the July 2026 high of ~AUD 3.95 to AUD 3.60 and the risk of persistent higher Australian interest rates weighing on REIT multiples. Sensitivity: further RBA rate cuts would flip this positive; sustained higher-for-longer rates would worsen to -1.5%.
- `bunnings_tenant_concentration` = ~97% (Cat A) — BWP Trust's portfolio is approximately 97% Bunnings Warehouse (Wesfarmers subsidiary) tenanted by lease income. This is a published structural characteristic of the trust. WALE is typically 8-10 years. Concentration is the primary qualitative gate trigger for a -1 asset_quality_concentration override.
- `leverage_gearing` = 0.32 (Cat B) — Estimated LVR of approximately 32% based on BWP Trust's historical balance sheet positioning (consistently conservative, well below AREIT sector norms). The August 2026 'Application for quotation of securities - BWP' filing signals a DRP or equity issuance, consistent with balance sheet management keeping gearing low. Precise FY2026 balance sheet figure not confirmed from available filing bodies; Category B.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between AUD and GBP. Currency basis and IASP.L benchmark denomination mean computed beta of 0.48 is a noisy estimate of true property-market beta. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- Extreme tenant concentration: approximately 97% of income is derived from Bunnings Warehouse (Wesfarmers), meaning any deterioration in Wesfarmers' credit quality, Bunnings store closures, or lease non-renewal would be immediately and severely earnings-dilutive.
- Interest rate sensitivity: prolonged higher RBA cash rates compress the yield spread advantage of BWP's ~5.1% distribution yield over the 3.99% T-bill rate, making the trust less attractive on a risk-adjusted basis and weighing on unit price.
- Portfolio reset execution risk: news coverage indicates FY27 involves portfolio reset and large-format retail growth initiatives; asset disposals below book value or capital recycling at unfavourable cap rates could erode NAV.
- Distribution restructuring: recent news noting 'Higher Unfranked Payout' and refocus of income story signals a structural shift in the distribution composition, which may disadvantage Australian tax-paying investors reliant on franking credits.
- AUD/GBP currency basis embedded in beta: the computed beta of 0.48 against GBP-denominated IASP.L absorbs AUD/GBP co-movement noise, meaning the CAPM alpha of 6.4% overstates true risk-adjusted outperformance in AUD terms.

## Invalidation Condition
Exit position if Wesfarmers/Bunnings formally announces non-renewal or material downsizing of leases representing more than 10% of BWP's gross lettable area, or if BWP's reported LVR breaches 40% (Australian REIT regulatory convention), or if the trailing distribution yield falls below 4.0% (signalling NAV-destructive pricing or DPU cut) for two consecutive semi-annual periods, or if the RBA cash rate rises above 5.0% and the trust's price-to-NTA premium moves below 0.85x.
