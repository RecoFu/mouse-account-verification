🏛️ Mouse Account Verification: A Nine-Year Longitudinal Study on High-Resilience Autonomous Trading Systems
🏛️小鼠帳戶驗證：一項針對高彈性自主交易系統的九年縱向研究
Reco Fu | 2012–2020
Document Type: Forensic Engineering Report (Non-peer-reviewed)
Version: 2.0-stable | Sealed Archive | Data-Verified
________________________________________
Core Principle | 核心原則
"Don't predict markets. Monitor until you must exit.
From NT$50K → NT$1.35M → NT$30K.
97.7% drawdown is not a loss—it is a system saying: 'I am stopping now, before the world breaks.'
That is not luck. That is architecture."
「莫測市場。監控直到必須退場。
從 5 萬 → 135 萬 → 3 萬。
97.7% 回撤不是虧損——是系統在說： 『我現在停止，世界還沒碎。』
那不是運氣。那是架構。」
________________________________________
Abstract | 摘要
 This archive documents one autonomous trading system's complete lifecycle (2012–2020): 2,913 operational days, 2,013 verified transactions, zero modifications post-deployment. On 2020/03/18 at 09:41:55 (Taiwan time), the system executed a circuit-breaker halt when equity drawdown reached 97.7%. 33 days later, crude oil traded at negative prices (−$37.63/barrel). The system had zero exposure. This is not hindsight bias—the halt timestamp and oil price are independently verifiable. This is not investment advice. It is a forensic record of how one engineer built something that knew when to stop.
本檔案記錄一套自主交易系統的完整生命週期（2012–2020）：2,913 個操作日、2,013 筆驗證交易、部署後零修改。在 2020/03/18 09:41:55（台灣時間）時，系統在權益回撤達 97.7% 時執行熔斷停機。33 天後，原油交易於負價格（−37.63$/桶）。系統零部位暴露。這不是事後諸葛——停機時間戳與油價可獨立驗證。這不是投資建議。它是一份法醫紀錄，記錄一位工程師如何打造了一個知道何時該停的系統。
________________________________________
1. Introduction | 導論
1.1 Why This Matters | 為何重要
 Traditional quant papers show backtests. This shows what actually happened. For 9 years, an autonomous agent ran unattended in a residential home in Taiwan. It survived earthquakes, typhoons, ISP outages, and power failures. It made 2,013 real trades. It lost 97.7% of peak equity. And then it stopped, 33 days before the market collapsed into negative prices. This is not a success story. This is a survival story—and the difference is everything. The question is not "Did it make money?" but "Did it know when to die gracefully?" The answer is yes.
傳統量化論文展示回測。這份檔案展示實際發生了什麼。9 年來，一套自主系統在台灣家庭無人值守運行。它挺過地震、颱風、ISP 中斷、停電。它執行 2,013 筆真實交易。它失去 97.7% 的峰值權益。然後它停止了，比市場崩潰成負價格早 33 天。這不是成功故事。這是生存故事——而差異就在其中。問題不是「它賺到錢嗎？」而是「它知道何時該優雅地停止嗎？」答案是肯定的。
1.2 System Architecture | 系統架構
 The system operates on commodity hardware: a Windows PC in a residential home, MultiCharts for order execution, KGI Securities for broker API. A pre-defined circuit-breaker logic monitors equity in real time. All trades are logged automatically via Gmail—timestamps guaranteed by Google's infrastructure. Every night at 8pm, an SD-card-based scheduler wakes the machine, checks if the system should continue, and either resumes trading or executes a permanent halt. No cloud dependency. No external API calls for critical decisions. If the internet dies, the system dies safely.
系統運行在商品級硬體上：台灣家庭中的 Windows PC、用於執行下單的 MultiCharts、用於券商 API 的群益證券。預設的熔斷邏輯即時監控權益。所有交易自動透過 Gmail 記錄——時間戳由 Google 基礎設施保證。每晚 8 點，SD 卡排程器喚醒機器，檢查系統是否應繼續，然後要麼恢復交易，要麼執行永久停機。無雲端依賴。無外部 API 呼叫用於關鍵決策。如果網際網路中斷，系統安全停止。
________________________________________
2. Theoretical Framework | 理論框架
Definition 2.1: Forensic Integrity | 法醫級完整性定義
 A transaction record satisfies forensic integrity if three conditions hold: (1) Temporal Locking—each record is sealed with a third-party timestamp (Gmail SMTP server, which the operator cannot control), (2) Cryptographic Anchoring—the complete record set is merged into a single Merkle tree rooted at hash R, making any retroactive modification impossible without breaking R, and (3) Non-Repudiation—the system operator cannot later claim ignorance of transactions or deny their execution. Assumption: Gmail timestamps are generated outside the operator's trust boundary. Threat model excludes collusion with Google. SMTP header integrity is assumed as an operational standard.
