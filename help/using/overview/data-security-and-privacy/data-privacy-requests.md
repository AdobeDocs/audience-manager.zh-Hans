---
description: 本文档介绍与 Audience Manager 数据隐私法规合规相关的技术。
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、隐私
title: 数据隐私请求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# 数据隐私请求 {#data-privacy-requests}

## 概述 {#overview}

本文档概要介绍如何管理可通过[Privacy ServiceUI](https://privacyui.cloud.adobe.io/)和&#x200B;**[!DNL Privacy Service API]**&#x200B;发送给[!DNL Audience Manager]的单个数据隐私请求和选择退出请求。

这些工具允许您发送在[!DNL GDPR]和[!DNL CCPA]下发出的消费者数据隐私请求。

在阅读本文之前，建议您先查阅 [GDPR 术语表](../data-security-and-privacy/aam-gdpr-glossary.md)和 [CCPA 术语表](aam-ccpa-glossary.md)，以便更好地了解本文中使用的术语。

您可以通过两种方式提交单个请求以从[!DNL Audience Manager]访问和删除使用者数据：

* 通过 [Privacy Service UI](https://privacyui.cloud.adobe.io/)。请参阅[此文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)。
* 通过 **[!DNL Privacy Service API]**。请参阅文档[此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)和[!DNL API]引用[此处](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)。

在发送单个数据隐私请求时，您可以提交任意[!DNL Audience Manager]标识符(ID)(如&#x200B;**[Audience Manager标识符](data-privacy-ids.md)**&#x200B;部分所述)，以及标识符对应的命名空间ID（数据源ID）。

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans) 支持两种类型的请求：数据访问请求和数据删除请求。

## 数据访问请求 {#access-data}

您可以通过[Privacy ServiceUI](https://privacyui.cloud.adobe.io)（文档[此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=zh-Hans)）或通过调用Privacy ServiceAPI（文档[此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)和[!DNL API]参考[此处](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)）发送单个数据访问请求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 允许您通过使用 [!UICONTROL Request Builder] 或上传 [!DNL JSON] 文件来创建新的作业请求。

要了解有效的 [!DNL JSON] 文件是什么样的，可以[下载示例 JSON](../data-security-and-privacy/assets/access_request.json)。

我们理解您承诺在法规规定的期限内响应数据隐私请求。

## 数据删除请求 {#delete-data}

您可以通过[Privacy ServiceUI](https://privacyui.cloud.adobe.io)（文档[此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=zh-Hans)）或通过调用Privacy ServiceAPI（文档[此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)和[!DNL API]引用[此处](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)）发送数据删除请求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 允许您通过使用 [!UICONTROL Request Builder] 或上传 [!DNL JSON] 文件来创建新的作业请求。

要了解有效的 [!DNL JSON] 文件是什么样的，可以[下载示例 JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe 理解您承诺在 30 天内响应数据隐私客户请求。因此，[!DNL Adobe]已承诺尽快处理您的数据删除请求。

在响应您的消费者数据删除请求时，[!DNL Audience Manager]将删除与请求中包含的[!DNL Audience Manager]标识符相关联的特征和区段。 此外，将删除[!DNL Audience Manager]选择退出进一步数据收集的个人对应的[!DNL Audience Manager]标识符以及相应的ID映射。

当您在数据隐私请求中发送声明的ID（如跨设备[!DNL CRM] ID或[!DNL cookie] ID）时，[!DNL Audience Manager]将在所有关联的设备（每个声明的ID最多100台设备）上执行必要的删除。

[!DNL Audience Manager]将尝试通过向激活合作伙伴发送请求删除特定数据的数据主体的取消分段信息，来向其通知删除请求。 但是，一些激活合作伙伴：

1. 不支持来自[!DNL Audience Manager]的取消分段（或删除区段）请求，和/或
2. 无法以低于30天的频率接收来自[!DNL Audience Manager]的更新。 在这些情况下，[!DNL Audience Manager]客户无法通过[!DNL Audience Manager]自动向激活合作伙伴发送删除请求。

在这些情况下，您无法通过[!DNL Audience Manager]自动向激活合作伙伴发送删除请求。

请参阅我们的[基于设备的目标列表文档](assets/AAM-Partners-October2019.xlsx)，了解哪些[!DNL Audience Manager]激活合作伙伴支持取消分段。

## 选择退出请求 {#opt-out-requests}

[!DNL Audience Manager]支持有关选择退出管理的行业标准。 请阅读并全面了解[!DNL Audience Manager]支持的选择退出类型相关信息。

数据访问和删除请求是通过[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)处理的，而选择退出请求当前是通过[!DNL DCS API]支持的。 请阅读并了解选择退出[!DNL API]调用应该是什么样的。

### 全局选择退出请求

全局选择退出表示在所有品牌的[!DNL Audience Manager]和其他[!DNL Adobe Experience Cloud]解决方案间选择退出。 下表列出了用于发出全局选择退出请求的方法：

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
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android 设备</a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 设备</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户还可以通过访问我们的行业标准合作伙伴的网站来选择退出全局数据收集。

* [数字广告联盟 (DAA)](https://optout.aboutads.info/?c=2#!/)；
* [网络广告促进协会 (NAI)](https://optout.networkadvertising.org/?c=1#!/)。

在收到上述选择退出请求后：

* [!DNL Audience Manager]将停止所有数据收集、分段或激活，只要用户不清除其浏览器Cookie。
* 将在 120 天后从用户配置文件中删除历史数据。

### 通过调用声明的 ID 发出合作伙伴级别的选择退出请求

合作伙伴级别的选择退出允许您选择退出特定[!DNL Audience Manager]合作伙伴的数据收集。 您可以发送跨设备ID的合作伙伴级别选择退出请求，包括[!DNL CRM] ID和经过哈希处理的电子邮件地址。

通过调用声明的 ID 发出合作伙伴级别的选择退出请求后：

* [CRM ID](../../reference/ids-in-aam.md) 将退出数据收集；
* 与 [CRM ID](../../reference/ids-in-aam.md) 关联的上一个设备 ID（[Audience Manager 独特用户 ID](../../reference/ids-in-aam.md)）将退出数据收集。
* [!DNL Audience Manager]将停止对[!DNL CRM] ID以及与[!DNL CRM] ID关联的上一个设备ID进行任何数据收集、分段或激活；
* [!DNL Audience Manager]从所有区段中取消选择退出的[!DNL CRM] ID和上一个设备ID的区段；
* [!UICONTROL Destination]合作伙伴将收到[!DNL CRM] ID和上一个设备ID的取消分段请求。 取消分段既适用于[实时](data-privacy-requests.md#aam-partners-with-unsegmentation)目标，也适用于批量目标。
* 不会删除历史数据。

当[!DNL Audience Manager]收到合作伙伴级别的选择退出请求时，[!DNL DCS]返回的[!DNL JSON]包含消息[!UICONTROL "Encountered opt out tag"]的[错误代码171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)，而不是[!DNL Audience Manager]用户ID。

您可以通过 `d_cid` 和 `d_cid_ic` 键值对，发出针对某个已声明 ID 的选择退出请求。虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

#### 通过[!DNL CID]和[!DNL CID_IC]选择退出

有关说明和语法，请参阅[已声明 ID 的 URL 变量和语法](../../features/declared-ids.md#variables-and-syntax)。

| 选择退出请求所用方式 | 代码示例 |
|--- |--- |
| 数据提供商 ID 和用户 ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户 ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多个`d_cid`和`d_cid_ic`键值对。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 通过调用设备 ID 发出合作伙伴级别的选择退出请求

合作伙伴级别的选择退出允许您选择退出特定[!DNL Audience Manager]合作伙伴的数据收集。 通过对 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 进行以下调用，可以使特定设备 ID 从某个品牌中选择退出数据收集：

| 选择退出请求所用方式 | 代码示例 |
|--- |--- |
| [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`)。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

有关 `uuid`、`mid` 和 `imsOrgId` 的更多信息，请参阅 [Audience Manager 中的 ID 索引](/help/using/reference/ids-in-aam.md)。

通过调用设备 ID 发出合作伙伴级别的选择退出请求后：

* 该设备 ID 将退出数据收集。
* [!DNL Audience Manager]今后将停止为该合作伙伴收集所有数据、分段或激活该设备ID。
* [!DNL Audience Manager]从所有区段中取消设备ID的区段；
* 目标合作伙伴将收到对该设备 ID 进行取消分段的请求。取消分段既适用于[实时](data-privacy-requests.md#aam-partners-with-unsegmentation)目标，也适用于批量目标。
* 不会删除历史数据。

## 具有取消分段功能的[!DNL Audience Manager]合作伙伴 {#aam-partners-with-unsegmentation}

为了帮助您自动处理消费者数据隐私请求，[!DNL Audience Manager]将尝试通过向激活合作伙伴发送取消分段（或删除区段）信息，来向其告知数据主体提出的数据删除请求。

但是，一些激活合作伙伴：

1. 不支持来自[!DNL Audience Manager]的取消分段请求和/或
2. 无法以30天内多于一次的频率接收来自[!DNL Audience Manager]的更新。

在这些情况下，您无法通过[!DNL Audience Manager]自动向激活合作伙伴发送删除请求。

请查阅[基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)，了解哪些[!DNL Audience Manager]激活合作伙伴支持取消分段。

## 数据更正请求 {#correction}

鉴于[!DNL Audience Manager]不是数据源，因此[!DNL Audience Manager]中的数据更正角色有限。 更正可能意味着使用者已请求从不正确的[!UICONTROL trait]/[!UICONTROL segment]中取消资格，或者请求获取所需的[!UICONTROL trait]/[!UICONTROL segment]的资格。

[!DNL Audience Manager]客户可以选择根据用户配置文件捕获相关信号/特征/区段，并通过[离线数据摄取](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)将此信息发送至[!DNL Audience Manager]。 请注意，如果用户重复其行为，则将继续获得原始[!UICONTROL trait]和[!UICONTROL segments]的资格。
