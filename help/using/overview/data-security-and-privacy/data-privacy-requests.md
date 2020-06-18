---
description: 本文档涵盖与Audience Manager数据隐私权法规合规性相关的技术细节。
seo-description: 本文档涵盖与Audience Manager数据隐私权法规合规性相关的技术细节。
seo-title: 数据隐私请求
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 数据隐私请求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1487'
ht-degree: 1%

---


# 数据隐私请求 {#data-privacy-requests}

## 概述 {#overview}

本文档概述了如何管理单个数据隐私和退出请求，您可以通过UI [!DNL Audience Manager] 和 [Privacy Service发送](https://privacyui.cloud.adobe.io/) 。 **[!DNL Privacy Service API]**

这些工具允许您发送和下发的消费者数据隐私 [!DNL GDPR] 请求 [!DNL CCPA]。

在阅读本文之前，我们建议阅读 [GDPR词汇](../data-security-and-privacy/aam-gdpr-glossary.md)[表和CCPA词汇表](aam-ccpa-glossary.md)，以更好地了解此处使用的术语。

您可以通过两种方式提交访问和删除消费者 [!DNL Audience Manager]数据的单个请求：

* 通过 [Privacy ServiceUI](https://privacyui.cloud.adobe.io/)。 请参阅此处 [的文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)。
* 通过 **[!DNL Privacy Service API]**。 请参阅此处 [的文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) 和此 [!DNL API] 处的 [参考](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)。

在发送单个Audience Manager隐私请求时，您可以提交任何Audience Manager标识符(ID)，如“标识符 **[”部分所述](data-privacy-ids.md)**，以及相应的命名空间ID（数据源ID）。

Privacy Service [支持](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 两种类型的请求： 数据访问和数据删除请求。

## 数据访问请求 {#access-data}

您可以通过Privacy ServiceUI [(此处](https://privacyui.cloud.adobe.io/) 的文档 [)或调用(](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)此处和 [!DNL Privacy Service API] 此处的引用文 [档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml))发送单独的数据访问请求。

Privacy Service [UI](https://privacyui.cloud.adobe.io/) 允许您通过使用或通过上传文件创建 [!UICONTROL Request Builder] 新的作业请求 [!DNL JSON] 。

要查看有效文 [!DNL JSON] 件的外观，可 [下载示例JSON](../data-security-and-privacy/assets/access_request.json)。

我们理解您承诺在法规规定的期限内遵守您的数据隐私要求。

## 数据删除请求{#delete-data}

您可以通过Privacy ServiceUI [(此处](https://privacyui.cloud.adobe.io/) 的文档 [)或调用](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)(此处的文 [!DNL Privacy Service API] 档和此处 [的API引用](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) )发送删除 [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)请求。

Privacy Service [UI](https://privacyui.cloud.adobe.io/) 允许您通过使用或通过上传文件创建 [!UICONTROL Request Builder] 新的作业请求 [!DNL JSON] 。

要查看有效文 [!DNL JSON] 件的外观，可 [下载示例JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe理解您承诺在30天内遵守您的数据隐私客户请求。 因此， [!DNL Adobe] 承诺尽快处理数据删除请求。

响应用户数据删除请求，删 [!DNL Audience Manager] 除与请求中包含的标识符相关 [!DNL Audience Manager] 的特征和区段。 此外，个 [!DNL Audience Manager] 人选择退出进一步数据收集的相应标识符 [!DNL Audience Manager] 和相应的ID映射将被删除。

当您在数据隐私请求中发送声明的ID( [!DNL CRM] 如跨设备ID或cookie ID)时， [!DNL Audience Manager] 将在所有链接设备（每个声明的ID最多100台设备）上执行必要的删除。

[!DNL Audience Manager] 将尝试通过向激活合作伙伴发送请求删除某些数据的数据主体的取消细分信息，向其通知删除请求。 但是，一些激活合作伙伴：

1. 不支持从和／或 [!DNL Audience Manager]
2. 无法接收频率低 [!DNL Audience Manager] 于30天的更新。 在这些情况下 [!DNL Audience Manager] ,激活无法以自动方式向合作伙伴发送删除请求 [!DNL Audience Manager]。

在这种情况下，您无法以自动方式向激活合作伙伴发送删除请求 [!DNL Audience Manager]。

下载我们 [的Partner Excel表](assets/AAM-Partners-October2019.xlsx) ，了解哪些激活 [!DNL Audience Manager] 合作伙伴支持取消细分。

## 退出请求 {#opt-out-requests}

[!DNL Audience Manager] 支持与选择退出管理相关的行业标准。 阅读以了解有关支持的退出类型的完整信息 [!DNL Audience Manager]。

虽然Privacy Service处理数据访问和删除请 [求](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，但是目前支持退出请求 [!DNL DCS API]。 阅读以了解退出呼叫的 [!DNL API] 外观。

### 全局退出请求

全球选择退出是所有品牌的选择退出 [!DNL Audience Manager] 和其 [!DNL Adobe Experience Cloud] 他解决方案。 下表列表了用于全局退出的方法：

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
   <td colname="col2"> <p>您 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 的隐私权选 </a> 择页面提供一键功能，让最终用户能够控制和选择退出Adobe Experience Cloud广告解决方案(包括Audience Manager)收集数据。 具体而言，请参 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 阅隐私选 </a> 择页面的业务客户部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接API调用Audience Manager </p> </td> 
   <td colname="col2"> <p>通过调用以下DCS API，并包含Audience Manager用户ID，您的用户可以选择退出所有品牌的 <a href="../../reference/ids-in-aam.md"> Audience Manager收集 </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>因此，我们将为提交 <code>demdex=NOTARGET</code> 的Audience Manager <code>dextp=NOTARGET</code> 用户ID设置和cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 </p> </td> 
   <td colname="col2"> <p>请参阅以下产品的选择退出和隐私设置： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android设备 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 设备 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户还可选择退出以通过访问我们行业标准合作伙伴的网站收集全球数据。

* [数字广告联盟(DAA)](https://optout.aboutads.info/?c=2#!/);
* [网络广告计划(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

按照上述选择退出请求执行操作：

* [!DNL Audience Manager] 只要用户不清除其浏览器cookie，将停止所有数据收集、分段或激活。
* 120天后，历史用户档案会从用户数据中删除。

### 使用声明的ID调用的合作伙伴级别退出

合作伙伴级别的退出功能允许您选择退出特定合作伙伴收集的 [!DNL Audience Manager] 用户。 您可以发送跨设备ID（包括ID和散列电子邮件地址）的合作伙伴级 [!DNL CRM] 别退出请求。

通过声明的ID调用执行合作伙伴级别的退出操作：

* CRM [ID已](../../reference/ids-in-aam.md) 被选择退出数据收集；
* 链接到CRM ID的[最后一个设备ID](../../reference/ids-in-aam.md)(Audience Manager唯 [一用户ID](../../reference/ids-in-aam.md) )已选择退出数据收集。
* [!DNL Audience Manager] 将停止对ID和链接到该ID的最后一个设备 [!DNL CRM] ID进行所有数据收集、分段或激活 [!DNL CRM] 操作；
* [!DNL Audience Manager] 从所有区段中 [!DNL CRM] 取消选择退出ID和最后一个设备ID;
* 目标合作伙伴将收到对ID和最 [!DNL CRM] 后一个设备ID的未细分请求。 取消分段适用于 [实时和批](data-privacy-requests.md#aam-partners-with-unsegmentation) 量目标。
* 未删除历史数据。

当接 [!DNL Audience Manager] 收到合作伙伴级退出请求时，由 [!DNL JSON] 返回的包 [!DNL DCS] 含错误代码171 [，其中包](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)含消息，而不是 [!UICONTROL "Encountered opt out tag"][!DNL Audience Manager] 用户ID。

您可以对和键值对发出声明 `d_cid` 的ID `d_cid_ic` 退出请求。 旧参数(如 `d_dpid` 和 `d_dpuuid` 仍可用)被视为已弃用。 请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

#### 选择退出CID和CID_IC

有关说明和语法，请参 [阅URL变量和Declared ID的语法](../../features/declared-ids.md#variables-and-syntax)。

| 使用 | 代码示例 |
|--- |--- |
| 数据提供程序ID和用户ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多个 `d_cid` 和 `d_cid_ic` 键值对。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 通过设备ID调用退出合作伙伴级别

合作伙伴级别的退出功能允许您选择退出特定合作伙伴收集的 [!DNL Audience Manager] 用户。 通过对DCS API进行以下调用，可以选择不在某个品牌的给定设备ID上进行 [数据收集](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 使用 | 代码示例 |
|--- |--- |
| [!DNL Audience Manager] ( [!DNL Unique User ID] )`uuid`。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| 一 [!DNL Experience Cloud] 个ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

阅读更多 `uuid`相关 `mid` 信息， `imsOrgId` 并在ID索 [引中阅读Audience Manager](/help/using/reference/ids-in-aam.md)。

通过设备ID调用执行合作伙伴级别的退出操作：

* 设备ID已选择退出数据收集。
* [!DNL Audience Manager] 将停止对合作伙伴的所有数据收集、分段或激活，继续获取设备ID。
* [!DNL Audience Manager] 从所有区段中取消对设备ID的分段；
* 目标合作伙伴将收到设备ID的未细分请求。 取消分段适用于 [实时和批](data-privacy-requests.md#aam-partners-with-unsegmentation) 量目标。
* 未删除历史数据。

## Audience Manager合作伙伴具有取消细分功能 {#aam-partners-with-unsegmentation}

为了帮助您自动处理激活数据隐私请求，将尝试通过向合作伙伴发送取消细分（或删除细分）信息，通知他们有关数据主体删除请求的信息。 [!DNL Audience Manager]

但是，我们的一些激活合作伙伴：

1. 无法支持来自和/ [!DNL Audience Manager] 或
2. 30天内无法多次 [!DNL Audience Manager] 接收更新。

在这种情况下，您无法以自动方式向激活合作伙伴发送删除请求 [!DNL Audience Manager]。

请查阅基 [于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md) ，了解哪些 [!DNL Audience Manager] 激活合作伙伴支持取消细分。

## 数据更正请求 {#correction}

由于 [!DNL Audience Manager] 不是数据源，因此在中进行数据更正的作用有限 [!DNL Audience Manager]。 更正可能意味着用户已请求取消不正确的特征／段的资格，或者被限定为所需的特征／段。

[!DNL Audience Manager] 客户可以根据用户用户档案选择捕获相关信号／特征／细分，并通过离线数据获取 [将此信息发送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 到 [!DNL Audience Manager]。 请注意，如果用户重复其行为，将继续获得符合原始特征和区段的资格。
