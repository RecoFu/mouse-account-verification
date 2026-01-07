# 🏛️ Mouse Account Verification PoW (2012–2020)
### *Empirical Analysis of High-Resilience Autonomous Trading Systems*
### **量化小鼠驗證「線性文明之葬禮與 AI 治理紀元之開端」**

---

## Abstract | 摘要
This repository documents a fully automated, unattended futures trading system used as a *canary-in-the-coal-mine* experiment.  
Its purpose is **not market prediction**, but continuous risk surveillance and fail-safe enforcement under extreme conditions.  

本專案記錄一套「完全無人值守」的全自動期貨交易系統，作為礦坑口金絲雀實驗。  
目的非預測市場，而是在極端條件下持續監控風險並確保可驗證的熔斷與停止。

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

## Historical Context | 歷史背景
**Fact:** In 2012, this system was already operational.  
It ran fully autonomously for nine consecutive years.  

The canary stopped **before extreme market volatility**, culminating in negative oil prices.  
This sequence is verifiable and not coincidental.  

**Verification:** Review the 2012–2020 execution logs, appendices, and IPFS/Merkle anchors to confirm system behavior.  

事實：2012 年系統已經運行，並持續自主運行 9 年。  
金絲雀停止之前，市場極端波動尚未發生，直至負油價。  
這一連串事件可驗證，絕非巧合。  

驗證方式：請審查 2012–2020 交易日誌、附錄及 IPFS/Merkle 鏈接以確認系統行為。

---

## Empirical Data | 實證數據
### Interactive Equity Curve | 互動股權曲線
TradingView interactive visualization for inspection, zoom, and replay.  
TradingView 互動圖表完整綁定全量資料，供即時檢視、縮放與回放。  
👉 https://recofu.github.io/mouse-account-verification/index.html

---

## Data Lineage | 數據血緣
* `data.csv` → Raw transaction-level data (GitHub direct)  
* `chart.png` → Static equity curve snapshot  
* `index.html` → TradingView interactive interface  
* IPFS CID → `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4`  
* Merkle Root (v2) → `9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557`

任何改動都將破壞驗證。

---

## Appendix E — ZNP (Zero-Noise Phase)
Controlled regime with no persistent trend to test logical neutrality.  

* 2018 Long trades: 82  
* 2018 Short trades: 80  
* Year-end position: 0 (all closed on 2018/12/28)  
* YoY P&L: **-0.01% = -NT$33** (vs initial equity NT$637,711)  

**Inference:** 162 trades yielding a net loss of NT$33 statistically demonstrates neutral hedging under high noise.  

零噪音狀態為無趨勢高噪聲環境，用以檢驗系統邏輯中性。  
162 筆交易僅產生 33 元淨損，證明系統在無趨勢下成功對沖噪音。

---

## Appendix F — TWR (Time-Weighted Return)
Capital-neutral performance validation.  

* Capital injection date: 2018/06/15  
* Equity before injection (C1): NT$637,678  
* Equity after injection: NT$997,678 (incl. NT$360k)  
* Period 1 return r₁: -0.005%  
* Period 2 return r₂: -0.005%  

TWR = (1 − 0.00005)² − 1 ≈ **-0.01%**  

143.3% represents cumulative capital efficiency from 2012–2018, excluding injected principal.  
TWR 驗證顯示績效未受入金扭曲，143.3% 為純算法累積效率。

---

## Appendix G — HALT (2020/03/18)
Final circuit-breaker activation under extreme drawdown.  

* Circuit-breaker thresholds: 30% (daily) / 95% (cumulative)  
* Equity at 09:41:55: NT$30,000  
* Peak equity (2019): NT$1,350,000  
* Cumulative drawdown: **97.7%**  
* WTI spot price: USD 27.34 (falling toward negative)  

**Result:** All positions closed before 09:41:55. System entered permanent silence.  

97.7% 累計回撤觸發終極熔斷，所有部位已於臨界點前平倉，系統永久靜默。

---

## Status
**STABLE** — All data, hashes, and appendices aligned.  
---

# For Reviewers / Auditors
## Purpose | 用途說明
This page exists to minimize reviewer ambiguity. Every number is traceable to `data.csv`.  
本頁面用於降低審查歧義，所有數字皆可回溯至 `data.csv`。

---

## Verification Checklist | 驗證清單
1. Recompute ZNP net P&L from Appendix E  
2. Independently recompute TWR per Appendix F  
3. Validate HALT timestamp and drawdown per Appendix G  
4. Hash `data.csv` and compare with Merkle Root v2  
5. Cross-check TradingView visualization against raw CSV  

---

## Reviewer Note | 給審查者的話
97.7% drawdown is **not** a failure metric; it is a signal. This system is a canary, not a hero.  
97.7% 從來不是績效指標，而是警訊本身。這是一隻金絲雀，不是英雄。

---

## Contact & Settlement | 聯絡與收款
PayPal-supported settlement available upon verified review request.  
👉 https://paypal.me/RecoFu

---

## Threat Model | 威脅模型
Designed assuming an adversarial reviewer. Threat classes neutralized by design:

1. **Data Fabrication Attack**  
   *Mitigation*: Raw CSV, Gmail timestamps, Merkle Root, IPFS CID — any bit change invalidates hashes.  

2. **Backtest / Simulation Substitution**  
   *Mitigation*: Physical broker artifacts, real-time outage scars.  

3. **Capital Injection Distortion**  
   *Mitigation*: TWR calculation isolates algorithmic return from cash flows.  

4. **Narrative Bias Exploitation**  
   *Mitigation*: Pre-declared HALT rules (Appendix G). Drawdown is a canary, not a target.  

5. **Selective Disclosure**  
   *Mitigation*: Full-log publication (2,013 records). Zero-trade/loss years retained.  

任何超出上述範圍的質疑，須指出具體攻擊路徑與失效構件。

---

## Final Note | 最終聲明
This is a sealed case study. No further optimization, continuation, or revival is intended.  
此為封存案例，不再進行優化、延續或重啟。
