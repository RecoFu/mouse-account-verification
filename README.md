# 🏛️ Mouse Account Verification PoW (2012–2020)
### *Author-Sealed Technical Case Study of High-Resilience Autonomous Trading Systems*
### **量化期貨小鼠驗證「線性文明之葬禮與 AI 治理紀元之開端」**

---

## Abstract | 摘要
This repository documents a fully automated, unattended futures trading system as a *canary-in-the-coal-mine* experiment.  
Its objective is not market prediction but continuous risk surveillance, fail-safe enforcement, and verifiable archival under extreme conditions.  

本專案記錄一套外派時在台「完全無人值守」的全自動期貨交易系統，作為礦坑口金絲雀實驗記錄與分析。  
其目的並非預測市場，而是在極端條件下持續監控各維度風險並確保可驗證的熔斷與封存。

---

## Core Thesis | 核心命題
Do not predict markets. Instrument them. Survival precedes performance.  
不要預測市場，而是量測並監控它；先存活，才有績效。

![Equity Curve](chart.png)

---

## System Overview | 系統概覽
* Fully automated futures trading system (no human intervention)  
* Continuous risk monitoring with hard HALT rules  
* Designed for falsifiability, not storytelling  

* 完全無人干預的自動化期貨交易系統  
* 持續風險監控並具備不可覆寫的熔斷機制  
* 以可證偽性為設計目標，而非敘事美學

---

## Empirical Observation | 實證觀察
In 2012, this system was fully designed and operational, and it ran **continuously for nine years**.  
After the canary HALT event, market volatility persisted all the way until negative oil prices appeared in 2020‑04‑20.  
If this seems obvious now, **return to 2012 and examine what was being built**; there is no shortcut.

2012 年，這套系統已完整設計並投入運作，並持續運行 **9 年**。  
金絲雀熔斷事件後，市場動盪一直延續至負油價出現（2020‑04‑20）。  
若今天看似顯而易見，**請回到 2012，看看當時實際在建什麼；沒有捷徑**。

> This is not a claim of causality; it is a documented time‑ordered observation.  
> 這不是因果宣稱，而是有序時間序列的紀錄。

---

## Evidence Artifacts | 證據構件
* `data.csv` → Raw transaction-level data  
* `chart.png` → Static equity curve snapshot  
* `index.html` → TradingView interactive interface  
* IPFS CID → `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4`  
* Merkle Root (v2) → `9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557`  

任何改動都會使驗證失效。

---

## Appendix E — ZNP (Zero-Noise Phase) | 零噪音階段
A controlled regime with no persistent trend, used to test logical neutrality.  
零噪音狀態為無趨勢高噪聲環境，用以檢驗系統邏輯中性。

* 2018 Long trades: 82  
* 2018 Short trades: 80  
* Year-end position: 0 (closed 2018/12/28)  
* YoY P&L: **-0.01% = -NT$33** (vs initial equity NT$637,711)  

**Inference | 推論**: 162 trades yielding NT$33 net loss statistically demonstrate neutral hedging under high noise.  
162 筆交易僅產生 33 元淨損，證明系統在無趨勢下成功對沖噪音。

---

## Appendix F — TWR (Time-Weighted Return) | 時間加權報酬
Capital-neutral performance validation.  
驗證績效不受資金流扭曲。

* Capital injection: 2018/06/15  
* Equity before injection: NT$637,678  
* Equity after injection: NT$997,678 (incl. NT$360k)  
* r₁: -0.005%, r₂: -0.005%  
TWR = (1 − 0.00005)² − 1 ≈ **-0.01%**  

143.3% represents cumulative efficiency 2012–2018, capital flow neutralized.  
143.3% 為純算法累積效率，排除資金注入影響。

---

## Appendix G — HALT Event | 熔斷事件
Circuit-breaker activation under extreme drawdown.  
極端回撤觸發熔斷。

* Thresholds: daily 30%, cumulative 95%  
* Equity 2020/03/18 09:41:55: NT$30,000  
* Peak equity (2019): NT$1,350,000  
* Cumulative drawdown: **97.7%**  
* WTI price: USD 27.34  

**Result | 結果**: All positions closed before threshold; system entered permanent silence.  
所有部位於門檻前平倉，系統永久靜默。

> Note | 附註: This drawdown is a designed signal, not a marketable investment target.  
> 此回撤為風險感測訊號，而非可商業化策略。

---

## Status | 狀態
**PROVISIONAL → STABLE upon local verification**  
完成本地 CSV 重算後，方可升級至 STABLE。

**Disclaimer | 免責聲明**  
This system is for research, auditing, and historical documentation only.  
It is **not an investment product**.  
本系統僅供科研、審計與歷史紀錄，不構成投資產品或保證收益。

---

## For Reviewers / Auditors | 審查者專頁
**Purpose | 目的**  
Minimize reviewer ambiguity; all numbers traceable to `data.csv`.  
降低審查歧義，所有數據可追溯至 `data.csv`。

**Verification Checklist | 驗證清單**
1. Recompute ZNP net P&L (Appendix E)  
2. Independently recompute TWR (Appendix F)  
3. Validate HALT timestamp & drawdown (Appendix G)  
4. Hash `data.csv` & compare with Merkle Root v2  
5. Cross-check TradingView visualization vs raw CSV  

**Reviewer Note | 審查者說明**  
97.7% drawdown is a signal, not a failure. This system is a canary history, not a hero.  
97.7% 回撤是訊號，而非失敗指標。本系統為9年金絲雀考古展示，不是英雄。

**Contact & Settlement | 聯絡與結算**  
PayPal-supported settlement available **after verified review request**.  
若有收穫，歡贏透過 PayPal 隨時進行支助。  
👉 https://paypal.me/RecoFu

---

## Threat Model | 威脅模型
Explicitly considered threat classes:

1. **Data Fabrication / 數據偽造**  
2. **Simulation Substitution / 回測替換**  
3. **Capital Injection Distortion / 入金扭曲**  
4. **Narrative Bias Exploitation / 敘事偏誤**  
5. **Selective Disclosure / 選擇性揭露**  

All mitigated via raw logs, hash anchors, Merkle Root, and pre-declared HALT rules.  
以上均透過原始日誌、Hash 錨定、Merkle Root 與事前定義熔斷規則消解。

---

## Final Note | 最終說明
This is a sealed, author-signed technical case study.  
No further optimization, continuation, or revival is intended.  
此為封存、作者簽署之技術案例，不再進行優化、延續或重啟。

**If this looks obvious today, it is only because time has passed.**  
**你今天的理所當然，只因時間已過。**

---
