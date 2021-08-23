---
description: Audience Manager和Adobe Experience Platform Identity服务会调用demdex.net域并从中接收数据。 这看起来像Adobe在与一个不同寻常的第三方领域合作，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager和Adobe Experience Platform Identity服务会调用demdex.net域并从中接收数据。 这看起来像Adobe在与一个不同寻常的第三方领域合作，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 参考
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 9%

---

# 了解对[!DNL Demdex]域的调用 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 和调 [!DNL Adobe Experience Platform Identity Service] 用并从域接收数 `demdex.net` 据。这看起来好像[!DNL Adobe]正在使用一个不同寻常的第三方域，但情况并非如此。 本节介绍`demdex.net`调用中的元素。

| 调用元素 | 描述 |
|---|---|
| `demdex.net` | 这是由[!DNL Adobe]控制的旧版域。 它反映了[!DNL Audience Manager]([!DNL Demdex])的收购前原始名称。 [!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。很难更改此域，因为它与[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]和我们已安装的用户群紧密相连。 您可能会看到附加到旧版`demdex.net`调用的其他前缀（例如`dcs.demdex.net`、`fast.demdex.net`等）。 无论前缀是什么，对`something.demdex.net`的调用始终都是对[!DNL Adobe]的调用，而不是对某些未知或可疑的第三方域的调用。 |
| `dpm` | [!DNL DPM] 是的缩写 [!DNL Data Provider Match]。它告知内部[!DNL Adobe]系统，来自[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]的调用正在传递客户数据以进行同步或正在请求ID。 这是您将在[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]中看到的最常见`demdex.net`调用。 <br><br>[!DNL DPM] 调用基础知识： <ul><li>[!DNL Audience Manager]:来自 [!DNL DPM] 的调用 [!DNL Audience Manager] 会向和发送 [!DNL Data Collection Servers] 数据 [!DNL Profile Cache Servers]。请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]:来自 [!DNL DPM] 的调 [!DNL Adobe Experience Cloud ID Service] 用是对访客ID的请求。请参阅[Cookie和Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)和[Adobe Experience Platform Identity服务如何请求和设置ID](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客户可以更 [!DNL DPM] 改域名中的前缀。请参阅[audienceManager Server和audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

