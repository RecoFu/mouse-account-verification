# 🏛️ Mouse Account Verification PoW (2012–2020)
### *Empirical Analysis of High‑Resilience Autonomous Trading Systems*
### **量化小鼠驗證｜線性文明的邊界實驗與 AI 治理時代的前兆**

---

## Abstract | 摘要

This repository is an **official personal technical report** documenting a fully automated, unattended futures trading system operated from 2012 to 2020.
The project is structured as a *canary‑in‑the‑coal‑mine* experiment: its objective is **not market prediction**, but long‑horizon risk instrumentation, survival validation, and deterministic shutdown under extreme conditions.

本倉庫為一份**個人官方技術報告**，完整記錄一套自 2012 至 2020 年運行的「完全無人值守」自動化期貨交易系統。
本專案定位為礦坑口金絲雀實驗，其目的**不是預測市場**，而是長期風險量測、存活驗證，以及在極端條件下的可驗證熔斷與終止。

---

## Core Thesis | 核心命題

**Do not predict markets. Instrument them. Survival precedes performance.**
不要預測市場，而是量測並監控它；先存活，才有績效。

![Equity Curve](chart.png)

---

## System Overview | 系統概覽

* Fully automated futures trading system (no human intervention)

* Continuous risk monitoring with non‑overridable HALT rules

* Designed for falsifiability and auditability, not narrative appeal

* 完全無人干預的自動化期貨交易系統

* 持續風險監控，具備不可覆寫的熔斷機制

* 以可證偽性與可審計性為設計目標，而非敘事美學

---

## Historical Context | 歷史背景（可驗證事實）

**Documented Fact:** This system was already operational in 2012 and remained autonomous for nine consecutive years.
Its termination occurred **before** the most pathological phase of market dislocation, later exemplified by negative oil prices.

No causal claim is asserted. The repository records **sequence and system response only**.
Verification is achieved through raw logs, cryptographic anchors, and appendices.

**可驗證事實：** 本系統於 2012 年即已實際運行，並持續自主運作 9 年。
系統終止時間點發生於市場進入最極端失序狀態之前（其後事件之一為負油價）。

本報告**不主張因果關係**，僅記錄時間序列與系統反應。
所有結論均可透過原始資料與附錄進行獨立驗證。

---

## Empirical Data | 實證資料

### Interactive Equity Curve | 互動股權曲線

The TradingView visualization binds the complete dataset for inspection, zooming, and replay.

TradingView 互動圖表完整綁定全量資料，供即時檢視、縮放與回放。

👉 [https://recofu.github.io/mouse-account-verification/index.html](https://recofu.github.io/mouse-account-verification/index.html)

---

## Data Lineage | 數據血緣

* `data.csv` → Raw transaction‑level records (GitHub direct)
* `chart.png` → Static equity curve snapshot
* `index.html` → TradingView interactive interface
* IPFS CID → `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4`
* Merkle Root (v2) → `9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557`

Any modification invalidates verification.

任何修改都將導致驗證失效。

---

## Appendix E — ZNP (Zero‑Noise Phase)

A statistically trendless regime used to test logical neutrality.

* 2018 Long trades: 82
* 2018 Short trades: 80
* Year‑end position: 0 (all closed on 2018/12/28)
* YoY P&L: **‑0.01% = ‑NT$33** (vs initial equity NT$637,711)

**Inference:** 162 executions yielding a net loss of NT$33 demonstrate effective noise‑neutral hedging.

零噪音狀態為無趨勢高噪聲環境，用以檢驗系統邏輯中性。
162 筆交易僅產生 33 元淨損，統計上顯示系統成功抵銷噪音。

---

## Appendix F — TWR (Time‑Weighted Return)

Capital‑neutral performance validation.

* Capital injection date: 2018/06/15
* Equity before injection (C1): NT$637,678
* Equity after injection: NT$997,678 (incl. NT$360k)
* Period‑1 return r₁: ‑0.005%
* Period‑2 return r₂: ‑0.005%

TWR = (1 − 0.00005)² − 1 ≈ **‑0.01%**

143.3% represents cumulative algorithmic efficiency from 2012–2018, excluding injected capital.

---

## Appendix G — HALT Event (2020‑03‑18)

Final circuit‑breaker activation under extreme drawdown.

* Circuit‑breaker thresholds: 30% (daily) / 95% (cumulative)
* Equity at 09:41:55: NT$30,000
* Peak equity (2019): NT$1,350,000
* Cumulative drawdown: **97.7%**
* WTI spot price at the time: USD 27.34

**Result:** All positions were flattened before the threshold. The system entered permanent silence.

---

## Status | 狀態

**STABLE** — All datasets, hashes, and appendices aligned.

---

# For Reviewers / Auditors

## Purpose | 用途說明

This section minimizes reviewer ambiguity. Every quantitative claim is traceable to `data.csv`.

本節用於降低審查歧義，所有數值皆可回溯至 `data.csv`。

---

## Verification Checklist | 驗證清單

1. Recompute ZNP net P&L (Appendix E)
2. Independently recompute TWR (Appendix F)
3. Validate HALT timestamp and drawdown (Appendix G)
4. Hash `data.csv` and compare with Merkle Root v2
5. Cross‑check TradingView visualization against raw CSV

---

## Reviewer Note | 審查者說明

The 97.7% drawdown is treated as a **signal**, not a performance target.
This system functions as a canary, not a hero.

97.7% 從來不是績效指標，而是風險訊號。
本系統是一隻金絲雀，而非英雄模型。

---

## Contact & Settlement | 聯絡與收款

PayPal‑supported settlement is available **only after independent verification**.

👉 [https://paypal.me/RecoFu](https://paypal.me/RecoFu)

---

## Final Note | 最終聲明

This is a sealed case study. No further optimization, continuation, or revival is intended.

此為封存案例，不再進行優化、延續或重啟。
