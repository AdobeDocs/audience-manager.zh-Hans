---
description: ID服務客戶應參閱本節，瞭解如何讀取進行DCS API呼叫所需ID的訪客Cookie。
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服務客戶應參閱本節，瞭解如何讀取需建立之ID的訪客Cookie [!DNL DCS] API呼叫。

## 從ID服務Cookie取得使用者ID {#get-user-ids-from-service-cookie}

此 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) 將訪客和地區ID指派給造訪您網站的使用者。 這些ID可識別 [!DNL Experience Cloud] 而且如果您想要 [!DNL DCS] 呼叫。

* 此 [!UICONTROL user ID] 需要識別資料並將其與特定訪客建立關聯。
* 此 [!UICONTROL region ID] 需要，因為它與地區伺服器名稱繫結，而您需要將該名稱傳送資料至 [!DNL DCS]. 此 [!DNL DCS] 會將資訊儲存在地理位置上最接近網站訪客的資料中心。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服務客戶可以從ID服務Cookie擷取此資訊，或是呼叫函式來擷取此資訊。 下表說明開始使用所需完成的工作或步驟。

中的程式碼 *斜體* 代表變數預留位置。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 檢查您的 <span class="keyword"> Experience Cloud</span> 狀態</b> </p> </td> 
   <td colname="col2"> <p>您需要 <span class="keyword"> Experience Cloud</span> 帳戶以使用ID服務。 如果您擁有 <span class="keyword"> Experience Cloud</span> 帳戶，太棒了！ </p> <p> 如果您不屬於 <span class="keyword"> Experience Cloud</span>，然後註冊。 我們很樂意擁有您，而且永遠有更多的空間。 如需如何設定帳戶的指示，請參閱 <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 啟用核心服務的解決方案</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. 設定 <span class="keyword"> ID服務</span></b> </p> </td> 
   <td colname="col2"> <p>此 <span class="keyword"> ID服務</span> 由放置於您要用於資料收集之每個頁面上的JavaScript程式碼組成。 請參閱ID服務 <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 實作指南</a> 以取得詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 閱讀 <span class="keyword"> ID服務</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p>此 <span class="keyword"> ID服務</span> 會將使用者和地區ID儲存在AMCV Cookie中。 完整的Cookie名稱為 <code>AMCV_<i>###</i>@AdobeOrg</code>. 此 <code><i>###</i></code> 元素是組織ID的預留位置。 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a> 以取得詳細資訊。 </p> <p>剖析這些機碼值組的AMCV Cookie： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>：此機碼值組保留 <span class="keyword"> Experience Cloud</span> 使用者ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>：此機碼值組保有地區ID (有時稱為 <span class="term"> 位置提示</span>)，此名稱與地區伺服器名稱相關聯。 </li> 
     </ul> </p> <p>您可以呼叫 <span class="wintitle"> DCS</span> 擁有使用者和地區ID後。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 擷取 <span class="keyword"> EXPERIENCE CLOUDID</span> 使用getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>（可選）</i> 此函式傳回 <span class="keyword"> Experience Cloud</span> 訪客ID。 專為自訂解決方案和特定使用案例而設計。 另請參閱 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 使用getMarketingCloudVisitorID</a> 下方和 <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> 相關ID服務檔案</a>. </p> <p>如果您從ID服務Cookie取得使用者和位置ID，則不需要使用此選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用 `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

另一個取得訪客ID的方法是 `getMarketingCloudVisitorID` 函式。 叫用時，此函式會查詢 [!DNL ID service] 和會傳回ID。 `getMarketingCloudVisitorID` 接受選用的 `callback` 引數，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回撥使用量和用途 {#callback-usage}

`callback` 是選用專案。 此函式可在沒有它的情況下運作，但只有在訪客擁有設定檔時才會傳回ID。 [!DNL Experience Cloud] 瀏覽器中的Cookie。 如果訪客Cookie遺失，或訪客沒有ID，此函式會傳回空白 `()` 物件。 即使頁面載入且訪客收到新ID，也可能會發生這種情況。 為避免此情況， `callback` 強制此函式在頁面載入後檢查訪客ID。 不含 `callback`，訪客ID函式將不會傳回ID，即使它稍後寫入訪客的瀏覽器中亦然。

## 后续步骤 {#next-steps}

擁有使用者和地區ID後，您就可以開始傳送和接收 [!DNL DCS] 資料。 另請參閱 [進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