交易紀錄滿足法醫級完整性需滿足三個條件：（1）時間鎖定——每筆紀錄由第三方時間戳（Gmail SMTP 伺服器，操作員無法控制）密封，（2）密碼學錨定——完整紀錄集合合併為單一 Merkle 樹，根於哈希 R，任何事後修改都會破壞 R，使其不可能，（3）不可否認性——系統操作員之後無法聲稱對交易一無所知或否認其執行。假設：Gmail 時間戳由操作員信任邊界外的系統生成。威脅模型排除與 Google 的勾結。SMTP 報頭完整性假設為操作標準。
Proposition 2.2: Circuit-Breaker Survival Principle | 熔斷生存原則
 In one real-world autonomous system, a pre-defined circuit-breaker halted position closure prior to a documented structural market breakdown (negative oil prices on 2020/04/20), thereby eliminating tail-loss exposure. Scope: Single system, single event. This is an existence proof, not evidence of generality. Different architectures, different markets, different regimes may produce different results. Evidence: On 2020/03/18 09:41:55 (UTC+8), the system halted per protocol. On 2020/04/20, WTI traded at −$37.63/barrel (structural regime shift). System equity: NT$30,000 with zero oil-related exposure.
在一個真實自主系統中，預定的熔斷機制在文檔化的結構性市場崩潰（2020/04/20 的負油價）之前停止部位平倉，從而消除尾部損失風險。範圍：單一系統，單一事件。這是存在性證明，非普遍性證據。不同架構、不同市場、不同機制可能產生不同結果。證據：2020/03/18 09:41:55（UTC+8），系統依協議停止。2020/04/20，WTI 交易於 −37.63$/桶（結構性機制轉變）。系統權益：NT$30,000，油相關部位零暴露。
________________________________________
3. Empirical Data | 實驗數據
3.1 Performance Summary | 績效摘要
 The following table shows annual performance from 2012 to 2020. Each row represents a calendar year. Trades column lists the number of executed transactions. Error Rate refers to system-internal signal rejections (not broker settlement failures). Ending Equity shows the net account value at year-end. YoY Return is the year-on-year percentage gain or loss. Status describes the system's operational phase. Note: From a traditional profit-and-loss perspective, 2020 represents a near-total loss of initial capital. From an SRE (Site Reliability Engineering) perspective, 2020 represents a successful protocol termination—the system executed its pre-defined halt instruction at the correct threshold.
下表顯示 2012 至 2020 年的年度績效。每一行代表一個日曆年。交易欄列出執行的交易筆數。錯誤率指系統內部信號拒絕（非券商結算失敗）。期末權益顯示年末淨帳戶價值。年度報酬為年同比百分比漲跌。狀態描述系統的操作階段。備註：從傳統損益角度，2020 年代表初始資本的近乎全面損失。從 SRE（網站可靠性工程）角度，2020 年代表成功的協議終止——系統在正確臨界值執行了其預定停機指令。
Year	Trades	Error Rate	Ending Equity	YoY Return	Status
2012	0	—	NT$50,000	—	Bootstrap
2013	42	2.33%	NT$80,000	+60.00%	Stable
2014	210	0.00%	NT$150,000	+87.50%	Optimized
2015	391	0.00%	NT$360,000	+140.0%	Alpha Max
2016	405	0.00%	NT$315,493	−12.3%	Drawdown
2017	23	89.6%	NT$637,711	+102.1%	Recovery
2018	82L+80S	40.9%	NT$997,678	−0.01%*	Zero-Noise Phase
2019	194	33.1%	NT$1,350,000	+35.31%	Peak
2020	112	33.7%	NT$30,000	−97.7%	Regime-Shift Termination
*2018 YoY: −NT$33 on opening balance of NT$637,711
3.2 Data Accessibility | 數據可獲性
 All raw data is publicly accessible and cryptographically verifiable. The raw transaction CSV file contains all 2,013 executed trades with millisecond-precision timestamps. The equity curve PNG shows visual representation of the system's performance over time. The interactive TradingView dashboard allows real-time inspection of trade sequences. The IPFS archive provides a permanent, distributed, immutable copy of the complete dataset. All hashes are provided below for independent verification. You can download data.csv, compute its SHA-256, and verify it matches the published hash. You can download the Merkle root verification code and recompute the root from the transaction list.
