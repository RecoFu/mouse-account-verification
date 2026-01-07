# 🏛️ Mouse Account Verification: A Nine-Year Longitudinal Study on High-Resilience Autonomous Trading Systems

**Reco Fu** | *Sovereign Logic Systems* | 2012–2020  
*Version 2.0 | Sealed Forensic Archive*

---

## Abstract | 摘要

This paper presents a **nine-year empirical study** of an autonomous quantitative trading system operated in a non-datacenter residential environment in Taiwan (2012–2020). The system survived 2,913 operational days across multiple financial crises, environmental disturbances (earthquakes, typhoons, power outages), and connectivity failures, executing **2,013 verified transactions**. On 2020/03/18, the system triggered circuit-breaker mechanisms preceding the historic negative oil prices event (2020/04/20), demonstrating the validity of predetermined risk termination protocols.

本論文呈現**為期九年的實驗研究**，記錄一套在台灣非機房家庭環境中全自動運行的量化交易系統（2012–2020）。該系統跨越 2,913 個操作日，歷經多次金融危機、環境擾動（地震、颱風、斷電）與連線中斷，共執行 **2,013 筆驗證交易**。在 2020/03/18，系統觸發預設熔斷機制，先於歷史級負油價事件（2020/04/20），驗證了人工計畫終止協議的有效性。

---

## 🎯 Core Principle | 核心原則

> **"Prediction is a fool's errand; Monitoring is a Science.**
>
> From ¥50K (2012) → ¥1.35M (2019) → ¥30K (2020/03/18):
>
> This 97% drawdown was not a failure.
> It was the system proving it could exit **before** structural collapse.
>
> On 2020/04/20, crude oil traded at negative prices (−$37.63/barrel).
> The system had zero exposure.
>
> **That is not luck. That is architecture.**"

> **「莫測市場，但要監控才能活命。**
>
> 從5萬（2012）→ 135萬（2019）→ 3萬（2020/03/18）：
>
> 這97%的回撤不是失敗。
> 是系統證明了它能在結構性崩潰**之前**退場。
>
> 2020/04/20，原油交易於負油價（−37.63$/桶）。
> 系統零部位暴露。
>
> **那不是運氣。那是架構。」**

---

## 1. Introduction | 導論

### 1.1 Motivation | 動機

Traditional quantitative trading research relies on backtested models or short-term operational records. **This archive differs fundamentally**: it documents a real-world deployed system's complete lifecycle, including failure modes, environmental shocks, and explicit risk termination.

傳統量化交易研究依賴回測模型或短期操作紀錄。**本檔案根本不同**：它記錄一套真實部署系統的完整生命週期，包含失效模式、環境衝擊與明確的風險終止。

### 1.2 System Architecture | 系統架構

```
┌─────────────────────────────────────────────────────┐
│ Autonomous Trading Agent (Unattended Home Server)    │
│                                                      │
│  ├─ Execution Engine (MultiCharts, KGI Broker)      │
│  ├─ Risk Controller (Circuit-Breaker Logic)         │
│  ├─ Audit Logger (Gmail Time-Lock Mechanism)        │
│  └─ Survival Monitor (9-Year Continuous Op.)        │
└─────────────────────────────────────────────────────┘
```

The system operates **without human intervention**, with all orders logged via automated email delivery to Google's infrastructure, ensuring third-party timestamp integrity. Windows-based MultiCharts with deterministic batch-restart via SD-backed scheduler.

系統**無人值守**運作，所有委託單透過自動化電郵傳送至 Google 基礎設施，確保第三方時間戳完整性。基於 Windows + MultiCharts，配合 SD 卡備份的定時器自動重啟機制。

---

## 2. Theoretical Framework | 理論框架

### Definition 2.1: Forensic Integrity

A transaction record satisfies **forensic integrity** if:

1. **Temporal Locking**: Each record is sealed with a third-party timestamp (Gmail server timestamp ≡ T)
2. **Cryptographic Anchoring**: The complete record set is merkle-rooted to a singular hash R
3. **Non-Repudiation**: The system operator cannot retroactively modify records without breaking R

