---
description: 資料檔案包含曝光數、點按數或轉換資料。 格式正確後，您可以將此資料匯入Audience Manager，並用於Audience Optimization報表和可操作的記錄檔。 根據本節中的規格格式化您的資料檔案。
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Audience Optimization 报表的数据文件以及可操作的日志文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 4%

---

# Audience Optimization 报表的数据文件以及可操作的日志文件 {#data-files-for-audience-optimization-reports}

資料檔案包含曝光數、點按數或轉換資料。 格式正確後，您可以將此資料匯入Audience Manager，以便在 [Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 並透過以下方式使用資料建立特徵： [可操作的記錄檔](/help/using/integration/media-data-integration/actionable-log-files.md). 依照本節中的這些規格來格式化您的資料檔案。

## 概述 {#overview}

正確命名和格式化的資料檔案可讓您將曝光數、點選數或轉換資料匯入 [Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). 在與未整合的合作夥伴合作時，此功能會很有用 [!DNL Audience Manager] 而且您想要在該報表套裝中處理其資料。 此程式需要不同的曝光數、點按數和轉換資料檔案。 請勿在單一檔案中混合使用這些事件。

資料檔案必須隨附中繼資料檔案。 中繼資料檔案內容會將資料檔案資訊與報表功能表中人工可讀的相關標籤相符。 如需詳細資訊，請參閱 [中繼資料檔案的概述與對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## 資料檔案的命名慣例 {#naming-conventions}

下列語法定義格式正確的資料檔案名稱的結構。 注意， *斜體* 表示會根據檔案內容而變更的變數預留位置。

**语法：** <pre><i>事件型別</i>_<i>yyyymmdd</i></code></pre>

在檔案名稱中：

* 事件型別會指出檔案包含曝光、點按或轉換。 為每個事件型別建立個別的檔案。
* 事件型別與年 — 月 — 日時間戳記之間以底線分隔。
* 上傳前，請先使用gzip壓縮檔案，然後使用 `.gz` 副檔名。

基於這些需求，請根據資料檔案的內容為檔案命名，如下所示：

* 曝光資料： <pre>曝光次數_<i>yyyymmdd</i>.gz</code></pre>
* 按一下資料： <pre>點按次數_<i>yyyymmdd</i>.gz</code></pre>
* 轉換資料： <pre>轉換_<i>yyyymmdd</i>.gz</code></pre>

## 資料檔案的內容格式 {#content-format}

下列語法會定義格式正確的資料檔案中的內容結構。 注意， *斜體* 表示變數預留位置，並在實際資料檔案中以標籤取代。

**语法：** <pre><i>頁首標籤1</i> | <i>頁首標籤2</i> ... <i>頁首標籤n</i> | <i>版本</i></code></pre>

在檔案內容中：

* 頁首標籤必須依照下表所示的順序顯示。 曝光次數和點按次數使用相同的標籤。 轉換檔案包含額外的標頭。
* 如果您沒有特定欄的資料，請以該欄位填入 `-1`.

* 檔案 *必須* 以版本編號結尾。 目前的版本是1.1。
* 以非列印ASCII 001字元分隔檔案標題和內容。 如果您無法使用ASCII 001，請使用定位字元分隔標題和資料。 由於這些是非列印字元，上述語法範例顯示一個垂直號 `"|"` 僅供顯示之用。

**欄位標籤**

下表列出並說明資料檔案的欄標題。 標頭區分大小寫，且必須依表格中的順序顯示。 除非另有指示，否則所有資料型別均為整數(INT)。

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>時間戳記 </p> </td> 
   <td colname="col2"> <p>曝光、點按或轉換事件的UTC日期和時間。 使用 <code> yyyy-MM-dd HH:mm:ss</code> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者ID </p> </td> 
   <td colname="col2"> <p>您網站訪客的ID，也稱為 <span class="term"> 資料提供者不重複使用者識別碼</span> 或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>廣告商的資料來源ID或整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>業務單位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>促销活动 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>创作 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>网站 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>位置ID </p> </td> 
   <td colname="col2"> <p> 來自廣告伺服器的數值位置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>插入訂單ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>戰術ID </p> </td> 
   <td colname="col2"> <p>策略ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>垂直產業或類別的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数量 </p> </td> 
   <td colname="col2"> <p> 轉換事件中出售的專案數。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>購買或其他轉換金額。 資料型別：浮點數。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other-Data </p> </td> 
   <td colname="col2"> <p>轉換登陸頁面的URL。 数据类型：字符串. </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>轉換型別。 指出是否符合轉換。 选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 印象 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>：未歸因或未知 </li> 
    </ul> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>必要的版本編號，顯示在曝光、點按或轉換資料檔案中每一列的結尾。 目前的版本是1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料檔案的傳送方法 {#delivery-methods}

將您的印象、點選或轉換資料檔案上傳至Amazon S3目錄，以供 [!DNL Audience Manager] 帳戶。 請參閱本節以瞭解有關傳送/目錄路徑、檔案處理時間和更新的資訊。

>[!IMPORTANT]
>
> 請聯絡您的Audience Manager顧問或客戶服務，以開始並設定 [!DNL Amazon S3] 資料檔案的目錄。

**傳遞路徑語法和範例**

資料會儲存在中每個客戶的個別名稱空間中， [!DNL Amazon S3] 目錄。 檔案路徑會遵循下列語法。 注意， *斜體* 表示變數預留位置。 其他元素為常數或索引鍵，不會變更。

**语法：** <pre>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>檔案型別</i>_<i>yyyymmdd</i></code></pre>

下表定義檔案傳送路徑中的每一個元素。

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案引數 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>這是目錄儲存路徑的開頭。 一切設定完成後，您將會收到完整路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此機碼值組包含 <span class="keyword"> Audience Manager</span> 客戶ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此機碼值組包含傳入事件呼叫的資料來源ID。 它可識別資料來自的機構，並將資料連結至支援的中繼資料檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 資料檔案的較高層級目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>指出包含哪種資料排序和傳送時間戳記的檔案型別名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例上傳路徑和檔案名稱**

上傳檔案時，路徑看起來類似這樣：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**檔案處理時間和更新**

資料檔案會定期一天處理四次。

若要更新資料，請傳送包含特定日期所有曝光數、點按數或轉換數的檔案。 在此情況下，一天是從一個午夜到下一個午夜的24小時期間。 最佳做法是使用UTC時間來定義您的日期間隔。

## 后续步骤 {#next-steps}

檢閱命名和建立中繼資料檔案的需求。 若要開始使用，請參閱 [中繼資料檔案的概述與對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
