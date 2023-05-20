---
description: 將媒體資料傳送至Audience Manager的一種方法，是使用廣告伺服器巨集將促銷活動屬性傳送至Audience Manager。
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: 通过像素调用捕获营销活动展示数据
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 20%

---

# 通过像素调用捕获营销活动展示数据{#capturing-campaign-impression-data-via-pixel-calls}

將媒體資料傳送至Audience Manager的一種方法，是使用廣告伺服器巨集將促銷活動屬性傳送至Audience Manager。

這種方法通常稱為「將創意內容畫素化」。 這些資料點會動態插入 [!DNL Audience Manager] 協力廠商廣告伺服器巨集的畫素代碼，這些巨集用於根據促銷活動的主要報告屬性來對應和報告所有曝光次數和點按。 彙總的資料可提供行銷活動績效的統一檢視，有助於識別自訂轉換路徑，並幫助客戶改善導致轉換的廣告伺服器事件順序。

## 事件呼叫語法

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）指示代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

该事件调用会收集展示和转化数据，并将其发送到 [!DNL Audience Manager] [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS])。此过程依赖于第三方广告服务器，这些服务器将调用置于创意中，以控制插入到代码中的内容。第三方广告服务器（例如，[!DNL DFA]）可以将此代码置于每个广告展示中。而且，广告调用不会使用 [!DNL JavaScript] 或采用禁止 iframe 的嵌套技术来访问广告标记之外的发布者数据。

事件呼叫包含使用下列語法的機碼值組：

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

在索引鍵值配對中，值變數是由廣告伺服器插入的ID或巨集。 當廣告標籤載入時，會 `%macro%` 會取代為必要的對應值。 此呼叫未傳回回應。

## 支援的索引鍵值配對 {#supported-key-value-pairs}

Impression事件呼叫接受形成索引鍵值配對的資料。 下表列出及說明用來儲存這些變數的索引鍵。 如果您想要擷取和分析以下專案中的資料，其中許多專案都是必要的： [Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>廣告商的資料來源ID或整合代碼。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> <p>可选。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>您業務單位的資料來源ID或整合代碼。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-busting值。 <span class="keyword"> Audience Manager </span> 自動傳送大多數瀏覽器和代理遵循的快取控制標頭。 如果您想要執行額外的防快取動作，請將此引數納入事件呼叫中，接著納入隨機字串。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值行銷活動ID。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在此內容中， <code> d_cid </code> 例項化機碼 — 值組，可讓您將行動裝置型別與唯一使用者ID (DPUUID)建立關聯。 固定ID會決定行動裝置型別。 此值（使用者ID）會有所不同。 將機碼值組分隔為 <code> %01 </code>，這是非列印用的控制字元。 此引數接受下列索引鍵： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914：識別Android (GAID)裝置。 例如， <code> d_cid = 20914 %01 1234 </code> 指出使用者1234與Android裝置相關聯。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915：識別iOS (IDFA)裝置。 例如， <code> d_cid = 20915 %01 5678 </code> 指出使用者5678與iOS裝置相關聯。 </li> 
    </ul> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>將事件呼叫識別為曝光事件。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供中繼資料的平台的資料來源ID或整合代碼（例如DFA、Atlas、GBM、Media Math等）。 </p> <p>下列專案需要： <span class="wintitle"> Audience Optimization </span> 報表。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p> <p><code>gdpr</code> 可以為0 （GDPR不適用）或1 （GDPR適用）。</p> <p>默认值为 0。</p><p>可选。</p><p>若 <code>gdpr=1</code>，然後 <code>gdpr_consent</code> 引數應包含IAB TC同意引數，才能成功處理資料。 否則，將會捨棄所有資料。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 若 <code>gdpr=1</code>，則 <code>${gdpr_consent_XXXX}</code> 取代為 <code>gdpr_consent</code> 字串和廠商ID (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規格</a>)。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>請聯絡您的Adobe Audience Manager諮詢或帳戶負責人，取得使用者端網域的特定確切URL。

## 其他功能 —  [!DNL Audience Optimization Reports] {#additional-functionality-aor}

您可以使用畫素呼叫來提供 [Audience Optimization報表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). 另請參閱 [中繼資料檔案的概述與對應](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 如果您想要使用畫素來支援報表。

>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

