---
description: 如需Adobe Audience Manager ID的完整清單，請參閱本檔案。
keywords: DPID； DPUUID； CID； UUID； uuid； uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuuid， uuuid， uuuid， uuuid， uuuid， uuuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Audience Manager 中的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# 中的ID索引 [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager] 會使用多個ID來識別及管理您傳送給它的資料。 請參閱本文以取得以下專案的完整清單： [!DNL Audience Manager] ID，以及您應搭配使用的首碼範例。

## ID前置詞 {#prefixing}

雖然您可以藉由這些ID的獨立名稱來參照大部分ID，但其中大部分的ID旨在透過傳遞資料時搭配各種首碼使用 [!DNL DCS] 呼叫。 其中一些ID是由 [!DNL Audience Manager] 而使用者介面(UI)中也可以看到其他專案。

若要瞭解下列範例中使用的首碼，請參閱 [DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] ID 列表 {#id-list}

| ID | 名稱和說明 | 使用方法與範例 | 使用者介面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也稱為 [!UICONTROL Device ID]. 38位數的數字裝置ID， [!DNL Audience Manager] 會與其互動的每個裝置建立關聯。 每當您在中看到提及不重複使用者時，請思考此ID [!DNL Audience Manager] UI。 Audience Manager會將此ID儲存為 [!DNL cookie] 在 `demdex.net` 第三方網域。 | 在 [!DNL DCS] 呼叫， `uuid` 前面加上 `d_` 前置詞。 <br>示例: `d_uuid = 07955261652886032950143702505894272138` | 您可以篩選 [!DNL traits] 作者： [!UICONTROL Device ID] 建立時 [相似模型](../features/algorithmic-models/create-model.md)、和 [建立區段](../features/segments/segment-builder.md). 您也可以依據以下條件篩選結果： [!UICONTROL Device ID] 執行時 [特徵的一般報表](../reporting/general-reports.md) 和 [特徵的趨勢報表](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]。這是公司註冊時隨附的ID [!DNL Experience Cloud] 帳戶。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在中不可見 [!DNL Audience Manager] 使用者介面。 瞭解如何尋找貴公司的 [!DNL Organization ID]，讀取 [尋找組織ID](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]。此 [!DNL PID] 為中的公司ID [!DNL Audience Manager]. Audience Manager關聯 [!DNL imsOrgId] 至 [!DNL PID]. | `1352` | 在中不可見 [!DNL Audience Manager] 使用者介面。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. 此 [!DNL Experience Cloud] ID ([!DNL ECID]，舊版縮寫 [!DNL MID] 或 [!DNL MCID])是從 [!DNL Organization ID] 和 [!DNL Audience Manager] [!UICONTROL Unique User ID]. 只要這些ID保持不變，就會產生正確的 [!DNL ECID] 對特定使用者而言，這僅僅是一個數學問題。 具有相同的 [!DNL Organization ID] 和 [!DNL Audience Manager] [!DNL UUID] 您會得到相同的 [!DNL ECID] 每次的值。 您可以深入瞭解 [!DNL ECID] 在 [Cookie和Experience CloudID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 說明檔案。 | `mid = 08382830887934830189014177072406221371` | 在中不可見 [!DNL Audience Manager] 使用者介面。 |
| [!DNL SID] | [!UICONTROL Trait ID]。此 [!UICONTROL Trait ID] 唯一識別 [!DNL traits] 在 [!DNL Audience Manager] 環境。 | 在 [!DNL DCS] 呼叫， `SID` 前面加上 `d_` 前置詞。 <br>示例 `d_sid=289983`. | A [!UICONTROL Trait ID] 指派給每個 [!DNL trait]，並顯示在使用者介面中的 [特徵](../features/traits/trait-details-page.md) 頁面。 |
| [!DNL SID] | [!UICONTROL Segment ID]。此 [!UICONTROL Segment ID] 唯一識別 [!DNL segments] 在 [!DNL Audience Manager] 環境。 | 在 [!DNL DCS] 呼叫， `SID` 前面加上 `d_` 前置詞。 <br>示例 `d_sid=4798574`. | A [!UICONTROL Segment ID] 指派給每個 [!DNL segment]，並顯示在使用者介面中的 [區段](../features/segments/segment-summary-view.md) 頁面。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一識別中的區段 [!DNL Audience Manager] 環境。 | `741232` | A [!UICONTROL Legacy Segment ID] 會指派給每個區段，並顯示在使用者介面的 [區段](../features/segments/segment-summary-view.md) 頁面。 |
| [!DNL destID] | [!UICONTROL Destination ID]。此 [!UICONTROL Destination ID] 唯一識別 [!DNL destinations] 在 [!DNL Audience Manager] 環境。 ID會指派給每個ID [!DNL destination] 在使用者介面中。 | `2523` | A [!UICONTROL Destination ID] 指派給每個 [!DNL destination]，並顯示在使用者介面中的 [目的地](../features/destinations/destinations-home.md) 頁面。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (也稱為 [!UICONTROL Data Provider ID])。 此 [!UICONTROL Data Source ID] 是ID的名稱空間，或 [!DNL traits]. ID會指派給每個ID [!DNL data source] （資料提供者）時。 | 在 [!DNL DCS] 呼叫， `dpid` 前面加上 `d_` 前置詞。 <br>示例: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] 指派給每個 [!DNL data source]，並顯示在使用者介面中的 [資料來源](../features/datasources-list-and-settings.md) 頁面。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也稱為 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]. 協力廠商ID。 這是您用來識別自己使用者的ID [!DNL CRM] 系統。 您可以同步 [!DNL DPUUIDs] 替換為 [!DNL Audience Manager] [!DNL UUIDs] 而且您可以同步處理 [!DNL DPUUIDs] 來自您的不同 [!UICONTROL Data Sources] ([!DNL DPIDs])。 | 在 [!DNL DCS] 呼叫， `dpuuid` 前面加上 `d_` 前置詞。 <br> 示例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 您可以篩選 [!DNL traits] 作者： [!UICONTROL Cross-Device ID] 建立時 [相似模型](../features/algorithmic-models/create-model.md)、和 [建立區段](../features/segments/segment-builder.md). 您也可以依據以下條件篩選結果： [!UICONTROL Cross-Device ID] 執行時 [特徵的一般報表](../reporting/general-reports.md) 和 [特徵的趨勢報表](../reporting/trend-reports.md). |
| [!DNL CRM ID] | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 此 [!DNL CID] 和 [!DNL CID_IC] 機碼值組取代 [!DNL DPID] 和 [!DNL DPUUID]. 它們提供與相同的功能 [!DNL DPID] 和 [!DNL DPUUID]，但效率較高，因為它們將資料提供者ID和使用者ID （或整合代碼）包含在單一索引鍵/值組中。 | 在 [!DNL DCS] 呼叫，這些ID前面會加上 `d_` 前置詞。 <br>示例: `d_cid_ic=39217_myIntegrationCode`. | 另請參閱 `DPID` 和 `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。每个硬件设备的用于广告宣传的独特 ID。通常由裝置或裝置作業系統的製造商提供。 | 另請參閱 [全域裝置ID](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

全域裝置ID是裝置製造商或作業系統提供的每個裝置專屬的裝置廣告ID。 下表說明這些ID及其格式。 如需關於全域裝置ID及其使用方式的詳細資訊，請參閱 [!DNL Audience Manager]，讀取 [全域資料來源](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | 名稱和說明 | 示例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行 [!DNL iOS] 作業系統。 | 格式必須由32個大寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，共36個字元。<br> 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]是Android裝置製造商提供的行動裝置識別碼。 這些ID代表執行 [!DNL Android] 作業系統。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 表示 [!DNL Roku] 串流裝置。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]是裝置識別碼，產生者為 [!DNL Windows 10] 以每個裝置、每個使用者為基礎。 | [!DNL MAID]s會格式化為英數字串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 裝置識別碼是由 [!DNL Samsung] 智慧型電視。 | [!DNL Samsung] [!DNL TIFA] ID會格式化為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 代表裝置執行的裝置識別碼 [!DNL Fire OS] 作業系統。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>示例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | 代表裝置執行的裝置識別碼 [!DNL LG webOS] 作業系統。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>示例: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | 代表執行Vizio智慧型電視作業系統之裝置的裝置識別碼。 | [!DNL Vizio IFA] ID會格式化為英數字串。 <br>示例: `7XCBNROQJQPYW`. |