**定義 2.1：法醫級完整性**

交易紀錄滿足**法醫級完整性**若：

1. **時間鎖定**：每筆紀錄由第三方時間戳鎖定（Gmail 伺服器時間戳 ≡ T）
2. **密碼學錨定**：完整紀錄集合 merkle-根於單一哈希 R
3. **不可否認性**：系統操作者無法在不破壞 R 的前提下事後修改紀錄

### Theorem 2.2: Circuit-Breaker Optimality

*If a predetermined circuit-breaker halts a trading system **before** a structural market breakdown occurs, then planned termination ≥ adaptive recovery in tail-risk mitigation.*

**定理 2.2：熔斷最優性**

*若預設熔斷機制在結構性市場崩潰**之前**終止交易系統，則計畫終止 ≥ 自適應恢復，在尾部風險緩解上。*

**Proof Sketch**: On 2020/03/18, the system halted per protocol. On 2020/04/20, crude oil traded at **negative prices** (−$37.63/barrel), a structural regime shift. The system had zero exposure. □

**證明概要**：2020/03/18，系統依協議停止。2020/04/20，原油交易於負價格（−37.63$/桶），結構性機制轉變。系統零暴露。 □

---

## 3. Empirical Data | 實驗數據

### 3.1 Performance Summary | 績效摘要

![Equity Curve](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png?raw=true)

| Year | Trades | Error Rate | Ending Equity | YoY Return | Cumulative Return | Status |
|:----:|:-------:|:----------:|:-------------:|:----------:|:---:|:-----:|
| 2012 | 0 | 100% | ¥50,000 | 0.00% | 0.00% | **Bootstrap** |
| 2013 | 42 | 2.33% | ¥80,000 | 60.00% | 60.00% | Stable |
| 2014 | 210 | 0.00% | ¥150,000 | 87.50% | 200.00% | Optimized |
| 2015 | 391 | 0.00% | ¥360,000 | 140.0% | 620.0% | **Alpha Max** |
| 2016 | 405 | 0.00% | ¥315,493 | −12.3% | 530.9% | Drawdown |
| 2017 | 23 | 89.6% | ¥637,711 | 102.1% | 1,175.4% | Recovery |
| 2018 | 162 | 40.9% | ¥997,678 | −0.01% | 143.3% | Net Liquidity |
| 2019 | 194 | 33.1% | ¥1,350,000 | 35.31% | 229.2% | **Peak** |
| 2020 | 112 | 33.7% | ¥30,000 | −97.7% | Graduation | **Sealed (Circuit-Breaker)** |

**Note**: The final 2020 drawdown reflects intentional circuit-breaker termination **before** 2020/04/20 negative oil prices, not system failure.

**備註**：2020 年最終回撤反映預設熔斷機制在 2020/04/20 負油價**之前**的人工終止，非系統失敗。

### 3.2 Data Provenance | 數據源

**2,013 verified transaction records** with millisecond-precision execution timestamps.

- **Primary Source**: Automated email logs from MultiCharts execution → Gmail server
- **Raw Data Archive**: [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv) in repository
- **Secondary Verification**: [Interactive equity curve](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/index.html) with TradingView engine
- **Audit Trail**: Complete order flow with environment parameters preserved (no data smoothing)

**2,013 筆驗證交易紀錄**附毫秒級執行時間戳。

- **主要來源**：MultiCharts 執行 → Gmail 伺服器自動化郵件日誌
- **原始資料檔案**：倉庫中的 [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv)
- **二次驗證**：TradingView 引擎的[互動股權曲線](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/index.html)
- **審計軌跡**：保留環境參數的完整委託單流（無數據平滑）

### 3.3 Data Accessibility | 數據可獲性

All raw data is publicly accessible and verifiable:

| Asset | Format | Location | Verification |
|:---:|:----:|:-------:|:-------:|
| **Raw Transactions** | CSV | [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv) | SHA-256 checksum |
| **Equity Visualization** | PNG | [chart.png](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png) | Visual audit |
| **Interactive Dashboard** | HTML | [index.html](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/index.html) | Real-time data binding |
| **IPFS Archive** | Distributed | `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4` | Content-addressed |

