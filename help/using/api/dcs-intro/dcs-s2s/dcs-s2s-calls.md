---
seo-title: 进行服务器到服务器 DCS API 调用
solution: Audience Manager
title: 进行服务器到服务器 DCS API 调用
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: 进行服务器到服务器DCS API调用时，会调用语法、示例和参数
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 9%

---

# 进行服务器到服务器 DCS API 调用 {#making-server-to-server-dcs-api-calls}

调用需要区域DCS服务器的主机名和用户ID。 如果您没有所需的用户和区域ID，请参阅[从DCS响应中获取用户ID和区域](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md)和/或[Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。 拥有用户ID和区域ID后，即可对DCS进行服务器到服务器调用。 有关语法和示例，请参阅此部分。

>[!NOTE]
>
>在代码和示例中， *斜体*&#x200B;表示变量占位符。 在对[!DNL DCS]进行服务器到服务器调用时，用实数值替换占位符。

## 调用语法和示例{#call-syntax-example}

向[!DNL DCS]发送数据的基本服务器到服务器请求使用以下语法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

示例调用类似于以下示例。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 调用参数{#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>调用的此部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由<span class="keyword">Audience Manager</span>分配的域别名（例如<i><code> my_domain.demdex.net</code></i>）。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目标域，始终为<i><code> demdex.net</code></i>。 请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>显示区域<span class="wintitle"> DCS</span>服务器名称的http标头主机参数。 主机名已绑定到区域ID，因此在进行这些类型的调用之前，您需要此ID。 请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 区域 ID、位置和主机名</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分调用： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将调用标识为事件调用。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到DCS的数据的URL字符串的开头。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是唯一的用户ID键，它将<span class="keyword">Audience Manager</span>用户ID值保存在键值对中。 </p> <p>如果您传入了<span class="keyword">Audience Manager</span>用户ID，请使用<code><i>d_uuid</i></code>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是唯一的用户ID键，它将<span class="keyword">Experience Cloud</span>用户ID值保存在键值对中。 另请参阅<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie">从ID服务Cookie</a>获取用户ID。 </p> <p>如果您传入的是从<span class="keyword">Experience Cloud</span> ID服务中捕获的<span class="keyword">Experience Cloud</span> ID，请使用<i><code> d_mid</code></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可选响应参数。 </p> <p> 向<span class="wintitle"> DCS</span>发送数据时，无需执行上述任何操作。 但是，如果您希望<span class="wintitle"> DCS</span>返回响应，则必须在请求中包含<i><code> d_rtbd=json</code></i>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例响应 {#sample-response}

请参阅[从DCS接收数据](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。
