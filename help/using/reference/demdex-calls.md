---
description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域发出调用并从中接收数据。 这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域发出调用并从中接收数据。 这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 和向 [!DNL Adobe Experience Platform Identity Service] 域拨号和从域接收数 `demdex.net` 据。 这似乎与一 [!DNL Adobe] 个不同寻常的第三方领域有关，但事实并非如此。 本节介绍呼叫中的 `demdex.net` 元素。

| 调用元素 | 描述 |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. 它反映()的原始、收购前 [!DNL Audience Manager] 名称[!DNL Demdex]。 [!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。很难更改此域，因为它与已安装的用户群 [!DNL Audience Manager]、用户 [!DNL Adobe Experience Cloud ID Service]群和用户群紧密相连。 您可能会看到附加到旧 `demdex.net` 版调用的其他前缀 `dcs.demdex.net`( `fast.demdex.net`例如，等等)。 无论前缀是什么，对的调 `something.demdex.net` 用始终是对某个未知或 [!DNL Adobe] 可疑的第三方域的调用，而不是对某个第三方域的调用。 |
| `dpm` | [!DNL DPM] 是的缩写 [!DNL Data Provider Match]。 It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. 这是您从或 `demdex.net` 将看到的最常见 [!DNL Audience Manager] 的呼叫 [!DNL Adobe Experience Cloud ID Service]。 <br><br>[!DNL DPM] 呼叫基础知识： <ul><li>[!DNL Audience Manager]: 来 [!DNL DPM] 自的调 [!DNL Audience Manager] 用将数据发送 [!DNL Data Collection Servers] 到和 [!DNL Profile Cache Servers]。 请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]: 来 [!DNL DPM] 自的调 [!DNL Adobe Experience Cloud ID Service] 用是请求访客ID。 请参 [阅Cookie和Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html)[以及Adobe Experience Platform身份服务如何请求和设置ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客户可以更 [!DNL DPM] 改域名中的前缀。 请参 [阅audienceManager Server和audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-am.html)

