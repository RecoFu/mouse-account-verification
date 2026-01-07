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
* Continuous risk monitoring with hard HALT rules
* Designed for falsifiability, not storytelling
* 完全無人干預的自動化期貨交易系統
* 持續風險監控並具備不可覆寫的熔斷機制
* 以可證偽性為設計目標，而非敘事美學
---
## Empirical Data | 實證數據
### Interactive Equity Curve | 互動股權曲線
The interactive TradingView visualization binds the complete dataset for inspection, zooming, and replay.
TradingView 互動圖表完整綁定全量資料，供即時檢視、縮放與回放。
👉https://recofu.github.io/mouse-account-verification/index.html
---
## Data Lineage | 數據血緣
* `data.csv` → Raw transaction-level data (GitHub direct)
* `chart.png` → Static equity curve snapshot
* `index.html` → TradingView interactive interface
* IPFS CID → `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4`
* Merkle Root (v2) → `9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557`
---
## Appendix E — ZNP (Zero-Noise Phase)
A controlled regime with no persistent trend, used to test logical neutrality.
* 2018 Long trades: 82
* 2018 Short trades: 80
* Year-end position: 0 (all closed on 2018/12/28)
* YoY P&L: **-0.01% = -NT$33** (vs initial equity NT$637,711)
**Inference**: 162 trades yielding a net loss of NT$33 statistically demonstrates neutral hedging under high noise.
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
**Result**: All positions closed before 09:41:55. System entered permanent silence.
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
97.7% drawdown is not a failure metric here. It is the signal. This system is a canary, not a hero.
97.7% 從來不是績效指標，而是警訊本身。這是一隻金絲雀，不是英雄。
---
## Contact & Settlement
PayPal-supported settlement available upon verified review request.
---
## Threat Model | 威脅模型（不可規避假設）
This project assumes an adversarial reviewer. The following threat classes are explicitly considered and neutralized by design. Any critique outside this scope must demonstrate a concrete attack path against the artifacts listed below.
1. **Data Fabrication Attack**
   *Threat*: Post-hoc modification of trade logs or performance metrics.
   *Mitigation*: Raw CSV, Gmail timestamping, Merkle Root, and IPFS hash binding. Any single-bit change invalidates all hashes.
2. **Backtest / Simulation Substitution**
   *Threat*: Replacing real execution with simulated or curve-fitted data.
   *Mitigation*: Physical gateway artifacts (broker error codes, domain residues) and real-time outage scars inconsistent with simulations.
3. **Capital Injection Distortion**
   *Threat*: Inflating performance via undisclosed deposits.
   *Mitigation*: Time-Weighted Return (Appendix F) mathematically isolates algorithmic return from cash flows.
4. **Narrative Bias Exploitation**
   *Threat*: Interpreting drawdown as system failure rather than signal.
   *Mitigation*: Pre-declared HALT rules (Appendix G). The 97.7% drawdown is treated as a canary event, not an optimization target.
5. **Selective Disclosure**
   *Threat*: Hiding unfavorable periods or trades.
   *Mitigation*: Full-log publication (2,013 records). Zero-trade and loss-dominant years are retained intentionally.
Any reviewer asserting fraud, overfitting, or survivorship bias must specify which threat class applies and which artifact fails.
---
本專案在設計時即假設審查者為敵對立場。以下威脅類型已被納入並於架構層級消解；任何質疑若超出此範圍，必須指出具體可行的攻擊路徑。
1. **數據偽造攻擊**
   威脅：事後竄改交易紀錄或績效。
   消解：原始 CSV、Gmail 授信時間戳、Merkle Root 與 IPFS 哈希綁定，任一位元變動即全數失效。
2. **回測／模擬替換**
   威脅：以回測或擬合數據冒充真實執行。
   消解：真實券商錯誤碼、域名殘留與斷線痕跡，為模擬環境無法生成之物理證據。
3. **入金扭曲績效**
   威脅：透過隱匿入金放大績效表現。
   消解：Appendix F 的 TWR 計算，數學上剝離資金流動對報酬的影響。
4. **敘事偏誤利用**
   威脅：將回撤誤讀為系統失敗。
   消解：事前定義之 HALT 熔斷規則（Appendix G）。97.7% 為礦坑金絲雀訊號，而非失控結果。
5. **選擇性揭露**
   威脅：隱匿不利年份或交易。
   消解：2,013 筆全量日誌公開，零交易年與虧損年均完整保留。
若主張造假、過度擬合或倖存者偏誤，請明確指出所屬威脅類型與失效之驗證構件。
________________________________________
## Final Note
This is a sealed case study.  
No further optimization, continuation, or revival is intended.
此為封存案例。  
不再進行優化、延續或重啟。
Contact & Settlement
PayPal-supported settlement available upon verified review request.
👉 https://paypal.me/RecoFu
---
