# JO-DOIS 核心公式與運算式清單

### 1. 主流程：自動生成案卷流水號 (Title)
在「建立項目」的「標題 (Title)」中使用：
```text
concat('DEC-', utcNow('yyyyMMdd'), '-', triggerOutputs()?['body/resourceData/responseId'])

```

---

### 2. 主流程：文字估值轉數字 (EstimatedValue)

在「建立項目」的「估值」中使用：

```text
float(outputs('取得回應詳細資料')?['body/r8xxxx...'])

```

*(可直接在 Power Automate 運算式中輸入 `float()`，並在括號內點選動態內容「8. 有關饋贈/利益的估值/價值」)*

---

### 3. 主流程：OneDrive 附件取得完整路徑

在「使用路徑取得檔案內容」的「檔案路徑 (File Path)」中使用：

```text
/Apps/Microsoft Forms/接受饋贈利益於賭博活動中獲得利益申報表 (HRF-031)/問題/@{items('Apply_to_each')?['name']}

```

---

### 4. 子流程：觸發條件防禦公式 (Trigger Conditions)

在子流程「建立或修改項目時」的「設定 ➔ 觸發程序條件」中使用，徹底杜絕無窮迴圈：

```text
@and(equals(triggerOutputs()?['body/OData__x6d41__x7a0b__x72c0__x614b/Value'], '已完成歸檔'), not(equals(triggerOutputs()?['body/OData__x7533__x5831__x4eba__x78ba/Value'], '申報人已確認')))

```

---

### 5. 子流程：香港標準時間戳記轉換 (HKT Timestamp)

在子流程「更新項目」的「申報人確認日期」中使用：

```text
convertTimeZone(utcNow(), 'UTC', 'China Standard Time')
