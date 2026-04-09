---
description: DIL及其工作方式的概述。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: 了解Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
TQID: https://experienceleague.adobe.com/SyaOtcmDa6IwaoPVjv-G6zvdnFa7ZVDaGP7MaX4RaBk
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
  - id: f8c1669e-86ba-49c4-b622-9dfa07854df8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 473
ht-degree: 1%

---

# 了解[!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此之后不会开发[!DNL DIL]。 建议客户评估[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)。

[!DNL Audience Manager DIL]代码库中提供的概述、入门和代码方法。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]触发ID同步和URL目标。 如果[!DNL ID Service]缺失、过时或未配置，则会发生错误。
>
>我们建议您使用[!DNL Adobe Experience Platform Tags]实施和管理您的[!DNL DIL]和[!DNL Adobe Experience Platform Identity Service]库。

但是，您还可以从我们的GitHub页面下载最新的Experience Cloud和[!DNL DIL]版本。 请参阅下面的下载链接：

* 下载[Adobe Experience Platform Identity服务](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL]是一个API库。 您可以将其视为[!DNL Adobe Audience Manager]的辅助代码正文。 不一定要使用[!DNL Audience Manager]，但[!UICONTROL DIL]提供的方法和函数意味着您不必开发自己的代码即可将数据发送到[!DNL Audience Manager]。 此外，[!UICONTROL DIL]与[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)提供的API不同。 该服务旨在跨不同的[!DNL Experience Cloud]解决方案管理访客身份。 相比之下，[!UICONTROL DIL]旨在：

* 进行事件调用并将数据发送到[数据收集服务器](../reference/system-components/components-data-collection.md)。
* 将数据发送到[目标](../features/destinations/destinations.md)。

## 获取和实施DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL]代码可在&#x200B;**[此处](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;下载。 请注意，从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]触发ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]缺失、过时或未配置，则会发生错误。

我们建议您改用[!UICONTROL DIL]Adobe Experience Platform标记[!DNL Audience Manager]，而不是使用[并手动设置](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hans)。 [!DNL Adobe Experience Platform Tags]是推荐的实施工具，因为它简化了代码部署、放置和版本管理。 有关[中](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=zh-Hans)Audience Manager扩展[!DNL Adobe Experience Platform Tags]的更多信息。

## 示例调用 {#sample-code}

[!UICONTROL DIL]在事件调用中向[!DNL Audience Manager]发送数据。 事件调用是指来自页面的XML HTTP请求。 它使用`POST`方法在请求正文中发送数据。

| 事件调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 正文 | 如下面的示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或合作伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：

* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL用例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级别DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级别的DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模块](/help/using/dil/dil-modules.md)
* [DIL Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