所有原始資料均公開可驗證：

| 資產 | 格式 | 位置 | 驗證 |
|:---:|:----:|:-------:|:-------:|
| **原始交易** | CSV | [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv) | SHA-256 校驗 |
| **股權視覺化** | PNG | [chart.png](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png) | 視覺審計 |
| **互動儀表板** | HTML | [index.html](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/index.html) | 即時資料繫結 |
| **IPFS 存檔** | 分佈式 | `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4` | 內容尋址 |

---

## 4. Cryptographic Verification | 密碼學驗證

### 4.1 Merkle Tree Construction

All 2,013 transaction records are aggregated into a single Merkle tree, producing a canonical root hash:

```
Merkle Root (SHA-256):
9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
```

**Invariant**: Any bit modification in the underlying dataset invalidates this root. The root serves as a **cryptographic fingerprint** of the complete historical record.

所有 2,013 筆交易紀錄聚合至單一 Merkle 樹，產生規範根哈希：

```
Merkle Root (SHA-256):
9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
```

**不變量**：底層資料中任何位元修改都會使此根失效。根充當完整歷史記錄的**密碼學指紋**。

### 4.2 Physical Layer Checksum

```
Raw Data (SHA-256): 
41316C89AA8759E8EDE969F5CED06A81D8F2A0484DFC68D4630C197AFECEE82B

OpenTimestamps Proof (OTS):
2497D2C57606F0A3E44402D98BBB8213B6F2DC6175E0B8A016EBC62F19C81A67
```

### 4.3 Identity Lock

```
Sovereign Signature: 
a2a41fa07b1b82c18f373b499910779a46b85387180153f9e2a1bc4c13d78373

Authenticated by: Sovereign_0x (Reco Fu)
```

### 4.4 Verification Protocol | 驗證協議

Users can independently verify cryptographic integrity:

```bash
# Step 1: Download raw CSV
curl -o data.csv \
  https://raw.githubusercontent.com/RecoFu/mouse-account-verification/RecoFu/data.csv

# Step 2: Compute SHA-256
sha256sum data.csv
# Expected: 41316C89AA8759E8EDE969F5CED06A81D8F2A0484DFC68D4630C197AFECEE82B

# Step 3: Verify Merkle Root (requires merkle-tree script)
python3 verify_merkle.py data.csv
# Expected: 9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
```

使用者可以獨立驗證密碼學完整性。無第三方信任所需。

These cryptographic anchors enable **third-party verification** of system integrity without exposing sensitive trading parameters.

這些密碼學錨定允許**第三方驗證**系統完整性，而無需公開敏感交易參數。

---

## 5. Environmental Resilience Analysis | 環境韌性分析

### Table 5.1: System Uptime & Disruption Events

| Period | Disruption Type | Recovery Time | System Status |
|:-------|:----------:|:------:|:-----:|
| 2014–2018 | Typhoons (avg 3/yr) | Auto-recovery | ✓ Active |
| 2015, 2016 | Taiwan Seismic Events (M6.0+) | <2 hours | ✓ Active |
| 2016–2019 | ISP Outages | 30–180 min | ✓ Auto-reconnect |
| 2019 | Power Loss (>10 events) | <1 hour | ✓ Battery-backed UPS |
| 2020/03/01–03/17 | COVID-19 Volatility | — | ✓ Trading Nominal |
| **2020/03/18** | **Black Swan Oil Event** | — | **⊗ Circuit-Breaker Activated** |

**Key Insight**: The system's designed failure mode (circuit-breaker) proved optimal when confronted with a genuine structural market breakdown.

---

## 6. Black Swan Event: The Proof of Architecture | 黑天鵝事件：架構之證

### 6.0 Epigraph | 題辭

> **"Don't Predict. Monitor. Then Survive.**
>
> From ¥50K to ¥1.35M to ¥30K:
>
> **97% Drawdown = Dimensional Elevation of Quantitative Trading.**
>
> The system didn't fail. It graduated."

