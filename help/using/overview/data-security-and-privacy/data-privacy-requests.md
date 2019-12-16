---
description: 本文档涵盖与Audience manager的数据隐私法规合规性相关的技术细节。
seo-description: 本文档涵盖与Audience manager的数据隐私法规合规性相关的技术细节。
seo-title: 数据隐私请求
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 数据隐私请求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# 数据隐私请求 {#data-privacy-requests}

## 概述 {#overview}

本文档概述了如何管理单个数据隐私和退出请求，您可以通过 [Privacy Service UI和](https://gdprui.cloud.adobe.io/) Audience Manager发送这些请求 **[!DNL Privacy Service API]**。

这些工具允许您发送根据GDPR和CCPA提出的消费者数据隐私请求。

在阅读本文之前，我们建议阅读 [GDPR词汇表](../data-security-and-privacy/aam-gdpr-glossary.md)[和CCPA词汇表](aam-ccpa-glossary.md)，以更好地了解此处使用的术语。

您可以通过两种方式提交个人请求以从Audience manager访问和删除消费者数据：

* 通过隐 [私服务UI](https://gdprui.cloud.adobe.io/)。 请参阅此处 [的文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)。
* 通过 **[!DNL Privacy Service API]**。 请参阅此处 [的文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) ，以及此处的API [参考](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)。

在发送单个数据隐私请求时，您可以提交任何Audience Manager标识符(ID)，如 **[Audience Manager标识符部分中所述](data-privacy-ids.md)** ，以及它们各自的命名空间ID（数据源ID）。

隐 [私服务支持](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 两种类型的请求：数据访问和数据删除请求。

## 数据访问请求 {#access-data}

您可以通过隐私服务UI [(](https://gdprui.cloud.adobe.io/) 此处的文档 [)或通过调用](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)( [!DNL Privacy Service API] 此处的文档和 [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)此处的引用)发送个人访问请求。

隐 [私服务UI](https://gdprui.cloud.adobe.io/) 允许您通过使用或上传文件来创建 [!UICONTROL Request Builder] 新的作业请 [!DNL JSON] 求。

要查看有效文 [!DNL JSON] 件的外观，可下 [载示例JSON](../data-security-and-privacy/assets/access_request.json)。

我们理解您承诺在法律规定的期限内遵守您的数据隐私要求。

## 数据删除请求{#delete-data}

您可以通过 [Privacy Service UI](https://gdprui.cloud.adobe.io/) ( [此处的文档](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md))或通过调用（此处的文档和API reference Deletion）发送数据请 [!DNL Privacy Service API] 求 [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)（此处的API ReferenceDeletion）。

隐 [私服务UI](https://gdprui.cloud.adobe.io/) 允许您通过使用或上传文件来创建 [!UICONTROL Request Builder] 新的作业请 [!DNL JSON] 求。

要查看有效文 [!DNL JSON] 件的外观，可下 [载示例JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe理解您承诺在30天内遵守您的数据隐私客户要求。 因此，Adobe承诺尽快处理您的数据删除请求。

为响应您的消费者数据删除请求，Audience manager将删除与请求中包含的Audience Manager标识符关联的特征和区段。 此外，Audience Manager选择不再收集进一步数据的个人的相应Audience manager标识符和相应的ID映射也将被删除。

当您在数据隐私请求中发送声明的ID（如跨设备ID或cookie ID）时，Audience manager将对所有链接的设备（每个声明的ID最多100台设备）执行必要的删除操作。 [!DNL CRM]

Audience manager将尝试通过向激活合作伙伴发送请求删除某些数据的数据主体的取消细分信息，向他们通知删除请求。 但是，一些激活合作伙伴：

1. 无法支持从Audience manager和／或
2. 无法从Audience manager接收频率低于30天的更新。 在这些情况下，Audience manager客户无法通过Audience manager向激活合作伙伴自动发送删除请求。

在这些情况下，您无法通过Audience manager以自动方式向激活合作伙伴发送删除请求。

下载我们 [的Partner excel表](assets/AAM-Partners-October2019.xlsx) ，了解哪些Audience manager激活合作伙伴支持取消细分。

## 退出请求 {#opt-out-requests}

Audience manager支持关于退出管理的行业标准。 阅读以了解有关Audience manager支持的退出类型的完整信息。

虽然数据访问和删除请求是通过隐私服务处理的 [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，但目前DCS API支持退出请求。 阅读以了解退出API调用的外观。

### 全局退出请求

全球选择退出是指在Audience manager和其他适用于所有品牌的Adobe Experience cloud解决方案中选择退出。 下表列出了用于全局退出的方法：

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
   <td colname="col2"> <p>您 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 的隐私权选择页 </a> 面提供一键功能，让您的最终用户能够控制Adobe Experience cloud广告解决方案（包括Audience Manager）收集和选择退出数据。 具体而言，请参阅“ <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 隐私权选择” </a> 页面的业务客户部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接向Audience manager调用API </p> </td> 
   <td colname="col2"> <p>通过调用以下DCS API并包含 <a href="../../reference/ids-in-aam.md"> Audience Manager用户ID，您的用户可以退出所有Audience Manager品牌的数据收集 </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>因此，我们将为已提交的Audience Manager <code>demdex=NOTARGET</code> 用 <code>dextp=NOTARGET</code> 户ID设置和Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 </p> </td> 
   <td colname="col2"> <p>请参阅以下选项和隐私设置： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android设备 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 设备 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户还可以通过访问我们行业标准合作伙伴的网站，选择退出全球数据收集。

* [数字广告联盟(DAA)](https://optout.aboutads.info/?c=2#!/);
* [网络广告计划(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

按照上述选择退出请求执行操作：

* 只要用户不清除其浏览器Cookie,Audience manager将停止所有数据收集、细分或激活。
* 120天后，历史数据将从用户配置文件中删除。

### 使用Declared ID调用的合作伙伴级别退出

合作伙伴级别的选择退出功能允许您从特定Audience manager合作伙伴收集的数据中选择退出用户。 您可以发送跨设备ID（包括CRM ID和哈希电子邮件地址）的合作伙伴级别退出请求。

使用声明的ID调用执行合作伙伴级别的退出操作：

* [CRM ID被选择](../../reference/ids-in-aam.md) ，不会收集数据；
* 与[CRM ID链接的最后一个设备ID(](../../reference/ids-in-aam.md)Audience Manager唯一用户ID [](../../reference/ids-in-aam.md) )已选择不进行数据收集。
* Audience manager将停止针对CRM ID和链接到CRM ID的最后一个设备ID的所有数据收集、细分或激活；
* Audience manager从所有细分中取消细分选择退出的CRM ID和最后一个设备ID;
* 目标合作伙伴将收到对CRM ID和最后一个设备ID的取消细分请求。 取消分段适用于 [实时目标](data-privacy-requests.md#aam-partners-with-unsegmentation) 和批处理目标。
* 不会删除历史数据。

当Audience manager收到合作伙伴级别的退出请求时，DCS返回的JSON包含错误代码171 [，其中包含消息](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]，而不是Audience manager用户ID。

您可以对和键值对发出声明的ID `d_cid` 退出 `d_cid_ic` 请求。 旧参数(如和 `d_dpid` 仍可 `d_dpuuid` 用，但被视为已弃用。 请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

#### 使用CID和CID_IC选择退出

有关说明和语法，请参阅 [URL变量和Declared ID的语法](../../features/declared-ids.md#variables-and-syntax)。

| 选择退出使用 | 代码示例 |
|--- |--- |
| 数据提供者ID和用户ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多个d_cid和d_cid_ic键值对。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 通过设备ID调用退出合作伙伴级别

合作伙伴级别的选择退出功能允许您从特定Audience manager合作伙伴收集的数据中选择退出用户。 通过对 [DCS API进行以下调用，可以选择退出品牌的给定设备ID上的数据收集](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 选择退出使用 | 代码示例 |
|--- |--- |
| Audience Manager唯一用户ID(`uuid`)。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

在Audience manager中， `uuid`阅读 `mid` ID索 `imsOrgId` 引，了解更多相关信息 [](/help/using/reference/ids-in-aam.md)。

通过设备ID调用执行合作伙伴级别的退出操作：

* 设备ID已选择退出数据收集。
* Audience manager将停止为合作伙伴收集、细分或激活所有数据，以后将停止设备ID。
* Audience manager从所有细分中取消分段设备ID;
* 目标合作伙伴将收到设备ID的取消区段请求。 取消分段适用于 [实时目标](data-privacy-requests.md#aam-partners-with-unsegmentation) 和批处理目标。
* 不会删除历史数据。

## 具有取消细分功能的Audience manager合作伙伴 {#aam-partners-with-unsegmentation}

为了帮助您自动处理消费者数据隐私请求，Audience manager将尝试通过向激活合作伙伴发送取消细分（或删除细分）信息，通知激活合作伙伴有关数据主体删除请求的信息。

但是，我们的一些激活合作伙伴：

1. 无法支持Audience Manager和／或Audience Manager的取消细分请求
2. 无法在30天内更频繁地从Audience manager接收更新。

在这些情况下，您无法通过Audience manager以自动方式向激活合作伙伴发送删除请求。

下载我们 [的Partner excel表](assets/AAM-Partners-October2019.xlsx) ，了解哪些Audience manager激活合作伙伴支持取消细分。

## 数据更正请求 {#correction}

由于Audience manager不是数据源，因此Audience manager中用于数据更正的角色有限。 更正可能意味着用户已请求取消其不正确的特征／段的资格，或者将其限定为所需的特征／段。

Audience Manager客户可以根据用户档案选择捕获相关信号／特征／细分，并通过离线数据获取将 [这些信息发送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 到Audience Manager。 请注意，如果用户重复其行为，他们将继续获得符合原始特征和区段的资格。
