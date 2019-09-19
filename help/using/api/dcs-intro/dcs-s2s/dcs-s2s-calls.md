---
seo-title: 发出服务器到服务器DCS API调用
solution: Audience Manager
title: 发出服务器到服务器DCS API调用
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 发出服务器到服务器DCS API调用 {#making-server-to-server-dcs-api-calls}

调用需要区域DCS服务器的主机名和用户ID。 如果您没有所需的用户和区域ID，请参 [阅从DCS响应和](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) /或 [Experience Cloud获取用户ID和区域](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。 用户和区域ID一经获得，即可对DCS进行服务器对服务器调用。 有关语法和示例，请参阅本节。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 在服务器对服务器调用占位符时，用实际值替换占位符 [!UICONTROL DCS]。

## 调用语法和示例 {#call-syntax-example}

向服务器发送数据的基本服务器对服务器请 [!UICONTROL DCS] 求使用以下语法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

示例调用与以下示例类似。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 调用参数 {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> 域 <i>别名</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>此部分调用包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由 <span class="keyword"> Audience Manager分配的域别名</span> (例如 <i><code> my_domain.demdex.net</code></i>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目标域，始终为 <i><code> demdex.net</code></i>。 请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS主机名</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>显示区域DCS服务器名称的http头主机 <span class="wintitle"> 参数</span> 。 主机名与区域ID关联，因此，您需要该ID才能进行这些类型的调用。 请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /事件?</code> </p> </td> 
   <td colname="col2"> <p>电话联系的这一部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将调用标识为活动调用。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到DCS的数据的URL字符串的开头。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager用户ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是唯一的用户ID密钥，它将 <span class="keyword"> Audience Manager用户</span> ID值保存在键值对中。 </p> <p>如 <code><i>果要传入</i></code> Audience Manager用户ID <span class="keyword"> ，请使用</span> d_uuid。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience cloud用户ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是唯一的用户ID密钥，它将 <span class="keyword"> Experience Cloud用户</span> ID值保存在键值对中。 另请参 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> 阅从ID服务Cookie获取用户ID</a>。 </p> <p>如果 <i><code> 您要传递从Experience Cloud</code></i> ID服务捕获的 <span class="keyword"> Experience Cloud</span> ID，请使用 <span class="keyword"></span> d_mid。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=回<i>调</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可选响应参数。 </p> <p> 所有这些都不需要将数据发送到 <span class="wintitle"> DCS</span>。 但是，如果您希望 <span class="wintitle"> DCS</span> 返回响应，则必须在请求中 <i><code> 包含d_rtbd=json</code></i> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

请参 [阅从DCS接收数据](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。
