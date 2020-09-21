---
description: 请参阅此文档，了解Adobe Audience ManagerID的完整列表。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 请参阅此文档，了解Adobe Audience ManagerID的完整列表。
seo-title: Audience Manager 中的 ID 索引
solution: Audience Manager
title: Audience Manager 中的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 5%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager] 使用多个ID来标识和管理您向其发送的数据。 有关ID的完整列表，请参 [!DNL Audience Manager] 阅本文，以及您应使用这些前缀的示例。

## ID前缀 {#prefixing}

虽然您可以通过这些ID的独立名称来引用这些ID中的大多数，但大多数ID在通过调用传递数据时都应与各种前缀一起 [!DNL DCS] 使用。 这些ID中的某些ID可供 [!DNL Audience Manager] 用户使用而不向用户公开，而其他ID也可在用户界面(UI)中显示。

要了解以下示例中使用的前缀，请参 [阅DCS API调用的支持属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 列表 {#id-list}

| ID | 名称和说明 | 用法和示例 | 用户界面位置 |
|---|-----------|---|------------|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也称为 [!UICONTROL Device ID]。 一个38位数的数字设备ID，它与 [!DNL Audience Manager] 与之交互的每个设备相关联。 每当您在UI中看到提及独特用户时，请考虑此 [!DNL Audience Manager] ID。 Audience Manager将此ID [!DNL cookie] 保存 `demdex.net` 为第3方域。 | 在 [!DNL DCS] 调用 `uuid` 中，前面有前 `d_` 缀。 <br>示例: `d_uuid = 07955261652886032950143702505894272138` | 您可以在创 [!DNL traits] 建类 [!UICONTROL Device ID] 似模 [型和构建细](../features/algorithmic-models/create-model.md)分时进行筛 [选](../features/segments/segment-builder.md)。 您还可以在运行“特征 [!UICONTROL Device ID] 常规报 [表”和“特征趋](../reporting/general-reports.md) 势报表”时筛选结果 [](../reporting/trend-reports.md)。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]。这是公司在注册帐户时获得的ID。 [!DNL Experience Cloud] | `5DC5123F5245B1D20A490D46@AdobeOrg` | 用户界面中 [!DNL Audience Manager] 不可见。 要了解如何找到公司，请阅 [!DNL Organization ID]读查 [找您的组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。这 [!DNL PID] 是公司的身份 [!DNL Audience Manager]。 Audience Manager将 [!DNL imsOrgId] 与关联 [!DNL PID]。 | `1352` | 用户界面中 [!DNL Audience Manager] 不可见。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. ID( [!DNL Experience Cloud] 旧版缩写[!DNL ECID]或)是从您和 [!DNL MID] 的中以数学方式得 [!DNL MCID]出的 [!DNL Organization ID][!DNL Audience Manager][!UICONTROL Unique User ID]。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same [!DNL Organization ID] and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以在Cookie和Experience Cloud [!DNL ECID] ID文 [档中阅读更多相关信息](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 。 | `mid = 08382830887934830189014177072406221371` | 用户界面中 [!DNL Audience Manager] 不可见。 |
| [!DNL SID] | [!UICONTROL Trait ID]。在 [!UICONTROL Trait ID] 环境 [!DNL traits] 中唯一标 [!DNL Audience Manager] 识。 | 在 [!DNL DCS] 调用 `SID` 中，前面有前 `d_` 缀。 <br>示例 `d_sid=289983`. | A [!UICONTROL Trait ID] 被分配给每 [!DNL trait]个属性，并在“特征”页的用户界面 [中可见](../features/traits/trait-details-page.md) 。 |
| [!DNL SID] | [!UICONTROL Segment ID]。在 [!UICONTROL Segment ID] 环境 [!DNL segments] 中唯一标 [!DNL Audience Manager] 识。 | 在 [!DNL DCS] 调用 `SID` 中，前面有前 `d_` 缀。 <br>示例 `d_sid=4798574`. | 系统 [!UICONTROL Segment ID] 会为每个区 [!DNL segment]段分配一个，并在“区段”页面的用户界面 [中显示](../features/segments/segment-summary-view.md) 。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一标识环境中的 [!DNL Audience Manager] 区段。 | `741232` | 系统 [!UICONTROL Legacy Segment ID] 会为每个区段分配一个，并在“区段”页面的用户界面中 [显示](../features/segments/segment-summary-view.md) 。 |
| [!DNL destID] | [!UICONTROL Destination ID]。在 [!UICONTROL Destination ID] 环境 [!DNL destinations] 中唯一标 [!DNL Audience Manager] 识。 ID被分配给用户界 [!DNL destination] 面中的每个人。 | `2523` | 每个 [!UICONTROL Destination ID] 目标都分配有 [!DNL destination]一个，并且在“目标”页的用户界面 [中可见](../features/destinations/destinations-home.md) 。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (也称为 [!UICONTROL Data Provider ID])。 是 [!UICONTROL Data Source ID] ID或的命名空间 [!DNL traits]。 ID被分配给用户界 [!DNL data source] 面中的每个（数据提供者）。 | 在 [!DNL DCS] 调用 `dpid` 中，前面有前 `d_` 缀。 <br>示例: `d_dpid=39217`. | 每个 [!UICONTROL Data Provider ID] 数据源都被分 [!DNL data source]配，并且在“数据源”页的用户界面 [中可见](../features/datasources-list-and-settings.md) 。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也称为 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。 第三方ID。 这是用于识别您自己系统中的最终用户的 [!DNL CRM] ID。 您可以与 [!DNL DPUUIDs] 同步 [!DNL Audience Manager] ，也可以 [!DNL UUIDs] 在ID同步过程中从 [!DNL DPUUIDs] 不同( [!UICONTROL Data Sources][!DNL DPIDs])进行同步。 | 在调 [!DNL DCS] 用中， `dpuuid` 前面有前 `d_` 缀。 <br> 示例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 您可以在创 [!DNL traits] 建类 [!UICONTROL Cross-Device ID] 似模 [型和构建细](../features/algorithmic-models/create-model.md)分时进行筛 [选](../features/segments/segment-builder.md)。 您还可以在运行“特征 [!UICONTROL Cross-Device ID] 常规报 [表”和“特征趋](../reporting/general-reports.md) 势报表”时筛选结果 [](../reporting/trend-reports.md)。 |
| [!DNL CRM ID] | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 和 [!DNL CID] 键 [!DNL CID_IC] 值对将替换 [!DNL DPID] 和 [!DNL DPUUID]。 它们提供与和相同的 [!DNL DPID] 函 [!DNL DPUUID]数，但效率更高，因为它们将数据提供者ID和用户ID（或集成代码）包含在单个键值对中。 | 在调 [!DNL DCS] 用中，这些ID前面有前缀 `d_` 。 <br>示例: `d_cid_ic=39217_myIntegrationCode`. | 请参阅 `DPID` 和 `DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 | 请参 [阅全局设备ID](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全局设备ID是设备广告ID，它们是设备制造商或操作系统提供的每个设备特有的。 下表说明了这些ID是什么及其格式。 有关全局设备ID以及如何在中使用它们的更多信 [!DNL Audience Manager]息，请 [阅读全局数据源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名称和说明 | 示例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是设备制造商提供的移动设备标识符。 这些ID表示运行操作系统 [!DNL iOS] 的设备。 | 格式严格由32个大写十六进制数字组成，以5组显示，以连字符分隔，格式为8-4-4-4-12，共36个字符。<br> 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]是由Android设备制造商提供的移动设备标识符。 这些ID表示运行操作系统 [!DNL Android] 的设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，以连字符分隔，格式为8-4-4-4-12，共36个字符。 <br>示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 表示 [!DNL Roku] 流设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，以连字符分隔，格式为8-4-4-4-12，共36个字符。 <br>示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是由每个设备 [!DNL Windows 10] 、每个用户生成的设备标识符。 | [!DNL MAID]s的格式为字母数字字符串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 是智能电视提供的设 [!DNL Samsung] 备标识符。 | [!DNL Samsung] [!DNL TIFA] ID的格式为字母数字字符串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 表示运行操作系统的设备 [!DNL Fire OS] 的设备标识符。 | 格式严格由32个小写十六进制数字组成，以5组显示，以连字符分隔，格式为8-4-4-4-12，共36个字符。 <br>示例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |