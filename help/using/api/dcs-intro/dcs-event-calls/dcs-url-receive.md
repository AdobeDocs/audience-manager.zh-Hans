---
description: 在此继续，了解如何在/事件调用中请求DCS响应。 本节包括响应示例和响应中常见数据元素的定义。
seo-description: 在此继续，了解如何在/事件调用中请求DCS响应。 本节包括响应示例和响应中常见数据元素的定义。
seo-title: 从 DCS 接收数据
solution: Audience Manager
title: 从 DCS 接收数据
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# 从 DCS 接收数据 {#receive-data-from-the-dcs}

继续此处，了解如何在呼叫 [!DNL DCS] 中请求响应的 `/event` 信息。 本节包括响应示例和响应中常见数据元素的定义。

在查看此内容之前，请参 [阅将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数： 评论 {#dcs-response-parameters}

如果 [!DNL DCS] 要接收 `d_rtbd=json` 来自的响应，则您的请求必须包含 [!DNL DCS]。 如 [!DNL DCS] 果忽略此参数，则不会返回数据。 对请求数据的基 [!DNL DCS] 本调用使用以下语法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

从“将数据发 [送到DCS”文档](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) ，虚构的公司 [!DNL Acme, Inc.] 发出了以下呼吁：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数，因此 [!DNL DCS] 会返回 [!DNL JSON] 下面显示的对象。 您的产品可能类似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列表了您在响应中可能看到的更常见的参数 [!DNL DCS]。 这适用于事件调用或返回 [!DNL DCS] 数 [!DNL API] 据的其他查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 已设置为URL目标的 [URL](../../../features/destinations/create-url-destination.md)。 |
| `cn` | 在Cookie目标的Cookie名称字段中设置的名 [称或ID](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 发送到由“cn”:“目标名称”参数定义的目标的值。 |
| `dcs_region` | 服 [务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。 此对象的列表根据用户的操作是动态的。 |
| `dmn` | 这是在Cookie域字段中为Cookie目标指定的域。 See [Optional Settings for Cookie Destinations](../../../features/destinations/cookie-destination-options.md).  对于服务器到服务器集成，我们建议使用像这样的域 `aam-api.com`。 |
| `e` | 已在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。 此对象的列表根据用户的操作是动态的。 |
| `tid` | 事务ID，它是用于调试的唯一12个字符ID。 对DCS的每次/事件调用都会收到一个ID，您可以在支持查询中引用它，以获得更好、更快的响应。 |
| `ttl` | Cookie的生存时间值（以天为单位）。 |
| `u` 和 `uuid` | 由Audience Manager分配的唯一用户ID。 如果要进行服务器到服 [务器DCS调用，则这是必需的](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。 |
| `y` | 目标类型、iFrame(`iframe`)或图像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

