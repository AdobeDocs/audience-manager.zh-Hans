---
description: 本文档介绍与 Audience Manager 数据隐私法规合规相关的技术。
seo-description: 本文档介绍与 Audience Manager 数据隐私法规合规相关的技术。
seo-title: 数据隐私请求
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 数据隐私请求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 62%

---


# 数据隐私请求 {#data-privacy-requests}

## 概述 {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

在阅读本文之前，建议您先查阅 [GDPR 术语表](../data-security-and-privacy/aam-gdpr-glossary.md)和 [CCPA 术语表](aam-ccpa-glossary.md)，以便更好地了解本文中使用的术语。

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* 通过 [Privacy Service UI](https://privacyui.cloud.adobe.io/)。请参阅[此文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)。
* 通过 **[!DNL Privacy Service API]**。See the documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)**section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 支持两种类型的请求：数据访问请求和数据删除请求。

## 数据访问请求 {#access-data}

您可以通过 [Privacy Service UI](https://privacyui.cloud.adobe.io/)（请参阅[此文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）或通过调用 [!DNL Privacy Service API]（请参阅[此文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)和[此 [!DNL API] 参考](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）发送单个数据访问请求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 允许您通过使用 [!UICONTROL Request Builder] 或上传 [!DNL JSON] 文件来创建新的作业请求。

要了解有效的 [!DNL JSON] 文件是什么样的，可以[下载示例 JSON](../data-security-and-privacy/assets/access_request.json)。

我们理解您承诺在法规规定的期限内响应数据隐私请求。

## 数据删除请求 {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 允许您通过使用 [!UICONTROL Request Builder] 或上传 [!DNL JSON] 文件来创建新的作业请求。

要了解有效的 [!DNL JSON] 文件是什么样的，可以[下载示例 JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe 理解您承诺在 30 天内响应数据隐私客户请求。For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

如果您在数据隐私请求中发送了声明的 ID（如跨设备 [!DNL CRM] ID 或 ID）， 将在所有关联的设备（每个声明的 ID 最多关联 100 台设备）上执行必要的删除操作。[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager]当数据主体请求删除某些数据时， 将尝试通过向激活合作伙伴发送有关取消分段的信息，来向其告知数据删除请求。但是，一些激活合作伙伴：

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

下载我们的[合作伙伴 Excel 表](assets/AAM-Partners-October2019.xlsx)，了解 的哪些激活合作伙伴支持取消分段。[!DNL Audience Manager]

## 选择退出请求 {#opt-out-requests}

[!DNL Audience Manager] 支持与选择退出管理相关的行业标准。 Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

数据访问和删除请求通过 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 进行处理，而选择退出请求当前则通过 [!DNL DCS API] 提供支持。Read on to learn what the opt-out [!DNL API] calls should look like.

### 全局选择退出请求

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. 下表列出了用于发出全局选择退出请求的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/cn/privacy/opt-out.html#customeruse" format="http" scope="external">隐私选择页面</a>提供了一键单击功能，通过该功能，最终用户能够控制各个 Adobe Experience Cloud 广告解决方案（包括 Audience Manager）的数据收集行为并选择退出数据收集。有关具体信息，请参阅隐私选择页面中的<a href="https://www.adobe.com/cn/privacy/opt-out.html#customeruse" format="http" scope="external">企业客户部分</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接对 Audience Manager 进行 API 调用 </p> </td> 
   <td colname="col2"> <p>您的用户可以通过调用以下 DCS API 并包含 <a href="../../reference/ids-in-aam.md">Audience Manager 用户 ID</a>，从所有 Audience Manager 品牌中选择退出数据收集： </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>因此，我们将为提交的 Audience Manager 用户 ID 设置 <code>demdex=NOTARGET</code> Cookie 和 <code>dextp=NOTARGET</code> Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 </p> </td> 
   <td colname="col2"> <p>请参阅适用于以下两类移动设备的选择退出和隐私设置： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/zh-Hans/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android 设备</a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/zh-Hans/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 设备</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户还可以通过访问我们的行业标准合作伙伴的网站来选择退出全局数据收集。

* [数字广告联盟 (DAA)](https://optout.aboutads.info/?c=2#!/)；
* [网络广告促进协会 (NAI)](https://optout.networkadvertising.org/?c=1#!/)。

在收到上述选择退出请求后：

* [!DNL Audience Manager] 将停止所有数据收集、分段或激活操作，但前提是用户不清除其浏览器 Cookie。
* 将在 120 天后从用户配置文件中删除历史数据。

### 通过调用声明的 ID 发出合作伙伴级别的选择退出请求

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

通过调用声明的 ID 发出合作伙伴级别的选择退出请求后：

* [CRM ID](../../reference/ids-in-aam.md) 将退出数据收集；
* 与 [CRM ID](../../reference/ids-in-aam.md) 关联的上一个设备 ID（[Audience Manager 独特用户 ID](../../reference/ids-in-aam.md)）将退出数据收集。
* [!DNL Audience Manager] 将停止对ID和链接到该ID的最后一个设备 [!DNL CRM] ID进行所有数据收集、分段或激活 [!DNL CRM] 操作；
* [!DNL Audience Manager] 从所有区段中 [!DNL CRM] 取消选择退出ID和最后一个设备ID;
* [!UICONTROL Destination] 合作伙伴将收到对ID和最 [!DNL CRM] 后一个设备ID的unsegment请求。 取消分段既适用于[实时](data-privacy-requests.md#aam-partners-with-unsegmentation)目标，也适用于批量目标。
* 不会删除历史数据。

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

您可以通过 `d_cid` 和 `d_cid_ic` 键值对，发出针对某个已声明 ID 的选择退出请求。虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

#### 选择退出 [!DNL CID] 和 [!DNL CID_IC]

有关说明和语法，请参阅[已声明 ID 的 URL 变量和语法](../../features/declared-ids.md#variables-and-syntax)。

| 选择退出请求所用方式 | 代码示例 |
|--- |--- |
| 数据提供商 ID 和用户 ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户 ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多个 `d_cid` 和 `d_cid_ic` 键值对。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 通过调用设备 ID 发出合作伙伴级别的选择退出请求

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. 通过对 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 进行以下调用，可以使特定设备 ID 从某个品牌中选择退出数据收集：

| 选择退出请求所用方式 | 代码示例 |
|--- |--- |
| [!DNL Audience Manager] ( [!DNL Unique User ID] )`uuid`。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| 一 [!DNL Experience Cloud] 个ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

有关 `uuid`、`mid` 和 `imsOrgId` 的更多信息，请参阅 [Audience Manager 中的 ID 索引](/help/using/reference/ids-in-aam.md)。

通过调用设备 ID 发出合作伙伴级别的选择退出请求后：

* 该设备 ID 将退出数据收集。
* [!DNL Audience Manager] 将从相应合作伙伴中停止对该设备 ID 进行任何数据收集、分段或激活操作。
* [!DNL Audience Manager] 从所有区段中取消对设备ID的分段；
* 目标合作伙伴将收到对该设备 ID 进行取消分段的请求。取消分段既适用于[实时](data-privacy-requests.md#aam-partners-with-unsegmentation)目标，也适用于批量目标。
* 不会删除历史数据。

## [!DNL Audience Manager] 具有取消细分功能的合作伙伴 {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

但是，一些激活合作伙伴：

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

请查阅[基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)，了解 的哪些激活合作伙伴支持取消分段。[!DNL Audience Manager]

## 数据更正请求 {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] 客户可以根据用户用户档案选择捕获相关信号／特征／细分，并通过离线数据获取 [将此信息发送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 到 [!DNL Audience Manager]。 Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