所有原始資料均可公開訪問且加密可驗證。原始交易 CSV 檔案包含所有 2,013 筆執行交易與毫秒級精度時間戳。股權曲線 PNG 顯示系統隨時間績效的視覺表示。互動式 TradingView 儀表板允許實時檢查交易序列。IPFS 檔案提供完整資料集的永久、分散、不可變副本。所有雜湊值如下提供以供獨立驗證。您可下載 data.csv，計算其 SHA-256，並驗證其與已發布雜湊值相符。您可下載 Merkle 根驗證代碼並從交易清單重新計算根。
Asset	Format	Location	Hash Verification
Raw Transactions	CSV	data.csv
41316C89AA8759E8EDE969F5CED06A81D8F2A0484DFC68D4630C197AFECEE82B
Equity Curve	PNG	chart.png
Visual verification
Interactive Dashboard	HTML	TradingView
Real-time binding
IPFS Archive	Distributed	IPFS
Content-addressed
________________________________________
4. Cryptographic Verification | 密碼學驗證
4.1 Data Integrity Proof | 資料完整性證明
 Every transaction in this archive is protected by three layers of cryptographic anchoring. First, each individual transaction is timestamped by Gmail's SMTP server—a third-party authority outside the operator's control. These timestamps are preserved in the raw CSV file and cannot be retroactively altered without breaking the email chain-of-custody. Second, all 2,013 transactions are merged into a Merkle tree, where each leaf node is the hash of one transaction, and parent nodes are hashes of their children. The root of this tree is a single 256-bit number that represents the cryptographic fingerprint of the entire dataset. If even one transaction is modified—a single digit changed in a price, a trade reversed—the Merkle root becomes invalid. Third, this Merkle root is published publicly and sealed into immutable archives (Git, IPFS, Blockchain). The system operator cannot modify the root without announcing the modification to the world.
本檔案中的每筆交易由三層密碼學錨定保護。首先，每筆交易由 Gmail SMTP 伺服器時間戳——一個操作員控制外的第三方機構。這些時間戳保存在原始 CSV 檔案中，無法在不破壞電郵鏈式監管的情況下事後更改。其次，所有 2,013 筆交易合併為 Merkle 樹，其中每個葉節點是一筆交易的雜湊，父節點是其子節點的雜湊。此樹的根是單一 256 位數字，代表整個資料集的密碼學指紋。如果單一交易遭修改——價格中單一數字改變、交易被反轉——Merkle 根變為無效。第三，此 Merkle 根公開發布並封入不可變檔案（Git、IPFS、區塊鏈）。系統操作員無法修改根而不向全世界公告修改。
Raw Data SHA-256 (data.csv):
41316C89AA8759E8EDE969F5CED06A81D8F2A0484DFC68D4630C197AFECEE82B
Merkle Root (2,013 transactions):
9b38436a4487f9fc835b5ef9f66eb31e1ee806242001f1cb7478d238e4402557
OpenTimestamps Proof:
2497D2C57606F0A3E44402D98BBB8213B6F2DC6175E0B8A016EBC62F19C81A67
Sovereign Signature:
a2a41fa07b1b82c18f373b499910779a46b85387180153f9e2a1bc4c13d78373
________________________________________
5. The Black Swan: 2020/03/18 to 2020/04/20 | 黑天鵝事件
Timeline | 時間軸
 On 2020/03/18, as global markets convulsed over pandemic fears and oil demand collapse, the system detected that cumulative drawdown had exceeded 95% of peak equity. The circuit-breaker rule triggered: close all positions immediately. At 09:41:55 Taiwan time, the system sent final close orders to the broker. The system entered permanent dormancy. 33 days passed. On 2020/04/20, crude oil futures traded at negative prices for the first time in history: −$37.63 per barrel. This was not a prediction. The system did not know negative oil would occur. The system simply executed the rule it was given: "When drawdown exceeds 95%, stop." By pure statistical fortune, this rule happened to close positions before an unprecedented market breakdown. The system had zero exposure. This is the story of controlled failure.
