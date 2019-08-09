---
description: 在此处继续获取有关如何在/event调用中请求DCS响应的信息。本节包含响应中常见数据元素的响应示例和定义。
seo-description: 在此处继续获取有关如何在/event调用中请求DCS响应的信息。本节包含响应中常见数据元素的响应示例和定义。
seo-title: 从DCS接收数据
solution: Audience Manager
title: 从DCS接收数据
uuid: fbb77197-8530-48a8-b708-d785 f7214494
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 从DCS接收数据 {#receive-data-from-the-dcs}

在此处继续获取有关如何在呼叫中请求 [!UICONTROL DCS] 响应的信息 `/event` 。本节包含响应中常见数据元素的响应示例和定义。

在查看此内容之前，请参阅 [将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数：A Review {#dcs-response-parameters}

[!UICONTROL DCS] 如果您希望收到响应，则必须包含 `d_rtbd=json` 您的请求 [!UICONTROL DCS]。如果忽略此参数，则不 [!UICONTROL DCS] 会返回数据。对请求数据的 [!UICONTROL DCS] 基本调用使用此语法：

<pre><code>https://domainalias.demdex.net/event<i></i>？<i>key1</i>= <i>val1</i>，&amp;<i>key2</i>= <i>val2</i>&amp; d_ dst=1&amp; d_ rtbd= json&amp; d_ cb=<i>callback</i></code>
</pre>

## 示例响应 {#sample-response}

回想一下，从 [发送数据到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 文档，虚构的公司 [!DNL Acme, Inc.] 进行了此次调用：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数， [!UICONTROL DCS] 因此将返回的 [!DNL JSON] 返回对象。您可能类似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列出并定义了您可能在响应中看到的更多常用参数 [!UICONTROL DCS]。此操作适用于返回数据的事件调用或其他 [!UICONTROL DCS][!DNL API] 查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 已设置为 [URL目标](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | [cookie目标的cookie名称字段中设置的名称或ID](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 发送到“cn”定义的目标的值：“estinaton name”参数。 |
| `dcs_region` | [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。此对象的列表根据用户的操作是动态的。 |
| `dmn` | 这是Cookie目标的Cookie域字段中指定的域。请参阅 [Cookie目标的可选设置](../../../features/destinations/cookie-destination-options.md)。对于服务器到服务器集成，我们建议使用这样 `aam-api.com`的域。 |
| `e` | 已在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。此对象的列表根据用户的操作是动态的。 |
| `tid` | 事务ID，它是用于调试目的的唯一12个字符ID。每个对DCS的/event调用都会收到一个您可以在支持查询中引用的tid，以便更好、更快地响应。 |
| `ttl` | 几天内Cookie的实时价值。 |
| `u` 和 `uuid` | Audience Manager分配的唯一用户ID。如果要进行 [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，则需要此操作。 |
| `y` | 目标类型，iFrame(`iframe`)或image(`img`)。 |

>[!MORE_ LIKE_ This]
>
>* [关键值前缀和由DCS支持的变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

