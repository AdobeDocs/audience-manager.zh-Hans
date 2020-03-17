---
description: DIL及其工作方式的概述。
seo-description: DIL及其工作方式的概述。
seo-title: 了解数据集成库(DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: 了解数据集成库(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 了解数据集成库(DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL代码库中提供的概述、入门和代码方法。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开 [!UICONTROL DIL] 始，对 [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)，版本3.3或更高版本的依赖性很强。 它依赖ID服务触发ID同步和URL目标。 如果ID服务缺失、旧或未配置，则会发生错误。
>
>我们建议您使用Adobe Experience Platform Launch来实施和管理您的DIL和Adobe Experience Platform Identity Service库。

但是，您也可以从我们的GitHub页面下载最新的Experience Cloud和DIL版本。 请参阅以下下载链接：

* 下载 [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL] 是API库。 您可以将它看作是帮助代码的正文 [!DNL Adobe Audience Manager]。 它不必使用，但 [!DNL Audience Manager]是方法和函数提供 [!UICONTROL DIL] 的含义是您不必开发自己的代码即可向其发送数据 [!DNL Audience Manager]。 此外， [!UICONTROL DIL] 它与 [Adobe Experience Platform Identity Service提供的API不同](https://marketing.adobe.com/resources/help/en_US/mcvid/)。 该服务旨在跨不同的解决方案管理访客 [!DNL Experience Cloud] 身份。 相反，设计 [!UICONTROL DIL] 的目标是：

* 发出事件调用并将数据发送到数 [据收集服务器](../reference/system-components/components-data-collection.md)。
* 将数据发送到 [目标](../features/destinations/destinations.md)。

## 获取和实施DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL] 此处可下载代 **[码](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 请注意，从版本8.0（2018年8月发布）开始，[!UICONTROL DIL]对[](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience Platform Identity Service版本3.3或更高版本的依赖性很强。 它依赖ID服务触发ID同步和URL目标。 如果ID服务缺失、旧或未配置，则会发生错误。

我们建议您改 [!UICONTROL DIL] 用 [!DNL Audience Manager] Adobe Experience Platform Launch，而 [不是手动操作和设置](https://docs.adobelaunch.com/) 。 [!DNL Adobe Experience Platform Launch] 是推荐的实施工具，因为它简化了代码部署、放置和版本管理。 阅读有关Adobe Experience Platform Launch [中Audience Manager扩展](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 的更多信息。

Adobe Experience Platform Launch是 [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM])的后续工具。

## 示例调用 {#sample-code}

[!UICONTROL DIL] 在事件调用 [!DNL Audience Manager] 中向发送数据。 事件调用是页面中的XML HTTP请求。 它使用一 `POST` 种方法在请求主体中发送数据。

| 事件调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 身体 | 如以下示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或合作伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：
* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL用例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模块](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)