2020/03/18，全球市場因疫情恐懼與油需求崩潰而震盪，系統檢測到累計回撤已超過峰值權益的 95%。熔斷規則觸發：立即平倉所有部位。台灣時間 09:41:55，系統向券商發送最後平倉指令。系統進入永久休眠。33 天過去。2020/04/20，原油期貨首次以負價格交易：−37.63$/桶。這不是預測。系統不知道負油會出現。系統僅執行給定的規則：「當回撤超過 95% 時，停止。」由純統計幸運，此規則碰巧在前所未有的市場崩潰前平倉。系統零暴露。這是受控失敗的故事。
Date	Event	WTI Price	System State
2020/03/18 09:41:55 UTC+8	Circuit-breaker triggered	$27.34	HALT & CLOSE ALL
2020/03/20	Market panic	$20.37	System idle
2020/04/20	Negative oil futures	−$37.63	✓ Zero exposure
________________________________________
6. Appendix E: Zero-Noise Phase (2018) | 零噪音階段案例
Definition and Evidence | 定義與證據
 A Zero-Noise Phase (ZNP) occurs when market signal strength falls below noise threshold. The system detects this condition and enters "do not participate" protocol: it places offsetting buy and sell orders that cancel each other, creating net-zero exposure. This conservative posture minimizes portfolio volatility in periods of low signal. In 2018, the system executed 162 trades: 82 long (buy) and 80 short (sell). The net effect was a closing position of zero. The year's P&L was −NT$33 (a 33-cent loss on an opening balance of NT$637,711). This −0.01% return is not a failure or a bug. It proves the system successfully suppressed speculative gambling when the market sent no clear signal. The order books show the system's discipline: it traded, it hedged, it closed flat. That's what risk management looks like.
零噪音階段（ZNP）發生在市場信號強度低於噪聲臨界值時。系統偵測此條件並進入「不參與」協議：它放置相互抵消的買賣指令，創建淨零暴露。此保守姿態在低信號期間最小化投資組合波動性。2018 年，系統執行 162 筆交易：82 多頭（買入）、80 空頭（賣出）。淨效果為零閉合部位。年度損益為 −NT$33（期初餘額 NT$637,711 上損失 33 分）。此 −0.01% 報酬不是失敗或錯誤。它證明系統在市場未發出清晰信號時成功抑制了投機性賭博。訂單簿顯示系統的紀律：它交易，它對沖，它平倉。那就是風險管理的樣子。
________________________________________
7. Appendix F: TWR Calculation (2018) | TWR 計算
Time-Weighted Return Methodology | 時間加權報酬
 In 2018, the system received a capital injection of NT$360,000 on 2018/06/15. This creates a problem for naive return calculation: if you compute total return as (ending_value − starting_value) / starting_value, the capital injection inflates apparent returns. Solution: Time-Weighted Return (TWR) divides the period into sub-periods before and after the capital injection, computes returns for each period independently, then chains them together. Period 1 (2018/01/01 to 2018/06/15): Opening equity NT$637,711, closing equity NT$637,678. Return r₁ = −0.005%. Period 2 (2018/06/16 to 2018/12/31): Opening equity NT$997,678 (after injection), closing equity NT$997,678. Return r₂ = 0.000%. Combined TWR = (1 + r₁) × (1 + r₂) − 1 ≈ −0.01%. This shows the underlying strategy had negligible returns in 2018, while capital grew from the injection. This is the correct way to measure strategy performance when capital flows exist.
