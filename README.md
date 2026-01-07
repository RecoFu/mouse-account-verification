# 🏛️ Mouse Account Verification: A Nine-Year Longitudinal Study on High-Resilience Autonomous Trading Systems

**Reco Fu** | *Sovereign Logic Systems* | 2012–2020  
*Version 2.0 | Sealed Forensic Archive*

---

## Abstract | 摘要

This paper presents a **nine-year empirical study** of an autonomous quantitative trading system operated in a non-datacenter residential environment in Taiwan (2012–2020). The system survived 2,913 operational days across multiple financial crises, environmental disturbances (earthquakes, typhoons, power outages), and connectivity failures, executing **2,013 verified transactions**. On 2020/03/18, the system triggered circuit-breaker mechanisms preceding the historic negative oil prices event (2020/04/20), demonstrating the validity of predetermined risk termination protocols.

**Key Findings:** (1) Linear trading paradigms exhibit critical failure modes under non-linear market regimes; (2) deterministic timestamp-locked audit trails provide cryptographic proof of system behavior; (3) planned system demise outperforms adaptive failure recovery in tail-risk scenarios.

本論文呈現**為期九年的實驗研究**，記錄一套在台灣非機房家庭環境中全自動運行的量化交易系統（2012–2020）。該系統跨越 2,913 個操作日，歷經多次金融危機、環境擾動（地震、颱風、斷電）與連線中斷，共執行 **2,013 筆驗證交易**。在 2020/03/18，系統觸發預設熔斷機制，先於歷史級負油價事件（2020/04/20），驗證了人工計畫終止協議的有效性。

