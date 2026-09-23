# 企業防貪合規與內部審計對照規範 (Compliance & Audit Mapping)

## 一、 法律合規基準 (Legal Basis: POBO Cap. 201)

依據香港法例第 201 章《防止賄賂條例》（Prevention of Bribery Ordinance, Cap. 201）第 9 條（代理人的貪污交易）：
* 僱員在未經主事者（僱主／董事會）許可下，因其職務關係索取或接受利益，即屬違法。
* 利益包括金錢、禮物、貸款、佣金、職位、合約、服務或優待等。

**JO-DOIS 系統的法律防禦核心**：
將原本「被動接受後口頭通報」轉換為「事前／即時之法定數位揭露」，並取得主事者（董事經理）的明確書面／數位處置批示，使利益處置具備不可撤銷的合規抗辯依據。

---

## 二、 ICAC 廉政指引與系統功能映射表 (ICAC Best Practice Mapping)

| ICAC 企業誠信治理建議 | 傳統紙本痛點 (Paper-based Flaws) | JO-DOIS 數位化控制機制 (Digital Control) |
|---|---|---|
| **及時申報原則 (Prompt Reporting)** | 表單層層傳遞耗時數週，物品常已被使用或消耗。 | Forms 即時提交，Power Automate 秒級派發 HR 初審與 MD 批示。 |
| **客觀透明估值 (Objective Valuation)** | 員工隨意手寫金額，無物證比對。 | 強制上傳實物相片及單據，由 HR 查驗公允市價後呈交。 |
| **多級權限分離 (Segregation of Duties)** | 部門主管私下核可，缺乏人事與最高層複審。 | 嚴格執行「HR 合規審查 ➔ 董事經理法定批示 ➔ HR 執行」之三權分立。 |
| **處置結果閉環 (Disposal Verification)** | 管理層批示退回或義贈，但無物理落實追蹤。 | HR 必須在 SharePoint 登錄處置流水帳，並變更狀態觸發閉環。 |
| **雙向確認存證 (Mutual Sign-off)** | 員工聲稱不知情處置要求，引發勞資與法規爭議。 | 系統自動派發確認卡片，強制員工按掣確認並蓋印 HKT 時間戳記。 |

---

## 三、 審計追蹤軌跡規格 (Audit Trail Specifications)

1. **不可篡改性 (Tamper-evident)**：
   * 申報原始資料儲存於 SharePoint Online，一般員工無編輯清單權限。
   * 每次狀態變更與簽批意見均由 Power Automate 系統帳號寫入，保留修改歷史。
2. **完整法律時間戳記 (Legally Binding Timestamps)**：
   * 提交時間：由 Microsoft Forms 記錄。
   * HR 初審時間：記錄於 Approvals 系統日誌。
   * MD 批示時間：記錄於 Approvals 系統日誌。
   * 申報人閉環時間：以香港標準時間（HKT, UTC+8）寫入 `DeclarantAckDate`。
