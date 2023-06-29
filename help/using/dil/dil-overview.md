---
description: DIL及其工作方式的概述。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: 了解数据集成库 (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# 了解 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发电子烟产品。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
><br>
>现有客户可以继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越了这一点。 建议客户评估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
><br>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

中提供的概述、入门指南和代码方法 [!DNL Audience Manager DIL] 代码库。

>[!IMPORTANT]
>
>从版本8.0（2018年8月发布）开始， [!UICONTROL DIL] 对 [Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html)，版本3.3或更高版本。 它依赖于 [!DNL ID Service] 以触发ID同步和URL目标。 在以下情况下会发生错误： [!DNL ID Service] 缺失、陈旧或未配置。
>
>我们建议您使用 [!DNL Adobe Experience Platform Tags] 实施和管理 [!DNL DIL] 和 [!DNL Adobe Experience Platform Identity Service] 库。

但是，您还可以下载最新的Experience Cloud和 [!DNL DIL] 从GitHub页面发布。 请参阅下面的下载链接：

* 下载 [Adobe Experience Platform Identity服务](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下载 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL目的 {#purpose-dil}

[!UICONTROL DIL] 是一个API库。 您可以将其视为帮助程序代码的主体 [!DNL Adobe Audience Manager]. 不需要使用 [!DNL Audience Manager]，但方法和函数 [!UICONTROL DIL] 提供意味着您无需开发自己的代码即可将数据发送到 [!DNL Audience Manager]. 另外， [!UICONTROL DIL] 与提供的API不同 [Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html). 该服务旨在跨不同用户管理访客身份 [!DNL Experience Cloud] 解决方案。 相比之下， [!UICONTROL DIL] 旨在：

* 进行事件调用并将数据发送到 [数据收集服务器](../reference/system-components/components-data-collection.md).
* 将数据发送到 [目标](../features/destinations/destinations.md).

## 获取和实施DIL代码 {#get-implement-dil-code}

[!UICONTROL DIL] 代码可供下载 **[此处](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 请注意，从版本8.0（2018年8月发布）开始， [!UICONTROL DIL] 对 [Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html)，版本3.3或更高版本。 它依赖于 [!DNL ID Service] 触发ID同步和 [!DNL URL destinations]. 在以下情况下会发生错误： [!DNL ID Service] 缺失、陈旧或未配置。

而不是使用 [!UICONTROL DIL] 和设置 [!DNL Audience Manager] 手动，我们建议您使用 [Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 而是。 [!DNL Adobe Experience Platform Tags] 是推荐的实施工具，因为它简化了代码部署、放置和版本管理。 详细了解 [Audience Manager扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 在 [!DNL Adobe Experience Platform Tags].

## 示例调用 {#sample-code}

[!UICONTROL DIL] 发送数据到 [!DNL Audience Manager] 在事件调用中。 事件调用是来自页面的XML HTTP请求。 它使用 `POST` 在请求正文中发送数据的方法。

| 事件调用元素 | 描述 |
|--- |--- |
| URL | DIL事件调用使用以下语法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 正文 | 如下面的示例所示，DIL将数据作为键值对传递。 特殊前缀字符将键值对标识为Audience Manager或合作伙伴变量。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