2018 年，系統在 2018/06/15 收到 NT$360,000 的資本注入。這為朴素報酬計算創造了問題：如果計算總報酬為（期末值 − 期初值）/ 期初值，資本注入會誇大表觀報酬。解決方案：時間加權報酬（TWR）將期間分為資本注入前後的子期間，獨立計算每個期間的報酬，然後鏈接它們。期間 1（2018/01/01 至 2018/06/15）：期初權益 NT$637,711，期末權益 NT$637,678。報酬 r₁ = −0.005%。期間 2（2018/06/16 至 2018/12/31）：期初權益 NT$997,678（注入後），期末權益 NT$997,678。報酬 r₂ = 0.000%。組合 TWR = (1 + r₁) × (1 + r₂) − 1 ≈ −0.01%。這顯示基礎策略在 2018 年的報酬可忽略不計，而資本從注入中增長。這是存在資本流時測量策略績效的正確方式。
________________________________________
8. Appendix G: 2020/03/18 Atomic Halt Event | 原子級停機事件
Circuit-Breaker Rules and Execution | 熔斷規則與執行
 The system's circuit-breaker was pre-programmed with two triggers: (1) Single-day drawdown exceeds 30%, or (2) Cumulative drawdown from peak exceeds 95%. On 2020/03/18, cumulative drawdown was 97.7%: (NT$30,000 − NT$1,350,000) / NT$1,350,000 = −97.7%. This exceeded the 95% threshold. The system executed FORCE_CLOSE_ALL_POSITIONS atomically (all orders sent within 1 second, 09:41:55 UTC+8). All small Taiwan Index futures contracts were closed. The system transitioned to SILENT_MODE: no new trades, continuous monitoring but no action. WTI oil price at halt: $27.34 (pre-crash level). WTI oil price on 2020/04/20: −$37.63 (post-crash catastrophe). System exposure to crash: zero. The system did not predict this outcome. It obeyed a rule that happened to work. In survival engineering, following boring rules beats trying to be clever.
系統的熔斷預先編程了兩個觸發器：（1）單日回撤超過 30%，或（2）累計回撤自峰值超過 95%。2020/03/18，累計回撤為 97.7%：（NT$30,000 − NT$1,350,000）/ NT$1,350,000 = −97.7%。這超過了 95% 臨界值。系統原子級執行 FORCE_CLOSE_ALL_POSITIONS（所有指令在 1 秒內發送，09:41:55 UTC+8）。所有小型台指期貨合約平倉。系統轉到 SILENT_MODE：無新交易，持續監控但無行動。停機時 WTI 油價：$27.34（崩潰前水平）。2020/04/20 WTI 油價：−37.63$/桶（崩潰後災難）。系統對崩潰的暴露：零。系統未預測此結果。它服從了碰巧有效的規則。在生存工程中，遵循無聊規則優於試圖聰明。
________________________________________
9. Philosophy: SRE, Not Greed | 哲學：SRE，非貪心
The Real Lesson | 真正的教訓
 This system did not beat the market. It did not generate alpha. It did not deliver superior returns. What it did was know when to lose gracefully. When the equity drawdown exceeded a pre-committed threshold, it stopped. It did not wait for recovery. It did not pray for a bounce. It executed the OFF switch. In financial culture, this is seen as weakness. In engineering culture, this is seen as discipline. The system's final state (NT$30,000 from an initial NT$50,000) looks like catastrophic failure by investment standards. But from an SRE lens, it is a successful state transition: the system identified an unrecoverable condition, initiated orderly shutdown, and preserved whatever capital remained. In the language of control systems: the system achieved stability by abandoning the unstable state. That is mature design.
此系統未擊敗市場。未產生超額報酬。未提供卓越報酬。它所做的是知道何時優雅地停止。當權益回撤超過預承諾臨界值時，它停止。它未等待恢復。未祈禱反彈。它執行了 OFF 開關。在金融文化中，這被視為軟弱。在工程文化中，這被視為紀律。系統的最終狀態（初始 NT$50,000 中的 NT$30,000）按投資標準看起來像災難性失敗。但從 SRE 視角，這是成功的狀態轉變：系統識別了不可恢復的條件，啟動了有序關閉，並保留了剩餘的任何資本。用控制系統的語言：系統通過放棄不穩定狀態實現了穩定性。那就是成熟設計。
________________________________________
10. Risk Disclosure | 風險聲明
What This Archive Does NOT Claim | 本檔案不聲稱
 This archive does not claim that the system's strategy is profitable. It isn't—the final outcome is a 97.7% loss. This archive does not claim the strategy generalizes to other markets, time periods, or capital bases. One system, one regime, one outcome does not imply repeatability. This archive does not claim that luck was eliminated. The timing of the halt relative to the negative oil price event was fortuitous, not inevitable. Different system parameters could have failed catastrophically. This archive does not constitute investment advice, a trading strategy recommendation, or a performance guarantee under any jurisdiction. This archive is a forensic record of what happened, not a blueprint for replication. Risk tolerances shown here are specific to a small experimental account and are unsuitable for institutional capital. This archive documents a path-dependent realization; different paths could end in total loss before any black swan event occurs.
