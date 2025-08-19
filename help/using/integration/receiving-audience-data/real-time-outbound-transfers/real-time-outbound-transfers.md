---
description: 出站实时数据传输流程会通过POST方法传入一系列JSON对象，从而返回用户数据。
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: 实时出站数据传输
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---

# 实时出站数据传输 {#real-time-outbound-data-transfers}

出站实时数据传输进程将用户数据作为一系列[!DNL JSON]格式消息传送到目标平台。

<!-- c_outbound_json.xml -->

## 推荐

要使用此方法，目标平台必须满足以下要求：

* 它必须提供一个端点[!DNL URL]，该端点可以扩展，以接收来自Audience Manager的大量消息；
* 它必须接受[!DNL JSON]格式(`Content-type: application/json`)的数据；
* 它必须接受安全`HTTPS`数据传输。 [!DNL Audience Manager]不会通过不安全的`HTTP`协议发送消息。

## 频率

这种数据传输方法可以在用户符合区段资格时近乎实时地发送数据。 实时消息仅在用户在线并对Audience Manager Edge网络主动可见时投放。 或者，此方法也可以每24小时发送一批离线或已载入的数据。

## 批量传输

实时传输和批量传输都发送到同一端点，并使用相同的消息格式。 启用批量传输后，在交付批量消息时，目标平台的消息量将会激增。 通过实时报文发送的许多区段资格将在批量报文中重复。 批转移将仅包括自上次交付批以来更改的区段资格（或取消资格）。

## 速率限制

未对投放消息的吞吐量设置速率限制。 设置速率限制可能会导致数据丢失。

## 必需的响应

默认情况下，收件人服务器必须返回`200 OK`代码以指示接收成功。 其他代码将解释为失败。 此响应应在3000毫秒内完成。 为响应失败，[!DNL Audience Manager]将仅进行一次重试尝试。

## 参数

下表定义了您发送到目标的[!DNL JSON]数据文件中的元素。

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
   <td colname="col2"> <p>日期时间 </p> </td> 
   <td colname="col3"> <p>执行请求的时间。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>User.DataPartner_UUID属性中用于指示消息中所包含设备ID类型的ID。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID (GAID)： <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID (IDFA)： <code> 20915</code> </li>
     <li>Web/Cookie ID：因目标平台而异</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>表示目标平台中的目标帐户。 此ID源自目标平台。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>Audience Manager“目标”对象的ID。 此ID源自Audience Manager。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p><code> POST</code>请求中的用户总数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>用户对象的数组。 默认情况下，每条消息将包含1到10个用户，以保持消息大小最优。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>目标平台UUID或全局设备ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 数组 </td> 
   <td colname="col3"> 我们看到此设备的<span class="keyword">Audience Manager</span>区域ID。 例如，如果设备在巴黎（欧洲）有一些活动，则区域ID将为<code> 6</code>。 查看<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> DCS区域ID、位置和主机名</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>区段对象的数组。 对于实时消息，数组包含用户属于的所有区段。 对于批处理消息，数组仅包含自上一批处理以来的区段更改。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>区段的标识符。 在大多数情况下，这是由Audience Manager生成的区段ID（整数）。 在某些情况下，如果目标平台允许，客户可以在Audience Manager用户界面中定义区段标识符（打开文本字段），该标识符随后将反映在此属性中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>定义用户在区段中的状态。 接受以下值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>：活动（默认） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>：不活动、已选择退出或未分段。 </li> 
    </ul> <p>用户在以下情况下不会进行分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根据区段规则从区段中删除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根据区段的<a href="../../../features/traits/segment-ttl-explained.md">生存时间间隔</a>从区段中删除。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天未看到这些幻灯片，则将其移至不活动状态。 </li>
     <li>由于隐私更改请求（即<span class="keyword"> GDPR</span>）已删除</li>
    </ul> <p>当用户未分段时，同步到<span class="keyword"> Audience Manager</span> ID的所有合作伙伴ID都将接收<code> "Status":"0"</code>标记。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>日期时间 </p> </td> 
   <td colname="col3"> <p>最近验证用户区段资格的时间。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

通过使用私钥[签署HTTP请求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)或通过[!DNL Audience Manager]OAuth 2.0[协议进行](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md)身份验证，您可以保护实时出站数据传输进程。

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
