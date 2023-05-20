---
description: Audience Manager和Adobe Experience Platform Identity服務會呼叫並從demdex.net網域接收資料。 Adobe似乎正與不尋常的第三方網域合作，但情況並非如此。 本節說明demdex.net呼叫中的元素。
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 8%

---

# 瞭解對的呼叫 [!DNL Demdex] 網域 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 和 [!DNL Adobe Experience Platform Identity Service] 呼叫並從接收資料 `demdex.net` 網域。 這可能看起來像 [!DNL Adobe] 使用不尋常的協力廠商網域，但情況並非如此。 本節說明中的元素 `demdex.net` 呼叫。

| 呼叫元素 | 描述 |
|---|---|
| `demdex.net` | 這是由控制的舊網域 [!DNL Adobe]. 它反映收購前的原始名稱 [!DNL Audience Manager] ([!DNL Demdex])。 [!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。由於此網域與緊密交織在一起，因此很難變更 [!DNL Audience Manager]，則 [!DNL Adobe Experience Cloud ID Service]，以及我們的已安裝使用者群。 您可能會看到其他附加至舊版的前置詞 `demdex.net` 呼叫(例如 `dcs.demdex.net`， `fast.demdex.net`、等)。 無論首碼為何，都會呼叫 `something.demdex.net` 永遠是呼叫 [!DNL Adobe] 而不是未知或可疑的第三方網域。 |
| `dpm` | [!DNL DPM] 是的縮寫 [!DNL Data Provider Match]. 它告訴內部， [!DNL Adobe] 呼叫來源的系統 [!DNL Audience Manager] 或 [!DNL Adobe Experience Cloud ID Service] 正在傳遞客戶資料以進行同步或請求ID。 這是最常見的 `demdex.net` 您將會看到來自的電話 [!DNL Audience Manager] 或 [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] 呼叫基本需知： <ul><li>[!DNL Audience Manager]：A [!DNL DPM] 呼叫來源 [!DNL Audience Manager] 會將資料傳送至 [!DNL Data Collection Servers] 和 [!DNL Profile Cache Servers]. 请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]：A [!DNL DPM] 呼叫來自 [!DNL Adobe Experience Cloud ID Service] 是對訪客ID的要求。 另請參閱 [Cookie與Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 和 [Adobe Experience Platform Identity服務如何要求與設定ID](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客戶可以變更 [!DNL DPM] 網域名稱中的前置詞。 另請參閱 [audienceManager伺服器和audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

