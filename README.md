<img width="865" height="389" alt="image" src="https://github.com/user-attachments/assets/42354dcc-46f0-4eb4-8b01-ff24e82a4653" /># 軟體測試作業 - 存貨系統測試 (Inventory App Testing)

**學號：** B11309058
**GitHub 專案連結：** [貼上你的 GitHub Repository 網址]

---

## 🚀 如何執行測試 (測試案例說明)

本作業完成了三個指定要求的測試，請在 Android Studio 中開啟對應檔案，點擊行號旁的綠色箭頭 (▶️) 執行：

### 要求 1：Room 資料庫靜默忽略測試
* **測試檔案：** `ItemDaoTest.kt`
* **測試名稱：** `daoInsert_duplicateId_ignoresSecondItem()`
* **測試目的：** 驗證當插入兩筆相同 ID 的資料時，Room 的 `@Insert(onConflict = OnConflictStrategy.IGNORE)` 會靜默忽略第二筆，不丟出例外且保留第一筆資料。

### 要求 2：ViewModel 單元測試
* **測試檔案：** `ItemDetailsViewModelTest.kt`
* **測試目的：** 使用 MockK 模擬 Repository，驗證 ViewModel 的商業邏輯：
    1. `reduceQuantityByOne when quantity gt 0...`: 數量 > 0 時，正確呼叫 `updateItem()` 並扣減數量。
    2. `reduceQuantityByOne when quantity is 0...`: 數量 = 0 時，不呼叫 `updateItem()`。
    3. `deleteItem should call...`: 正確呼叫 `deleteItem()` 並傳遞正確物件。

### 要求 3：自動化 UI 測試
* **測試檔案：** `InventoryUITest.kt`
* **測試名稱：** `addItem_isDisplayedInList()`
* **測試目的：** 啟動模擬器，自動導航至新增頁面，輸入指定學號與數量，並驗證儲存後資料有顯示在畫面上。
<img width="865" height="389" alt="image" src="https://github.com/user-attachments/assets/be09f3ae-c068-48f4-8332-e95eaa0de37f" />
