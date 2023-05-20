---
description: 輸出即時資料傳輸程式會以POST方法傳入的一系列JSON物件的形式傳回使用者資料。
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: 实时出站数据传输
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 5%

---

# 实时出站数据传输 {#real-time-outbound-data-transfers}

輸出即時資料傳輸程式會將使用者資料以一系列 [!DNL JSON] 格式化訊息至目的地平台。

<!-- c_outbound_json.xml -->

## 推荐

若要使用此方法，目的地平台必須符合下列要求：

* 它必須提供端點 [!DNL URL] 可調整規模以接收來自Audience Manager的大量訊息；
* 它必須接受資料 [!DNL JSON] 格式(`Content-type: application/json`)；
* 它必須接受安全 `HTTPS` 資料傳輸。 [!DNL Audience Manager] 不會透過不安全的系統傳送訊息 `HTTP` 通訊協定。

## 频度

使用者符合區段資格時，此資料傳輸方法可近乎即時傳送資料。 即時訊息只會在使用者上線並主動對Audience Manager邊緣網路可見時傳送。 或者，此方法也可以傳送批次的離線或已上線資料，頻率為每24小時一次。

## 批次傳輸

即時和批次傳輸都會傳送至相同的端點，並使用相同的訊息格式。 啟用批次傳輸時，當批次訊息傳送時，目的地平台的訊息量將會激增。 透過即時訊息傳送的許多區段資格將在批次訊息中重複。 批次移轉將僅包含自上次傳遞批次以來已變更的區段資格（或取消資格）。

## 速率限制

傳送訊息的輸送量沒有速率限制。 設定速率限制可能會導致資料遺失。

## 必要的回應

依預設，收件者伺服器必須傳回 `200 OK` 表示成功收款的代碼。 其他程式碼將解譯為失敗。 此回應預計在3000毫秒內。 回應失敗時， [!DNL Audience Manager] 只會進行一次重試嘗試。

## 参数

下表定義了 [!DNL JSON] 您傳送至目的地的資料檔案。

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 数据类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>日期時間 </p> </td> 
   <td colname="col3"> <p>執行要求的時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>User.DataPartner_UUID屬性中的一個ID，可指出訊息中所包含的裝置ID型別。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID (GAID)： <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID (IDFA)： <code> 20915</code> </li>
     <li>Web/Cookie ID：因目的地平台而異</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>代表目的地平台中的目標帳戶。 此ID源自於目的地平台。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Audience Manager「destination」物件的ID。 此ID源自Audience Manager。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>中的使用者總數 <code> POST</code> 要求。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>使用者物件的陣列。 依預設，每則訊息將包含1到10位使用者，以保持訊息大小最佳化。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>此 <span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>目的地平台UUID或全域裝置ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 数组 </td> 
   <td colname="col3"> 此 <span class="keyword"> Audience Manager</span> 我們在此裝置看到的地區ID。 例如，如果裝置在巴黎進行某些活動（歐洲），則區域ID會是 <code> 6</code>. 请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 對於即時訊息，陣列包含使用者屬於的所有區段。 對於批次訊息，陣列僅包含自上次批次以來的區段變更。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>區段的識別碼。 在大多數情況下，這是Audience Manager產生的區段ID （整數）。 在某些情況下，如果目的地平台允許，客戶可以在Audience Manager使用者介面（開放文字欄位）中定義區段識別碼，這會反映在此屬性中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>定義區段中使用者的狀態。 接受下列值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>：作用中（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>：非使用中、選擇退出或未分段。 </li> 
    </ul> <p>使用者符合以下條件時，系統不會進行分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段中移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段的 <a href="../../../features/traits/segment-ttl-explained.md"> 存留時間間隔</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果過去120天未出現，則移至非作用中狀態。 </li>
     <li>因隱私權變更請求而移除(即 <span class="keyword"> GDPR</span>)</li>
    </ul> <p>同步至的所有合作夥伴ID <span class="keyword"> Audience Manager</span> ID將接收 <code> "Status":"0"</code> 標幟未分段的使用者。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>日期時間 </p> </td> 
   <td colname="col3"> <p>最近驗證使用者區段資格的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以透過以下方式確保即時傳出資料傳輸程式的安全 [簽署HTTP請求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 使用私密金鑰或具有 [!DNL Audience Manager] 驗證透過 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 通訊協定。

## 请求

即時請求看起來可能類似以下內容：

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
