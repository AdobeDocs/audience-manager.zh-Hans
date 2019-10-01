---
description: 出站实时数据传输过程将用户数据作为一系列JSON对象返回，这些对象通过POST方法传入。
seo-description: 出站实时数据传输过程将用户数据作为一系列JSON对象返回，这些对象通过POST方法传入。
seo-title: 实时出站数据传输
solution: Audience Manager
title: 实时出站数据传输
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# 实时出站数据传输 {#real-time-outbound-data-transfers}

该出站实时数据传输过程将用户数据作为一系列格式化消息 [!DNL JSON] 传送给目标平台。

<!-- c_outbound_json.xml -->

## 推荐

要使用此方法，目标平台必须满足以下要求：

* 它必须提供一个端 [!DNL URL] 点，该端点可以缩放以从Audience manager接收大量消息；
* 它必须接受格式 [!DNL JSON] (`Content-type: application/json`)的数据；
* 它必须接受安全 `HTTPS` 的数据传输。 [!DNL Audience Manager] 不会通过不安全协议发送 `HTTP` 消息。

## 频度

这种数据传输方法可以在用户符合细分条件时近乎实时地发送数据。 实时消息仅在用户在线且活动可见Audience Manager edge网络时发送。 或者，此方法也可以每24小时发送一批脱机或已载入的数据。

## 批转移

实时传输和批处理传输都发送到同一端点，并使用相同的消息格式。 启用批传输后，目标平台在传送批传输消息时，消息量将出现尖峰。 通过实时消息发送的许多细分资格将在批处理消息中重复。 批转移将仅包括自上次批交付以来已更改的段资格（或取消资格）。

## 费率限制

对交付消息的吞吐量没有速率限制。 设定利率限制可能导致数据丢失。

## 所需答复

默认情况下，收件人服务器必须返回代 `200 OK` 码以指示成功接收。 其他代码将被解释为失败。 此响应应在3000毫秒内完成。 响应失败时，将 [!DNL Audience Manager] 仅尝试一次重试。

## 参数

The following table defines the elements in the returned  data file.[!DNL JSON]

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
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>执行请求的时间。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>An ID that indicates the type of device IDs contained within the message, in the User.DataPartner_UUID property. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA):  20915<code></code> </li>
     <li>Web/Cookie IDs: varies by destination platform</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>Represents the target account in the destination platform. This ID originates from the destination platform.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>The ID of the Audience Manager “destination” object. This ID originates from Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>用户</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>An array of user objects. By default, each message will contain between 1 and 10 users, to keep the message size optimal. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>Audience Manager <span class="keyword"></span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>目标平台UUID或全局设备ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 数组 </td> 
   <td colname="col3"> 我们 <span class="keyword"> 在其中看到此设备的Audience Manager</span> 区域ID。 例如，如果设备在巴黎（欧洲）有某些活动，则区域ID将为6 <code></code>。 请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>区段</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>段对象的数组。 对于实时消息，该数组包含用户所属的所有区段。 对于批处理消息，数组仅包含自上次批处理以来的段更改。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>区段的标识符。 在大多数情况下，这是Audience manager生成的区段ID（整数）。 在某些情况下，如果目标平台允许，客户可以在Audience Manager UI（打开文本字段）中定义区段标识符，然后该标识符会反映在此属性中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>定义区段中用户的状态。 接受以下值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:活动（默认） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非活动、已选择退出或未分段。 </li> 
    </ul> <p>用户在以下情况下将取消分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根据区段规则从区段中删除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根据区段的生存时间间隔从 <a href="../../../features/traits/segment-ttl-explained.md"> 区段中删除</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天未看到活动状态，则将其移至非活动状态。 </li>
     <li>由于隐私更改请求(即[!DNL GDPR])</li>
    </ul> <p>当用户取消分段时，所有同步到 <span class="keyword"> Audience Manager</span> ID的合作伙伴ID都将收到 <code></code> “状态”:“0”标志。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最近验证用户区段资格的时间。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

通过使用私钥对 [HTTP请求进行签名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) ，或通过 [!DNL Audience Manager] OAuth 2.0协议进行身份验证，可以保护实时出站数据传输过程 [](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 。

## 请求

实时请求可能类似于以下内容：

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
