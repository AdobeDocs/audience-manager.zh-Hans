---
description: URL目的地會從頁面對您的目的地進行畫素呼叫。 請依照這些指示，使用Destination Builder建立URL目的地。
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: 配置 URL 目标
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 3%

---

# 設定 [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] 從頁面對進行畫素呼叫 [!DNL destination]. 依照下列指示建立 [!DNL URL] [!DNL destination] 替換為 [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

若要建立新的 [!DNL URL] [!DNL destination]，前往 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成以下所述的章節。

## 基本信息 {#basic-info}

本節包含開始 [!DNL URL destination] 建立程式。 若要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 以公開控制項。
2. 為命名 [!DNL destination]. 避免使用縮寫和特殊字元。
3. *（可選）* 說明 [!DNL destination]. 簡潔的說明是定義或提供更多相關資訊的有效方式。 [!DNL destination].
4. 在 **[!UICONTROL Category]** 清單，選擇 **[!UICONTROL Custom]**.
5. 在 **[!UICONTROL Environment]** 清單中，選取要觸發的環境 [!DNL URL destination].
6. 在 **[!UICONTROL Type]** 清單，按一下 **[!UICONTROL URL]**.
7. *（可選）* 選取 **[!UICONTROL Auto-fill Destination Mapping]**. 选项包括：
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至 [!DNL destination].
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼，並將其傳送至目的地對應。 整合代碼是客戶建立及使用的唯一識別碼。 上限為255個字元。
8. 按一下 **[!UICONTROL Next]** 前往 [!UICONTROL Configuration] 設定或按一下 **[!UICONTROL Data Export Labels]** 將匯出控制項套用至 [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本節包含套用的選項 [資料匯出控制](../../features/data-export-controls.md) 至 [!DNL URL] 目的地。 如果您不使用資料匯出控制項，請略過此步驟。 若要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 以公開控制項。
2. 選取與套用至目的地的資料匯出控制對應的標籤(請參閱 [將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) 以取得詳細資訊)。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configure-base-data}

本節包含可讓您設定基底的選項 [!DNL URL] 和資料分隔符號傳入的 [!DNL URL] 字串。 此區段為選用。 若要完成本節：

1. 按一下 **[!UICONTROL Configuration]** 以公開控制項。
1. *（可選）* 選取 **[!UICONTROL Serialize]** 核取方塊。
這可讓您將區段傳送至 [!DNL destination] 循序進行，而非針對每個區段分別呼叫。 序列化有助於提高資料傳輸效率。 選取此核取方塊會顯示URL和分隔符號欄位。 如需詳細資訊，請參閱 [標準和序列索引鍵值配對](../../features/destinations/key-value-pairs.md).
1. 如果您選取 **[!UICONTROL Serialize]**，則您也必須設定URL和分隔符號欄位，如下所述。

| 字段 | 描述 |
|--- |--- |
| [!UICONTROL Base URL] | 標準的基本部分 `HTTP` [!DNL URL] 這不會改變。 此外，您需要將 `%ALIAS%`  [預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined) 在基本URL中。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 安全的基底部分 `HTTPS` [!DNL URL] 這不會改變。 此外，您需要將 `%ALIAS%`   [預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined) 在基本URL中。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 在中分隔區段變數的符號 [!DNL URL] 字串。 這通常是逗號或分號。 從您的目的地合作夥伴取得此資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

本節可讓您搜尋區段並將其新增至 [!UICONTROL destination]. 若要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 以公開控制項。
1. 在 **[!UICONTROL Search and Add Segments]** 方塊中，開始輸入區段名稱或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用區段的清單。
1. 按一下 **[!UICONTROL Add Selected Segments]** 當您找到要使用的區段時。 新增區段會開啟 [!UICONTROL Edit Mapping] 視窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供區段使用的機碼值組。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**：選擇開始和結束日期 [!DNL destination]. 如果結束日期為空白，則 [!DNL destination] 永不過期。
1. 单击 **[!UICONTROL Done]**.
