---
description: 點選追蹤可記錄協力廠商創意內容的點選型活動，因此可測量訪客在整個行銷活動中的參與度。
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: 通过像素调用捕获营销活动点击数据
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 9%

---

# 通过像素调用捕获营销活动点击数据 {#capturing-campaign-click-data-via-pixel-calls}

點選追蹤可記錄協力廠商創意內容的點選型活動，因此可測量訪客在整個行銷活動中的參與度。 類似於 [曝光數集合](/help/using/integration/media-data-integration/impression-data-pixels.md)，事件呼叫會傳送至 [!DNL Audience Manager] 資料收集伺服器([!DNL DCS])以進行處理。 然後訪客會被重新導向至預期的網址。

>[!NOTE]
>
>請聯絡您的 [!DNL Audience Manager] 諮詢或帳戶潛在客戶，以瞭解 [!DNL URL] 特定於使用者端網域。

## 要求

點選追蹤呼叫需要下列引數：

* `d_event=click`：將事件呼叫識別為點選事件的機碼值組。
* `d_rd=redirect URL`：包含雙重編碼重新導向的機碼值組 [!DNL URL]. 如果您使用線上編碼工具，請透過編碼器執行字串，然後再次對結果進行編碼，以便重新導向可正常運作。

此外，呼叫可包含機碼值組，這些機碼值組可用於特徵資格或提供其他報表的資料和中繼資料。

## 要求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 响应

回應會將瀏覽器重新導向至 [!DNL URL] 指定於 `d_rd` 引數。 回應字串可包含下列任何支援巨集所產生的值。

根據上述範例，瀏覽器會重新導向至下列專案 [!DNL URL]：

`https://adobe.com/callback?creative=123`

## 支援的巨集

按一下「事件」可支援下表中列出的巨集。 巨集是自我包含程式碼的一個小單位，當廣告標籤載入以進行行銷活動和使用者追蹤時會啟用。 巨集將會與目的地一起傳遞 [!DNL URL]，只要以下列格式標籤： `%macro%`. 有些金鑰沒有巨集，而是接受硬式編碼ID值。 如果您想要分析以下專案中的資料，則需要接受硬式編碼值的金鑰： [Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键 </th> 
   <th colname="col02" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>沒有巨集。 </p> <p>接受硬式編碼ID值。 </p> </td> 
   <td colname="col2"> <p>广告商 ID.</p> <p>廣告商資料來源的整合程式碼。 請注意，這與Audience Manager資料來源無關。</p> <p> 下列專案需要： <span class="wintitle"> Audience Optimization</span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數值ID。 </p> <p> 下列專案需要： <span class="wintitle"> Audience Optimization</span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值行銷活動ID。 </p> <p> 下列專案需要： <span class="wintitle"> Audience Optimization</span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> <p>常用於 <code> d_dpuuid</code> 將資料提供者ID連結至使用者ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者提供的唯一使用者ID。 </p> <p>常用於 <code> d_dpid</code> 將使用者ID連結至資料提供者ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). 如需ECID的詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>. </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>為請求提供服務的DCS叢集的數值區域ID。 如需DCS的詳細資訊，請參閱 <a href="../../reference/system-components/components-data-collection.md"> 資料收集元件</a>. </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用於快取失敗的隨機數。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager提取中繼資料之來源的DPID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而非依賴Demdex Cookie。 </p> <p>可选。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。 </p><p><code>gdpr</code> 可以為0 （GDPR不適用）或1 （GDPR適用）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 若 <code>gdpr=1</code>，則 <code>${gdpr_consent_XXXX}</code> 取代為 <code>gdpr_consent</code> 字串和廠商ID (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規格</a>)。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

## 巨集範例

此範例示範如何傳遞創意、廣告群組和版位巨集。 此變數假設每個引數的值都會傳入點選追蹤呼叫的非重新導向部分。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 请求

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## 响应

根據上述範例，瀏覽器會重新導向至下列專案 [!DNL URL]：

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 —  [!UICONTROL Audience Optimization Reports]

您可以使用畫素呼叫來提供 [Audience Optimization報表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). 另請參閱 [中繼資料檔案的概述與對應](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 如果您想要使用畫素來支援報表。


>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

