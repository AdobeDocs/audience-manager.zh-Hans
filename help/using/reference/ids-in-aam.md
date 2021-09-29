---
description: 有关Adobe Audience Manager ID的完整列表，请参阅此文档。
keywords: DPID;DPUUID;CID;UUID;uuid;uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid，
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

# [!DNL Audience Manager]中的ID索引 {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager] 使用多个ID来标识和管理您发送到该ID的数据。有关[!DNL Audience Manager] ID的完整列表，以及应与之一起使用的前缀示例，请参阅本文。

## ID前缀 {#prefixing}

虽然您可以通过这些ID的独立名称来引用这些ID中的大多数，但在通过[!DNL DCS]调用传入数据时，这些ID中的大多数会与各种前缀一起使用。 其中一些ID由[!DNL Audience Manager]使用，不会向用户显示，而其他ID也会显示在用户界面(UI)中。

要了解以下示例中使用的前缀，请参阅[DCS API调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 列表 {#id-list}

| ID | 名称和描述 | 用法和示例 | 用户界面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也称为 [!UICONTROL Device ID]。一个38位的数字设备ID， [!DNL Audience Manager]与其交互的每个设备相关联。 每当您在[!DNL Audience Manager] UI中看到提及独特用户时，请考虑此ID。 Audience Manager将此ID另存为[!DNL cookie]在`demdex.net`第三方域中。 | 在[!DNL DCS]调用中， `uuid`前面有`d_`前缀。 <br>示例: `d_uuid = 07955261652886032950143702505894272138` | 创建[相似人群拓展模型](../features/algorithmic-models/create-model.md)时，可以按[!UICONTROL Device ID]过滤[!DNL traits]，创建区段](../features/segments/segment-builder.md)时，可以按过滤[。 运行特征](../reporting/general-reports.md)的常规报表和特征[的趋势报表](../reporting/trend-reports.md)时，您还可以按[!UICONTROL Device ID]过滤结果。[ |
| [!DNL ImsOrgId] | [!DNL Organization ID]。这是公司在注册[!DNL Experience Cloud]帐户时获得的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在[!DNL Audience Manager]用户界面中不可见。 要了解如何查找公司的[!DNL Organization ID]，请阅读[查找组织ID](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。[!DNL PID]是[!DNL Audience Manager]中的公司ID。 Audience Manager将[!DNL imsOrgId]关联到[!DNL PID]。 | `1352` | 在[!DNL Audience Manager]用户界面中不可见。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. [!DNL Experience Cloud] ID（[!DNL ECID]，旧版缩写[!DNL MID]或[!DNL MCID]）是通过数学方法从您的[!DNL Organization ID]和[!DNL Audience Manager] [!UICONTROL Unique User ID]中计算得来的。 只要这些ID保持不变，为特定用户生成正确的[!DNL ECID]就只是一个数学问题。 使用相同的[!DNL Organization ID]和[!DNL Audience Manager] [!DNL UUID]，您每次会获得相同的[!DNL ECID]值。 您可以在[Cookie和Experience CloudID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17)文档中阅读有关[!DNL ECID]的更多信息。 | `mid = 08382830887934830189014177072406221371` | 在[!DNL Audience Manager]用户界面中不可见。 |
| [!DNL SID] | [!UICONTROL Trait ID]。[!UICONTROL Trait ID]唯一标识[!DNL Audience Manager]环境中的[!DNL traits]。 | 在[!DNL DCS]调用中， `SID`前面有`d_`前缀。 <br>示例 `d_sid=289983`. | 将[!UICONTROL Trait ID]分配给每个[!DNL trait]，并显示在[特征](../features/traits/trait-details-page.md)页面的用户界面中。 |
| [!DNL SID] | [!UICONTROL Segment ID]。[!UICONTROL Segment ID]唯一标识[!DNL Audience Manager]环境中的[!DNL segments]。 | 在[!DNL DCS]调用中， `SID`前面有`d_`前缀。 <br>示例 `d_sid=4798574`. | 将[!UICONTROL Segment ID]分配给每个[!DNL segment]，并显示在[区段](../features/segments/segment-summary-view.md)页面的用户界面中。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID唯一标识[!DNL Audience Manager]环境中的区段。 | `741232` | [!UICONTROL Legacy Segment ID]分配给每个区段，并显示在[区段](../features/segments/segment-summary-view.md)页面的用户界面中。 |
| [!DNL destID] | [!UICONTROL Destination ID]。[!UICONTROL Destination ID]唯一标识[!DNL Audience Manager]环境中的[!DNL destinations]。 用户界面中的每个[!DNL destination]都会分配一个ID。 | `2523` | 将[!UICONTROL Destination ID]分配给每个[!DNL destination]，并显示在[目标](../features/destinations/destinations-home.md)页面的用户界面中。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (也称为 [!UICONTROL Data Provider ID])[!UICONTROL Data Source ID]是ID或[!DNL traits]的命名空间。 用户界面中的每个[!DNL data source]（数据提供程序）都分配有ID。 | 在[!DNL DCS]调用中， `dpid`前面有`d_`前缀。 <br>示例: `d_dpid=39217`. | 将[!UICONTROL Data Provider ID]分配给每个[!DNL data source]，并显示在[数据源](../features/datasources-list-and-settings.md)页面的用户界面中。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也称为 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。第三方ID。 这是用于识别您自己[!DNL CRM]系统中的最终用户的ID。 您可以将[!DNL DPUUIDs]与[!DNL Audience Manager] [!DNL UUIDs]同步，并且可以从ID同步过程中的不同[!UICONTROL Data Sources]([!DNL DPIDs])同步[!DNL DPUUIDs]。 | 在[!DNL DCS]调用中， `dpuuid`前面有`d_`前缀。 <br> 示例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 创建[相似人群拓展模型](../features/algorithmic-models/create-model.md)时，可以按[!UICONTROL Cross-Device ID]过滤[!DNL traits]，创建区段](../features/segments/segment-builder.md)时，可以按过滤[。 运行特征](../reporting/general-reports.md)的常规报表和特征[的趋势报表](../reporting/trend-reports.md)时，您还可以按[!UICONTROL Cross-Device ID]过滤结果。[ |
| [!DNL CRM ID] | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID]和[!DNL CID_IC]键值对将替换为[!DNL DPID]和[!DNL DPUUID]。 它们提供的函数与[!DNL DPID]和[!DNL DPUUID]相同，但效率更高，因为它们将数据提供程序ID和用户ID（或集成代码）包含在单个键值对中。 | 在[!DNL DCS]调用中，这些ID前面有`d_`前缀。 <br>示例: `d_cid_ic=39217_myIntegrationCode`. | 请参阅`DPID`和`DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 | 请参阅[全局设备ID](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全局设备ID是设备广告ID，是设备制造商或操作系统提供的每个设备特有的设备广告ID。 下表说明了这些ID是什么以及其格式。 有关全局设备ID以及如何在[!DNL Audience Manager]中使用它们的更多信息，请阅读[全局数据源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名称和描述 | 示例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是设备制造商提供的移动设备标识符。这些ID表示运行[!DNL iOS]操作系统的设备。 | 格式严格由32个大写的十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共包含36个字符。<br> 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]是由Android设备制造商提供的移动设备标识符。这些ID表示运行[!DNL Android]操作系统的设备。 | 格式严格由32个小写的十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共包含36个字符。 <br>示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 表示 [!DNL Roku] 流设备。 | 格式严格由32个小写的十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共包含36个字符。 <br>示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]是由每个设备和每 [!DNL Windows 10] 个用户生成的设备标识符。 | [!DNL MAID]格式为字母数字字符串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 是智能电视提供的设 [!DNL Samsung] 备标识符。 | [!DNL Samsung] [!DNL TIFA] ID的格式为字母数字字符串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 表示运行[!DNL Fire OS]操作系统的设备的设备标识符。 | 格式严格由32个小写的十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共包含36个字符。 <br>示例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | 表示运行[!DNL LG webOS]操作系统的设备的设备标识符。 | 格式严格由32个小写的十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共包含36个字符。 <br>示例: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | 代表运行Vizio智能电视操作系统的设备的设备标识符。 | [!DNL Vizio IFA] ID的格式为字母数字字符串。<br>示例: `7XCBNROQJQPYW`. |
