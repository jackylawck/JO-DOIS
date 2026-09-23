# JO_Gift_Declarations 清單規格書 (SharePoint List Schema)

- **清單名稱**：`JO_Gift_Declarations`
- **網站 URL**：`https://jumboorient.sharepoint.com/sites/hr`

| 欄位顯示名稱 | 內部名稱 / 類型 | 必填 | 選項值 / 格式 / 預設值 | 業務說明 |
|---|---|:---:|---|---|
| **標題** | `Title` (單行文字) | 是 | 自動生成公式：`DEC-YYYYMMDD-ID` | 系統案件唯一流水號 |
| **申報同事** | `DeclarantName` (單行文字) | 是 | 文字 | 申報人姓名 |
| **申報人電郵** | `DeclarantEmail` (單行文字) | 是 | 文字 / 電子郵件 | 提交者企業郵箱 |
| **所屬組別** | `Department` (單行文字/選擇) | 是 | 文字 | 所屬部門或組別 |
| **提供者姓名及職銜** | `ProviderNameTitle` (單行文字) | 是 | 文字 | 餽贈人身份 |
| **提供者公司** | `ProviderCompany` (單行文字) | 是 | 文字 | 餽贈人所屬機構 |
| **業務關係** | `BusinessRelationship` (單行文字) | 是 | 文字 | 雙方業務往來性質 |
| **獲贈場合** | `Occasion` (單行文字) | 是 | 文字 | 接受餽贈場合/時節 |
| **饋贈利益詳情** | `GiftDetails` (單行文字/多行文字) | 是 | 文字 | 物品名稱、品牌、數量等 |
| **估值** | `EstimatedValue` (數字) | 是 | 數字 (小數點位數: 0 或 2) | 物品估算市場價值 (HKD) |
| **流程狀態** | `Status` (選擇) | 是 | 選項：`待HR初審`, `待董事經理批核`, `待HR執行處置`, `已完成歸檔`, `HR退回申報`<br>預設值：`待HR初審` | 流程生命週期狀態 |
| **HR初審結果** | `HRReviewResult` (單行文字) | 否 | `Approve` / `Reject` | 乙部審查結論 |
| **HR初審備註** | `HRReviewComments` (多行文字) | 否 | 文字 | HR 審核意見 |
| **董事經理批示** | `MDDecision` (單行文字/選擇) | 否 | 7 個法定處置選項之一 | 丙部決策結論 |
| **董事經理備註** | `MDComments` (多行文字) | 否 | 文字 | 董事經理附加指示 |
| **丁部處置落實記錄** | `DisposalActionLog` (多行文字) | 否 | 文字 | 實體處置詳情（拍賣/分享/退回等） |
| **申報人確認狀態** | `DeclarantAckStatus` (選擇) | 否 | 選項：`待申報人確認`, `申報人已確認`<br>預設值：`待申報人確認` | 丁部閉環簽署狀態 |
| **申報人確認日期** | `DeclarantAckDate` (日期和時間) | 否 | 包含時間：是 | 員工數位按掣簽核之時間戳記 |
