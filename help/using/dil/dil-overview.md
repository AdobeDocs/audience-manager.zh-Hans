---
description: DIL及其工作方式的概述。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: 了解Data Integration Library(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# 了解[!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此点之后不会开发[!DNL DIL]。 建议客户评估[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)。

[!DNL Audience Manager DIL]代码库中提供的概述、入门和代码方法。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]触发ID同步和URL目标。 如果[!DNL ID Service]缺失、过时或未配置，则会发生错误。
>
>我们建议您使用[!DNL Adobe Experience Platform Tags]实施和管理您的[!DNL DIL]和[!DNL Adobe Experience Platform Identity Service]库。

但是，您还可以从我们的GitHub页面下载最新Experience Cloud和[!DNL DIL]版本。 请参阅下面的下载链接：

* 下载[Adobe Experience Platform Identity服务](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL目的 {#purpose-dil}

[!UICONTROL DIL]是一个API库。 您可以将其视为[!DNL Adobe Audience Manager]的辅助代码正文。 不一定要使用[!DNL Audience Manager]，但[!UICONTROL DIL]提供的方法和函数意味着您不必开发自己的代码即可将数据发送到[!DNL Audience Manager]。 此外，[!UICONTROL DIL]与[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)提供的API不同。 该服务旨在跨不同的[!DNL Experience Cloud]解决方案管理访客身份。 相比之下，[!UICONTROL DIL]旨在：

* 进行事件调用并将数据发送到[数据收集服务器](../reference/system-components/components-data-collection.md)。
* 将数据发送到[目标](../features/destinations/destinations.md)。

## 获取和实施DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL]代码可在&#x200B;**[此处](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;下载。 请注意，从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]触发ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]缺失、过时或未配置，则会发生错误。

我们建议您改用[Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hans)，而不是使用[!UICONTROL DIL]并手动设置[!DNL Audience Manager]。 [!DNL Adobe Experience Platform Tags]是推荐的实施工具，因为它简化了代码部署、放置和版本管理。 有关[!DNL Adobe Experience Platform Tags]中的[Audience Manager扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=zh-Hans)的更多信息。

## 示例调用 {#sample-code}

[!UICONTROL DIL]在事件调用中向[!DNL Audience Manager]发送数据。 事件调用是指来自页面的XML HTTP请求。 它使用`POST`方法在请求正文中发送数据。

| 事件调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 正文 | 如下面的示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：
* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL用例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级别DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级别的DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模块](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [FlashDIL](/help/using/dil/dil-flash.md)