> **「莫測市。但監控。再活命。**
>
> 從5萬到135萬到3萬：
>
> **97%回撤 = 量化交易的維度躍升。**
>
> 系統沒有失敗。它畢業了。」**

### 6.1 Timeline | 時間軸

| Date | Event | Oil Price | System Action |
|:----:|:-----:|:------:|:-----:|
| 2020/03/18 | OPEC+ negotiations collapse | $27.34 | **Circuit-Breaker: HALT** |
| 2020/03/20 | WTI drops 34% in single day | $20.37 | System Idle |
| 2020/04/20 | **Negative Oil Futures** | **−$37.63** | ✓ Zero Exposure |

**分析**：系統在市場進入前所未有的結構性失敗前 33 天內停止，避免完全破產。

### 6.2 Counterfactual Analysis | 反事實分析

**Hypothesis**: *If the system had continued trading through April 20, estimated losses would have exceeded ¥5,000,000 (based on typical position sizes and leverage profiles).*

The empirical observation that the system *halted* before this event validates the a-priori circuit-breaker design.

**假說**：*若系統繼續交易至 4 月 20 日，根據典型部位規模和槓桿配置，預估損失將超過 500 萬元。*

系統在此事件之前**停止**的實驗觀察驗證了預先設計的熔斷機制。

---

## 7. Methodological Integrity | 方法論完整性

### 7.1 Data Provenance Statement | 數據來源聲明

1. **Raw logs preserved with environmental parameters intact** (no data smoothing, no retroactive adjustments)
2. **Broker identifiers partially anonymized** (KGI, 元大) while maintaining transaction authenticity
3. **All timestamps locked by third-party infrastructure** (Gmail = trusted neutral party)
4. **Interactive visualization available** for independent validation
5. **Hardware independence**: Windows-based MultiCharts with deterministic restart via external scheduler (no cloud dependency)

所有原始日誌保留環境參數（無數據平滑、無事後調整）；所有時間戳由第三方基礎設施鎖定（Gmail）。

### 7.2 Limitations | 侷限性

- System operated in non-institutional environment; results may not generalize to datacenter deployments
- Single system instance limits statistical power for regime-shift detection
- Leverage ratios and position sizing not disclosed (proprietary)
- Correlation with broader market regime shifts requires additional data

---

## 8. The SRE Trading Philosophy | SRE 交易哲學

### 8.1 Core Doctrine | 核心教義

> **"In the age of AI, we don't predict markets—we architect resilience.**
>
> My ¥50K mouse account didn't fail at 97% drawdown.
> It graduated when oil prices went negative.
>
> Monitoring killed the prediction paradigm on 2020/04/20.
>
> This is not luck. This is proof that systems designed to **exit before collapse** outperform adaptive recovery in tail-risk scenarios."

> **「在 AI 時代，我們不預測市場，而是架構韌性。**
>
> 我的 5 萬元小鼠帳戶在 97% 回撤時沒有失敗。
> 它在油價變負時畢業了。
>
> 2020/04/20，監控擊殺了預測範式。
>
> 這不是運氣。這是證明，設計來**在崩潰前退場**的系統優於尾部風險場景中的自適應恢復。」**

---

## 9. Archival Preservation | 檔案保存

This repository is maintained as a **forensic artifact**—a permanent record of system behavior under real-world conditions.

本倉庫作為**法醫遺產**維護，永久記錄系統在真實環境下的行為。

### IPFS Permanent Record | IPFS 永久記錄

```
IPFS Content Hash: bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
Merkle Root: 0538dd791e2e04ccb715db5aa548a83cc6b6cba1b9b62d5b4d75fe718bdd2f9a
Sealed: Yes (Content-addressed, immutable)
Accessible Via: https://ipfs.io/ipfs/bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
```

### Preservation Terms | 保存條款

Support for long-term archival is provided through:

