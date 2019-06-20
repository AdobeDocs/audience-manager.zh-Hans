---
seo-title: 进行服务器到服务器DCS API调用
solution: Audience Manager
title: 进行服务器到服务器DCS API调用
uuid: bdfe3430-e27 f-4a5 c-88d9-ae164 d28 f601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Making Server-to-Server DCS API Calls {#making-server-to-server-dcs-api-calls}

调用需要区域DCS服务器的主机名和用户ID。If you do not have the required user and region IDs, see [Get User IDs and Regions From a DCS Response](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) and/or [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). 有了用户和区域ID后，可以对DCS进行服务器到服务器的调用。有关语法和示例，请参阅本节。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you server-to-server calls to the [!UICONTROL DCS].

## Call Syntax and Example {#call-syntax-example}

A basic server-to-server request that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>“主持人：<i>domain alias</i>. demdex. net"https://DCS<i>主机name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>。</code>
</pre>

示例调用类似于以下示例。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Call Parameters {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>此部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager分配的域别名</span> (例如 <i><code> ，my_ domain. demdex. net</code></i>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <i><code> demdex.net</code></i>. 请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>DCS主机名</i>demdex. net</code> </p> </td> 
   <td colname="col2"> <p>The http header host parameter which shows the name of the regional <span class="wintitle"> DCS</span> server. 主机名绑定到区域ID，这就是您在发出此类调用之前需要的原因。请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /事件?</code> </p> </td> 
   <td colname="col2"> <p>此部分的电话： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将调用标识为活动调用。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到DCS的数据的URL字符串的开头。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid= <i>Audience Manager用户ID</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Audience Manager</span> user ID value in a key-value pair. </p> <p>Use <code><i>d_uuid</i></code> if you're passing in the <span class="keyword"> Audience Manager</span> user ID. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid=<i>Experience Cloud用户ID</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Experience Cloud</span> user ID value in a key-value pair. See also <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Get the User ID from the ID Service Cookie</a>. </p> <p>Use <i><code> d_mid</code></i> if you're passing in a <span class="keyword"> Experience Cloud</span> ID captured from the <span class="keyword"> Experience Cloud</span> ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd= json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可选的响应参数。 </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <i><code> d_rtbd=json</code></i> in your request. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
