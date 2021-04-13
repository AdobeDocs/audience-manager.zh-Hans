---
description: 有关Adobe Audience Manager ID的完整列表，请参阅此文档。
keywords: DPID;DPUUID;CID;UUID;uid;uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid
seo-description: 有关Adobe Audience Manager ID的完整列表，请参阅此文档。
seo-title: Audience Manager 中的 ID 索引
solution: Audience Manager
title: Audience Manager 中的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: 参考
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 5%

---

# [!DNL Audience Manager] {#index-of-ids-in-audience-manager}中ID的索引

## 概述 {#overview}

[!DNL Audience Manager] 使用多个ID来标识和管理您发送给它的数据。有关[!DNL Audience Manager] ID的完整列表，以及您应使用它们的前缀示例，请参阅本文。

## ID前缀{#prefixing}

虽然您可以通过这些ID的独立名称来引用其中的大多数ID，但在通过[!DNL DCS]调用传入数据时，这些ID中的大多数用于各种前缀。 其中一些ID由[!DNL Audience Manager]使用，但不向用户公开，而其他ID也在用户界面(UI)中可见。

要了解以下示例中使用的前缀，请参阅[DCS API调用的支持属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 列表 {#id-list}

| ID | 名称和说明 | 用法和示例 | 用户界面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也称为 [!UICONTROL Device ID]。一个38位数字设备ID，它与[!DNL Audience Manager]交互的每个设备相关联。 每当您在[!DNL Audience Manager] UI中看到提及独特用户时，请考虑此ID。 Audience Manager将此ID保存为`demdex.net`第三方域中的[!DNL cookie]。 | 在[!DNL DCS]调用中，`uuid`前面有`d_`前缀。 <br>示例: `d_uuid = 07955261652886032950143702505894272138` | 在创建[相似模型](../features/algorithmic-models/create-model.md)时，可以按[!UICONTROL Device ID]筛选[!DNL traits]和[生成区段](../features/segments/segment-builder.md)。 在运行“特征](../reporting/general-reports.md)的常规报告”和“特征](../reporting/trend-reports.md)的趋势报告”时，您也可以按[!UICONTROL Device ID]筛选结果。[[ |
| [!DNL ImsOrgId] | [!DNL Organization ID]。这是公司在注册[!DNL Experience Cloud]帐户时向其提供的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在[!DNL Audience Manager]用户界面中不可见。 要了解如何找到公司的[!DNL Organization ID]，请阅读[查找组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。[!DNL PID]是[!DNL Audience Manager]中的公司ID。 Audience Manager将[!DNL imsOrgId]与[!DNL PID]关联。 | `1352` | 在[!DNL Audience Manager]用户界面中不可见。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. [!DNL Experience Cloud] ID（[!DNL ECID]，旧缩写[!DNL MID]或[!DNL MCID]）是从您的[!DNL Organization ID]和[!DNL Audience Manager] [!UICONTROL Unique User ID]中以数学方式导出的。 只要这些ID保持不变，为特定用户生成右[!DNL ECID]就只是一个数学问题。 使用相同的[!DNL Organization ID]和[!DNL Audience Manager] [!DNL UUID]，您每次都能获得相同的[!DNL ECID]值。 您可以在[Cookie和Experience CloudID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17)文档中阅读有关[!DNL ECID]的更多信息。 | `mid = 08382830887934830189014177072406221371` | 在[!DNL Audience Manager]用户界面中不可见。 |
| [!DNL SID] | [!UICONTROL Trait ID]。[!UICONTROL Trait ID]在[!DNL Audience Manager]环境中唯一标识[!DNL traits]。 | 在[!DNL DCS]调用中，`SID`前面有`d_`前缀。 <br>示例 `d_sid=289983`. | 将[!UICONTROL Trait ID]分配给每个[!DNL trait]，并在用户界面的[ Traits](../features/traits/trait-details-page.md)页中可见。 |
| [!DNL SID] | [!UICONTROL Segment ID]。[!UICONTROL Segment ID]在[!DNL Audience Manager]环境中唯一标识[!DNL segments]。 | 在[!DNL DCS]调用中，`SID`前面有`d_`前缀。 <br>示例 `d_sid=4798574`. | 每个[!DNL segment]都分配有[!UICONTROL Segment ID]，在用户界面的[区段](../features/segments/segment-summary-view.md)页中可见。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一标识[!DNL Audience Manager]环境中的区段。 | `741232` | 每个区段都分配有[!UICONTROL Legacy Segment ID]，在用户界面的[区段](../features/segments/segment-summary-view.md)页中可见。 |
| [!DNL destID] | [!UICONTROL Destination ID]。[!UICONTROL Destination ID]在[!DNL Audience Manager]环境中唯一标识[!DNL destinations]。 将为用户界面中的每个[!DNL destination]分配一个ID。 | `2523` | 将[!UICONTROL Destination ID]分配给每个[!DNL destination]，并在用户界面的[目标](../features/destinations/destinations-home.md)页中可见。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (亦称 [!UICONTROL Data Provider ID])[!UICONTROL Data Source ID]是ID或[!DNL traits]的命名空间。 将ID分配给用户界面中的每个[!DNL data source]（数据提供者）。 | 在[!DNL DCS]调用中，`dpid`前面有`d_`前缀。 <br>示例: `d_dpid=39217`. | 将[!UICONTROL Data Provider ID]分配给每个[!DNL data source]，并在用户界面的[数据源](../features/datasources-list-and-settings.md)页中可见。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也称为 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。第三方ID。 这是您在自己的[!DNL CRM]系统中标识最终用户的ID。 您可以将[!DNL DPUUIDs]与[!DNL Audience Manager] [!DNL UUIDs]同步，并可以在ID同步过程中从不同的[!UICONTROL Data Sources]([!DNL DPIDs])同步[!DNL DPUUIDs]。 | 在[!DNL DCS]调用中，`dpuuid`前面有`d_`前缀。 <br> 示例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 在创建[相似模型](../features/algorithmic-models/create-model.md)时，可以按[!UICONTROL Cross-Device ID]筛选[!DNL traits]和[生成区段](../features/segments/segment-builder.md)。 在运行“特征](../reporting/general-reports.md)的常规报告”和“特征](../reporting/trend-reports.md)的趋势报告”时，您也可以按[!UICONTROL Cross-Device ID]筛选结果。[[ |
| [!DNL CRM ID] | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID]和[!DNL CID_IC]键值对替换[!DNL DPID]和[!DNL DPUUID]。 它们提供的函数与[!DNL DPID]和[!DNL DPUUID]相同，但效率更高，因为它们将数据提供程序ID和用户ID（或集成代码）包含在单个键值对中。 | 在[!DNL DCS]调用中，这些ID前面有`d_`前缀。 <br>示例: `d_cid_ic=39217_myIntegrationCode`. | 请参阅`DPID`和`DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 | 请参阅[全局设备ID](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全局设备ID是设备广告ID，每个设备唯一，由设备制造商或操作系统提供。 下表说明了这些ID是什么及其格式。 有关全局设备ID以及如何在[!DNL Audience Manager]中使用这些ID的详细信息，请阅读[全局数据源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名称和说明 | 示例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是由设备制造商提供的移动设备标识符。这些ID表示运行[!DNL iOS]操作系统的设备。 | 格式严格地由32个大写十六进制数字组成，以5个组显示，并以连字符分隔，形式为8-4-4-4-12，共36个字符。<br> 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]是由Android设备制造商提供的移动设备标识符。这些ID表示运行[!DNL Android]操作系统的设备。 | 格式严格地由32个小写十六进制数字组成，以5组显示，以连字符分隔，形式为8-4-4-4-12，共36个字符。 <br>示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 表示 [!DNL Roku] 流设备。 | 格式严格地由32个小写十六进制数字组成，以5组显示，以连字符分隔，形式为8-4-4-4-12，共36个字符。 <br>示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是由每个设备、每 [!DNL Windows 10] 个用户生成的设备标识符。 | [!DNL MAID]s的格式为字母数字字符串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 是智能电视提供的设 [!DNL Samsung] 备标识符。 | [!DNL Samsung] [!DNL TIFA] ID的格式为字母数字字符串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 表示运行[!DNL Fire OS]操作系统的设备的设备标识符。 | 格式严格地由32个小写十六进制数字组成，以5组显示，以连字符分隔，形式为8-4-4-4-12，共36个字符。 <br>示例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
