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

请继续此处，了解如何在`/event`调用中请求[!DNL DCS]响应。 本节包括响应示例和响应中常见数据元素的定义。

在查看此内容之前，请参阅[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数：评论{#dcs-response-parameters}

如果要接收来自[!DNL DCS]的响应，则[!DNL DCS]请求必须包含`d_rtbd=json`。 如果忽略此参数，[!DNL DCS]将不返回数据。 对[!DNL DCS]进行请求数据的基本调用使用以下语法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

在[将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)文档中，虚构的公司[!DNL Acme, Inc.]发出此调用：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数，因此[!DNL DCS]将返回下面显示的[!DNL JSON]对象。 您的产品可能类似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列表了您在[!DNL DCS]的响应中可能看到的更常见的参数。 这适用于事件调用或返回数据的其他[!DNL DCS] [!DNL API]查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 已设置为[URL目标](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | 在[cookie目标](../../../features/destinations/create-cookie-destination.md)的cookie名称字段中设置的名称或ID。 |
| `cv` | 发送到由“cn”:“目标名称”参数定义的目标的值。 |
| `dcs_region` | [服务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。 此对象的列表根据用户的操作是动态的。 |
| `dmn` | 这是在Cookie域字段中为Cookie目标指定的域。 请参阅[ Cookie目标的可选设置](../../../features/destinations/cookie-destination-options.md)。  对于服务器到服务器集成，我们建议使用`aam-api.com`这样的域。 |
| `e` | 已在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。 此对象的列表根据用户的操作是动态的。 |
| `tid` | 事务ID，它是用于调试的唯一12个字符ID。 对DCS的每次/事件调用都会收到一个ID，您可以在支持查询中引用它，以获得更好、更快的响应。 |
| `ttl` | Cookie的生存时间值（以天为单位）。 |
| `u` 和 `uuid` | 由Audience Manager分配的唯一用户ID。 如果要进行[服务器到服务器DCS调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，则这是必需的。 |
| `y` | 目标类型、iFrame(`iframe`)或图像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

