---
description: DIL及其工作方式的概述。
seo-description: DIL及其工作方式的概述。
seo-title: 了解数据集成库(DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: 了解数据集成库(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# 了解 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

代码库中提供的概述、快速入门和代 [!DNL Audience Manager DIL] 码方法。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开 [!UICONTROL DIL] 始，对Adobe Experience Platform身份服务 [版本3](https://docs.adobe.com/content/help/en/id-service/using/home.html).3或更高版本的依赖性很强。 它依赖于触 [!DNL ID Service] 发ID同步和URL目标。 缺少、旧或 [!DNL ID Service] 未配置时出错。
>
>我们建议您使 [!DNL Adobe Experience Platform Launch] 用来实施和管理您 [!DNL DIL] 的库 [!DNL Adobe Experience Platform Identity Service] 和库。

但是，您也可以从GitHub页面下载 [!DNL DIL] 最新Experience Cloud和版本。 请参阅以下下载链接：

* 下载 [Adobe Experience Platform标识服务](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL] 是API库。 您可以将它视为帮助代码的正文 [!DNL Adobe Audience Manager]。 它不需要使用， [!DNL Audience Manager]但方法和函数 [!UICONTROL DIL] 提供的含义是您不必开发自己的代码即可将数据发送到 [!DNL Audience Manager]。 此外， [!UICONTROL DIL] 它与Adobe Experience Platform身份服务提供的 [API不同](https://docs.adobe.com/content/help/en/id-service/using/home.html)。 该服务旨在跨不同的解决方案管理访客 [!DNL Experience Cloud] 身份。 相比之下， [!UICONTROL DIL] 其设计目标是：

* 发出事件调用，并将数据发 [送到数据收集服务器](../reference/system-components/components-data-collection.md)。
* 将数据发送 [到目标](../features/destinations/destinations.md)。

## 获取和实现DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL] 代码可从此处 **[下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 请注意，从版本8.0（2018年8月发布）[!UICONTROL DIL]开始，对Adobe Experience Platform身份服务[版本3](https://docs.adobe.com/content/help/en/id-service/using/home.html).3或更高版本的依赖性很强。 它依赖于触[!DNL ID Service]发ID同步和[!DNL URL destinations]。 缺少、旧或[!DNL ID Service]未配置时出错。

我们建议您改 [!UICONTROL DIL] 用Adobe Experience Platform [!DNL Audience Manager] 启动，而不是手动 [操作和设置](https://docs.adobelaunch.com/) 。 [!DNL Adobe Experience Platform Launch] 是推荐的实施工具，因为它简化了代码部署、放置和版本管理。 请阅读中有关 [Audience Manager扩展](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 的更多 [!DNL Adobe Experience Platform Launch]。

[!DNL Adobe Experience Platform Launch] 是Adobe Dynamic [Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM])的后继者。

## 示例调用 {#sample-code}

[!UICONTROL DIL] 在事件呼 [!DNL Audience Manager] 叫中发送数据。 事件调用是来自您页面的XML HTTP请求。 它使用一 `POST` 种方法在请求主体中发送数据。

| 事件呼叫元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 身体 | 如以下示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：
* [密钥变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API调用支持的属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL用例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模块](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)