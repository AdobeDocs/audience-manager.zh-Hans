---
description: 请继续此处，了解如何在/event调用中请求DCS响应。 本节包括响应示例和响应中常见数据元素的定义。
seo-description: 请继续此处，了解如何在/event调用中请求DCS响应。 本节包括响应示例和响应中常见数据元素的定义。
seo-title: ' 从DCS接收数据'
solution: Audience Manager
title: 从DCS接收数据
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 从DCS接收数据 {#receive-data-from-the-dcs}

继续此处，了解如何在呼叫中 [!UICONTROL DCS] 请求响应的相 `/event` 关信息。 本节包括响应示例和响应中常见数据元素的定义。

在查看此内容之前，请参 [阅将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS响应参数：评论 {#dcs-response-parameters}

如果您 [!UICONTROL DCS] 希望从 `d_rtbd=json` 收到响应，则您的请求必须包含在内 [!UICONTROL DCS]。 如 [!UICONTROL DCS] 果忽略此参数，则不会返回数据。 对请求数据的基 [!UICONTROL DCS] 本调用使用以下语法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 示例响应 {#sample-response}

回想一下，在 [Send Data to DCS文档中](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) ，虚构的公司发出 [!DNL Acme, Inc.] 了如下呼吁：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由于此调用包含所需的响应参数，因此 [!UICONTROL DCS] 会发送回以 [!DNL JSON] 下显示的对象。 您的产品可能类似或更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 响应参数 {#response-parameters}

下表列出并定义了在响应中可能看到的更常见参数 [!UICONTROL DCS]。 这适用于事件调用或返回数 [!UICONTROL DCS] 据的 [!DNL API] 其他查询。

| 参数 | 描述 |
|--- |--- |
| `c` | 已设置为 [URL目标的URL](../../../features/destinations/create-url-destination.md)。 |
| `cn` | Cookie目标的Cookie名称字段中设置的名称或 [ID](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 发送到由“cn”:“目标名称”参数定义的目标的值。 |
| `dcs_region` | 服 [务器到服务器DCS调用](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此对象包含在UI中配置的所有URL目标的信息。 此对象的列表会根据用户的操作而动态显示。 |
| `dmn` | 这是在Cookie域字段中为Cookie目标指定的域。 请参 [阅Cookie目标的可选设置](../../../features/destinations/cookie-destination-options.md)。  对于服务器到服务器的集成，我们建议使用类似的域 `aam-api.com`。 |
| `e` | 在URL目标中设置的安全URL。 |
| `stuff` | 此对象包含所有Cookie目标的信息。 此对象的列表会根据用户的操作而动态显示。 |
| `tid` | 事务ID，它是用于调试的唯一12个字符ID。 对DCS的每个/event调用都会收到一个tid，您可以在支持查询中引用它以获得更好、更快的响应。 |
| `ttl` | cookie的生存时间值（以天为单位）。 |
| `u` 和 `uuid` | 由Audience manager分配的唯一用户ID。 如果要进行服务器到服 [务器DCS调用，则此为必需](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。 |
| `y` | 目标类型、iFrame(`iframe`)或图像(`img`)。 |

>[!MORE_LIKE_THIS]
>
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

