---
description: 若要建立新資料來源，請前往「對象資料>資料來源>新增」，並完成此處所述每個區段的步驟。 建立資料來源需要管理員許可權。
keywords: 資料來源；管理資料來源；audience manager資料來源
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 管理資料來源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# 跨渠道和解决方案一致地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 创建一个 [!UICONTROL Data Source] {#create-data-source}

若要建立新的 [!UICONTROL data source]，前往 **[!UICONTROL Audience Data > Data Sources > Add New]** 並完成此處所述每個區段的步驟。 需要管理員許可權才能建立 [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>另請參閱 [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options) 這些不同控制項的說明。

## [!UICONTROL Data Source] 详细信息 {#details}

若要完成 [!UICONTROL Data Source Details] 區段：

1. 為命名 [!UICONTROL data source].
1. *（可選）* 說明 [!UICONTROL data source]. 簡潔的說明可協助您定義 [!UICONTROL data source].
1. 提供 [!UICONTROL integration code]. 一般而言， [!UICONTROL integration codes] 是選用專案。 當您想要：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * 使用 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * 使用 [設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md).

1. 選擇 **[!UICONTROL ID Type]**. [!UICONTROL ID Type] 選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立 [!UICONTROL Profile Merge Rule])。 請注意，對於某些客戶，此選項會公開 **[!UICONTROL ID Definition]** 選項。

   >[!NOTE]
   >
   >對於已針對Audience Manager和Experience Platform布建的每個組織，即使您並未在兩個應用程式之間設定區段共用，當您建立跨裝置資料來源時，也應針對 [身分名稱空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) 以Experience Platform建立。

1. 選擇 **[!UICONTROL ID Definition]** 選項。 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[資料匯出控制](../features/data-export-controls.md) 是可套用至的選用分類規則 [!UICONTROL data source] 和 [!UICONTROL destination]. 它們可防止您將資料傳送至 [!UICONTROL destination] 當該動作違反資料隱私權或使用合約時。 如果您不使用，請略過本節 [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] 设置 {#settings}

這些設定會決定 [!UICONTROL data source] 會識別、使用和共用。 您也可以啟用傳入資料檔案的錯誤報告。 若要完成 [!UICONTROL Data Source Settings] 區段：

1. 選取 [!UICONTROL Data Source Setting] 核取方塊以套用選項至 [!UICONTROL data source].
2. 单击 **[!UICONTROL Save]**.

## 刪除資料來源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除 [!UICONTROL data source] 您不再需要的服務。

>[!NOTE]
>
>請注意下列限制：
>
>* 您無法刪除 [作用中對象或資料來源同步特徵](../features/traits/client-activity-synced-audience-traits.md).
>* 對於使用Adobe Analytics的客戶：Audience Manager不允許您刪除自動從以下專案建立的資料來源： [!DNL Analytics] 報表套裝。 使用 [核心服務](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) 以取消這些資料來源的對應。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 選取一或多個資料來源旁的核取方塊。
您可以使用 [!UICONTROL Search] 方塊找出所需的資料來源（如果您有長清單）。
1. 按一下  ![](assets/icon_trash.png)，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)

