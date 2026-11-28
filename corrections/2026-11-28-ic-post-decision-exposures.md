# Correction: country and sector figures on some Track B decisions

Some decision records in Track B — Human Investment Committee Portfolio showed the wrong country and sector weights. We have fixed the calculation. The holdings and the performance figures were not affected.

## What was wrong

The portfolio may hold no more than 35% in one country and no more than 30% in one sector. When the investment committee buys a new holding, it sometimes sells part or all of an existing one to stay inside those limits. Each published decision shows the country and sector weights after the decision.

On decisions that included one of these sales, the weights were worked out as if the sale had not happened. The country and sector of the holding sold kept their old weight, so the published figure for each was too high. The total invested figure on the same records was correct.

## What was not affected

The trades were not affected. Holdings, their values, the portfolio's value and its performance are calculated from the positions held, and this error did not touch them. The limits were applied correctly too: the figures the committee sees while it chooses what to sell already counted each sale. The error was in the weights written onto the decision record, and only there. It did not affect Track A — Fully Automated Portfolio.

## Which records

Track B has made 82 purchase decisions. 11 of them included a sale to make room. 11 records carry incorrect country or sector weights. On 8 records, the published figures show a country or sector above its limit; the corrected figures are within the limits. The table at the end gives each figure as recorded and as it should have been.

## What we have done

The calculation now counts these sales, and a test checks it. Decisions recorded from 2026-11-28 (UTC) onwards carry the correct figures.

We have not edited the published records. The audit repository keeps every record as it was first committed, and this correction sits beside them. The correct figures were recomputed from the portfolio as stored with each decision.

## Corrected figures

| Decision | Date (UTC) | Holding bought | Sold to make room | Figure | Recorded | Correct |
| --- | --- | --- | --- | --- | --- | --- |
| B_memo_triggered_b_RFF_AX_20260721_083901_a1c853e6 | 2026-07-21 | RFF.AX | RGN.AX, to 3% | Country: Australia | 35.93% | 32.88% |
| B_memo_triggered_b_RFF_AX_20260721_083901_a1c853e6 | 2026-07-21 | RFF.AX | RGN.AX, to 3% | Sector: Retail | 18.04% | 14.99% |
| B_memo_triggered_b_CIP_AX_20260801_002605_b0d5a191 | 2026-08-01 | CIP.AX | A17U.SI, to 6% | Country: Singapore | 33.11% | 30.93% |
| B_memo_triggered_b_CIP_AX_20260801_002605_b0d5a191 | 2026-08-01 | CIP.AX | A17U.SI, to 6% | Sector: Industrial/Logistics | 27.25% | 25.07% |
| B_memo_triggered_b_CIP_AX_20260823_030035_690e1093 | 2026-08-23 | CIP.AX | GMG.AX, to 1.5% | Country: Australia | 34.35% | 32.86% |
| B_memo_triggered_b_CIP_AX_20260823_030035_690e1093 | 2026-08-23 | CIP.AX | GMG.AX, to 1.5% | Sector: Industrial/Logistics | 29.32% | 27.83% |
| B_memo_triggered_b_RGN_AX_20260831_235716_2ae1125b | 2026-08-31 | RGN.AX | APZ.AX, all | Country: Australia | 36.19% | 33.03% |
| B_memo_triggered_b_RGN_AX_20260831_235716_2ae1125b | 2026-08-31 | RGN.AX | APZ.AX, all | Sector: Residential | 3.16% | 0.00% |
| B_memo_triggered_b_GMG_AX_20260902_213816_65fe8952 | 2026-09-02 | GMG.AX | DXS.AX, to 2% | Country: Australia | 36.16% | 34.94% |
| B_memo_triggered_b_GMG_AX_20260902_213816_65fe8952 | 2026-09-02 | GMG.AX | DXS.AX, to 2% | Sector: Diversified | 18.13% | 16.91% |
| B_memo_triggered_b_BWP_AX_20260905_115604_9e4ab13c | 2026-09-05 | BWP.AX | RGN.AX, to 7.5% | Country: Australia | 35.64% | 34.96% |
| B_memo_triggered_b_BWP_AX_20260905_115604_9e4ab13c | 2026-09-05 | BWP.AX | RGN.AX, to 7.5% | Sector: Retail | 23.20% | 22.52% |
| B_memo_triggered_b_GOZ_AX_20260905_120200_c9cb7c0f | 2026-09-05 | GOZ.AX | RFF.AX, to 6%; RGN.AX, to 6.5% | Country: Australia | 37.46% | 34.77% |
| B_memo_triggered_b_GOZ_AX_20260905_120200_c9cb7c0f | 2026-09-05 | GOZ.AX | RFF.AX, to 6%; RGN.AX, to 6.5% | Sector: Diversified | 17.40% | 15.71% |
| B_memo_triggered_b_GOZ_AX_20260905_120200_c9cb7c0f | 2026-09-05 | GOZ.AX | RFF.AX, to 6%; RGN.AX, to 6.5% | Sector: Retail | 22.52% | 21.52% |
| B_memo_triggered_b_CQE_AX_20260906_022011_96bacd77 | 2026-09-06 | CQE.AX | CIP.AX, to 1% | Country: Australia | 35.97% | 34.95% |
| B_memo_triggered_b_CQE_AX_20260906_022011_96bacd77 | 2026-09-06 | CQE.AX | CIP.AX, to 1% | Sector: Industrial/Logistics | 22.88% | 21.86% |
| B_memo_triggered_b_DXI_AX_20260927_225825_28a8816c | 2026-09-27 | DXI.AX | GMG.AX, to 3%; RGN.AX, to 6% | Country: Australia | 36.90% | 34.76% |
| B_memo_triggered_b_DXI_AX_20260927_225825_28a8816c | 2026-09-27 | DXI.AX | GMG.AX, to 3%; RGN.AX, to 6% | Sector: Industrial/Logistics | 29.23% | 27.94% |
| B_memo_triggered_b_DXI_AX_20260927_225825_28a8816c | 2026-09-27 | DXI.AX | GMG.AX, to 3%; RGN.AX, to 6% | Sector: Retail | 17.14% | 16.29% |
| B_memo_triggered_b_3279_T_20261109_223426_c520787b | 2026-11-09 | 3279.T | 0823.HK, to 3%; SGP.AX, to 2% | Country: Australia | 35.70% | 33.50% |
| B_memo_triggered_b_3279_T_20261109_223426_c520787b | 2026-11-09 | 3279.T | 0823.HK, to 3%; SGP.AX, to 2% | Country: HongKong | 9.22% | 7.13% |
| B_memo_triggered_b_3279_T_20261109_223426_c520787b | 2026-11-09 | 3279.T | 0823.HK, to 3%; SGP.AX, to 2% | Sector: Diversified | 32.30% | 28.01% |
| B_memo_triggered_b_COF_AX_20261115_075448_2d8dab7a | 2026-11-15 | COF.AX | RGN.AX, to 5% | Country: Australia | 34.52% | 33.32% |
| B_memo_triggered_b_COF_AX_20261115_075448_2d8dab7a | 2026-11-15 | COF.AX | RGN.AX, to 5% | Sector: Retail | 18.75% | 17.55% |

---

*Record of a simulated portfolio from a personal research project. No money is invested and no orders are placed. Not investment advice, and not a recommendation to buy, sell or hold any security. Produced in whole or in part by AI language models and may contain errors. The views are the author's own and not those of any employer. See README.md in this repository.*
