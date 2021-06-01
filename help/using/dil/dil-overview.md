---
description: DIL及其工作方式概述。
seo-description: DIL及其工作方式概述。
seo-title: 了解数据集成库 (DIL)
keywords: 'dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil '
solution: Audience Manager
title: 了解数据集成库 (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL实施
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 16%

---

# 了解[!DNL Data Integration Library](DIL){#understanding-the-data-integration-library-dil}

[!DNL Audience Manager DIL]代码库中提供的概述、快速入门和代码方法。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]来触发ID同步和URL目标。 如果[!DNL ID Service]缺失、旧或未配置，则会发生错误。
>
>我们建议您使用[!DNL Adobe Experience Platform Launch]来实施和管理[!DNL DIL]和[!DNL Adobe Experience Platform Identity Service]库。

但是，您也可以从我们的GitHub页面下载最新Experience Cloud和[!DNL DIL]版本。 请参阅下面的下载链接：

* 下载[Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL{#purpose-dil}的用途

[!UICONTROL DIL] 是API库。您可以将其视为[!DNL Adobe Audience Manager]的帮助程序代码正文。 使用[!DNL Audience Manager]并不需要，但[!UICONTROL DIL]提供的方法和函数意味着您无需开发自己的代码即可将数据发送到[!DNL Audience Manager]。 此外， [!UICONTROL DIL]与[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)提供的API不同。 该服务旨在跨不同的[!DNL Experience Cloud]解决方案管理访客身份。 相反，[!UICONTROL DIL]的设计目标是：

* 进行事件调用并将数据发送到[数据收集服务器](../reference/system-components/components-data-collection.md)。
* 将数据发送到[目标](../features/destinations/destinations.md)。

## 获取和实施DIL代码{#get-implement-dil-code}

[!UICONTROL DIL] 代码可在此处 **[下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。请注意，从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)、版本3.3或更高版本具有硬依赖关系。 它依赖[!DNL ID Service]来触发ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]缺失、旧或未配置，则会发生错误。

我们建议您改用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)，而不是使用[!UICONTROL DIL]手动设置[!DNL Audience Manager]。 [!DNL Adobe Experience Platform Launch] 是推荐的实施工具，因为它简化了代码部署、放置和版本管理。有关[!DNL Adobe Experience Platform Launch]中[Audience Manager扩展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)的更多信息。

## 示例调用{#sample-code}

[!UICONTROL DIL] 在事件调 [!DNL Audience Manager] 用中向发送数据。事件调用是来自您页面的XML HTTP请求。 它使用`POST`方法发送请求正文中的数据。

| 事件调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法：`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 正文 | 如以下示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或合作伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：
* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API 调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL 用例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级别 DIL 方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级别 DIL 方法](/help/using/dil/dil-instance-methods.md)
* [DIL 模块](/help/using/dil/dil-modules.md)
* [DIL 工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
