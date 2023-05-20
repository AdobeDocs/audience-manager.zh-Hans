---
description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和區域ID。
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: 从 DCS 响应中获取用户 ID 和区域
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 16%

---

# 从 DCS 响应中获取用户 ID 和区域 {#get-user-ids-and-regions-from-a-dcs-response}

本節說明如何剖析 [!DNL DCS] 擷取對進行即時呼叫所需的訪客和區域ID的回應 [!DNL DCS].

## 使用者和地區ID {#user-region-ids}

A [!DNL DCS] 回應包含網站訪客的相關資料。 您需要先取得訪客和地區ID，才能對 [!DNL DCS].

* 使用者ID必須用來識別資料並將其與特定訪客建立關聯。
* 區域ID為必要項，因為它與區域伺服器名稱繫結，而您需要將資料傳送至 [!DNL DCS]. 此 [!DNL DCS] 會將資訊儲存在地理位置上最接近網站訪客的資料中心。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

這些引數說明如下。 中的程式碼 *斜體* 代表變數預留位置。

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

此簡單回應會顯示 `UUID` 和區域 `ID`. 請注意，這僅是範例資料。 您的記錄檔可能更長、更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 后续步骤 {#next-steps}

擁有使用者ID和區域伺服器名稱后，您就可以開始傳送和接收 [!DNL DCS] 資料。 另請參閱 [進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
