---
description: 在此处继续获取有关如何在/event调用中请求DCS响应的信息。本节包含响应中常见数据元素的响应示例和定义。
seo-description: 在此处继续获取有关如何在/event调用中请求DCS响应的信息。本节包含响应中常见数据元素的响应示例和定义。
seo-title: 从DCS接收数据
solution: Audience Manager
title: 从DCS接收数据
uuid: fbb77197-8530-48a8-b708-d785 f7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. 本节包含响应中常见数据元素的响应示例和定义。

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

[!UICONTROL DCS] 如果您希望收到响应，则必须包含 `d_rtbd=json` 您的请求 [!UICONTROL DCS]。The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domainalias.demdex.net/event<i></i>？<i>key1</i>= <i>val1</i>，&amp;<i>key2</i>= <i>val2</i>&amp; d_ dst=1&amp; d_ rtbd= json&amp; d_ cb=<i>callback</i></code>
</pre>

## 示例响应 {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. 您可能类似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| 参数 | 描述 |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | [cookie目标的cookie名称字段中设置的名称或ID](../../../features/destinations/manage-destinations.md#create-cookie-destination)。 |
| `cv` | 发送到“cn”定义的目标的值：“estinaton name”参数。 |
| `dcs_region` | [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。此对象的列表根据用户的操作是动态的。 |
| `dmn` | 这是Cookie目标的Cookie域字段中指定的域。See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | 已在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。此对象的列表根据用户的操作是动态的。 |
| `tid` | 事务ID，它是用于调试目的的唯一12个字符ID。每个对DCS的/event调用都会收到一个您可以在支持查询中引用的tid，以便更好、更快地响应。 |
| `ttl` | 几天内Cookie的实时价值。 |
| `u` 和 `uuid` | Audience Manager分配的唯一用户ID。This is required if you&#39;re making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ This]
>
>* [关键值前缀和由DCS支持的变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

