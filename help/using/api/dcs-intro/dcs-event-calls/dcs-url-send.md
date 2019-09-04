---
description: 请从此处开始以了解有关向DCS发出/event调用的信息。本节包含有关调用语法、参数、格式和请求示例的信息。
seo-description: 请从此处开始以了解有关向DCS发出/event调用的信息。本节包含有关调用语法、参数、格式和请求示例的信息。
seo-title: 将数据发送到DCS
solution: Audience Manager
title: 将数据发送到DCS
uuid: 024e307d-bfcb-46cf-ac3 a-fc71 df0248 fe
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 将数据发送到DCS {#send-data-to-the-dcs}

请从此处开始，以了解有关如何 `/event` 拨打电话的信息 [!UICONTROL DCS]。本节包含有关调用语法、参数、格式和请求示例的信息。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 使用此方法将数据发送到占位 [!UICONTROL DCS] 符时，替换占位符的真实值。

## 调用语法 {#dcs-call-syntax}

向使用下面显示的语法发送数据的基本 `URL`[!UICONTROL DCS] 字符串。

<pre><code>https://domainalias.demdex.net/event<i></i>？<i>key1</i>=<i>val1</i>，&amp;<i>key2</i>=<i>val2</i>&amp; d_ dst=1&amp; d_ rtbd= json&amp; d_ cb=<i>callback</i></code></pre>

>[!NOTE]
>
>您还可以使用 [!UICONTROL DCS]`POST` 该方法将数据发送到。[DCS API方法中介绍了调用语法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)。

## 调用参数 {#dcs-call-parameters}

下表定义简单 [!UICONTROL DCS] 调用的基本组件。

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>此部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager分配的域别名</span> (例如 <code> ，my_ domain. demdex. net</code>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目标域，始终 <code> 为demdex. net</code>。请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /事件?</code> </p> </td> 
   <td colname="col2"> <p>此部分的电话： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">将调用标识为活动调用。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定义包含要发送到 <span class="wintitle"> DCS</span>的数据的URL字符串的开头。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>键值对中的唯一标识符。 </p> <p>这些键值对使用特定前缀来标识要向 <span class="wintitle"> DCS发送的数据类型</span>。For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>一个变量值，属于键值对中由键定义的集合。 </p> <p>使用值时： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">以双引号括住字符串数据( <code> 例如，age=“41至55”</code>)。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在一个值上传递多个键(例如 <i><code>，key</i>=<i>val1、val2、val3</i></code></i>)。 </i></li> 
     </ul> </p> <p>请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 在DCS调用中格式化密钥值对</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd= json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可选的响应参数。 </p> <p> 这些都不需要向 <span class="wintitle"> DCS发送数据</span>。但是，如果希望 <span class="wintitle"> DCS</span> 返回响应，则必须在请求中包括 <code> d_ rtbd= json</code> 。 </p> <p>请参阅 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 定义</a>的d_ key-value对。 </p> </td> 
  </tr>
 </tbody>
</table>

## 示例调用 {#dcs-sample-call}

此示例显示了虚构的公司，该公司 [!DNL Acme, Inc.] 通过 [!UICONTROL DCS][!DNL HTTP] 电话发送数据。请注意，此调用包括可选参数 `d_dst=1`、 `d_rtbd=json``d_cb=callback`和。这些表示 [!DNL Acme] 希望接收回调函数 [!DNL JSON][!UICONTROL DCS] 的响应。记住，这只是一个示例。切勿剪切和粘贴此代码。

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

## 后续步骤 {#dcs-next-steps}

现在，您已经熟悉发送数据的过程 [!UICONTROL DCS]了，现在应该了解如何从数据中返回数据并解析该信息。请参阅 [接收来自DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)的数据。

>[!MORE_ LIKE_ This]
>
>* [键值对解释](../../../reference/key-value-pairs-explained.md)

