# Specialist Memo — NTDU.SI

**Memo ID**: `NTDU.SI_2026-08-30_equity_reit_v1@1.0_2481e3e7a4b3`
**Ticker**: NTDU.SI (NTT DC REIT)
**Market**: Singapore
**Sector**: Data Centre
**As of**: 2026-08-30
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
NTT DC REIT offers exposure to the structurally growing global data centre market backed by NTT Corporation, one of the world's largest data centre operators, providing a credible pipeline of institutional-quality assets. The FY2026 DPU outperformance of 2.6% versus IPO forecast signals operational delivery, and the estimated ~6.83% distribution yield at current price provides a meaningful spread above the 3.69% risk-free rate. Beta of 0.30 versus IASP.L (currency-basis caveat applies; NTDU.SI trades in USD) indicates relatively low co-movement with the broader APAC REIT benchmark, consistent with the differentiated DC sub-sector. The OU Monte Carlo yields a simulated return of 10.2% with 78.8% probability of a positive 12-month outcome, supporting moderate conviction; however, the absence of filed financial statements in the system introduces information risk on leverage and DPU coverage that warrants a one-step downward gate override.

## Quantitative Chain

- E(R): 0.1030
- Std dev: 0.1284
- P-gain: 0.7875
- CAPM alpha: 0.0911
- Beta: 0.3017
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0600
  - Distribution yield compresses as DPU falls 10% from higher financing costs and lease non-renewal; leverage breaches 45% MAS limit forcing equity dilution; data centre cap rates expand 50bps on rate shock or AI demand disappointment; multiple contracts -3%; total return approximately -6%.
- **base**: E(R)=0.1000
  - Central case as built in the quantitative chain: distribution yield ~6.83%, DPU growth 3.0% p.a., multiple change +0.5%, occupancy stable with long-term triple-net leases, leverage below 45% MAS limit.
- **bull**: E(R)=0.2200
  - AI/cloud capex boom accelerates NTT sponsor pipeline injections at accretive yields; DPU growth of 5% p.a.; cap rate compression of 25bps as global rates ease; multiple expansion +3%; occupancy near 100% with long-dated leases; total return approximately 22%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info [override_applied=-1]
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=pass
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0683 (Cat B) — Estimated trailing DPU yield derived from IPO forecast DPU (adjusted +2.6% per Yahoo Finance Singapore, May 2026 news) divided by current unit price of USD 0.925. NTT DC REIT IPO (~Oct 2024) was structured at ~7% indicative yield; FY2026 DPU outperformance of 2.6% over IPO forecast implies DPU ~USD 0.0632/unit, yielding ~6.83% at current price. No filed annual report available in the system; yield is Category B derived estimate.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth assumption of 3.0% p.a. reflecting: (1) AI/cloud-driven demand for data centre capacity supporting rental reversion; (2) NTT sponsor pipeline of data centre assets across Asia-Pacific and Americas available for accretive injection; (3) long-term triple-net lease structures typical of DC REITs providing embedded escalators. Sensitivity: bear case 0%, bull case 5%. Source: analyst estimate; no filed guidance available in system.
- `multiple_change` = 0.005 (Cat C) — Modest +0.5% multiple expansion assumption. NTDU.SI currently trades at USD 0.925, above IPO price of ~USD 0.88, suggesting partial re-rating already realised. Near-term multiple upside is modest given rate environment. Sensitivity: bear case -2%, bull case +3%. Analyst assumption.
- `leverage_assumption` = below_45pct (Cat C) — No filed gearing data available in the system. MAS aggregate leverage limit for Singapore REITs is 45% (50% with credit rating). NTT DC REIT IPO prospectus (Oct 2024) targeted leverage of approximately 35-40%. Category C — analyst assumption in absence of filed financials as of as_of date. Leverage gate treated as 'info' with -1 override applied due to data gap.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between USD and GBP. NTDU.SI trades in USD on SGX, adding a dual currency layer (USD/SGD listing; USD/GBP vs benchmark). Treated as Category B input. CAPM alpha inherits the same currency and iasp basis noise.

## Key Risks
- Leverage information gap: no filed financials available as of as_of date; gearing and DPU coverage ratios cannot be independently verified from system data, creating residual uncertainty on regulatory compliance.
- Higher-for-longer US interest rates compressing the yield spread and increasing refinancing costs on USD-denominated debt, given NTDU.SI distributes and finances in USD.
- AI demand disappointment or hyperscaler capex pullback reducing data centre lease absorption and rental reversion assumptions underpinning the 3% DPU growth rate.
- Concentration risk: NTT Group as sole sponsor and dominant counterparty; any deterioration in NTT Corporation's credit or strategic commitment to the REIT could impair pipeline and fee structure.
- USD/SGD and USD/GBP FX basis distorts beta and CAPM alpha computations; actual co-movement with APAC REIT peers may differ materially from the 0.30 beta estimate.

## Invalidation Condition
Exit if any of the following occur: (1) filed aggregate leverage ratio breaches 43% (approaching the 45% MAS limit) for two consecutive reporting periods without a credible deleveraging plan; (2) DPU coverage by AFFO falls below 1.0x for one reporting period, indicating payout is not fully cash-backed; (3) NTT Corporation formally reduces its committed pipeline to NTDU.SI or divests a material stake below 30% unitholding without a replacement sponsor commitment; or (4) occupancy across the portfolio falls below 92% reflecting demand weakness in the DC sub-sector.
