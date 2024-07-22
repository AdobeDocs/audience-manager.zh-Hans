---
description: 本节介绍如何分析DCS响应，以检索实时调用DCS所需的访客ID和区域ID。
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: 从DCS响应中获取用户ID和区域
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---

# 从DCS响应中获取用户ID和区域 {#get-user-ids-and-regions-from-a-dcs-response}

本节介绍如何分析[!DNL DCS]响应以检索实时调用[!DNL DCS]所需的访客和区域ID。

## 用户和区域ID {#user-region-ids}

[!DNL DCS]响应包含有关网站访客的数据。 在对[!DNL DCS]进行服务器到服务器调用之前，您需要具有访客和区域ID。

* 必须提供用户ID，才能识别数据并将其与特定访客关联。
* 区域ID是必需的，因为它与区域服务器名称绑定，您需要将该名称发送数据到[!DNL DCS]。 [!DNL DCS]将信息存储在地理位置最接近网站访客的数据中心。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

这些参数如下所述。 *斜体*&#x200B;中的代码表示变量占位符。

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

此简单响应显示`UUID`和区域`ID`。 请注意，这只是示例数据。 您的日志文件可能会更长、更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 后续步骤 {#next-steps}

获得用户ID和区域服务器名称后，即可开始发送和接收[!DNL DCS]数据。 请参阅[进行DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
