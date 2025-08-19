---
description: 请继续阅读此处，以了解有关如何在/event调用中请求DCS响应的信息。 此部分包括响应示例以及响应中常见数据元素的定义。
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: 从DCS接收数据
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# 从DCS接收数据 {#receive-data-from-the-dcs}

继续此处以了解有关如何在[!DNL DCS]调用中请求`/event`响应的信息。 此部分包括响应示例以及响应中常见数据元素的定义。

在查看此内容之前，请参阅[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数：审查 {#dcs-response-parameters}

如果您想从[!DNL DCS]接收响应，您的`d_rtbd=json`请求必须包括[!DNL DCS]。 如果忽略此参数，[!DNL DCS]将不会返回数据。 对[!DNL DCS]的基本调用将使用此语法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

回想一下，在[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)文档中，虚构的公司[!DNL Acme, Inc.]进行了以下调用：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数，因此[!DNL DCS]发送回如下所示的[!DNL JSON]对象。 您的可能会相似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列出并定义了您在[!DNL DCS]的响应中可能看到的更常见参数。 这适用于事件调用或其他[!DNL DCS] [!DNL API]返回数据的查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 已设置为[URL目标](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | 在[Cookie目标](../../../features/destinations/create-cookie-destination.md)的Cookie名称字段中设置的名称或ID。 |
| `cv` | 发送到由“cn”：“目标名称”参数定义的目标位置的值。 |
| `dcs_region` | [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。 此对象的列表是动态的，取决于用户的操作。 |
| `dmn` | 这是Cookie目标的“Cookie域”字段中指定的域。 请参阅[Cookie目标的可选设置](../../../features/destinations/cookie-destination-options.md)。  对于服务器到服务器的集成，我们建议使用类似`aam-api.com`的域。 |
| `e` | 已在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。 此对象的列表是动态的，取决于用户的操作。 |
| `tid` | 交易ID，用于调试的唯一的12个字符ID。 对DCS进行的每个/event调用都会收到一个tid，您可以在支持查询中引用该值，以便做出更好、更快的响应。 |
| `ttl` | Cookie存留期值（以天为单位）。 |
| `u` 和 `uuid` | Audience Manager分配的独特用户ID。 如果您正在进行[服务器到服务器DCS调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，则需要此项。 |
| `y` | 目标类型、iFrame (`iframe`)或图像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
