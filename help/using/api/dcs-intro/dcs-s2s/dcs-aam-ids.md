---
description: 本节介绍如何分析DCS响应以检索对DCS进行实时调用所需的访客和区域ID。
seo-description: 本节介绍如何分析DCS响应以检索对DCS进行实时调用所需的访客和区域ID。
seo-title: 从 DCS 响应中获取用户 ID 和区域
solution: Audience Manager
title: 从 DCS 响应中获取用户 ID 和区域
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# 从 DCS 响应中获取用户 ID 和区域 {#get-user-ids-and-regions-from-a-dcs-response}

本节介绍如何分析[!DNL DCS]响应以检索对[!DNL DCS]进行实时调用所需的访客和区域ID。

## 用户和区域ID {#user-region-ids}

[!DNL DCS]响应包含有关站点访客的数据。 在对[!DNL DCS]进行服务器对服务器调用之前，需要访客和区域ID。

* 需要用户ID来识别数据并将其与特定访客关联。
* 区域ID是必需的，因为它与区域服务器名称关联，您需要将数据发送到[!DNL DCS]。 [!DNL DCS]在地理上最接近站点访客的数据中心中存储信息。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

此简单响应显示`UUID`和区域`ID`。 注意，这只是示例数据。 您的日志文件可能更长、更复杂。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 后续步骤 {#next-steps}

用户ID和区域服务器名称一经确定，即可开始发送和接收[!DNL DCS]数据。 请参阅[发出DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