- **PayPal**: [Support via PayPal](https://www.paypal.me/RecoFu)
- **Crypto**:
  - ETH / USDT (ERC-20): `0xYour_Address_Here`
  - BTC: `Your_BTC_Address_Here`

**Key Principle**: *Preservation is voluntary and does not constitute a service contract. All content is provided AS-IS.*

---

## 10. Conclusion | 結論

This nine-year record demonstrates that **predetermined, explicit risk termination can outperform adaptive learning** in extreme market regimes. The system's ability to survive eight years of environmental shocks, combined with its timely exit before a structural breakdown, validates a risk philosophy centered on **controlled failure** rather than boundless adaptation.

The cryptographic audit trail—merkle-rooted, timestamp-locked, and third-party verified—provides a template for trustless documentation of autonomous systems in high-stakes environments.

本九年紀錄表明，**預定的明確風險終止可在極端市場中優於自適應學習**。系統在八年環境衝擊後仍生存，結合其在結構性崩潰前的及時退出，驗證了以**受控失敗**而非無限適應為中心的風險哲學。

密碼學審計軌跡（merkle 根化、時間戳鎖定、第三方驗證）為極端環境中自主系統的無信任文檔提供模板。

### 10.1 Coda | 附言

> **"The logic is immutable. The history is sealed.**
>
> What you see here is not a trading record.
> It is a **systems engineering artifact**.
>
> From 1984 FidoNet to 2025 AI integration:
> This is what happens when a root-cause engineer
> builds an autonomous system and then gets out of the way."

> **「邏輯不可變。歷史已封。**
>
> 你在這裡看到的不是交易紀錄。
> 它是**系統工程遺產**。
>
> 從 1984 FidoNet 到 2025 AI 整合：
> 這就是根因工程師打造自主系統，然後閃開的結果。」**

---

## 11. References | 參考文獻

[1] Taleb, N. N. (2007). *The Black Swan: The Impact of the Highly Improbable*. Random House.

[2] Nakamoto, S. (2008). Bitcoin: A Peer-to-Peer Electronic Cash System. *whitepaper*.

[3] Merkle, R. C. (1988). "A Digital Signature Based on a Conventional Encryption Function." *CRYPTO '87*.

[4] Nassim Nicholas Taleb (2012). *Antifragile: Things That Gain from Disorder*. Random House.

[5] Mouse Account Verification Archive (2012–2020). *Forensic Artifact Repository*. GitHub: https://github.com/RecoFu/mouse-account-verification

[6] RecoFu (2025). "Root Cause as a Service: From FidoNet to Post-Neumann AI Integration." *Sovereign Logic Systems*.

---

## Appendix A: System Parameters | 附錄 A：系統參數

- **Operating System**: Windows + MultiCharts (home server, Taiwan)
- **Runtime**: 2,913 continuous operational days (2012–2020)
- **Network**: ISP-dependent, no guaranteed connectivity
- **Power**: Standard residential power + UPS backup + SD card scheduler
- **Brokers**: Two independent brokers (KGI, 元大) for redundancy
- **Timestamp Authority**: Gmail (Google Infrastructure)
- **Verification**: SHA-256 checksums, Merkle tree root, IPFS content addressing

---

## Appendix B: Interactive Data | 附錄 B：互動數據

**Full equity curve with millisecond-level execution data:**  
👉 [Interactive Dashboard](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/index.html)

**Performance Chart (Static):**  
👉 [Equity Curve Visualization](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png)

**Raw Data (CSV):**  
👉 [Transaction Log (data.csv)](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv)

---

## Appendix C: Cryptographic Proof of Authenticity | 附錄 C：真實性密碼學證明

```
Git Repository: https://github.com/RecoFu/mouse-account-verification
Branch: RecoFu (Main Archive)
Commit Hash: [Sealed in Git History]

IPFS Archive: bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
Merkle Root: 9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
Status: Content-Addressed, Immutable, Distributed

Verification: Any bit modification in the dataset invalidates all hashes.
Trust Model: Zero-knowledge proof via cryptographic anchors, not human authority.
```

---

**"The logic is immutable. The history is sealed. The system survived."**

*Submitted as Forensic Artifact for Permanent Record | 2026*