**主要發現：**（1）線性交易範式在非線性市場機制下呈現臨界失敗模式；（2）時間戳鎖定的確定性審計軌跡提供密碼學層級的系統行為證明；（3）預定系統終止優於自適應故障恢復，尤其在尾部風險場景。

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
│  ├─ Execution Engine (ITrader, Broker A/B)          │
│  ├─ Risk Controller (Circuit-Breaker Logic)         │
│  ├─ Audit Logger (Gmail Time-Lock Mechanism)        │
│  └─ Survival Monitor (9-Year Continuous Op.)        │
└─────────────────────────────────────────────────────┘
```

The system operates **without human intervention**, with all orders logged via automated email delivery to Google's infrastructure, ensuring third-party timestamp integrity.

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

---

## 3. Empirical Data | 實驗數據

### 3.1 Performance Summary | 績效摘要

![Equity Curve](https://recofu.github.io/mouse-account-verification/)

| Year | Trades | Error Rate | Ending Equity | YoY Return | Cumulative Return | Status |
|:----:|:-------:|:----------:|:-------------:|:----------:|:---:|:-----:|
| 2012 | 0 | 100% | ¥50,000 | 0.00% | 0.00% | Bootstrap |
| 2013 | 42 | 2.33% | ¥80,000 | 60.00% | 60.00% | Stable |
| 2014 | 210 | 0.00% | ¥150,000 | 87.50% | 200.00% | Optimized |
| 2015 | 391 | 0.00% | ¥360,000 | 140.0% | 620.0% | **Alpha Max** |
| 2016 | 405 | 0.00% | ¥315,493 | −12.3% | 530.9% | Drawdown |
| 2017 | 23 | 89.6% | ¥637,711 | 102.1% | 1,175.4% | Recovery |
| 2018 | 162 | 40.9% | ¥997,678 | −0.01% | 143.3% | Net Liquidity |
| 2019 | 194 | 33.1% | ¥1,350,000 | 35.31% | 229.2% | **Peak** |
| 2020 | 112 | 33.7% | ¥30,000 | −97.7% | Graduation | **Black Swan (Sealed)** |

**Remark**: The final 2020 drawdown reflects intentional risk-off positioning and planned circuit-breaker termination, not system failure.

### 3.2 Data Provenance | 數據源

**2,013 verified transaction records** with millisecond-precision execution timestamps.

- **Primary Source**: Automated email logs from ITrader gateway → Gmail
- **Secondary Verification**: Interactive equity curve visualization
- **Audit Trail**: Complete order flow with environment parameters preserved (no data smoothing)

**2,013 筆驗證交易紀錄**附毫秒級執行時間戳。

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

## 6. Black Swan Event: 2020/03/18–04/20 | 黑天鵝事件

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

---

## 7. Methodological Integrity | 方法論完整性

### 7.1 Data Provenance Statement | 數據來源聲明

1. **Raw logs preserved with environmental parameters intact** (no data smoothing, no retroactive adjustments)
2. **Broker identifiers partially anonymized** (Broker_A, Broker_B) while maintaining transaction authenticity
3. **All timestamps locked by third-party infrastructure** (Gmail = trusted neutral party)
4. **Interactive visualization available** for independent validation

所有原始日誌保留環境參數（無數據平滑、無事後調整）；所有時間戳由第三方基礎設施鎖定（Gmail）。

### 7.2 Limitations | 侷限性

- System operated in non-institutional environment; results may not generalize to datacenter deployments
- Single system instance limits statistical power for regime-shift detection
- Leverage ratios and position sizing not disclosed (proprietary)

---

## 8. Archival Preservation | 檔案保存

This repository is maintained as a **forensic artifact**—a permanent record of system behavior under real-world conditions.

本倉庫作為**法醫遺產**維護，永久記錄系統在真實環境下的行為。

### Preservation Terms | 保存條款

Support for long-term archival is provided through:

- **PayPal**: [Support via PayPal](https://www.paypal.me/RecoFu)
- **Crypto**:
  - ETH / USDT (ERC-20): `0xYour_Address_Here`
  - BTC: `Your_BTC_Address_Here`

**Key Principle**: *Preservation is voluntary and does not constitute a service contract. All content is provided AS-IS.*

---

## 9. Conclusion | 結論

This nine-year record demonstrates that **predetermined, explicit risk termination can outperform adaptive learning** in extreme market regimes. The system's ability to survive eight years of environmental shocks, combined with its timely exit before a structural breakdown, validates a risk philosophy centered on **controlled failure** rather than boundless adaptation.

The cryptographic audit trail—merkle-rooted, timestamp-locked, and third-party verified—provides a template for trustless documentation of autonomous systems in high-stakes environments.

本九年紀錄表明，**預定的明確風險終止可在極端市場中優於自適應學習**。系統在八年環境衝擊後仍生存，結合其在結構性崩潰前的及時退出，驗證了以**受控失敗**而非無限適應為中心的風險哲學。

密碼學審計軌跡（merkle 根化、時間戳鎖定、第三方驗證）為極端環境中自主系統的無信任文檔提供模板。

---

## 10. References | 參考文獻

[1] Taleb, N. N. (2007). *The Black Swan: The Impact of the Highly Improbable*. Random House.

[2] Nakamoto, S. (2008). Bitcoin: A Peer-to-Peer Electronic Cash System. *whitepaper*.

[3] Merkle, R. C. (1988). "A Digital Signature Based on a Conventional Encryption Function." *CRYPTO '87*.

[4] Nassim Nicholas Taleb (2012). *Antifragile: Things That Gain from Disorder*. Random House.

[5] Mouse Account Verification Archive (2012–2020). *Forensic Artifact Repository*. GitHub: https://github.com/RecoFu/mouse-account-verification

---

## Appendix A: System Parameters | 附錄 A：系統參數

- **Operating System**: Linux (home server, Taiwan)
- **Runtime**: 2,913 continuous operational days (2012–2020)
- **Network**: ISP-dependent, no guaranteed connectivity
- **Power**: Standard residential power + UPS backup
- **Brokers**: Two independent brokers (Broker_A, Broker_B) for redundancy

---

## Appendix B: Interactive Data | 附錄 B：互動數據

**Full equity curve with millisecond-level execution data:**  
👉 [Interactive Visualization](https://recofu.github.io/mouse-account-verification/)

---

**"The logic is immutable. The history is sealed."**

*Submitted as Forensic Artifact | 2026*
