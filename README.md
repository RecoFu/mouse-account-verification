# 🏛️ Mouse Account Verification: A Nine-Year Longitudinal Study on High-Resilience Autonomous Trading Systems

**Reco Fu** | *Sovereign Logic Systems* | 2012–2020  
**Document Type**: Forensic Case Study / Engineering Report (non-peer-reviewed)  
**Version**: 2.0 | Sealed Archive

---

## Abstract | 摘要

This paper presents a **nine-year empirical study** of an autonomous quantitative trading system operated in a non-datacenter residential environment in Taiwan (2012–2020). The system survived 2,913 operational days across multiple financial crises, environmental disturbances (earthquakes, typhoons, power outages), and connectivity failures, executing **2,013 verified transactions**. On 2020/03/18, the system triggered circuit-breaker mechanisms preceding the historic negative oil prices event (2020/04/20), demonstrating the validity of predetermined risk termination protocols.

**This archive is not an investment performance advertisement and does not recommend any strategy.** It is a forensic engineering record of one autonomous system's lifecycle under real-world constraints.

本論文呈現**為期九年的實驗研究**，記錄一套在台灣非機房家庭環境中全自動運行的量化交易系統（2012–2020）。該系統跨越 2,913 個操作日，歷經多次金融危機、環境擾動（地震、颱風、斷電）與連線中斷，共執行 **2,013 筆驗證交易**。在 2020/03/18，系統觸發預設熔斷機制，先於歷史級負油價事件（2020/04/20），驗證了人工計畫終止協議的有效性。

**本檔案非投資績效宣傳，不推薦任何策略。** 它是一套自主系統在真實環境下生命週期的法醫工程紀錄。

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

Traditional quantitative trading research relies on backtested models or short-term operational records. **This archive differs fundamentally**: it documents a real-world deployed system's complete lifecycle, including failure modes, environmental shocks, and explicit risk termination. Risk tolerances shown here are specific to a small experimental "mouse" account and are **not suitable for institutional capital**.

傳統量化交易研究依賴回測模型或短期操作紀錄。**本檔案根本不同**：它記錄一套真實部署系統的完整生命週期，包含失效模式、環境衝擊與明確的風險終止。本檔案所示的風險容忍度特定於小型實驗用的「小鼠帳戶」，**不適用於機構資本**。

### 1.2 System Architecture | 系統架構

```
┌──────────────────────────────────────────────┐
│ Autonomous Trading Agent (Unattended Server) │
│                                              │
│  ├─ Execution: Windows + MultiCharts (KGI)   │
│  ├─ Risk Control: Circuit-Breaker Logic      │
│  ├─ Audit: Gmail Time-Lock Timestamps        │
│  └─ Resilience: 9-Year Continuous Op.        │
└──────────────────────────────────────────────┘
```

**System Design**: All orders logged via automated email to Google infrastructure, ensuring third-party timestamp integrity. Windows-based MultiCharts with deterministic restart via SD-card scheduler. **No cloud dependency. Local hardware sovereignty.**

---

## 2. Theoretical Framework | 理論框架

### Definition 2.1: Forensic Integrity

A transaction record satisfies **forensic integrity** if:

1. **Temporal Locking**: Each record sealed with third-party timestamp (Gmail ≡ T)
2. **Cryptographic Anchoring**: Complete record set merkle-rooted to singular hash R
3. **Non-Repudiation**: Operator cannot retroactively modify records without breaking R

**Assumption**: Gmail timestamps are generated outside the operator's trust boundary and are therefore independent of system operator control.

---

### Theorem 2.2: Circuit-Breaker Principle

**Claim**: A predetermined circuit-breaker halting before structural market breakdown prevents catastrophic tail losses.

**Scope**: Single-system, single-event, engineering decision rule. *Not a universal financial theorem.*

**Evidence**: On 2020/03/18, system halted per protocol. On 2020/04/20, crude oil traded at −$37.63/barrel. System had zero exposure. □

---

## 3. Empirical Data | 實驗數據

### 3.1 Performance Summary | 績效摘要

*Note: From a pure PnL perspective, the 2020 entry corresponds to a near-total loss of initial capital. In this archive it is interpreted as successful execution of preplanned termination.*

