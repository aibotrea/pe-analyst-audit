# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-07-12_equity_reit_v1@1.0_2f531b681a19`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-07-12
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Parkway Life REIT (C2PU.SI) is Singapore's largest listed healthcare REIT, offering a highly defensive income profile anchored by CPI-linked master leases with IHH Healthcare for three Singapore private hospitals (Mt Elizabeth, Gleneagles, Parkway East) and an 80+ asset Japan nursing home portfolio. The trailing distribution yield of ~5.0% at SGD 4.11 provides a meaningful spread over the 3-month T-bill rate of 3.69%, and the CPI-escalation mechanism underpins a 2.0% p.a. DPU growth assumption without relying on acquisitions. Beta of 0.239 versus IASP.L (SGD/GBP currency-basis caveat applies) reflects the low cyclicality of healthcare real estate and a WALE of approximately 22 years for the Singapore hospital portfolio. An OU Monte Carlo PGain of 83.7% and CAPM alpha of 5.2% support an above-average conviction rating at a 12-month horizon, with the primary risk being JPY depreciation compressing SGD-translated distributions from the Japan portfolio.

## Quantitative Chain

- E(R): 0.0700
- Std dev: 0.0711
- P-gain: 0.8366
- CAPM alpha: 0.0520
- Beta: 0.2390
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0500
  - Singapore hospital master leases are renegotiated at materially lower rents upon renewal, or IHH Healthcare (master lessee) faces credit stress. Japan nursing home occupancy declines significantly (sub-90%) forcing rent concessions. SGD strengthens sharply against JPY, compressing JPY-denominated distributions when translated back to SGD. Global rate spike causes cap-rate expansion of 50bps, compressing NAV and unit price. DPU growth assumption falls to -1.0% p.a.
- **base**: E(R)=0.0700
  - Central case: distribution yield 5.0%, DPU growth 2.0% via CPI-linked lease escalations, neutral multiple change. Singapore hospital occupancy and revenue stable under IHH master lease. Japan portfolio 80+ nursing home assets perform in line with historical. Gearing remains ~37%, within 45% MAS limit. SGD/JPY stable within recent range.
- **bull**: E(R)=0.1700
  - Accretive acquisitions of additional Japan nursing homes or new Asian healthcare assets at yields above 5.5%. IHH exercises additional asset injection into the REIT from its hospital pipeline. Singapore CPI runs higher than expected at 3%+, boosting lease escalations above base assumption. Global rates ease 50-75bps, compressing cap rates and supporting NAV expansion. DPU growth accelerates to 4.5% p.a.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.05 (Cat A) — Trailing distribution yield derived from current market price of SGD 4.11 (trade date 2026-07-10) and Parkway Life REIT's published trailing DPU of approximately SGD 0.205 per unit for FY2025, implying a gross yield of ~5.0%. Observed public market data.
- `dpu_growth_3yr` = 0.02 (Cat C) — Forward DPU growth assumption of 2.0% p.a. anchored to CPI-linked rent escalation mechanism embedded in Singapore master lease agreements (Mt Elizabeth, Gleneagles, Parkway East hospitals). Japan nursing home rents tracked to annual CPI adjustments. Conservatively excludes accretive acquisitions given limited pipeline visibility at as_of date. Sensitivity: bear -1.0%, bull +2.5%.
- `multiple_change` = 0.0 (Cat C) — Neutral cap-rate / multiple-change assumption. Parkway Life REIT trades at a premium to book given the long WALE (~22 years Singapore hospitals) and defensive income. No meaningful compression or expansion assumed at base case given elevated global rates environment.
- `singapore_regulatory_limit` = 0.45 (Cat A) — MAS aggregate leverage limit for Singapore REITs is 45% (or 50% with credit rating). Parkway Life REIT has historically operated at 35-37% gearing, comfortably within the regulatory ceiling. Observed published regulatory threshold.
- `sponsor_ihh_commitment` = disclosed (Cat B) — IHH Healthcare (world's largest listed private healthcare group by market cap) is the controlling sponsor and master lessee for the Singapore hospital portfolio. IHH's master lease structure for the three Singapore hospitals (Mt Elizabeth, Gleneagles, Parkway East) provides high income visibility. Sponsor commitment derived from publicly reported lease structure and IHH's strategic healthcare footprint in Asia.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP (currency basis). Treated as Category B input. CAPM alpha inherits the same noise. The low beta of 0.239 partly reflects currency dampening and the defensive nature of healthcare leases.

## Key Risks
- JPY/SGD depreciation: Japan nursing homes contribute approximately 20-25% of AUM; a sustained JPY weakness compresses SGD-translated distributions and NAV
- Master lease renewal concentration: Singapore hospital leases (Mt Elizabeth, Gleneagles, Parkway East) are long-WALE but highly concentrated with a single master lessee (IHH Healthcare); any IHH credit deterioration poses tail risk
- Higher-for-longer Singapore rates compressing the distribution yield spread vs the 3-month T-bill (currently ~131bps)
- Acquisition risk: premium valuation (unit price trades above book) may limit accretive deal execution; overpaying for Japan nursing homes would dilute returns
- No stored SGX filings were available at as_of date; memo relies on public DPU and gearing estimates from news reports and known structural features — formal filing data could revise the distribution yield and leverage assumptions

## Invalidation Condition
Exit position if: (1) IHH Healthcare's credit rating is downgraded below investment grade or IHH signals intent to renegotiate Singapore hospital master lease terms; (2) portfolio gearing breaches 42% aggregate leverage for two consecutive reporting periods, signalling loss of balance-sheet headroom toward the 45% MAS limit; (3) reported DPU for any two consecutive semi-annual periods falls more than 10% below the trailing DPU of approximately SGD 0.10 per semi-annual period, indicating structural rather than transient income decline; or (4) JPY/SGD depreciates beyond 15% from current levels sustained over a 6-month window, materially impairing Japan portfolio contribution to distributions.
