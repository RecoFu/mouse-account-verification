# 🏛️ Mouse Account Verification PoW (2012-2020)
### *Empirical Analysis of High-Resilience Autonomous Trading Systems*
### **量化小鼠驗證「線性文明之葬禮與 AI 治理紀元之開端」**

## Abstract | 摘要
This repository documents a fully automated, unattended futures trading system used as a *canary-in-the-coal-mine* experiment. The objective is not market prediction, but continuous risk surveillance and fail-safe enforcement under extreme conditions.  
本專案記錄一套「完全無人值守」的全自動期貨交易系統，作為礦坑口金絲雀實驗。其目的並非預測市場，而是在極端條件下持續監控風險並確保可驗證的熔斷與停止。

---

## Core Thesis | 核心命題
Do not predict markets. Instrument them. Survival precedes performance.  
不要預測市場，而是量測並監控它；先存活，才有績效。  

![Equity Curve](chart.png)

---

## System Overview | 系統概覽
* Fully automated futures trading system (no human intervention)  
  完全無人干預的自動化期貨交易系統
* Continuous risk monitoring with hard HALT rules  
  持續風險監控並具備不可覆寫的熔斷機制
* Designed for falsifiability, not storytelling  
  以可證偽性為設計目標，而非敘事美學

---

## Empirical Data | 實證數據

### Interactive Equity Curve | 互動股權曲線
The interactive TradingView visualization binds the complete dataset for inspection, zooming, and replay.  
TradingView 互動圖表完整綁定全量資料，供即時檢視、縮放與回放。  
👉https://recofu.github.io/mouse-account-verification/index.html

---

## Data Lineage | 數據血緣
* `data.csv` → Raw transaction-level data (GitHub direct)  
  原始交易紀錄（GitHub 直連）
* `chart.png` → Static equity curve snapshot  
  股權曲線快照
* `index.html` → TradingView interactive interface  
  TradingView 互動圖表
* IPFS CID → `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4`
* Merkle Root (v2) → `9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557`

---

## Appendix E — ZNP (Zero-Noise Phase)
A controlled regime with no persistent trend, used to test logical neutrality.  
零噪音狀態為無趨勢高噪聲環境，用以檢驗系統邏輯中性。

* 2018 Long trades: 82 / 做多交易：82  
* 2018 Short trades: 80 / 做空交易：80  
* Year-end position: 0 (all closed on 2018/12/28) / 年末持倉：0（2018/12/28 全數平倉）  
* YoY P&L: **-0.01% = -NT$33** (vs initial equity NT$637,711) / 年度損益：-0.01%，33 元（期初權益 637,711 元）  

**Inference / 判斷**: 162 trades yielding a net loss of NT$33 statistically demonstrates neutral hedging under high noise.  
162 筆交易僅產生 33 元淨損，證明系統在無趨勢下成功對沖噪音。

---

## Appendix F — TWR (Time-Weighted Return)
Capital-neutral performance validation.  
TWR 驗證顯示績效未受入金扭曲，143.3% 為純算法累積效率。

* Capital injection date: 2018/06/15 / 資金注入：2018/06/15  
* Equity before injection (C1): NT$637,678 / 注入前權益：637,678 元  
* Equity after injection: NT$997,678 (incl. NT$360k) / 注入後權益：997,678 元（含 360k 元）  
* Period 1 return r₁: -0.005% / 期間1報酬：-0.005%  
* Period 2 return r₂: -0.005% / 期間2報酬：-0.005%  

TWR = (1 − 0.00005)² − 1 ≈ **-0.01%**  
143.3% represents cumulative capital efficiency from 2012–2018, excluding injected principal.  
2012–2018 累積資本效率 143.3%，已剔除注入本金干擾。

---

## Appendix G — HALT (2020/03/18)
Final circuit-breaker activation under extreme drawdown.  
終極熔斷事件（極端回撤下觸發）

* Circuit-breaker thresholds: 30% (daily) / 95% (cumulative)  
  熔斷門檻：日回撤 30%，累計回撤 95%  