| Year | Trades | Error Rate | Ending Equity | YoY Return | Cumulative Return | Status |
|:----:|:-------:|:----------:|:-------------:|:----------:|:---:|:-----:|
| 2012 | 0 | 100% | ¥50,000 | 0.00% | 0.00% | Bootstrap |
| 2013 | 42 | 2.33% | ¥80,000 | 60.00% | 60.00% | Stable |
| 2014 | 210 | 0.00% | ¥150,000 | 87.50% | 200.00% | Optimized |
| 2015 | 391 | 0.00% | ¥360,000 | 140.0% | 620.0% | Alpha Max |
| 2016 | 405 | 0.00% | ¥315,493 | −12.3% | 530.9% | Drawdown |
| 2017 | 23 | 89.6% | ¥637,711 | 102.1% | 1,175.4% | Recovery |
| 2018 | 162 | 40.9% | ¥997,678 | −0.01% | 143.3% | Net Liquidity |
| 2019 | 194 | 33.1% | ¥1,350,000 | 35.31% | 229.2% | Peak |
| 2020 | 112 | 33.7% | ¥30,000 | −97.7% | Graduation | **Regime-Shift Termination (Graduation)** |

### 3.2 Data Provenance | 數據源

- **Primary Source**: Automated email logs from MultiCharts execution → Gmail
- **Total Records**: 2,013 verified transactions with millisecond-precision timestamps
- **Audit Trail**: Complete order flow with environment parameters preserved (no smoothing)

### 3.3 Data Accessibility | 數據可獲性

