---
description: 從這裡開始，瞭解如何對DCS進行/event呼叫。 本節包含呼叫語法、引數、格式設定和請求範例的相關資訊。
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: 将数据发送到 DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 6%

---

# 将数据发送到 DCS {#send-data-to-the-dcs}

從這裡開始，瞭解如何製作 `/event` 呼叫 [!DNL DCS]. 本節包含呼叫語法、引數、格式設定和請求範例的相關資訊。

>[!NOTE]
>
>在程式碼和範例中， *斜體* 代表變數預留位置。 將資料傳送至時，以實值取代預留位置 [!DNL DCS] 使用此方法。

## 呼叫語法 {#dcs-call-syntax}

基本 `URL` 將資料傳送至的字串 [!DNL DCS] 會使用下列語法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您也可以將資料傳送至 [!DNL DCS] 藉由使用 `POST` 方法。 呼叫語法的說明，請參閱 [DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## 呼叫引數 {#dcs-call-parameters}

下表定義簡單的基本元件 [!DNL DCS] 呼叫。

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
   <td colname="col2"> <p>這部分呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您的網域別名指派者 <span class="keyword"> Audience Manager</span> (例如， <code> my_domain.demdex.net</code>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目的地網域，一律為 <code> demdex.net</code>. 请参阅<a href="../../../reference/demdex-calls.md">了解 Demdex 域调用</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>通話的這個部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含您要傳送至之資料的URL字串起始 <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>機碼值組中的唯一識別碼。 </p> <p>這些機碼值組會使用特定首碼來識別您要傳送至的資料型別 <span class="wintitle"> DCS</span>. 如需詳細資訊，請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API呼叫的支援屬性</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>屬於索引鍵/值配對中索引鍵所定義之集合的變數值。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">以雙引號括住字串資料(例如， <code> age="41 to 55"</code>)。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在單一值上傳入多個索引鍵(例如， <i><code>key</i>=<i>val1,val2,val3</i></code></i>)。 </li> 
     </ul> </p> <p>另請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 格式化DCS呼叫中的索引鍵值配對</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>選擇性回應引數。 </p> <p> 這些都不需要用來傳送資料給 <span class="wintitle"> DCS</span>. 不過，如果您想要 <span class="wintitle"> DCS</span> 若要傳回回應，您必須包含 <code> d_rtbd=json</code> 在您的請求中。 </p> <p>另請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 已定義d_機碼值組</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## 呼叫範例 {#dcs-sample-call}

此範例顯示虛構的公司 [!DNL Acme, Inc.] 將資料傳送至 [!DNL DCS] 透過 [!DNL HTTP] 呼叫。 請注意，此呼叫包含選用引數 `d_dst=1`， `d_rtbd=json`、和 `d_cb=callback`. 這些表示 [!DNL Acme] 想要接收 [!DNL JSON] 回應來自 [!DNL DCS] 使用回呼函式。 請記住，這只是個範例。 請勿剪下並貼上此程式碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 后续步骤 {#dcs-next-steps}

現在您已熟悉傳送資料至 [!DNL DCS]，現在該審視如何從其中取回資料，並剖析該資訊了。 另請參閱 [從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [键值对说明](../../../reference/key-value-pairs-explained.md)

