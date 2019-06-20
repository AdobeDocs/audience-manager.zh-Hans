---
description: 本节介绍如何解析DCS响应以检索对DCS发出实时调用所需的访客和区域ID。
seo-description: 本节介绍如何解析DCS响应以检索对DCS发出实时调用所需的访客和区域ID。
seo-title: 通过DCS响应获取用户ID和区域
solution: Audience Manager
title: 通过DCS响应获取用户ID和区域
uuid: 08036045-b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

[!UICONTROL DCS] 响应包含有关站点访客的数据。You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* 需要该用户ID来识别和关联特定访客的数据。
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

这些参数如下所述。*斜体代码* 表示变量占位符。

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 数据类型 </th> 
   <th colname="col3" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>“uuid”： <i>用户ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p> <code> “uuid”：“123456789”</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>“cs_ region”：<i>区域ID</i></code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p> <code> “cs_ region”：9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

This simple response shows the `UUID` and region `ID`. 注意，这只是示例数据。您的日志文件可能更长更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 后续步骤 {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
