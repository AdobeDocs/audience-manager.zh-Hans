---
description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
keywords: DPID;DPUUID;CID;UUID;uid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
seo-title: Audience manager中的ID索引
solution: Audience Manager
title: Audience manager中的ID索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# Audience manager中的ID索引{#index-of-ids-in-audience-manager}

有关Adobe Audience Manager ID的完整列表，请参阅本文档。

| ID|名称和说明|示例||—|—|—|| [!DNL AAM UUID] | Audience Manager唯一用户ID。 Audience manager与其交互的每个设备关联的38位数字设备ID。 每当您在Audience Manager UI中看到提及独特用户时，请考虑此ID。 Audience manager将此ID保存为第三方域 `demdex.net` 中的Cookie。 Audience Manager UUID在事件调用中作为信号发 `d_uuid` 送。 | `demdex = 07955261652886032950143702505894272138` |
| [!DNL ImsOrgId]|组织 ID. 这是公司在注册Experience cloud时获得的ID。 要了解如何找到您公司的组织ID，请阅读查 [找您的组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |`5DC5123F5245B1D20A490D46@AdobeOrg`||PID|合作伙伴ID。 PID是Audience manager中的公司ID。 Audience Manager将关联 [!DNL imsOrgId] 到某个 [!DNL PID]。 |`1352`|
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. Experience Cloud ID(旧版缩写[!DNL ECID]或 [!DNL MID][!DNL MCID])是从您的组织ID和Audience Manager唯一用户ID中以数学方式派生的。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以在 [Cookies和Experience Cloud ID文档中阅读有关ECID的更多信息](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) 。 |`mid = 08382830887934830189014177072406221371` ||[!DNL SID]|特征ID。 特征ID可唯一标识Audience manager环境中的特征。 在用户界面(UI)中，将为每个特征分配一个特征ID。 |`289983`||SID|区段ID。 区段ID可唯一标识Audience manager环境中的区段。 在UI中，会为每个区段分配一个区段ID。 |`4798574`||[!DNL csegID]|旧版区段ID。 此ID可唯一标识Audience manager环境中的区段。 旧版区段ID将分配给UI中的每个区段。 |`741232`|
|[!DNL destID]|Destination ID. 目标ID可唯一标识Audience manager环境中的目标。 在UI中，会为每个目标分配一个ID。 |`2523`||[!DNL DPID]|数据源ID（也称为数据提供者ID）。 数据源ID是ID或特征的命名空间。 在UI中，每个数据源（数据提供者）都会分配一个ID。 | `39217` ||[!DNL DPUUID]|数据提供者唯一用户ID(也称为 [!DNL CRM ID])。 第三方ID。 这是用于识别您自己系统中的最终用户的 [!DNL CRM] ID。 您可以与 [!DNL DPUUIDs] Audience Manager同步， [!DNL UUIDs] 并可以在ID同 [!DNL DPUUIDs] 步过程中从不同的数据源([!DNL DPIDs])进行同步。 |`2132-3423vn-343fds-3432r`||[!DNL CRM ID]|请参阅DPUUID。`2132-3423vn-343fds-3432r`|[!DNL CID]||[!DNL CID_IC],|客户ID，客户ID集成代码。 和 [!DNL CID] 键 [!DNL CID_IC] 值对将替换 [!DNL DPID] 和 [!DNL DPUUID]。 它们提供的功能与和相同 [!DNL DPID][!DNL DPUUID]，但效率更高，因为它们将数据提供者ID和用户ID（或集成代码）包含在单个键值对中。 ||
|[!DNL DAID]|Device Advertising ID. 每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 |请参 [阅全局设备ID](#global-device-ids)。 |

## 全局设备ID {#global-device-ids}

全局设备ID是设备广告ID，每个设备唯一，由设备制造商或操作系统提供。 下表说明了这些ID是什么及其格式。

| ID | 名称和说明 | 示例 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [!DNL IDFA] | [!DNL Identifier for Advertisers] ID是设备制造商提供的移动设备标识符。 这些ID表示运行iOS操作系统的设备。 | 格式严格由32个大写十六进制数字组成，以5组显示，以8-4-4-4-12形式用连字符分隔，总共36个字符。 示例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | [!DNL Google Advertising ID]s是由Android设备制造商提供的移动设备标识符。 这些ID表示运行操作系统 [!DNL Android] 的设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 示例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | [!DNL Roku IDs for Advertising] 表示流 [!DNL Roku] 式设备。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 示例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | [!DNL Microsoft Advertising ID]s是由每个设备、每 [!DNL Windows 10] 个用户生成的设备标识符。 | [!DNL MAID]s的格式为字母数字字符串。 |
| [!DNL DUID] | [!DNL Samsung DUID]s是由Samsung Smart TV提供的设备标识符。 | Samsung的 [!DNL DUID]格式为字母数字字符串。 |
| [!DNL Amazon Fire TV Advertising ID] | 表示运行操作系统的设备的设 [!DNL Fire OS] 备标识符。 | 格式严格由32个小写十六进制数字组成，以5组显示，并以连字符分隔，格式为8-4-4-4-12，总共36个字符。 示例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
