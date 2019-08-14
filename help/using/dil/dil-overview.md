---
description: 概述DIL及其工作原理。
seo-description: 概述DIL及其工作原理。
seo-title: 了解数据集成库(DIL)
keywords: 'dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil、dil，dil，dil，dil， '
solution: Audience Manager
title: 了解数据集成库(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982 f27 b36 e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 了解数据集成库(DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL代码库中提供的概述、入门和代码方法。

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依赖ID服务来触发ID同步和URL目标。如果ID服务丢失、旧或未配置，则会发生错误。
>
>我们建议您使用Adobe Launch来实施和管理您的DIL和Experience Cloud ID服务库。

但是，您还可以从我们的GitHub页面下载最新的Experience Cloud和DIL版本。请参阅下面的下载链接：

* 下载 [Experience Cloud ID服务](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL] 是API库。您可以将它视为辅助代码的一体 [!DNL Adobe Audience Manager]。它不需要使用 [!DNL Audience Manager]，但方法和函数 [!UICONTROL DIL] 意味着您不必开发自己的代码 [!DNL Audience Manager]来发送数据。此外， [!UICONTROL DIL] 与 [Experience Cloud ID服务提供的API不同](https://marketing.adobe.com/resources/help/en_US/mcvid/)。该服务旨在管理 [!DNL Experience Cloud] 不同解决方案中的访客身份。相反， [!UICONTROL DIL] 设计为：

* 进行事件调用并将数据发送到 [Data Collection Server](../reference/system-components/components-data-collection.md)。
* 将数据发送到 [目标](../features/destinations/destinations.md)。

## 获取和实施DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL] 可在此处下载 **[代码](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依赖ID服务来触发ID同步和URL目标。如果ID服务丢失、旧或未配置，则会发生错误。

我们建议您改用Adobe [!UICONTROL DIL][!DNL Audience Manager][Launch](https://docs.adobelaunch.com/) ，而不是手动设置和设置。[!DNL Adobe Launch] 是建议的实施工具，因为它简化了代码部署、放置和版本管理。阅读有关Adobe Launch中 [Audience Manager扩展](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 的更多信息。

Adobe Launch是 [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM])的后继产品。

## 示例调用 {#sample-code}

[!UICONTROL DIL] 将数据发送 [!DNL Audience Manager] 到活动调用中。事件调用是页面中的XML HTTP请求。它使用 `POST` 一种方法在请求的正文中发送数据。

| 活动调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Body | 如下面示例所示，DIL将数据作为关键值对传递。特殊前缀字符将键值对识别为Audience Manager或合作伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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