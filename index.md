# WTS-DE-A2｜LLM Wiki 知識總索引

> 版本：v1.3（WBS-03.3 全庫品質檢查）｜狀態：**DE-W01～DE-W07 均已完成 v1.0 教學稿及 claim-to-page 映射；獨立語言審校與 Graph 檢索測試未完成**

## 專案定位

德語 A2 學習知識庫；由七份課次 PDF 的來源盤點建立主題導覽，後續以原創教學摘要、跨文章關聯及可追溯的來源映射，支援 HTML 教學簡報。

## 內容成熟度

- **DE-W01**：v1.0 教學內容已建立（時間與日期；仍待正式語言審校）。
- **DE-W03**：v1.0 教學內容已建立（預約、改期、取消；仍待正式語言審校）。
- **DE-W02、DE-W04**：v1.0 教學內容已建立（情態動詞／禮貌請求；待獨立審校）。
- **DE-W05、DE-W06、DE-W07**：v1.0 教學內容已建立（城市交通／服務購物／邀請回覆；待獨立德語審校）。

## 主題檢索入口

| Wiki ID | 知識文章 | 學習目標 | 核心來源 |
|---|---|---|---|
| [DE-W01｜Zeit und Datum｜時間與日期](DE-W01.md) | Zeit und Datum | 能以德語說明事件日期、時間、先後與持續期間 | DE-SRC-001, DE-SRC-005, DE-SRC-007 |
| [DE-W02｜Modalverben｜情態動詞與句型](DE-W02.md) | Modalverben | 能區分必須、允許與轉述建議，並掌握主要子句語序 | DE-SRC-002, DE-SRC-003 |
| [DE-W03｜Terminvereinbarung｜預約、改期與取消](DE-W03.md) | Terminvereinbarung | 能用合宜句型完成預約、改期、取消，並確認日期與時間 | DE-SRC-003, DE-SRC-005, DE-SRC-007 |
| [DE-W04｜Höfliche Bitten｜禮貌詢問與請求](DE-W04.md) | Höfliche Bitten | 能區分直接命令、禮貌要求與尋求解釋 | DE-SRC-002, DE-SRC-005, DE-SRC-003 |
| [DE-W05｜Stadt und Verkehr｜城市交通與位置](DE-W05.md) | Stadt und Verkehr | 能詢問位置、方向、交通方式與車站資訊 | DE-SRC-002, DE-SRC-004 |
| [DE-W06｜Service und Einkaufen｜購物與服務](DE-W06.md) | Service und Einkaufen | 能詢問維修、商品款式、尺寸、價格與偏好 | DE-SRC-005, DE-SRC-006 |
| [DE-W07｜Einladungen und Antworten｜邀請與回覆](DE-W07.md) | Einladungen und Antworten | 能書寫邀請、接受或婉拒，說明日期及理由 | DE-SRC-007, DE-SRC-003 |

## 建議教學路徑（HTML 簡報）

1. [DE-W01 時間與日期](DE-W01.md)：先學習日期、時間與期間。
2. [DE-W02 情態動詞](DE-W02.md)：理解必須、允許與建議。
3. [DE-W04 禮貌請求](DE-W04.md)：練習正確的請求語氣。
4. [DE-W03 預約、改期、取消](DE-W03.md)：完成主要情境任務。
5. [DE-W07 邀請與回覆](DE-W07.md)：延伸至接受、婉拒及說明理由。

補充：[DE-W05 城市交通](DE-W05.md) 為前往預約地點的情境；[DE-W06 購物與服務](DE-W06.md) 為其他服務對話。

## 查詢路由（供 AI / 人員檢索）

| 想問的問題 | 先查詢 | 再交叉查詢 |
|---|---|---|
| 怎麼說日期與多久以前？ | DE-W01 | DE-W07 |
| müssen、dürfen、sollen 有何差別？ | DE-W02 | DE-W03 |
| 如何預約、改期、取消？ | DE-W03 | DE-W01、DE-W04 |
| 如何禮貌請求對方協助？ | DE-W04 | DE-W02、DE-W06 |
| 如何問路、搭車、轉車？ | DE-W05 | DE-W01 |
| 如何詢問店員商品尺寸、維修？ | DE-W06 | DE-W04 |
| 如何邀請或婉拒？ | DE-W07 | DE-W01、DE-W03 |

## 來源與證據

- [來源清單與版權限制](../sources/catalog.md)
- [來源—Wiki 對照表](../sources/source-map.md)
- [WBS-03.1 驗收紀錄](../evidence/WBS-03.1-check.md)

## 入庫政策

- 原始教材 PDF 留在私有資料層；本壓縮包**不含**出版社 PDF。
- DE-W01～DE-W07 均已建立原創教學內容和 claim-to-page 來源映射；仍需逐篇獨立審校，亦未宣稱已完成自動檢索或 Graph 測試。
- AI 生成的德語例句須經文法、語義和難度 QC；沒有提供的音檔不可推定聽力答案。
- 本批次已核對 DE-W02、DE-W04 對應來源頁面，仍須獨立語言審校及後續實作檢索。

## 第三批補充證據

- [第三批內容檢查紀錄](../evidence/WBS-03.2-batch3-check.md)
- DE-W05、DE-W06、DE-W07 均有 W05/W06/W07-C01～C05 的來源頁碼表及原創練習。

## WBS-03.3 品質驗收結果

- [全庫品質驗證報告](../evidence/WBS-03.3-QC-report.md)
- 第二輪 AI 輔助語言、語義及跨篇校對已執行；母語教師獨立審校仍列為 PENDING。
- 語言教材來源屬同系列不同課次，不宣稱七個獨立出版來源。
