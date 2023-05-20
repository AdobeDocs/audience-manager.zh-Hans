---
description: 中繼資料檔案會連結具有您可閱讀及瞭解之名稱的數值ID。 Audience Optimization報表會在各種報表選項選單中顯示可讀名稱。
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: 元数据文件的概述和映射
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 4%

---

# 元数据文件的概述和映射{#overview-and-mappings-for-metadata-files}

中繼資料檔案會連結具有您可閱讀及瞭解之名稱的數值ID。 Audience Optimization報表會在各種報表選項選單中顯示可讀名稱。

## 概述 {#overview}

稽核中繼資料及其使用方式。 中繼資料檔案必須隨附資料檔案。 中繼資料檔案內容會將資料檔案資訊與報表功能表中人工可讀的相關標籤相符。 如需詳細資訊，請參閱 [Audience Optimization報表的資料檔案和可操作的記錄檔](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### 中繼資料檔案包含其他資料的相關資料

中繼資料檔案包含其他資料型別的相關資訊。 為協助您瞭解此功能的運作方式，讓我們檢視其運作方式 [!DNL Audience Manager] 接收資料。

在曝光或點選事件期間， [!DNL Audience Manager] 接收URL字串(稱為 *事件呼叫*.

事件呼叫會將資訊組織成已定義的索引鍵/值組集合。 機碼值組中的值包含數值資料。 中繼資料檔案包含與每個機碼值組中的ID對應的名稱和其他可讀資訊。

### 中繼資料連結ID至可讀名稱

需要中繼資料檔案將數值ID連結至可讀取的名稱。 例如，假設事件呼叫在索引鍵/值組中包含創意ID，如下所示： `d_creative:1234`. 如果沒有中繼資料檔案，此創意內容在選項選單中會顯示為1234。

不過，格式正確的中繼資料檔案可將此創意連結回「廣告商Creative A」之類的真實名稱，這是您可以在報告中閱讀和辨識的名稱。

### 您何時需要中繼資料檔案

首先，當您想要使用 [Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

第二，如果您要將自己的資料傳送至，則需要中繼資料檔案 [!DNL Audience Manager] 或者，如果您想從其他未與我們整合的提供者那裡檢視報表中的資料。 例如， [!DNL Audience Manager] 與Google整合 [連按兩下Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM)。 由於這種關係， [!DNL Audience Manager] 可將ID與報表選項使用的名稱和說明建立關聯。 如果沒有整合，我們仍可內嵌資料，但報表選項會顯示數值ID，而非描述性名稱。

![中繼資料功能表影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 檔案對應 {#file-mappings}

下表列出儲存資料使用的機碼值組： [!UICONTROL Audience Optimization] 報表。 如果您需要使用中繼資料檔案，該檔案會包含與索引鍵值配對中值相對應且可供讀取的資訊。 這些索引鍵的值僅接受整數（資料型別INT）。 注意， *斜體* 表示變數預留位置。 其他元素為常數或索引鍵，不會變更。

>[!IMPORTANT]
>
>如果您使用 [!UICONTROL Audience Optimization] 報表、 *全部* 事件呼叫中需要這些值的其中之一。

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告選項 </th> 
   <th colname="col2" class="entry"> 中繼資料索引鍵值配對 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>广告商 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>這是廣告商的資料來源ID或建立資料來源時提供的整合代碼。 另請參閱 <a href="../../../features/manage-datasources.md#create-data-source"> 建立資料來源</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>業務單位(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促销活动 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受2個不同的機碼值組： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>這是 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料來源</a> 提供中繼資料資訊的平台ID （例如DFA、Atlas、GBM、MediaMath等）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>策略 </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直 </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件呼叫ID如何形成檔案名稱、內容和傳遞路徑 {#how-ids-shape-file-names}

這些機碼值組傳入的ID有助於建立中繼資料檔案名稱及其內容。 以下章節和插圖示範其運作方式。 這些範例會建置包含行銷活動中創意內容名稱的檔案，但可能有其他組合。

### 事件呼叫

在此範例中，我們將建立中繼資料檔案，將創意名稱帶入 [!UICONTROL Audience Optimization] 報告。 為此，我們需要從事件呼叫中擷取創意、行銷活動和資料來源ID。

![事件呼叫影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 文件名

檔案名稱以創意、行銷活動和資料來源ID為基礎。 在此案例中，比較事件呼叫中的索引鍵值資料與其在檔案名稱中的使用方式之間的差異。

在檔案名稱中：

* 資料來源金鑰變更為 `dpid` 從 `d_src`.

* 創意和促銷活動ID代表類別，而非實際識別碼。

![如何建立檔案名稱](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

另請參閱 [中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 檔案內容

在此範例中，檔案內容反映了在事件呼叫中傳入的創意和促銷活動ID。 此處的新元素為可讀名稱。 處理之後，此檔案中的名稱將在「 」的「創作」選單中顯示為一個選項。 [!UICONTROL Audience Optimization] 報告。

![中繼資料檔案的內容](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

另請參閱 [中繼資料檔案的內容格式](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 檔案傳送

將資料命名並新增至檔案後，會傳送至提供的Amazon S3儲存目錄 [!DNL Audience Manager]. 另請參閱 [中繼資料檔案的傳送方法](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [通过像素调用捕获营销活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)
>* [通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)

