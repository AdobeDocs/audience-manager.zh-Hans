---
description: 想要從Audience Manager內購買第三方資料的資料購買者概觀和工作流程
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: 面向数据购买者的 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] 適用於資料購買者 {#audience-marketplace-for-data-buyers}

資料購買者若想從內購買協力廠商資料，適用的概觀和工作流程 [!DNL Audience Manager].

>[!NOTE]
>[角色型許可權](../../../reporting/reports-dashboard.md) 控制對的存取 [!UICONTROL Audience Marketplace] 功能。
>
>* 管理員可以建立資料摘要、管理訂閱者，以及訂閱資料摘要。
>* 使用者只能搜尋和檢視摘要。


## 此 [!UICONTROL Marketplace]：關於 {#about-marketplace}

此 [!UICONTROL Marketplace] 是 [!DNL Audience Manager] 適用於資料購買者的功能，其中列出您可以訂閱的資料摘要。 它列出統一費率， [!DNL CPM]和私人資料摘要。 這些摘要是由使用的協力廠商所提供 [!DNL Audience Manager] 以銷售資料。

在 [!UICONTROL Marketplace]，報告工具可讓您追蹤摘要使用情形，以及 [!UICONTROL traits] 以及訂閱資料摘要中的受眾。 最後，使用 [!UICONTROL Audience Marketplace]， [!DNL Adobe] 會處理發票和費用支付（不過您必須在訂閱時自行報告使用狀況） [!DNL CPM] 摘要)。 這些功能可讓您找到有效的資料來源，而不會浪費時間尋找資料提供者。

>[!TIP]
>
>使用 **[AdobeAudience Finder](https://www.adobe-audience-finder.com/)** 以尋找您可以訂閱的高品質資料摘要。 然後，返回 [!DNL Audience Manager] 使用者介面或使用 [Audience Marketplace購買者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) 以訂閱您找到的摘要。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

此 [!UICONTROL Marketplace] 清單包含您可以排序和搜尋的資訊，以尋找適合您的資料摘要。 中的專案 [!UICONTROL Marketplace] 購買者清單包括：

* **[!UICONTROL Search]**：依名稱或文字說明尋找資料摘要。
* **[!UICONTROL Similar Traits]**：顯示類似專案的數量 [!UICONTROL traits] 從資料摘要擷取。 此欄會在您輸入 [!UICONTROL trait] 或 [!UICONTROL segment] 在中篩選依據 **[!UICONTROL Similarity To]** 區段。
* **[!UICONTROL Name]**：資料摘要的名稱。
* **[!UICONTROL Description]**：資料摘要內容的相關資訊。
* **[!UICONTROL Provider]**：資料提供者的名稱。
* **[!UICONTROL Traits]**：的數量 [!UICONTROL traits] 在資料摘要中。
* **[!UICONTROL 30 Day Provider Unique Users]**：過去30天內檢視的不重複使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]**：您的帳戶中與提供者帳戶中的使用者重疊的使用者數量。
* **[!UICONTROL Feed Overlap]**：以百分比顯示的30天重疊不重複值，計算方式為：資料購買者30天重疊不重複/資料購買者30天不重複) x 100。
* **[!UICONTROL Private Feeds]**：請參閱 [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**：您與資料提供者之間的訂閱數目。

 

若要輕鬆找到符合您需求的最佳資料摘要，請使用 [!UICONTROL Marketplace] 頁面：

* **[!UICONTROL Similarity To]**：根據資料摘要與以下任一專案的相似性來篩選資料摘要： [!UICONTROL trait] 或 [!UICONTROL segment] 您選擇的。 輸入 [!UICONTROL trait] 或區段來比較，您可以使用 [!UICONTROL trait] 或 [!UICONTROL segment] ID或其個別名稱。
* **[!UICONTROL Similarity Cutoff]**：拖曳滑桿，根據資料摘要的相似性來篩選資料摘要 [!UICONTROL traits] 與您選取的相同 [!UICONTROL trait] 或 [!UICONTROL segment]. 若要深入瞭解 [!UICONTROL trait] 相似性分數，請參閱 [特徵相似度分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**：根據您的訂閱狀態篩選資料摘要。
* **[!UICONTROL Plan Use Case]**：根據資料摘要支援的使用案例來篩選資料摘要： **[!UICONTROL Activation]**， **[!UICONTROL Segments and Overlap]**、和 **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**：根據資料摘要的定價型別來篩選資料摘要。

## 尋找類似專案 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 提供您尋找 [!UICONTROL traits] 根據與您現有資料摘要的相似性，從各種資料摘要中選取 [!UICONTROL traits] 或區段。 以下是其操作方式：

1. 前往 **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. 使用 **[!UICONTROL Similarity To]** 選擇器，選擇是否根據 [!UICONTROL trait] 或 [!UICONTROL segment]. 您可以根據 [!UICONTROL trait]/[!UICONTROL segment] id或名稱。 搜尋方塊會根據您的輸入自動顯示相關建議。
3. 識別您要作為篩選依據的特徵或區段後，在建議清單中按一下該特徵或區段。
4. 若要縮小結果範圍，請使用 **[!UICONTROL Similarity Cutoff]** 滑桿，從較不相似的滑桿移動 [!UICONTROL traits]，變更為更類似的變數。

篩選完成後，您會在結果頁面中看到新欄： **[!UICONTROL Similar Traits]**. 此欄顯示類似專案的數目 [!UICONTROL traits] 從符合篩選條件的每個資料摘要，轉換為您篩選的資料摘要。

若要檢視類似特徵的完整清單，請按一下 **[!UICONTROL Similar Traits]** 欄。

>[!NOTE]
>
> Audience Marketplace會顯示前500個類似專案 [!UICONTROL trait] 來自所有資料摘要的結果。

觀看以下影片，全面瞭解如何尋找類似專案 [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 专用数据信息源 {#private-data-feeds}

在 [!UICONTROL Marketplace] 清單，有時為提供者的名稱和 [!UICONTROL trait] 資料會標籤為私人。 這表示 [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md). 私人資料摘要可讓賣家限制買家存取其資料。 當賣家提供特別優惠、折扣，或當隱私權和存取控制對他們來說很重要時，他們可以將摘要設為私人。 如果您想要存取私人摘要，身為買家，您必須傳送訂閱要求給賣家。 另請參閱 [訂閱私人資料摘要](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 以取得詳細資訊。

>[!MORELIKETHIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

