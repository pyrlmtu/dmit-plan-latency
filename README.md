# DMIT 評測：洛杉磯、香港、東京 Pro／EB／T1 三條線路差在哪？全套餐價格與實測延遲一次看完

搜「DMIT 評測」的人，多半不是想知道這家公司在哪裡註冊，而是被同一個問題卡住：三條線路、三個機房、十幾個檔位，價格從一年三十幾美元一路到月付八百，到底該從哪裡下手。

先把話說在前面。DMIT 貴的不是硬體——全線 AMD EPYC 加 NVMe，這個配置本身撐不起它的價格。真正在定價的是線路：CN2 GIA、CMIN2、AS9929 這些中國方向優化資源，以及它自己跟三大運營商簽的頻寬。看懂這一點，後面的選擇就沒那麼難了。

> 以下是撰寫時從官網產品頁與多個主機資訊站整理的資料。DMIT 補貨、改價、下架套餐的頻率相當高（東京 EB、香港 EBv2 都已先後退場），下單前請以官網即時顯示的配置與價格為準。

## Pro、EB、T1 到底差在哪

這三條線就是全部的分歧點，選錯了後面全是白花錢。

**Pro（Premium）**：面向中國大陸訪問優化，回程走中國電信 CN2 GIA（AS4809）。洛杉磯的 Pro 是電信去程 GIA、聯通直連 AS4837、移動經香港移動 AS58453 進入，三網回程統一 GIA。香港的 Pro 是三網回程經香港 CTG 接國內 CN2 GIA。東京的 Pro 回程 CN2 GIA，去程另外走 9929／CMI。電信用戶想要晚高峰不掉速，這條是首選。

**EB（Eyeball）**：同樣做中國方向優化，但用的是移動 CMIN2、聯通 AS9929 這條路線（洛杉磯 EB 的電信流量在 AS9929 與 AS58807 之間做負載均衡）。同價位下流量通常比 Pro 更大。移動、聯通用戶值得優先看。注意：香港與東京的 EB 系列已經下架，目前只有洛杉磯還買得到。

**T1（Tier 1）**：純國際 BGP 線路，官方明確不做中國方向優化。好處是便宜、頻寬大、流量多，超量之後限速不停機。適合用戶在海外、或者只是要一個落地節點的人。

一個常見的踩坑點：如果你人在中國大陸、用的是電信，買香港 T1 的實際體驗可能還不如洛杉磯 Pro，因為 T1 根本不針對回國線路優化。

## 三地實測延遲參考

延遲這種東西跟你的城市、運營商、當天線路狀況都有關，以下是各家評測反覆出現的區間，只當作量級參考。

- **香港 Pro**：三網平均約 40–50ms，電信、聯通約 42ms，移動約 46ms
- **東京 Pro**：大陸方向大致落在 50–90ms，上海方向表現最好
- **洛杉磯 Pro／EB**：三網平均約 140–160ms
- **洛杉磯 T1**：三網平均約 200ms 上下，電信約 180ms、移動可能到 250ms

想自己測的話，官網有提供測試 IP：香港 Pro `103.117.100.199`、香港 T1 `154.12.176.28`、東京 Pro `154.12.190.32`、東京 T1 `154.31.112.5`、洛杉磯 Pro `179.255.100.100`、洛杉磯 EB `179.255.150.150`。建議在晚上八點到十一點這個時段 ping，白天測出來的數字沒什麼參考價值。

## 洛杉磯 LAX.AS3.Pro 全套餐

洛杉磯 Pro 是 DMIT 賣得最久、也最常補貨的一條線。標配 KVM 虛擬化、1 個 IPv4 加 IPv6 /64，流量超量後限速 4–10Mbps 不限量。

