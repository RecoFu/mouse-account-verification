# Mouse Account Verification PoW (2012-2020)
自動化交易系統完整資料驗證。
## 資料完整性
- **總交易筆數**: 1,539 筆
- **時間範圍**: 2012-2020
- **Merkle Root Hash**: [0538dd791e2e04ccb715db5aa548a83cc6b6cba1b9b62d5b4d75fe718bdd2f9a]
## 驗證方法
1. 下載此 CSV 文件
2. 運行 `python3 compute_merkle.py`
3. 對比輸出的 Hash 值與上面的 Merkle Root
若 Hash 匹配 → 資料未被篡改 ✓
## Email 驗證
所有交易記錄通過 Gmail 自動發送，精確到秒。
- Gmail 時間戳記由 Google 伺服器保證
- 無法假造
## 關鍵資料
| 年份 | 期初 | 期末 | 年報酬 | 錯誤率 |
|------|------|------|--------|--------|
| 2012-15 | ¥50K | ¥360K | 620% | ~2% |
| 2017 | ¥315K | ¥637K | 102.13% | 89.59% |
| 2019 | ¥997K | ¥1.35M | 35.31% | 33.10% |
| 2020 | ¥1.35M | ¥30K | -97.78% | 33.73% |
2020年3月18日系統停止運行。
---
Author: Reco Fu
Verification: GitHub Commit + Gmail Timestamp + Merkle Hash
```
---
## Gmail 郵件樣本
郵件：
```
Date: 2020/02/24 09:03:44 GMT
From: OrderMaster  
To:  gmail.com
【TCA】 "11543" 減碼多單
策略倉位: 11 → 10
帳戶: 【KGI】(小型台指)
帳戶倉位: 11 → 10
倍數: 1
本次下單: -1
下單後帳戶總倉位: 10
```
**關鍵驗證點：**
- ✅ Gmail 時間戳記：`2020/02/24 09:03:44`（精確到秒）
- ✅ 帳戶：KGI
- ✅ 交易方向：減碼多單（空）
- ✅ 成交價：11543
