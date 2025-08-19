---
description: 有关对DCS进行/event调用的信息，请在此处开始。 本节包含有关调用语法、参数、格式和请求示例的信息。
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: 将数据发送到DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# 将数据发送到DCS {#send-data-to-the-dcs}

从此处开始了解有关对`/event`进行[!DNL DCS]调用的信息。 本节包含有关调用语法、参数、格式和请求示例的信息。

>[!NOTE]
>
>在代码和示例中，*斜体*&#x200B;表示变量占位符。 使用此方法向[!DNL DCS]发送数据时，请用实值替换占位符。

## 调用语法 {#dcs-call-syntax}

向`URL`发送数据的基本[!DNL DCS]字符串使用如下所示的语法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您还可以使用[!DNL DCS]方法将数据发送到`POST`。 [DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)中介绍了调用语法。

## 调用参数 {#dcs-call-parameters}

下表定义了简单[!DNL DCS]调用的基本组件。

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>此调用部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由<span class="keyword"> Audience Manager</span>分配的域别名（如<code> my_domain.demdex.net</code>）。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目标域，始终为<code> demdex.net</code>。 请参阅<a href="../../../reference/demdex-calls.md">了解对Demdex域</a>的调用。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>呼叫的以下部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将调用标识为事件调用。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到<span class="wintitle"> DCS</span>的数据的URL字符串的开头。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>键值对中的唯一标识符。 </p> <p>这些键值对使用特定的前缀来标识您发送到<span class="wintitle"> DCS</span>的数据类型。 有关详细信息，请参阅<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API调用支持的属性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>属于键值对中的键所定义的集的变量值。 </p> <p>使用值时： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">将字符串数据用双引号引住（例如，<code> age="41 to 55"</code>）。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在一个值（例如，<i><code>key</i>=<i>val1,val2,val3</i></code></i>）上传入多个键。 </li> 
     </ul> </p> <p>请参阅格式化DCS调用<a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md">中的键值对</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可选的响应参数。 </p> <p> 将数据发送到<span class="wintitle"> DCS</span>不需要任何这些参数。 但是，如果您希望<span class="wintitle"> DCS</span>返回响应，则必须在请求中包含<code> d_rtbd=json</code>。 </p> <p>查看定义的<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_键值对</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 示例调用 {#dcs-sample-call}

此示例显示虚构的公司[!DNL Acme, Inc.]通过[!DNL DCS]调用向[!DNL HTTP]发送数据。 请注意，此调用包括可选参数`d_dst=1`、`d_rtbd=json`和`d_cb=callback`。 这表示[!DNL Acme]希望从[!DNL JSON]接收带有回调函数的[!DNL DCS]响应。 记住，这只是个例子。 请勿剪切并粘贴此代码。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 后续步骤 {#dcs-next-steps}

现在您已经熟悉了将数据发送到[!DNL DCS]，接下来该考虑如何从其中获取数据并解析该信息。 请参阅[从DCS接收数据](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。

>[!MORELIKETHIS]
>
>* [键值对说明](../../../reference/key-value-pairs-explained.md)