| 方案 | CPU | 記憶體 | 硬碟 | 頻寬／月流量 | 超量政策 | 月付價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Pro.TINY | 1 核 | 2GB | 20GB | 1Gbps / 1TB | 4Mbps 不限量 | US$10.90 | [ 查看 TINY 方案](https://www.dmit.io/aff.php?aff=12046) |
| Pro.Pocket | 2 核 | 2GB | 40GB | 4Gbps / 1.5TB | 4Mbps 不限量 | US$16.90 | [ 看 Pocket 目前價格](https://www.dmit.io/aff.php?aff=12046) |
| Pro.STARTER | 2 核 | 2GB | 80GB | 10Gbps / 3TB | 4Mbps 不限量 | US$34.90 | [ 前往選購 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MINI | 4 核 | 4GB | 80GB | 10Gbps / 5TB | 8Mbps 不限量 | US$62.90 | [ 查看 MINI 方案](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MICRO | 4 核 | 4GB | 160GB | 10Gbps / 7TB | 8Mbps 不限量 | US$87.90 | [ 看 MICRO 配置](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MEDIUM | 6 核 | 8GB | 160GB | 10Gbps / 14TB | 10Mbps 不限量 | US$199.90 | [ 查看 MEDIUM 方案](https://www.dmit.io/aff.php?aff=12046) |

## 洛杉磯 LAX.AS3.EB 全套餐

同樣價格、更大流量，這是 EB 存在的意義。對照上面那張表，Pocket 就從 1.5TB 跳到 3TB。

| 方案 | CPU | 記憶體 | 硬碟 | 頻寬／月流量 | 超量政策 | 月付價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| EB.TINY | 1 核 | 2GB | 20GB | 2Gbps / 1.5TB | 4Mbps 不限量 | US$10.90 | [ 查看 EB TINY](https://www.dmit.io/aff.php?aff=12046) |
| EB.Pocket | 2 核 | 2GB | 40GB | 4Gbps / 3TB | 4Mbps 不限量 | US$16.90 | [ 看 EB Pocket 價格](https://www.dmit.io/aff.php?aff=12046) |
| EB.STARTER | 2 核 | 2GB | 80GB | 10Gbps / 5TB | 4Mbps 不限量 | US$34.90 | [ 前往訂購 EB STARTER](https://www.dmit.io/aff.php?aff=12046) |
| EB.MINI | 4 核 | 4GB | 80GB | 10Gbps / 10TB | 8Mbps 不限量 | US$62.90 | [ 查看 EB MINI](https://www.dmit.io/aff.php?aff=12046) |
| EB.MICRO | 4 核 | 4GB | 160GB | 10Gbps / 14TB | 8Mbps 不限量 | US$87.90 | [ 看 EB MICRO 配置](https://www.dmit.io/aff.php?aff=12046) |
| EB.MEDIUM | 6 核 | 8GB | 160GB | 10Gbps / 30TB | 10Mbps 不限量 | US$199.90 | [ 查看 EB MEDIUM](https://www.dmit.io/aff.php?aff=12046) |

## Tier 1 全套餐（洛杉磯／香港／東京同價同階梯）

T1 是三地價格最一致的產品線，入門款 WEE 年付 US$36.9 也是 DMIT 全站最低門檻。流量用盡後降速不停機，各檔限速從 50Mbps 到 1Gbps 不等。同型號在不同機房的記憶體與硬碟配置偶有差異，以官網為準。

| 方案 | CPU | 記憶體 | 硬碟 | 頻寬／月流量 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1.WEE | 1 核 | 1GB | 20GB | 4Gbps / 1TB | 50–100Mbps 不限量 | US$36.9／年 | [ 看 T1 WEE 方案](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 核 | 1GB | 20GB | 4Gbps / 2TB | 100–200Mbps 不限量 | US$6.9／月 | [ 查看 T1 TINY](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 1 核 | 2GB | 40GB | 10Gbps / 4TB | 100–200Mbps 不限量 | US$12.9／月 | [ 看 T1 STARTER 價格](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 核 | 2–4GB | 60–80GB | 10Gbps / 8TB | 100–200Mbps 不限量 | US$21.9／月 | [ 前往選購 T1 MINI](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 核 | 4GB | 80–120GB | 10Gbps / 16TB | 200–500Mbps 不限量 | US$32.9／月 | [ 查看 T1 MICRO](https://www.dmit.io/aff.php?aff=12046) |
| T1.MEDIUM | 4 核 | 8GB | 160GB | 10Gbps / 32TB | 200Mbps 不限量 | US$49.9／月 | [ 看 T1 MEDIUM 方案](https://www.dmit.io/aff.php?aff=12046) |
| T1.LARGE | 8 核 | 16GB | 320GB | 10Gbps / 64TB | 500Mbps 不限量 | US$99.9／月 | [ 查看 T1 LARGE](https://www.dmit.io/aff.php?aff=12046) |
| T1.GIANT | 8 核 | 24GB | 640GB | 10Gbps / 128TB | 1Gbps 不限量 | US$199.9／月 | [ 看 T1 GIANT 配置](https://www.dmit.io/aff.php?aff=12046) |

## 香港 HKG.Pro 全套餐

香港的價值只有一個字：近。三網回程經香港 CTG 接國內 CN2 GIA，全系 1Gbps 頻寬，價格也是全站最高的一條線。常規產品已升級到 AN5 平台，部分評測站上仍留有舊 AS3 報價（例如 MINI 標 US$126.9），差別主要來自平台世代。

| 方案 | CPU | 記憶體 | 硬碟 | 頻寬／月流量 | 月付價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- |
| HKG.Pro.TINY | 1 核 | 1GB | 20GB | 1Gbps / 500GB | US$39.90 | [ 看香港 TINY 價格](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.STARTER | 1 核 | 2GB | 40GB | 1Gbps / 1TB | US$79.90 | [ 查看香港 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MINI | 2 核 | 2GB | 80GB | 1Gbps / 1.5TB | US$149.90 | [ 前往選購 HKG MINI](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MICRO | 2 核 | 4GB | 160GB | 1Gbps / 2TB | US$159.90 | [ 看香港 MICRO](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.MEDIUM | 4 核 | 4GB | 160GB | 1Gbps / 2.5TB | US$180.00 | [ 查看香港 MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.LARGE | 4 核 | 8GB | 320GB | 1Gbps / 3TB | US$240.00 | [ 看香港 LARGE 方案](https://www.dmit.io/aff.php?aff=12046) |
| HKG.Pro.GIANT | 8 核 | 16GB | 640GB | 1Gbps / 6TB | US$500.00 | [ 前往訂購 HKG GIANT](https://www.dmit.io/aff.php?aff=12046) |

香港 Pro 另外會不定期上架特價年付機型（曾出現 HKG.Pro.MongKok US$149.9／年、HKG.Pro.TsuenWan US$259.9／年）。這類機器數量少、下架快，看到有貨基本就該決定。

## 東京 TYO.Pro 全套餐

東京的定位是「延遲介於香港和洛杉磯之間，但帶日本原生 IP 的價值」。回程走 CN2 GIA，去程另外接 9929 與 CMI。這裡要提醒一句：東京 Pro 的檔位規格與價格在近期調整過，一些評測站上還留著 STARTER US$39.9、MINI US$79.9 的舊報價，目前官網與多數 2026 年資料顯示的是下面這組。

| 方案 | CPU | 記憶體 | 硬碟 | 頻寬／月流量 | 月付價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- |
| TYO.Pro.TINY | 1 核 | 1GB | 20GB | 1Gbps / 500GB | US$21.90 | [ 看東京 TINY 價格](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.STARTER | 1 核 | 2GB | 40GB | 1Gbps / 1TB | US$45.90 | [ 查看東京 STARTER](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.MINI | 2 核 | 2GB | 60GB | 1Gbps / 2TB | US$89.90 | [ 前往選購 TYO MINI](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.MICRO | 2–4 核 | 4GB | 80GB | 1Gbps / 4TB | US$189.90 | [ 看東京 MICRO](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.MEDIUM | 4 核 | 8GB | 160GB | 1Gbps / 5TB | US$320.90 | [ 查看東京 MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.LARGE | 8 核 | 16GB | 320GB | 1Gbps / 8TB | US$429.90 | [ 看東京 LARGE 方案](https://www.dmit.io/aff.php?aff=12046) |
| TYO.Pro.GIANT | 8 核 | 24GB | 640GB | 1Gbps / 15TB | US$799.90 | [ 前往訂購 TYO GIANT](https://www.dmit.io/aff.php?aff=12046) |

東京 Pro 的流量政策跟洛杉磯不一樣：流量用盡後是暫停服務，不是降速繼續跑。

## AS3 和 AN5 差在哪，值不值得加錢

DMIT 現在把平台分成兩個世代，這件事比多數人以為的重要。

- **AS3**：AMD EPYC 7003 系列，Geekbench 5 單核約 1000 分等級。定位入門，洛杉磯有 1 核 1GB 的起售檔。
- **AN5**：AMD EPYC 9005 系列，單核約 1900 分等級，搭 DDR5。定位高階，同規格價格比 AS3 貴約 20–30%。

關鍵在於：**同一個型號，AS3 和 AN5 的線路類型與其他配置是一樣的**。差的就是 CPU 算力。如果你只是跑網站、代理、小型 API，AS3 完全夠用；要跑資料庫、編譯、需要長期吃 CPU 的場景，AN5 那個差距才有意義。

香港 Pro 目前常規產品已經全面轉到 AN5，洛杉磯則是 AS3 與 AN5 並行，價差明顯。

## 優惠碼：哪些有機會生效，哪些別等了

DMIT 的優惠碼是分產品線、分付款週期給的，隨便填一個基本不會生效。整理目前流通性較高、且與多家資訊站描述吻合的幾組：

- `202510_HKG_TYO_PRO_20OFF_RECURRING`：香港 Pro、東京 Pro，季付及以上享 8 折，循環折扣
- `202510_HKG_TYO_T1_30OFF_RECURRING`：香港 T1、東京 T1，季付及以上享 7 折，循環折扣（不含 WEE）
- `2025-XMAS-LAX-PRO-EB-ANNUALLY-STARTER-AND-HIGHER-15OFF-RECURRING`：洛杉磯 Pro／EB 年付 STARTER 以上，15% 折扣加 10% 返現

有兩件事要清楚。第一，**入門機型是沒有任何優惠碼的**，T1.WEE、T1.TINY、Pro.TINY 這類常年原價，官方立場就是這樣，能以原價買到有貨的入門款已經算不錯。第二，帶年份的節日碼（2025 系列）大概率已過期，看到別人分享請先驗證。

結帳流程是：選好配置與週期 → 在優惠碼欄位填入 → 點 Validate Code 驗證 → 確認折扣真的生效再去付款。不要看到代碼就直接結帳。

想直接看目前還有哪些機型在售，可以 [👉 前往 DMIT 官網確認庫存與現行優惠](https://www.dmit.io/aff.php?aff=12046)。

## 付款、換 IP 與幾個實際會遇到的問題

**付款方式**對中國用戶算友善：支付寶、微信支付、PayPal、信用卡都收，也有中文客服。至少不用為了買一台 VPS 去折騰外幣卡。

**更換 IP**：符合條件時每 15 天可免費換一次 IPv4，條件大致是實例已開通滿 7 天、距上次換 IP 至少 15 天、ICMP 與全端口 TCP 都不可達、且剩餘服務期不少於 7 天。不符合免費條件的情況可以付費換 IP，費用依官網當下規則。

**流媒體解鎖**：多篇實測顯示洛杉磯、香港、東京多數套餐可以解鎖 Netflix、YouTube、TikTok 這類服務，IP 也多數是原生 IP。但這取決於你拿到哪個 IP 段，官方不做保證——東京 EB 的實測裡就出現過 Disney+ 被判定封鎖的情況。

**退款**：網上普遍引述原則是 3 天內可申請全額退款（流量使用不超過 30GB）、30 天內按剩餘時長或流量部分退款。這種條款會改，下單前建議自己看一眼官網政策。

**是否超售**：官方說明裡明確強調不超售，這也是它在評測圈被反覆提到的點。便宜的 VPS 靠超賣壓成本，DMIT 走的是相反的路，代價就是你看到的那個價格。

## 該買哪一個：按場景對號入座

- **只想最低成本試一下 DMIT 的品質**：洛杉磯 T1.WEE，US$36.9／年，四核心頻寬起步，用來建站、跑腳本、做監控都夠。
- **訪客主要在中國大陸、預算普通**：洛杉磯 Pro.TINY（US$10.90／月）或 Pro.Pocket（US$16.90／月）。要是你的用戶以移動、聯通為主，換成同價的 EB 版本，流量還多一倍。
- **要正式跑業務、在意晚高峰穩定性**：洛杉磯 Pro.STARTER 以上，或直接上香港 Pro。
- **對延遲敏感、預算不是問題**：香港 Pro.TINY 起，US$39.90／月。40ms 級別的延遲，洛杉磯給不了。
- **需要日本 IP**：東京 Pro.TINY US$21.90／月起；純落地、不看回國速度就選東京 T1。

DMIT 這家服務商的實際情況就是這樣：硬體不是它的賣點，價格也不算好看，真正讓人掏錢的是那幾條線路和它自己控頻寬這件事。如果你的問題是「便宜的伺服器晚高峰就廢」，那多付的錢是有對應東西的；如果你只需要一台跑海外業務的普通 VPS，T1 那一檔就別再往上看，Pro 對你沒有任何額外價值。