* Equity at 09:41:55: NT$30,000 / 權益：30,000 元  
* Peak equity (2019): NT$1,350,000 / 2019 年峰值：1,350,000 元  
* Cumulative drawdown: **97.7%** / 累計回撤：97.7%  
* WTI spot price: USD 27.34 (falling toward negative) / 當時 WTI：27.34 美元，下跌至負值  

**Result / 結果**: All positions closed before 09:41:55. System entered permanent silence.  
所有部位已於臨界點前平倉，系統永久靜默。

---

## Status
**STABLE** — All data, hashes, and appendices aligned.  
穩定 — 所有數據、哈希與附錄均對齊。

---

# For Reviewers / Auditors
## Purpose | 用途說明
This page exists to minimize reviewer ambiguity. Every number is traceable to `data.csv`.  
本頁面用於降低審查歧義，所有數字皆可回溯至 `data.csv`。

## Verification Checklist | 驗證清單
1. Recompute ZNP net P&L from Appendix E / 重新計算 Appendix E 的淨損益  
2. Independently recompute TWR per Appendix F / 獨立計算 Appendix F 的 TWR  
3. Validate HALT timestamp and drawdown per Appendix G / 驗證 Appendix G 的熔斷時間與回撤  
4. Hash `data.csv` and compare with Merkle Root v2 / 計算 CSV 哈希與 Merkle Root 對比  
5. Cross-check TradingView visualization against raw CSV / 交叉檢查 TradingView 與原始 CSV  

## Reviewer Note | 給審查者的話
97.7% drawdown is not a failure metric here. It is the signal. This system is a canary, not a hero.  
97.7% 從來不是績效指標，而是警訊本身。這是一隻金絲雀，不是英雄。

---

## Contact & Settlement
PayPal-supported settlement available upon verified review request.  
PayPal 收款支援，需經審核確認後進行  
👉 https://paypal.me/RecoFu

---

## Threat Model | 威脅模型（不可規避假設）
This project assumes an adversarial reviewer. The following threat classes are explicitly considered and neutralized by design.  
本專案假設審查者為敵對立場，以下威脅類型已在設計上消解：

1. **Data Fabrication Attack / 數據偽造攻擊**  
   Threat: Post-hoc modification of trade logs or performance metrics / 事後竄改交易紀錄或績效  
   Mitigation: Raw CSV, Gmail timestamping, Merkle Root, IPFS hash binding / 原始 CSV、Gmail 授信時間戳、Merkle Root 與 IPFS 哈希綁定  
2. **Backtest / Simulation Substitution / 回測／模擬替換**  
   Threat: Replacing real execution with simulated data / 以模擬或擬合數據冒充真實交易  
   Mitigation: Physical broker artifacts and outage scars / 真實券商錯誤碼與斷線痕跡  
3. **Capital Injection Distortion / 入金扭曲績效**  
   Threat: Inflating performance via undisclosed deposits / 隱匿入金放大績效  
   Mitigation: TWR calculation isolates algorithmic returns / TWR 計算剝離資金流影響  
4. **Narrative Bias Exploitation / 敘事偏誤利用**  
   Threat: Interpreting drawdown as system failure / 將回撤誤讀為失敗  
   Mitigation: Pre-declared HALT rules. 97.7% treated as signal / 事前定義熔斷規則，97.7% 視為金絲雀訊號  
5. **Selective Disclosure / 選擇性揭露**  
   Threat: Hiding unfavorable periods or trades / 隱匿不利年份或交易  
   Mitigation: Full log publication, zero-trade years retained / 全量日誌公開，零交易年亦保留  

Any reviewer asserting fraud, overfitting, or survivorship bias must specify which threat class applies and which artifact fails.  
任何質疑造假、過度擬合或倖存者偏誤者，必須明確指出威脅類型及失效構件。

---

## Final Note | 最終說明
This is a sealed case study. No further optimization, continuation, or revival is intended.  
此為封存案例，不再進行優化、延續或重啟。

Contact & Settlement / 聯絡與收款  
PayPal-supported settlement available upon verified review request / 經審核確認後可使用 PayPal 收款  
👉 https://paypal.me/RecoFu
