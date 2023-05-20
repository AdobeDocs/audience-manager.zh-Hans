---
description: 個別特徵的詳細資訊頁面提供特徵名稱、ID、效能測量結果、定義特徵的運算式、其所屬區段及特徵稽核記錄檔等資訊的總覽。 若要檢視這些詳細資訊，請前往「對象資料>特徵」 ，然後按一下您要使用之特徵的名稱。
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: 特征详细信息页面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: 身分型別劃分、身分劃分、對象身分報告、跨裝置、跨裝置ID、裝置ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] 詳細資訊頁面 {#trait-details-page}

個人的詳細資訊頁面 [!UICONTROL trait] 提供以下專案的概觀： [!UICONTROL trait] 詳細資訊，例如 [!UICONTROL trait] 名稱、ID、效能測量結果、定義 [!UICONTROL trait]，它所屬的區段，以及 [!UICONTROL trait] 稽核記錄。 若要檢視這些詳細資訊，請前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** 並按一下 [!UICONTROL trait] 您想要搭配使用。

## [!UICONTROL Trait] 管理工具 {#trait-management-tools}

頂端 [!UICONTROL trait] 詳細資訊頁面內建了可用來管理您的專案的工具。 [!UICONTROL traits]：

1. **[!UICONTROL Add New]**：使用此選項來建立新的 [!UICONTROL rule-based]， [!UICONTROL algorithmic]，或 [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**：使用此選項可變更目前的設定 [!UICONTROL trait].
3. **[!UICONTROL Delete]**：使用此選項可移除目前的 [!UICONTROL trait] 來自您的Audience Manager帳戶。
4. **[!UICONTROL Marketplace Recommendations]**：使用此選項尋找類似專案 [!UICONTROL traits] 至您正在檢視的專案，從 [!UICONTROL Audience Marketplace] 您尚未訂閱的資料費用。 另請參閱 [適用於資料購買者的Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 以瞭解如何導覽 [!UICONTROL Marketplace] 並尋找類似的特徵。

![基本特徵資訊](assets/basic-trait-information.png)

## [!UICONTROL Trait] 信息 {#basics}

此 [!UICONTROL Trait Information] 區段顯示您在建置時完成的必要和選用欄位的詳細資訊 [!UICONTROL trait]. 這包括 [!UICONTROL trait] 型別， [!UICONTROL trait] ID、說明、 [!UICONTROL data source]和其他中繼資料。 這些詳細資料會因以下因素而異 [!UICONTROL trait] 型別([!UICONTROL folder]， [!UICONTROL onboarded]，或 [!UICONTROL rule-based])。

## [!UICONTROL Trait Graph] {#trait-graph}

此 [!UICONTROL Trait Graph] 提供您選取之效能測量結果的概覽 [!UICONTROL trait]. 將游標停留在趨勢線上，即可檢視所選專案的其他資料 [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] 代表新增此專案的不重複使用者人數 [!UICONTROL trait] 至指定時間範圍內的設定檔。 此 [!UICONTROL Total Trait Population] 表示目前符合此資格的不重複使用者人數 [!UICONTROL trait].

對象 [!UICONTROL rule-based traits]， [!UICONTROL trait] 符合資格限定會即時進行，因為使用者符合 [!UICONTROL trait] 在瀏覽器中。

對象 [!UICONTROL onboarded traits]， [!UICONTROL trait] 限定會在處理傳入檔案後發生，即傳入檔案為 [已饋送至Audience Manager](../../faq/faq-inbound-data-ingestion.md) 這時 [!UICONTROL trait] 符合資格。

此 [!UICONTROL Trait Graph] 顯示下列資訊：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**：選取此選項可檢視以下專案的結果： [!UICONTROL traits] 正在收集已驗證設定檔的資料。 選取此選項時，您只會在 [!UICONTROL Cross-Device ID] 報告，且下不會出現任何資料 [!UICONTROL Device ID] 報告。
   * **[!UICONTROL Device ID]**：選取此選項可檢視以下專案的結果： [!UICONTROL traits] 正在收集裝置設定檔的資料。 選取此選項時，您只會在 [!UICONTROL Device ID] 報告，且下不會出現任何資料 [!UICONTROL Cross-Device ID] 報告。

      ![特徵圖](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**：新增此專案的不重複使用者計數 [!UICONTROL trait] 至指定時間範圍內的設定檔。
* **[!UICONTROL Total Trait Population]**：目前符合資格的不重複使用者人數 [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**：前三個專案顯示前三個 [!UICONTROL cross-device data sources] 擁有符合「 」資格的最高母體計數 [!UICONTROL trait]，以遞減順序排列。 第四個專案會顯示其他所有專案的總和 [!DNL DPUUIDs] ([!DNL CRM IDs])符合 [!UICONTROL trait]，來自 [!UICONTROL cross-device data sources] 不在前三名的專案。 此報表僅會在您選取 [!UICONTROL Cross-device ID] 在 [!UICONTROL Show Results By] 頁面右上方的下拉式功能表。 預設的下拉式清單選項為 [!UICONTROL Device ID]，此報告不會顯示。

   ![特徵圖](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager只會顯示 [!UICONTROL Identity Type Breakdown] 報告（若您有） [!UICONTROL cross-device] ID符合 [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]表达式 {#trait-expression}

此 [!UICONTROL Trait Expression] 區段會向您顯示使用者必須符合哪些條件才符合 [!UICONTROL trait]. 這些規則是在以下情況下設定： [建立或編輯特徵](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] 区段 {#trait-segments}

此 [!UICONTROL Segments with this Trait] 區段會列出所有選取的區段 [!UICONTROL trait] 屬於。 您可以按一下區段名稱來檢視有關該區段的詳細資訊。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 稽核/歷史記錄記錄 {#trait-audit-history}

對象 [!UICONTROL rule-based] 和 [!UICONTROL onboarded traits]，則 [!UICONTROL Trait Expression Change History] 顯示對進行的最後10項變更 [!UICONTROL trait] 運算式規則及建立這些規則的人員。 若您的 [!UICONTROL trait] 超過10項變更，請按一下 **[!UICONTROL Export to CSV]** 以下載整個稽核記錄。 稽核記錄不可用於 [!UICONTROL folder] 或 [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] 在 [!UICONTROL By User] 欄表示該使用者的帳戶已刪除。

![](assets/traitHistory.png)
