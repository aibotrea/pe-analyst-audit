# Specialist Memo — JYEU.SI

**Memo ID**: `JYEU.SI_2026-10-21_equity_reit_v1@1.0_dfc7c775fdcc`
**Ticker**: JYEU.SI (Lendlease Global Commercial REIT)
**Market**: Singapore
**Sector**: Retail/Commercial
**As of**: 2026-10-21
**Framework**: equity_reit_v1@1.0
**Conviction score**: 3/5 (Moderate)
**Max position**: 5.0%

## Thesis
Lendlease Global Commercial REIT offers Singapore-centred retail and office exposure with a trailing yield of about 6.8%, roughly 270bp above the 4.1% T-bill rate. 2H FY2026 DPU rose 3.0% YoY and perps were cut about 40%, which supports distribution growth. The OU Monte Carlo gives a 12-month expected return of 8.4% with a PGain of 75.9%. That would imply conviction of 4, but I applied a one-step downward gate override because coverage and gearing were not verified from filing bodies. Beta of 0.26 against IASP.L is low but unreliable because of currency-basis noise, so conviction is Moderate at a 5% maximum position.

## Quantitative Chain

- E(R): 0.0850
- Std dev: 0.1201
- P-gain: 0.7590
- CAPM alpha: 0.0678
- Beta: 0.2613
- MC model: `ou`

## Scenarios
- **bear**: E(R)=-0.0800
  - Stagflation or higher-for-longer rate pathway: SGD rates and the REIT risk premium widen the required yield by about 50bp, Singapore retail rents soften, DPU falls about 4%, and refinancing costs rise on the debt and perps. Gearing drifts toward the 50% limit if valuations are marked down.
- **base**: E(R)=0.0850
  - Central case as built in the chain: yield about 6.8%, DPU growth about 2%, flat multiple, stable occupancy, and gearing held in the low 40% range.
- **bull**: E(R)=0.1900
  - Rate cuts compress the required yield by about 40bp, Jem and Paragon rental reversions beat expectations, perps are refinanced or repaid at lower cost, and DPU growth reaches about 5%.

## Qualitative Gates
- `leverage_within_regulatory_limit` — status=info
- `sponsor_quality` — status=pass
- `distribution_coverage` — status=info [override_applied=-1]
- `asset_quality_concentration` — status=info
- `management_alignment` — status=pass

## Key Assumptions
- `unit_price` = 0.525 (Cat A) — Latest close SGD 0.525 on 2026-10-21 (get_price).
- `distribution_yield` = 0.068 (Cat B) — Derived from the 2H FY2026 DPU of 1.85 cents, up 3.0% YoY, as reported in news. The trailing FY2026 DPU of about 3.6 cents is my own annualisation, not an observed full-year figure. Divided by a 0.525 price, that gives about 6.8%. Unverified against the filed annual report because the report body was not captured.
- `dpu_growth` = 0.02 (Cat C) — Forward DPU growth assumed at 2.0%, below the 3.0% recent YoY print. It rests on Singapore retail rental reversions and lower perpetual securities cost after the perps were reduced about 40%. Tested in scenario analysis.
- `multiple_change` = -0.003 (Cat C) — Assumed roughly flat yield and multiple, so the price return contribution is about zero. I round E(R) to 8.5% as 6.8% yield plus 2.0% growth minus a small allowance for fee dilution from units issued to the manager. Sensitivity: each 25bp move in the required yield moves price by about 4-5%.
- `risk_free_rate` = 0.041 (Cat A) — Stored DTB3 3-month T-bill reading of 4.10% on 2026-10-19. The live get_tbill_rate call failed with a FRED error, so the stored FRED value was used instead.
- `expected_market_return` = -0.050186 (Cat B) — Trailing 5.17-year annualised log return of IASP.L (GBP index). It is negative and absorbs currency effects. It is a poor proxy for a forward market return.
- `filing_acquisition_fee_units` = units_issued (Cat A) — JYEU.SI 2026-10-12 ANNC: acquisition fees for FY26 paid in units, which supports manager alignment. The announcement body was an attachment only, so the amount is not captured.
- `filing_q1_update` = 2026-10-30 (Cat A) — JYEU.SI 2026-10-01 ANNC: Q1 FY2027 business update scheduled for 30 Oct 2026 after market close. This is a near-term catalyst.
- `filing_manager_chair_change` = update_announced (Cat A) — JYEU.SI 2026-10-19 ANNC: update on the chairperson of the manager. Details are in an attachment that was not captured. Treated as a governance watch item.
- `beta_caveat` = disclosed (Cat B) — Beta computed against IASP.L (GBP-denominated benchmark). Coefficient absorbs both property-market co-movement and FX co-movement between SGD and GBP. Treated as Category B input. CAPM alpha inherits the same noise. Currency basis also shows in the 0.17 correlation to IASP.L.

## Key Risks
- Rates higher for longer, or a stagflation path, would widen the required yield and compress valuations and DPU. The 4.1% T-bill is already close to the REIT yield spread.
- Concentration in Singapore retail and commercial assets (Jem, Paragon, 313@Somerset) and tenant-mix risk. Sponsor Lendlease also has its own capital-recycling pressures.
- Distribution coverage, gearing and ICR were not verified from filing bodies. The annual report and perp structure could show thinner AFFO coverage than assumed.
- Governance: an announced chairperson change at the manager (2026-10-19) and units issued as manager fees add dilution risk.
- Low correlation (0.17) and beta (0.26) against IASP.L reflect currency basis, so CAPM alpha is noisy. The 5-year IASP.L return is negative (-5.0%), which flatters alpha. The T-bill came from stored data after the live call failed.

## Invalidation Condition
Exit if the Q1 FY2027 business update due 30 Oct 2026, or the next half-year result, shows distribution coverage below 1.0x AFFO or a DPU decline of more than 5% year on year. Also exit if aggregate leverage rises above about 45% or interest cover falls below 2.0x, or if Lendlease reduces its sponsor stake or support. A sustained rise of 50bp or more in the 10-year SGD yield without a matching DPU rise would also invalidate the thesis.
