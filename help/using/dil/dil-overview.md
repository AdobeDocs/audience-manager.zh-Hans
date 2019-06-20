---
description: 概述DIL及其工作原理。
seo-description: 概述DIL及其工作原理。
seo-title: 了解数据集成库(DIL)
solution: Audience Manager
title: 了解数据集成库(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982 f27 b36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL代码库中提供的概述、入门和代码方法。

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依赖ID服务来触发ID同步和URL目标。如果ID服务丢失、旧或未配置，则会发生错误。
>
>我们建议您使用Adobe Launch来实施和管理您的DIL和Experience Cloud ID服务库。

但是，您还可以从我们的GitHub页面下载最新的Experience Cloud和DIL版本。请参阅下面的下载链接：

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] 是API库。You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don&#39;t have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] 可在此处下载 **[代码](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依赖ID服务来触发ID同步和URL目标。如果ID服务丢失、旧或未配置，则会发生错误。

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] 是建议的实施工具，因为它简化了代码部署、放置和版本管理。Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] 将数据发送 [!DNL Audience Manager] 到活动调用中。事件调用是页面中的XML HTTP请求。It uses a `POST` method to send data in the body of the request.

| 活动调用元素 | 描述 |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Body | 如下面示例所示，DIL将数据作为关键值对传递。Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另请参阅：
* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
* [DCS API调用的支持属性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相关链接

* [DIL使用案例和代码示例](/help/using/dil/dil-use-cases.md)
* [类级DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [实例级DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模块](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)