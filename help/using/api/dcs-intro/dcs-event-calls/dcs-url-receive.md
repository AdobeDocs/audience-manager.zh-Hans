---
description: 请继续此处，以了解有关如何在/event调用中请求DCS响应的信息。 本节包括响应示例和响应中常用数据元素的定义。
seo-description: 请继续此处，以了解有关如何在/event调用中请求DCS响应的信息。 本节包括响应示例和响应中常用数据元素的定义。
seo-title: 从 DCS 接收数据
solution: Audience Manager
title: 从 DCS 接收数据
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# 从 DCS 接收数据 {#receive-data-from-the-dcs}

请继续此处，以了解有关如何在`/event`调用中请求[!DNL DCS]响应的信息。 本节包括响应示例和响应中常用数据元素的定义。

在查看此内容之前，请参阅[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数：{#dcs-response-parameters}评论

如果要从[!DNL DCS]接收响应，则[!DNL DCS]请求必须包含`d_rtbd=json`。 如果忽略此参数，则[!DNL DCS]将不返回数据。 对[!DNL DCS]进行请求数据的基本调用使用以下语法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

回想一下，在[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)文档中，虚构的公司[!DNL Acme, Inc.]发出了以下调用：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数，因此[!DNL DCS]会发送回下面显示的[!DNL JSON]对象。 您的可能相似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列出并定义了在[!DNL DCS]响应中可能看到的更常见参数。 这适用于返回数据的事件调用或其他[!DNL DCS] [!DNL API]查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 设置为[URL目标](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | 在[Cookie目标](../../../features/destinations/create-cookie-destination.md)的Cookie名称字段中设置的名称或ID。 |
| `cv` | 发送到由“cn”：“目标名称”参数定义的目标的值。 |
| `dcs_region` | [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。 此对象的列表是基于用户操作动态的。 |
| `dmn` | 这是在Cookie目标的Cookie域字段中指定的域。 请参阅[Cookie目标的可选设置](../../../features/destinations/cookie-destination-options.md)。  对于服务器到服务器的集成，我们建议使用`aam-api.com`之类的域。 |
| `e` | 在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。 此对象的列表是基于用户操作动态的。 |
| `tid` | 交易ID，为唯一的12个字符ID，用于调试。 对DCS的每个/event调用都会收到一个tid，您可以在支持查询中引用该tid，以获得更好、更快的响应。 |
| `ttl` | Cookie的生存时间值（以天为单位）。 |
| `u` 和 `uuid` | 由Audience Manager分配的唯一用户ID。 如果要进行[服务器到服务器DCS调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，则需要此参数。 |
| `y` | 目标类型、iFrame(`iframe`)或图像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

