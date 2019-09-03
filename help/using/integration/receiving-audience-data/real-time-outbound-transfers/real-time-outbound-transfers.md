---
description: 出站实时数据传输过程将用户数据返回为使用POST方法传入的一系列JSON对象。
seo-description: 出站实时数据传输过程将用户数据返回为使用POST方法传入的一系列JSON对象。
seo-title: 实时出站数据传输
solution: Audience Manager
title: 实时出站数据传输
uuid: 1895e818-7ab8-4569-a920-4b0 a4 b83 d2 d
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# 实时出站数据传输 {#real-time-outbound-data-transfers}

出站实时数据传输过程将用户数据返回为使用方法传入的 [!DNL JSON] 一系列对象 `POST` 。

<!-- c_outbound_json.xml -->

## 推荐

要使用此方法，我们建议您的数据合作伙伴：

* 以 [!DNL JSON] 格式接受数据。
* 提供可 `POST` 由调用使用的返回数据URL。
* 接受安全 `HTTPS` 的数据传输。[!DNL Audience Manager] 不会使用不安全 `HTTP` 协议发送此文件。

## 频度

该数据传输方法可在用户有资格获得区段时实时发送数据。此外，此方法可以像每24小时一样发送脱机或已载入的数据批次。

## 必需的答复

默认情况下，收件人服务器必须返回 `200 OK` 代码以表示成功接收收据。其他代码将解释为失败。此响应应在3000毫秒内进行。为了响应失败， [!DNL Audience Manager] 将仅重试尝试。

## 参数

下表定义返回 [!DNL JSON] 的数据文件中的元素。

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
   <td colname="col1"> <code><i>进程时间</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>执行请求时的时间。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>指示文件是否包含Android或iOS ID的ID。使用以下ID值： </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GID)： <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA)： <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>要将数据发送到的系统使用的客户端ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Dependment_ ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>目标合作伙伴为您分配的ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p><code> POST</code> 请求中的用户数。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>用户</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组用户对象。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DatatAtNer_ UUID</i></code> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>数据合作伙伴UUID。如果您的数据合作伙伴没有UUID，则保留为空。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_地区</i></code> </td> 
   <td colname="col2"> 数组 </td> 
   <td colname="col3"> <span class="keyword"> 我们已查看此设备的Audience Manager</span> 区域ID。例如，如果设备在巴黎(欧洲)有某些活动，则区域ID将为 <code> 6</code>。请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>区段</i></code> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>区段对象的数组。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>区段_ ID</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>区段ID目标映射。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>状态</i></code> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>定义用户在区段中的状态。接受以下各项： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code></code>1：活动(默认) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code></code>0：非活动、选择退出或取消分段。 </li> 
    </ul> <p>用户在以下情况下已取消分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">基于区段规则从区段删除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根据区段的 <a href="../../../features/traits/segment-ttl-explained.md"> 实时时间间隔从区段中删除</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果未在过去120天内被查看，则移至非活动状态。 </li> 
    </ul> <p>同步到 <span class="keyword"> Audience Manager</span> ID的所有合作伙伴ID都将收到“ <code> 状态”：“0”</code> 标记。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最新区段资格的时间。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

通过使用私钥 [签名HTTP请求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 或通过 [!DNL Audience Manager][OAuth2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 协议进行身份验证，您可以保护实时出站数据传输流程。

## 代码示例

实时数据响应可能类似于以下情况：

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