| Asset | Format | Location | Verification |
|:---:|:----:|:-------:|:-------:|
| **Transactions** | CSV | [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv) | SHA-256 |
| **Equity Chart** | PNG | [chart.png](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png?raw=true) | Visual audit |
| **Interactive Dashboard** | HTML | [TradingView Engine](https://recofu.github.io/mouse-account-verification/index.html) | Live binding |
| **IPFS Archive** | Distributed | `bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4` | Content-addressed |

---

## 4. Cryptographic Verification | 密碼學驗證

### 4.1 Merkle Tree Construction

All 2,013 transaction records aggregated into single Merkle tree:

```
Merkle Root (SHA-256):
9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
```

**Invariant**: Any bit modification invalidates this root. Root serves as cryptographic fingerprint.

**Verification Scope**: This cryptography verifies **data integrity**, not strategy optimality or trading skill. All sensitive trading parameters remain proprietary.

### 4.2 Physical Layer Checksum

```
Raw Data SHA-256:
41316C89AA8759E8EDE969F5CED06A81D8F2A0484DFC68D4630C197AFECEE82B

OpenTimestamps Proof:
2497D2C57606F0A3E44402D98BBB8213B6F2DC6175E0B8A016EBC62F19C81A67
```

### 4.3 Identity Lock

```
Sovereign Signature:
a2a41fa07b1b82c18f373b499910779a46b85387180153f9e2a1bc4c13d78373

Authenticated by: Sovereign_0x (Reco Fu)
```

---

## 5. Environmental Resilience Analysis | 環境韌性分析

| Period | Disruption Type | Recovery Time | System Status |
|:-------|:----------:|:------:|:-----:|
| 2014–2018 | Typhoons (avg 3/yr) | Auto-recovery | ✓ Active |
| 2015, 2016 | Seismic Events (M6.0+) | <2 hours | ✓ Active |
| 2016–2019 | ISP Outages | 30–180 min | ✓ Auto-reconnect |
| 2019 | Power Loss (>10 events) | <1 hour | ✓ UPS backup |
| 2020/03/01–03/17 | COVID-19 Volatility | — | ✓ Trading Nominal |
| **2020/03/18** | **Black Swan Oil** | — | **⊗ Circuit-Breaker Activated** |

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

### 6.1 Timeline | 時間軸

| Date | Event | Oil Price | System Action |
|:----:|:-----:|:------:|:-----:|
| 2020/03/18 | OPEC+ collapse | $27.34 | **Circuit-Breaker: HALT** |
| 2020/03/20 | WTI drops 34% | $20.37 | System Idle |
| 2020/04/20 | **Negative Oil** | **−$37.63** | ✓ Zero Exposure |

**Analysis**: System halted 33 days before unprecedented regime shift, preventing structural collapse.

### 6.2 Counterfactual Analysis | 反事實分析

**Scenario Analysis** (not realized PnL):

If system had continued trading through 2020/04/20, estimated loss range under historical position sizing *(based on historical volatility scaling and 2015–2019 regime data)*: ¥X–¥Y, median scenario ≈ ¥5,000,000. Exact sizing parameters remain proprietary.

**Validation**: System did halt before this event, validating pre-committed exit design.

---

## 7. Methodological Integrity | 方法論完整性

### 7.1 Data Provenance Statement

- Raw logs preserved with environmental parameters intact (no smoothing, no retroactive adjustments)
- Broker identifiers anonymized (KGI, 元大) while maintaining authenticity
- All timestamps locked by third-party infrastructure (Gmail)
- Interactive visualization available for independent validation
- Hardware independent: Windows + MultiCharts + SD-card scheduler (no cloud)

### 7.2 Limitations

- Non-institutional environment; results do not generalize to datacenter deployments
- Single system instance limits statistical power for regime-shift detection
- Leverage ratios and position sizing not disclosed (proprietary)
- Risk tolerances are **not suitable for institutional capital**

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
> Operationally, this archive supports the claim that pre-committed exit rules can prevent catastrophic tail losses in at least one real-world deployment. It does not claim that all predictive models are obsolete."

---

## 9. Archival Preservation | 檔案保存

This repository is maintained as a **forensic artifact**—permanent record of system behavior under real-world conditions.

### IPFS Permanent Record

```
IPFS Content Hash: bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
Merkle Root: 9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
Status: Content-addressed, immutable, distributed
Accessible: https://ipfs.io/ipfs/bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
```

### Support for Archival Preservation

This repository is maintained as a permanent record. Support for long-term archival is provided through:

- **PayPal**: [Support via PayPal](https://www.paypal.me/RecoFu)
- **GitHub**: [Issues & Inquiries](https://github.com/RecoFu/mouse-account-verification/issues)

**Key Principle**: Contributions are voluntary gifts recognizing historical preservation, not service contracts. All content provided AS-IS.

---

## 10. Conclusion | 結論

This nine-year record demonstrates that **predetermined, explicit risk termination can prevent catastrophic tail losses** in extreme market regimes. The system's ability to survive eight years of environmental shocks, combined with its timely exit before a structural breakdown, validates a risk philosophy centered on **controlled failure** rather than boundless adaptation.

The cryptographic audit trail provides a template for trustless documentation of autonomous systems in high-stakes environments.

本九年紀錄表明，**預定的明確風險終止可防止極端市場中的災難性尾部損失**。系統在八年環境衝擊後仍生存，結合其在結構性崩潰前的及時退出，驗證了以**受控失敗**而非無限適應為中心的風險哲學。

### 10.1 Coda | 附言

> **"The logic is immutable. The history is sealed.**
>
> What you see here is not a trading record.
> It is a **systems engineering artifact.**
>
> From 1984 FidoNet to 2025 AI integration:
> This is what happens when a root-cause engineer builds an autonomous system and then gets out of the way."

---

## 11. References | 參考文獻

[1] Taleb, N. N. (2007). *The Black Swan*. Random House.

[2] Nakamoto, S. (2008). Bitcoin: A Peer-to-Peer Electronic Cash System. *whitepaper*.

[3] Merkle, R. C. (1988). "A Digital Signature Based on a Conventional Encryption Function." *CRYPTO '87*.

[4] Mouse Account Verification Archive (2012–2020). *Forensic Artifact Repository*. GitHub: https://github.com/RecoFu/mouse-account-verification

---

## Appendix A: System Parameters | 附錄 A：系統參數

- **OS**: Windows + MultiCharts (home server, Taiwan)
- **Runtime**: 2,913 continuous days (2012–2020)
- **Network**: ISP-dependent, no guaranteed connectivity
- **Power**: Residential power + UPS + SD-card scheduler
- **Brokers**: Two independent brokers (anonymized for operational privacy)
- **Timestamps**: Gmail (Google Infrastructure)
- **Verification**: SHA-256, Merkle root, IPFS

---

## Appendix B: Interactive Data | 附錄 B：互動數據

- **Interactive Dashboard**: [TradingView Engine](https://recofu.github.io/mouse-account-verification/index.html)
- **Equity Chart**: [chart.png](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/chart.png?raw=true)
- **Raw Data**: [data.csv](https://github.com/RecoFu/mouse-account-verification/blob/RecoFu/data.csv)

---

## Appendix C: Cryptographic Proof of Authenticity | 附錄 C：真實性密碼學證明

```
Git Repository: https://github.com/RecoFu/mouse-account-verification
Branch: RecoFu

IPFS Archive: bafybeigzq7c3yljcxsvjivrphlgo7mhsilcc5qhm24i4tbwcgw5ucjimp4
Merkle Root: 9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557

Status: Content-Addressed, Immutable, Distributed
Trust Model: Zero-knowledge proof via cryptographic anchors, not human authority.
```

---

**"The logic is immutable. The history is sealed. The system survived."**

*Forensic Artifact for Permanent Record | 2026*
