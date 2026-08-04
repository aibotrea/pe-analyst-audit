# Specialist Memo — C2PU.SI

**Memo ID**: `C2PU.SI_2026-08-03_equity_reit_v1@1.0_acc297188845`
**Ticker**: C2PU.SI (Parkway Life REIT)
**Market**: Singapore
**Sector**: Healthcare
**As of**: 2026-08-03
**Framework**: equity_reit_v1@1.0
**Conviction score**: 4/5 (Above average)
**Max position**: 8.0%

## Thesis
Parkway Life REIT offers one of the most defensive income profiles in the Singapore REIT universe, underpinned by master hospital leases to IHH Healthcare (expiring 2042) with CPI-linked escalation and a well-diversified portfolio of ~145 Japan nursing homes. The trailing yield of ~3.5% at SGD 4.22 is lower than typical S-REITs, but 15+ years of unbroken DPU growth, conservative gearing (~37%), and a premium healthcare real estate franchise justify the valuation premium. An OU Monte Carlo simulation produces a 12-month sim return of 5.97% with a PGain of 79.6%, supported by a positive CAPM alpha of 4.1% versus the IASP.L benchmark (currency-basis caveat applies). The primary risk is JPY/SGD translation, which affects approximately 55% of NPI; hedging partially mitigates but does not eliminate this exposure.

## Quantitative Chain

- E(R): 0.0600
- Std dev: 0.0720
- P-gain: 0.7963
- CAPM alpha: 0.0413
- Beta: 0.2517
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0400
  - JPY depreciates materially against SGD (e.g. 10%+ move), reducing Japan NPI translation by ~5-6% in SGD terms; Singapore CPI escalation falls to minimum floor of 1%; DPU coverage pressured by rising Japan acquisition financing costs; potential rate-shock scenario where SGD rates rise 50bps compresses yield spread and triggers P/NAV multiple de-rating of 200bps, resulting in negative total return despite positive income yield.
- **base**: E(R)=0.0600
  - Central case as built in quantitative chain: distribution yield 3.48%, DPU growth 3.0% driven by CPI-linked Singapore escalation plus modest Japan accretive acquisitions, slight P/NAV multiple compression of -0.5%. JPY/SGD broadly stable. Leverage remains ~37%, gearing headroom supports one to two bolt-on Japan acquisitions.
- **bull**: E(R)=0.1400
  - JPY appreciates against SGD, boosting Japan NPI translation; Singapore CPI escalation at upper end (~2-3% contractual); IHH Healthcare sponsor injects accretive pipeline assets at yield-on-cost above 5%; rate environment softens with SGD rates declining 25-50bps, driving P/NAV multiple expansion; DPU growth accelerates to 5%+ for the year.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=pass
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=pass
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `distribution_yield` = 0.0348 (Cat A) — Trailing DPU yield derived from FY2025 published DPU of approximately SGD 0.1470 per unit divided by observed closing price of SGD 4.22 on 2026-08-03. DPU sourced from public annual results disclosure; price is Category A market data.
- `dpu_growth_3yr` = 0.03 (Cat C) — Forward DPU growth assumption of 3.0% p.a. Based on PLife's historical DPU CAGR of approximately 3-4% over 15+ years of consecutive growth. Singapore hospital master leases carry CPI-linked rental escalation (floor ~1% p.a.) expiring 2042; Japan nursing home portfolio (~145 assets) contributes accretive acquisition growth. Sensitivity tested at +/- 1% in scenario analysis.
- `multiple_change` = -0.005 (Cat C) — Assumed slight P/NAV multiple compression of -0.5% over the 12-month horizon. PLife historically trades at a material premium to NAV (~1.6-1.8x book) reflecting scarcity of healthcare real estate exposure and defensive income. With rate environment stabilising and price having risen ~6.5% over two months, a marginal multiple headwind is prudent. Sensitivity: bull case assumes flat multiples; bear case assumes -2% compression.
- `singapore_hospital_leases` = disclosed (Cat A) — Singapore hospital master leases (Mount Elizabeth, Gleneagles, Parkway East) expire in 2042 providing ~16-year remaining WALE. Lessor is IHH Healthcare Bhd (sponsor). CPI-escalation clause locks in minimum annual rental growth. Sourced from publicly available investor presentations and REIT annual reports.
- `gearing_ratio` = 0.37 (Cat B) — Aggregate leverage estimated at approximately 37% based on publicly available FY2025 balance sheet disclosures and news coverage of healthcare S-REIT sector. Well within the MAS regulatory limit of 50% (with interest coverage above 2.5x threshold for the higher 50% cap). Classified Category B as derived estimate from sector coverage rather than real-time filed balance sheet.
- `jpy_fx_exposure` = disclosed (Cat B) — Approximately 55% of net property income is derived from Japan nursing homes denominated in JPY. PLife hedges a portion of this exposure using JPY forward contracts, but residual FX translation risk remains. JPY/SGD movements represent a key income uncertainty factor treated as a qualitative risk rather than a precise numerical input.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP, as well as indirect JPY/GBP and JPY/SGD currency basis from PLife's Japan exposure. Treated as Category B input. CAPM alpha inherits the same noise.

## Key Risks
- JPY/SGD depreciation reducing Japan nursing home NPI translation by a material amount; approximately 55% of NPI is JPY-denominated with only partial hedging coverage
- Higher-for-longer SGD interest rates compressing the yield spread versus the 3.69% T-bill rate, which is already narrow relative to the ~3.5% distribution yield
- IHH Healthcare sponsor credit or strategic risk: any weakening of sponsor commitment, credit quality deterioration, or lease renegotiation at 2042 renewal could re-rate the Singapore hospital segment significantly downward
- Regulatory or policy risk in Japan: changes to nursing home reimbursement rates by the Japanese government or tightening of care facility regulations could impair Japan NPI
- Premium valuation risk: PLife trades at a significant P/NAV premium (~1.6-1.8x historically); any sector rotation away from defensive REITs or a broad APAC REIT de-rating could compress multiples even if fundamentals remain intact

## Invalidation Condition
Exit position if: (1) gearing breaches 43% (signalling aggressive debt-funded acquisitions or NAV erosion) for two consecutive reported periods; or (2) IHH Healthcare formally signals intent to renegotiate Singapore hospital master lease terms prior to 2042 expiry, including any reduction in CPI escalation floor; or (3) JPY/SGD rate falls below 0.0085 on a sustained 30-day basis, implying >10% NPI translation headwind that would push DPU growth negative; or (4) DPU coverage falls below 1.0x AFFO for any reporting period.
