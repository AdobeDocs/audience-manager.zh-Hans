---
description: Audience Manager和Adobe Experience Platform Identity服务会调用demdex.net域并从中接收数据。 这看起来像Adobe正在与某个不寻常的第三方域合作，但事实并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: 了解Demdex域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# 了解[!DNL Demdex]域的调用 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager]和[!DNL Adobe Experience Platform Identity Service]调用并接收来自`demdex.net`域的数据。 这可能看起来像[!DNL Adobe]正在处理一个不寻常的第三方域，但情况并非如此。 本节介绍`demdex.net`调用中的元素。

| 调用元素 | 描述 |
|---|---|
| `demdex.net` | 这是由[!DNL Adobe]控制的旧域。 它反映了[!DNL Audience Manager] ([!DNL Demdex])的原始收购前名称。 [!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。很难更改此域，因为它与[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]和我们的已安装用户群深度交织在一起。 您可能会看到附加到旧版`demdex.net`调用的其他前缀（例如，`dcs.demdex.net`、`fast.demdex.net`等）。 无论前缀如何，对`something.demdex.net`的调用始终是对[!DNL Adobe]的调用，而不是对未知或可疑的第三方域的调用。 |
| `dpm` | [!DNL DPM]是[!DNL Data Provider Match]的缩写。 它告知内部[!DNL Adobe]系统，来自[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]的调用正在传递客户数据以进行同步或正在请求ID。 这是您将会从`demdex.net`或[!DNL Audience Manager]看到的最常见的[!DNL Adobe Experience Cloud ID Service]调用。 <br><br>[!DNL DPM]调用基础知识： <ul><li>[!DNL Audience Manager]：来自[!DNL DPM]的[!DNL Audience Manager]调用将数据发送到[!DNL Data Collection Servers]和[!DNL Profile Cache Servers]。 请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]：来自[!DNL DPM]的[!DNL Adobe Experience Cloud ID Service]调用是对访客ID的请求。 请参阅[Cookie和Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans)和[Adobe Experience Platform Identity服务如何请求和设置ID](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=zh-Hans)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service]客户可以更改域名中的[!DNL DPM]前缀。 请参阅[audienceManager服务器和audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=zh-Hans)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)
>* [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=zh-Hans)
