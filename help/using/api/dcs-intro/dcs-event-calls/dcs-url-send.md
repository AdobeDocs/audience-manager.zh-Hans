---
description: 开始此处，获取有关对DCS进行/事件调用的信息。 本节包括有关调用语法、参数、格式和请求示例的信息。
seo-description: 开始此处，获取有关对DCS进行/事件调用的信息。 本节包括有关调用语法、参数、格式和请求示例的信息。
seo-title: 将数据发送到 DCS
solution: Audience Manager
title: 将数据发送到 DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# 将数据发送到 DCS {#send-data-to-the-dcs}

开始此处，获取有关对[!DNL DCS]进行`/event`调用的信息。 本节包括有关调用语法、参数、格式和请求示例的信息。

>[!NOTE]
>
>在代码和示例中，*斜体*&#x200B;表示变量占位符。 使用此方法将数据发送到[!DNL DCS]时，用实值替换占位符。

## 调用语法{#dcs-call-syntax}

将数据发送到[!DNL DCS]的基本`URL`字符串使用以下语法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您还可以使用`POST`方法向[!DNL DCS]发送数据。 调用语法在[DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)中有介绍。

## 调用参数{#dcs-call-parameters}

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
   <td colname="col2"> <p>此部分调用包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由<span class="keyword">Audience Manager</span>分配的域别名（例如<code> my_domain.demdex.net</code>）。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目标域，始终为<code> demdex.net</code>。 请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将呼叫标识为事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到<span class="wintitle"> DCS</span>的数据的URL字符串的开始。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>键值对中的唯一标识符。 </p> <p>这些键值对使用特定的前缀来标识您要发送到<span class="wintitle"> DCS</span>的数据类型。 有关详细信息，请参阅<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API调用的支持属性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>属于由键值对中的键定义的集的变量值。 </p> <p>使用值时： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">将字符串数据括在多次引号中（例如<code> age="41 to 55"</code>）。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">可以在单个值（例如<i><code>key</i>=<i>val1,val2,val3</i></code></i>）上传递多个键。 </li> 
     </ul> </p> <p>请参阅<a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md">格式化DCS调用中的键值对</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可选响应参数。 </p> <p> 所有这些都不需要发送数据到<span class="wintitle"> DCS</span>。 但是，如果希望<span class="wintitle"> DCS</span>返回响应，则必须在请求中包含<code> d_rtbd=json</code>。 </p> <p>请参阅<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_键值对已定义</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 示例调用{#dcs-sample-call}

此示例显示虚构的公司[!DNL Acme, Inc.]通过[!DNL HTTP]调用将数据发送到[!DNL DCS]。 请注意，此调用包含可选参数`d_dst=1`、`d_rtbd=json`和`d_cb=callback`。 这表示[!DNL Acme]希望从[!DNL DCS]接收具有回叫功能的[!DNL JSON]响应。 记住，这只是个例子。 请勿剪切和粘贴此代码。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 后续步骤 {#dcs-next-steps}

既然您已经熟悉向[!DNL DCS]发送数据，现在应该了解如何从中获取数据并分析该信息。 请参阅[从DCS接收数据](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。

>[!MORELIKETHIS]
>
>* [键值对说明](../../../reference/key-value-pairs-explained.md)

