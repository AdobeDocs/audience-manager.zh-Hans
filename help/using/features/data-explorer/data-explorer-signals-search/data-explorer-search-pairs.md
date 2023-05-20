---
description: 根據各自的索引鍵值配對，搜尋一或多個訊號。
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# 依索引鍵值配對搜尋訊號 {#search-signals-by-key-value-pairs}

根據各自的索引鍵值配對，搜尋一或多個訊號。
若要搜尋多個訊號，請按一下 ![新增](assets/icon_add.png) 按鈕。 輸入您要搜尋的索引鍵值配對，然後使用下列篩選條件來縮小結果的範圍。

* **訊號狀態**：搜尋特徵中包含的訊號、未使用的訊號或兩者。
* **檢視記錄**：選取搜尋已接收訊號的時間間隔。
* **最小計數**：僅顯示具有所選間隔中指定最小總數的訊號。

>[!IMPORTANT]
>
>為了提供簡化的使用者體驗，索引鍵/值配對搜尋結果會根據資料取樣。 另請參閱 [資料取樣和錯誤率](/help/using/reporting/report-sampling.md) 以取得如何進行 [!DNL Audience Manager] 使用資料取樣，以及比較索引鍵值搜尋與一般搜尋時，為何會出現細微結果差異。

使用多個索引鍵值配對搜尋訊號時， [!DNL Audience Manager] 使用邏輯 **和** 運運算元。 例如，假設您使用下列索引鍵值配對來執行搜尋：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜尋只會傳回符合約一次呼叫中全部三個篩選條件的結果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 從訊號搜尋中排除的訊號 {#excluded-signals}

Audience Manager使用的關鍵變數，前置詞為 `d_` 和 `h_` 字首未顯示於 [!UICONTROL Signals Search]. 另請參閱 [關鍵變數的前置詞要求](../../traits/trait-variable-prefixes.md) 以取得詳細資訊。

## 區分大小寫與搜尋自動完成 {#case-insensitivity}

索引鍵和值搜尋欄位區分大小寫。 關鍵搜尋欄位包含自動完成的建議。

![](assets/signal-search-suggestions.png)

假設 [!DNL Audience Manager] 收到下列訊號：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

當您輸入時 `product` 在「索引鍵搜尋」欄位中，您會收到 `productCategory` 和 `product`.

同樣地，當您搜尋 `product == PHONE`， [!UICONTROL Data Explorer] 只傳回以下專案的結果： `product == PHONE`.

回填特徵實現也區分大小寫。 包含具有機碼值組的訊號的特徵 `PRODUCT == SMARTPHONE` 不符合機碼值組的訊號資格 `product == smartphone`.