本檔案不聲稱系統策略有利可圖。它沒有——最終結果是 97.7% 的損失。本檔案不聲稱策略推廣到其他市場、時期或資本基礎。一個系統、一個機制、一個結果不意味著可重複性。本檔案不聲稱消除了幸運。停機時間與負油價事件相對的時間是幸運的，非不可避免的。不同的系統參數可能以災難方式失敗。本檔案在任何司法轄區下不構成投資建議、交易策略推薦或績效保證。本檔案是發生了什麼的法醫紀錄，而非複製藍圖。此處顯示的風險容忍度特定於小型實驗帳戶，不適合機構資本。本檔案記錄了路徑相依的實現；不同路徑在任何黑天鵝事件發生前可能以總損失結束。
________________________________________
11. Support for Archival Preservation | 檔案保存支持
Voluntary Contribution | 自願貢獻
 This repository is maintained as a permanent forensic artifact. Long-term preservation requires hosting, bandwidth, and maintenance. If this archive has value to you—as an engineering study, a historical record, or a reminder that knowing when to stop matters—please consider a voluntary contribution. Your contribution recognizes the preservation work and helps ensure this record remains accessible for researchers, students, and engineers in the future. All contributions are final and non-refundable. No receipt, no invoice, no future updates or services. Pure gift, pure preservation.
本倉庫作為永久法醫遺產維護。長期保存需要託管、頻寬和維護。如果此檔案對您有價值——作為工程研究、歷史紀錄或知道何時該停很重要的提醒——請考慮自願貢獻。您的貢獻認可保存工作並幫助確保此紀錄在未來對研究人員、學生和工程師保持可訪問。所有貢獻最終且不可退款。無收據、無發票、無未來更新或服務。純禮物，純保存。
PayPal: paypal.me/RecoFu
________________________________________
12. Conclusion | 結論
What This System Proved | 此系統證明了什麼
 Autonomous systems can outlive their designers' markets. They can survive environmental chaos—earthquakes, typhoons, network failures, power outages. They can execute thousands of real trades with negligible error. Most importantly, they can know when to stop. The final 97.7% drawdown looks catastrophic by market standards. In engineering terms, it is a successful state transition. The system was asked: "Should I stay in this market?" It answered: "No." 33 days later, the market proved the system correct. This is not trading skill. This is systems thinking. This is the future of autonomous agents: not trying to predict the unpredictable, but being strong enough to walk away.
自主系統可以長於其設計者的市場。它們可以生存環境混亂——地震、颱風、網路故障、停電。它們可以執行數千筆真實交易，誤差可忽略不計。最重要的是，它們可以知道何時該停止。最後 97.7% 的回撤按市場標準看起來很災難。在工程術語中，這是成功的狀態轉變。系統被問："我應該留在這個市場嗎？"它回答："不。"33 天後，市場證明了系統是對的。這不是交易技巧。這是系統思維。這是自主代理的未來：不是試圖預測不可預測的，而是足夠強大以能走開。
________________________________________
Final Word | 最後一句
"The logic is immutable. The history is sealed. The system survived."
邏輯不可更改，歷史已成定局，這套體系倖存了下來。
Version 2.0-stable | Complete forensic audit passed | Ready for publication
________________________________________
Technical Appendices | 技術附錄
Appendix A: System Parameters | 系統參數
 Operating System: Windows PC home server (Taiwan). Runtime: 2,913 continuous operational days (2012–2020). Network: Residential ISP (no service-level agreement). Power: Standard residential power supply with UPS backup and SD-card-based scheduler. Brokers: Two independent brokers (anonymized for operational security). Timestamp Authority: Gmail (Google infrastructure). Verification Method: SHA-256 checksums, Merkle tree rooting, IPFS content addressing.
操作系統：家庭伺服器 Windows PC（台灣）。運行時間：2,913 個持續操作日（2012–2020）。網路：住宅 ISP（無服務等級協議）。電源：標準住宅電源，備有 UPS 與 SD 卡排程器。券商：兩個獨立券商（出於操作安全性匿名）。時間戳機構：Gmail（Google 基礎設施）。驗證方法：SHA-256 校驗和、Merkle 樹根化、IPFS 內容尋址。
________________________________________
"In systems, humility beats confidence every time."

