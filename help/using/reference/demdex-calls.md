---
description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域拨号并从中接收数据。 这看起来似乎是Adobe在处理一个不同寻常的第三方领域，但事实并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域拨号并从中接收数据。 这看起来似乎是Adobe在处理一个不同寻常的第三方领域，但事实并非如此。 本节介绍demdex.net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 7286af6dd85a0464ccf52a88139d07cb151783e6
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 15%

---


# 了解对[!DNL Demdex]域{#understanding-calls-to-the-demdex-domain}的调用

[!DNL Audience Manager] 和向 [!DNL Adobe Experience Platform Identity Service] 域拨号和从域接收数 `demdex.net` 据。这看起来好像[!DNL Adobe]在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍`demdex.net`调用中的元素。

| 调用元素 | 描述 |
|---|---|
| `demdex.net` | 这是由[!DNL Adobe]控制的旧域。 它反映[!DNL Audience Manager]([!DNL Demdex])的原始、预获取名称。 [!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。很难更改此域，因为它与[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]和我们已安装的用户群紧密相连。 您可能会看到附加到传统`demdex.net`调用的其他前缀（例如`dcs.demdex.net`、`fast.demdex.net`等）。 无论前缀是什么，对`something.demdex.net`的调用始终是对[!DNL Adobe]的调用，而不是对某个未知或可疑的第三方域的调用。 |
| `dpm` | [!DNL DPM] 是的缩写 [!DNL Data Provider Match]。它告诉内部[!DNL Adobe]系统，来自[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]的调用正在传递客户数据以进行同步或请求ID。 这是您从[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]中看到的最常见的`demdex.net`调用。 <br><br>[!DNL DPM] 呼叫基础知识： <ul><li>[!DNL Audience Manager]:来自 [!DNL DPM] 的调 [!DNL Audience Manager] 用会向和发 [!DNL Data Collection Servers] 送数据 [!DNL Profile Cache Servers]。请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]:来 [!DNL DPM] 自的调 [!DNL Adobe Experience Cloud ID Service] 用是请求访客ID。请参阅[Cookie和Adobe Experience Platform标识服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html)和[Adobe Experience Platform标识服务如何请求和设置ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客户可以更 [!DNL DPM] 改域名中的前缀。请参阅[audienceManager Server和audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-am.html)

