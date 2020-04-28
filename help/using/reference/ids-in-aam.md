---
description: 请参阅本文档，了解Adobe受众管理器ID的完整列表。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 请参阅本文档，了解Adobe受众管理器ID的完整列表。
seo-title: 受众管理器中ID的索引
solution: Audience Manager
title: 受众管理器中ID的索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 723c75e8946c42779b4c27727ff9e6398b5fc9b1

---


# 受众管理器中ID的索引{#index-of-ids-in-audience-manager}

## 概述 {#overview}

受众管理器使用多个ID来标识和管理您向其发送的数据。 有关Adobe受众管理器ID的完整列表，请参阅本文，以及应使用这些ID的前缀示例。

## ID前缀 {#prefixing}

虽然您可以通过这些ID的独立名称来引用其中的大多数ID，但在通过DCS调用传入数据时，这些ID中的大多数应与各种前缀一起使用。 其中一些ID由受众管理器使用，但不向用户公开，而其他ID也在用户界面(UI)中可见。

要了解以下示例中使用的前缀，请参阅DCS API [调用的支持属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## 受众经理列表ID {#id-list}

| ID | 名称和说明 | 使用和示例 | UI位置 |
|---|---|---|---|
| [!DNL AAM UUID] | 受众管理器唯一用户ID，也称为 [!UICONTROL Device ID]。 38位数字设备ID,受众管理器将其与之交互的每个设备关联。 每当您在受众管理器UI中看到提及独特用户时，请考虑此ID。 受众管理器将此ID保存为第 `demdex.net` 三方域中的cookie。 | 在调 [!DNL DCS] 用中， `uuid` 前面有前 `d_` 缀。 <br>示例：`d_uuid = 07955261652886032950143702505894272138` | 您可以在创建相似模 [!UICONTROL Device ID] 型和构 [建区段时筛选](../features/algorithmic-models/create-model.md)特征 [](../features/segments/segment-builder.md)。 您还可以在运行“特征的常规 [!UICONTROL Device ID] 报告”和“特 [征的趋势报告](../reporting/general-reports.md) ”时， [通过筛选结果](../reporting/trend-reports.md)。 |
| [!DNL ImsOrgId] | 组织 ID. 这是公司注册Experience Cloud帐户时获得的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在受众管理器UI中不可见。 要了解如何找到公司的组织ID，请阅读查 [找您的组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| PID | 合作伙伴ID。 PID是受众管理器中的公司ID。 受众经理将 [!DNL imsOrgId] 与关联 [!DNL PID]。 | `1352` | 在受众管理器UI中不可见。 |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. Experience Cloud ID(旧版缩写[!DNL ECID]或 [!DNL MID][!DNL MCID])是从您的组织ID和受众管理器唯一用户ID中以数学方式派生的。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以在 [Cookies和Experience Cloud ID文档中阅读有关ECID的更多信息](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 。 | `mid = 08382830887934830189014177072406221371` | 在受众管理器UI中不可见。 |
| [!DNL SID] | 特征ID。 特征ID可唯一标识受众管理器环境中的特征。 | 在调 [!DNL DCS] 用中， `SID` 前面有前 `d_` 缀。 <br>示例 `d_sid=289983`. | 特征ID被分配给每个特征，并在“特征”页面的UI中可 [见](../features/traits/trait-details-page.md) 。 |
| [!DNL SID] | 区段ID。 区段ID可唯一标识受众管理器环境中的区段。 | 在调 [!DNL DCS] 用中， `SID` 前面有前 `d_` 缀。 <br>示例 `d_sid=4798574`. | 区段ID会分配给每个区段，并显示在区段页面的UI [中](../features/segments/segment-summary-view.md) 。 |
| [!DNL csegID] | 旧版区段ID。 此ID可唯一标识受众管理器环境中的区段。 | `741232` | 旧版区段ID会分配给每个区段，并显示在区段页面的UI [中](../features/segments/segment-summary-view.md) 。 |
| [!DNL destID] | 目标ID。 目标ID可唯一标识受众管理器环境中的目标。 在UI中，会为每个目标分配一个ID。 | `2523` | 目标ID将分配给每个目标，并显示在目标页面的UI [中](../features/destinations/destinations-home.md) 。 |
| [!DNL DPID] | 数据源ID（也称为数据提供者ID）。 数据源ID是ID或特征的命名空间。 UI中的每个数据源（数据提供者）都分配有ID。 | 在调 [!DNL DCS] 用中， `dpid` 前面有前 `d_` 缀。 <br>示例: `d_dpid=39217`. | 数据提供者ID被分配给每个数据源，并显示在“数据源”页面的UI [中](../features/datasources-list-and-settings.md) 。 |
| [!DNL DPUUID] | 数据提供者唯一用户ID，也称 [!DNL CRM ID] 为或 [!UICONTROL Cross-Device ID]。 第三方ID。 这是用于识别您自己系统中的最终用户的 [!DNL CRM] ID。 您可以与 [!DNL DPUUIDs] 受众管理器同 [!DNL UUIDs] 步，也可以在ID同 [!DNL DPUUIDs] 步过程中从不同的数据源([!DNL DPIDs])同步。 | 在DCS调用中， `dpuuid` 前面有前缀 `d_` 。 <br> 示例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 您可以在创建相似模 [!UICONTROL Cross-Device ID] 型和构 [建区段时筛选](../features/algorithmic-models/create-model.md)特征 [](../features/segments/segment-builder.md)。 您还可以在运行“特征的常规 [!UICONTROL Cross-Device ID] 报告”和“特 [征的趋势报告](../reporting/general-reports.md) ”时， [通过筛选结果](../reporting/trend-reports.md)。 |
| [!DNL CRM ID] | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 | 请参阅`DPUUID`。 |
| [!DNL CID], [!DNL CID_IC] | 客户ID，客户ID集成代码。 和 [!DNL CID] 键 [!DNL CID_IC] 值对将替换 [!DNL DPID] 和 [!DNL DPUUID]。 它们提供的功能与和相同 [!DNL DPID][!DNL DPUUID]，但效率更高，因为它们将数据提供者ID和用户ID（或集成代码）包含在单个键值对中。 | 在DCS调用中，这些ID前面有前 `d_` 缀。 <br>示例: `d_cid_ic=39217_myIntegrationCode`. | 请参阅 `DPID` 和 `DPUUID`。 |
| [!DNL DAID] | 设备广告ID。 每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 | 请参 [阅全局设备ID](#global-device-ids)。 |  |

## 全局设备ID {#global-device-ids}

全局设备ID是设备广告ID，每个设备唯一，由设备制造商或操作系统提供。 下表说明了这些ID是什么及其格式。 有关全局设备ID以及如何在受众管理器中使用它们的详细信息，请阅读全 [局数据源](/help/using/features/global-data-sources.md)。

| ID | 全局数据源ID | 名称和说明 | 示例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是设备制造商提供的移动设备标识符。 这些ID表示运行iOS操作系统的设备。 | 格式严格由32个大写十六进制数字组成，以5组显示，以8-4-4-4-12形式用连字符分隔，总共36个字符。<br> 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s是由Android设备制造商提供的移动设备标识符。 这些ID表示运行操作系统 [!DNL Android] 的设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 <br>示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 表示流 [!DNL Roku] 式设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 <br>示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是由每个设备、每 [!DNL Windows 10] 个用户生成的设备标识符。 | [!DNL MAID]s的格式为字母数字字符串。 |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s是由Samsung Smart TV提供的设备标识符。 | Samsung的 [!DNL DUID]格式为字母数字字符串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 表示运行操作系统的设备的设 [!DNL Fire OS] 备标识符。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 <br>示例：`df07c7dc-cea7-4a89-b328-810ff5acb15d` |

