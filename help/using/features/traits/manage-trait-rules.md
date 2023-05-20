---
description: 在特徵產生器中，運算式產生器可讓您建立和測試建立對象資格要求的規則。 規則由索引鍵值配對組成，例如「color == blue」或「price &gt； 100」。 比較運運算元建立索引鍵和值之間的關係。 布林值運算式決定規則群組之間的關係。
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: 管理特征规则
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# 管理特征规则 {#managing-trait-rules}

在 [!UICONTROL Trait Builder]，則 [!UICONTROL Expression Builder] 可讓您建立和測試建立對象資格要求的規則。 規則包含索引鍵值配對，例如 `color == blue` 或 `price > 100`. 比較運運算元建立索引鍵和值之間的關係。 [!DNL Boolean] 運算式決定規則群組之間的關係。

<!-- c_tb_rules.xml -->

## 說明的主要訊號規則功能

![](assets/manage-trait-rules.png)

1. 此 **[!UICONTROL Expression Builder]** 或 **[!UICONTROL Code View]** 索引標籤提供特徵中規則的概觀。 此 **[!UICONTROL Expression Builder]** 索引標籤可讓您建立包含欄位和下拉式功能表的規則。 此 **[!UICONTROL Code View]** 可讓您手動將這些運算式寫入程式碼來建立規則。 上圖顯示了一個由訊號組成的簡單特徵，該訊號會針對產品金鑰等於特定值的合格條件（在此例中為）評估資料 `color == "blue"`.

1. 本節中的欄位和控制項可讓您從索引鍵/值組建立訊號，並使用比較運運算元設定它們之間的關係。 索引鍵、運運算元和值為必填。
1. 此 [!UICONTROL Data Explorer Options] 可讓您回填訊號的特徵實現。

   >[!NOTE]
   >
   >此選項僅適用於 [!UICONTROL Data Explorer] 客戶。 如需詳細資訊，請聯絡您的Adobe顧問。

1. 本節會針對中定義的訊號，顯示過去7天之特徵實現的預估值 [!UICONTROL Expression Builder]，適用於回填和非回填特徵。

   >[!NOTE]
   >
   >此選項僅適用於 [!UICONTROL Data Explorer] 客戶。 如需詳細資訊，請聯絡您的Adobe顧問。

1. 測試欄位可讓您驗證訊號規則或 [!DNL URL]您想要在傳送資料給Audience Manager時使用。

## 建立特徵規則 {#create-trait-rule}

規則（或運算式）包含個別或機碼值組群組。 比較運運算元設定索引鍵/值配對之間的關係。 若要建立規則，請提供索引鍵、值、選取運運算元，然後按一下 **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

填妥以下欄位中的必填欄位： **[!UICONTROL Basic Information]** 區段 *早於* 建立特徵規則。

1. 展開 **[!UICONTROL Trait Expression]** 區段並輸入索引鍵和值名稱。 這會建立 *`signal`*.

   >[!NOTE]
   >
   >包含 `c_` 如果您的事件呼叫將資料傳送至，則為關鍵變數的前置詞（或任何其他命名慣例） [!DNL Audience Manager] 使用該語法。

1. 選取 [比較運運算元](../../features/traits/trait-comparison-operators.md) 從 **[!UICONTROL Operator]** 下拉式清單。 比較運運算元會評估訊號中元素之間的關係。

   >[!NOTE]
   >
   >此 [!DNL Boolean] [!UICONTROL OR] 運運算元建立多個訊號之間的關係 *範圍* 群組，無法變更。

1. 单击 **[!UICONTROL Add Rule]**. 已儲存的規則會顯示在資料輸入欄位上方的特徵工作區中。

### 示例 {#example-trait-rule}

在以下範例中，使用者已根據產品ID建立新特徵規則。 若要建置此規則，使用者已提供金鑰 `productkey` 連結至等於運運算元( `==`)至值 `2093`.

![](assets/tb_sample_rule1.png)

按一下 **[!UICONTROL Add Rule]** 儲存特徵並將特徵移入 [!UICONTROL Expression Builder] 工作區。

![](assets/tb_sample_rule2.png)

## 建立新的規則群組 {#create-rule-group}

此程式說明如何建立新的規則群組。

<!-- t_tb_new_rule_group.xml -->

特徵必須至少包含兩個規則，才能建立新規則群組。

1. 將游標移至要移動的規則上方，以反白該規則。
1. 暫留在醒目提示的規則邊框上。

   這會自動將規則與其目前群組分開，並將它移動到新群組中。

   >[!NOTE]
   >
   >如果您無意間移動規則，請將規則拖回其原始群組。

1. 選取 [!DNL Boolean] 運運算元([!UICONTROL AND]， [!UICONTROL OR]， [!UICONTROL AND NOT])，以設定規則群組之間的關係。

## 在群組之間移動規則 {#move-rules-between-groups}

若要移動規則，請按一下「 」，然後將其拖曳至其他群組。

## 編輯特徵 {#edit-trait}

此程式說明如何編輯特徵。

<!-- t_tb_edit.xml -->

1. 在 [!UICONTROL Traits] 儀表板，暫留在 **[!UICONTROL Actions]** 要編輯的特徵欄。 這會顯示特徵管理圖示。
1. 按一下鉛筆以編輯特徵。

   ![](assets/tb_edit_trait.png)

## 刪除特徵規則 {#delete-trait}

此程式說明如何刪除特徵規則。

<!-- t_tb_delete_rule.xml -->

1. 在 [!UICONTROL Traits] 儀表板，暫留在 [!UICONTROL Actions] 要編輯的特徵欄，然後按一下鉛筆圖示。 這會顯示特徵管理圖示。
1. 展開 [!UICONTROL Trait Expression] 區段。
1. 將游標停留在您要刪除的規則上，然後按一下X圖示。 規則會立即刪除。

>[!MORELIKETHIS]
>
>* [建立新的規則群組](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [建立特徵規則](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [刪除特徵規則](../../features/traits/manage-trait-rules.md#delete-trait)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

