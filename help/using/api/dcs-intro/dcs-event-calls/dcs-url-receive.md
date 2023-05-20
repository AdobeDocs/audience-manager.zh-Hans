---
description: 請繼續這裡，瞭解如何在/event呼叫中要求DCS回應。 本節包含回應的範例，以及回應中常見資料元素的定義。
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: 从 DCS 接收数据
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 4%

---

# 从 DCS 接收数据 {#receive-data-from-the-dcs}

請繼續參閱此處以瞭解如何請求 [!DNL DCS] 中的回應 `/event` 呼叫。 本節包含回應的範例，以及回應中常見資料元素的定義。

檢閱此內容之前，請參閱 [將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS回應引數：複查 {#dcs-response-parameters}

您的 [!DNL DCS] 要求必須包括 `d_rtbd=json` 如果您想從 [!DNL DCS]. 此 [!DNL DCS] 如果省略此引數，將不會傳回資料。 對「 」的基本呼叫 [!DNL DCS] 若要要求資料，請使用下列語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

從 [將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 檔案，虛構的公司 [!DNL Acme, Inc.] 進行此呼叫：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由於此呼叫包含必要的回應引數，因此 [!DNL DCS] 傳回 [!DNL JSON] 物件如下所示。 您的可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列出並定義您在回應中可能看到的較常見引數， [!DNL DCS]. 這適用於事件呼叫或其他 [!DNL DCS] [!DNL API] 傳回資料的查詢。

| 参数 | 描述 |
|--- |--- |
| `c` | 已設定為的URL [URL目的地](../../../features/destinations/create-url-destination.md). |
| `cn` | 在的Cookie名稱欄位中設定的名稱或ID [Cookie目的地](../../../features/destinations/create-cookie-destination.md). |
| `cv` | 傳送至由「cn」：「目的地名稱」引數定義之目的地的值。 |
| `dcs_region` | 此 [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | 此物件包含在UI中設定的所有URL目的地的資訊。 此物件的清單是根據使用者的動作而動態的。 |
| `dmn` | 這是Cookie目的地的「Cookie網域」欄位中指定的網域。 另請參閱 [Cookie目的地的選用設定](../../../features/destinations/cookie-destination-options.md).  對於伺服器對伺服器的整合，我們建議使用網域，例如 `aam-api.com`. |
| `e` | 已在URL目的地中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。 此物件的清單是根據使用者的動作而動態的。 |
| `tid` | 交易ID，此唯一12個字元的ID用於偵錯。 對DCS發出的每個/event呼叫都會收到一個tid，您可以在支援查詢中參考該代碼，以取得更好且更快速的回應。 |
| `ttl` | Cookie存留時間值（以天為單位）。 |
| `u` 和 `uuid` | 由Audience Manager指派的不重複使用者ID。 如果您正在進行 [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | 目的地型別， iFrame (`iframe`)或影像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支援的機碼值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

