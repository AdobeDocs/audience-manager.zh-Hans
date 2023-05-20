---
description: 有關客戶資料摘要(CDF)檔案的基本資訊，以及如何開始的說明。 如果您有興趣接收CDF檔案或只是想要更多資訊，請從這裡開始。
keywords: 第二方資料；第二方；第二方資料；第二方
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: 客户数据信息源
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有關以下專案的基本資訊： [!UICONTROL Customer Data Feed] ([!UICONTROL CDF])檔案和如何開始使用的說明。 如果您有興趣接收，請從這裡開始 [!UICONTROL CDF] 檔案或只是想要更多資訊。

## 文件内容和目的 {#file-contents-purpose}

[!UICONTROL CDF] 文件包含的数据与 [!DNL Audience Manager] 事件调用 (`/event`) 发送到我们服务器的数据相同。这包括点赞用户 Id、 [!UICONTROL trait IDs] 、 [!UICONTROL segment IDs] 以及由事件调用捕获的所有其他参数的数据。 内部 [!DNL Audience Manager] 系统会将事件数据处理到一个 [!UICONTROL CDF] 文件中，内容组织到按设置的顺序显示的字段中。 [!DNL Audience Manager] 嘗試產生 [!UICONTROL CDF] 每小時都會建立檔案，並儲存在上安全、客戶特定的貯體中 [!DNL Amazon S3] 伺服器。 我們提供這些檔案，讓您可以 [!DNL Audience Manager] 資料超出使用者介面所設限制。

>[!IMPORTANT]
>
>使用CDF檔案時，請注意下列限制：
>
>* 設定CDF檔案傳送之前，請確定您擁有來自第三方資料提供者的適當許可權，可匯出第三方特徵。 Audience Manager目前不支援使用者介面中的功能，無法向協力廠商資料提供者要求CDF檔案傳遞匯出許可權，因此請單獨與他們聯絡。
>* 您不應使用 [!UICONTROL CDF] 檔案作為Proxy來監控頁面流量、協調報表差異或計費等。


## 入门指南 {#getting-started}

沒有要啟動的自助服務程式 [!UICONTROL CDF] 檔案傳送。 聯絡您的 [!DNL Audience Manager] 顧問或客戶服務人員開始使用。 實施期間，您的 [!DNL Audience Manager] 代表將：

* 設定您的 [!DNL Amazon S3] 儲存貯體。
* 提供唯讀 [!DNL S3] 檔案儲存貯體的驗證認證。 您將無法檢視或存取其他客戶的目錄和檔案。

檔案通知和 [!UICONTROL CDF] 檔案將顯示在您的 [!DNL S3] 儲存貯體。 您負責監視和下載指派給您的檔案 [!DNL S3] 目錄。 请参阅[客户数据信息源文件处理通知](#cdf-file-processing-notifications)。

## 后续步骤 {#next-steps}

以下各節及 [客戶資料摘要常見問題集](../faq/faq-cdf.md) 可協助您進一步熟悉此服務。

## [!UICONTROL Customer Data Feed] 已定義內容 {#cdf-defined}

列出並定義中的資料元素和陣列 [!UICONTROL CDF] 檔案，依外觀順序。 定義包含資料型別，但此資訊不是的一部分 [!UICONTROL CDF] 檔案。

>[!IMPORTANT]
>
>CDF設定預設會排除事件畫素。 如果您希望將事件畫素包含在CDF檔案中，請務必在傳送給客戶服務的請求中指定。 每個事件畫素都會填入CDF檔案中的唯一列。

## 定义 {#definitions}

A [!UICONTROL CDF] 檔案包含下面定義的部分或全部欄位。 如需內部檔案組織的相關資訊，請參閱 [客戶資料摘要檔案結構](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 数据类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>時間戳記 </p> </td> 
   <td colname="col3"> <p>處理CDF檔案的時間 <span class="wintitle"> 資料收集伺服器</span> (DCS)。 時間戳記會使用 <i>yyyy-mm-dd hh:mm:ss</i> 格式並設定為UTC時區。 </p> <p> <p>注意：事件时间 <i> 不 </i> 是： <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或事件调用自身的时间，尽管可能接近这些时间。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名中的 DC 小时相关。 <a href="#different-processing-times">另请参阅客户数据馈送文件名称和文件内容时间 ... </a> 。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>這是 <span class="wintitle"> 不重複使用者ID</span> (UUID)，網站訪客的38位數裝置ID。 另请参阅 <a href="../reference/ids-in-aam.md">Audience Manager 中的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>数值 </p> </td> 
   <td colname="col3"> <p>觸發ID同步的容器的ID。 只有當您在中設定容器ID時，此欄位才會填入 <i>d_nsid</i> 欄位。 否則，預設值0將不會包含在CDF檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>一個特徵ID陣列，包含訪客在事件呼叫中實現（符合資格）的所有特徵。 </p> <p>請注意，陣列可包含訪客之前已符合資格的特徵，以及訪客透過此事件呼叫重新符合資格的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID陣列，包含訪客在事件呼叫中實現（符合）的所有區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>擷取所有引數（變數、ID、機碼值組、裝置廣告ID等）的字串。 已在事件呼叫中傳入。 </p> <p>簡短範例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>反向链接页面的未编码 URL （如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>訪客在事件呼叫中擷取的IP位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>此 <span class="keyword"> Experience Cloud</span> 指派給網站訪客的ID (MID)。 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與AdobeExperience Platform識別服務</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID陣列，包含訪客符合資格的先前實現區段和新區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特徵ID陣列，包含訪客自上次產生資料摘要以來符合資格的先前實現的特徵和新特徵。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案結構 {#cdf-file-structure}

列出並定義 [!UICONTROL CDF] 檔案。 这包括数据序列、字段分隔符和分隔符、数据文件映射和示例文件。

## 数据字段标识符和序列 {#identifiers-and-sequence}

[!UICONTROL CDF] 文件不包含已标记的列或字段标题。 相反， [!UICONTROL CDF] 文件会定义包含非打印 [!DNL ASCII] 字符的字段和数组。 此外， [!UICONTROL CDF] 檔案會以特定順序列出每個欄位和陣列。 瞭解欄位識別碼和順序將有助於您正確剖析檔案。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF檔案元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>欄位分隔符號和分隔符號 </p> </td> 
   <td colname="col2"> <p>這些非列印字元定義CDF檔案的元素和結構： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII) <code> 001</code> 或 <code> ^A</code>)會以非列印用的空格指示器分隔個別欄位中的資料。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII) <code> 002</code> 或 <code> ^B</code>)將資料分隔為陣列和要求引數。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII) <code> 003</code> 或 <code> ^C</code>)會定義機碼值組。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位順序 </p> </td> 
   <td colname="col2"> <p> <p>重要： <span class="keyword"> Audience Manager</span> 保留在未來版本中在CDF檔案結尾新增新欄位的權利。 這表示檔案剖析系統的技術設計不應假設欄數固定（雖然它可能假設現有欄的順序固定）。</p> </p> <p>CDF檔案中的資料會以下列順序顯示。/N可以取代這些欄位中的任何一個，表示null值。</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件時間 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已實現的特徵 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已實現的區段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud裝置ID （或MID）。 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與Adobe Experience Platform Identity服務</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有區段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特徵 </li> 
     </ol> </p> <p>如需欄位說明，請參閱 <a href="#cdf-defined"> 已定義客戶資料摘要內容</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 檔案地圖 {#cdf-file-map}

[!UICONTROL CDF] 文件数据按下面显示的顺序显示。

![](assets/sequence-map.png)

## 识别数组

文件中 [!UICONTROL CDF] 的数组开始并以 `Ctrl + a` 字段分隔符结尾。 这会使数组中的第一个元素显示点赞独立的数据字段。 例如，已实现 [!UICONTROL traits] 的数组以开头 `^A1234` 。 陣列分隔符號和ID `^B5678` 會依循此專案。 因此，您可能會覺得已實現中的第一個元素 [!UICONTROL traits] 陣列識別碼為5678 (因為它開頭為 `^B`)。 但事實並非如此，因此您需要熟悉資料檔案的順序和結構。 即使已實現中的第一個元素 [!UICONTROL trait] 陣列（或中任何其他陣列） [!UICONTROL CDF] file)開頭為 `^A`中，檔案中的外觀或位置順序會定義陣列的開頭。 而且，陣列中的第一個元素一律會與前一個專案分開，分隔方式如下 `^A`.

## 範例 [!UICONTROL CDF] 檔案 {#sample-file}

範例 [!UICONTROL CDF] 檔案可能類似於以下內容。 我們在此範例中插入了分行符號，以協助它符合頁面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 檔案命名慣例 {#cdf-naming-conventions}

以下各節列出並定義中的元素 [!UICONTROL CDF] 檔案名稱。

## [!UICONTROL CDF] 檔案名稱：語法和範例 {#cdf-file-name}

典型 [!UICONTROL CDF] 檔案名稱包含下列元素。 注意， *斜體* 表示變數預留位置：

### 语法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### 示例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

在您的 [!DNL S3] 儲存貯體，檔案會依合作夥伴ID ([!UICONTROL PID])、日和小時。

## [!UICONTROL CDF] 已定義的檔案名稱元素 {#cdf-file-name-elements}

下表列出并定义了文件名中 [!UICONTROL CDF] 的元素。

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名称元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>這是Amazon S3伺服器上CDF檔案的預設根儲存貯體。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>儲存CDF檔案的唯讀S3儲存貯體名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>處理您的檔案的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小時標籤法表示並以UTC時區設定的時間值。 另請參閱 <a href="#different-processing-times"> 客戶資料摘要檔案名稱時間與檔案內容時間……</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>識別檔案序列的值。 序列增量如下： 0_0_0 、 0_1_0 、 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip副檔名。 CDF檔案會以gzip壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案處理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 寫入 `.info` 檔案至您的 [!DNL S3] 目錄，通知您何時使用 [!UICONTROL Customer Data File] ([!UICONTROL CDF])已可供下載。 此 `.info` 檔案也包含 [!DNL JSON] 有關您檔案內容的格式化中繼資料 [!UICONTROL CDF] 檔案。 有关此通知文件使用的语法和字段的信息，请查看此部分。

## 示例信息文件 {#sample-info-file}

每个文件都 `.info` 包含一个 `Files` 和 `Totals` 部分。 该 `Files` 区域包含一个数组，用于保存每小时文件的特定量度。 此 `Totals` 區段包含所有量度彙總 [!UICONTROL CDF] 特定日期的檔案。 您的網站內容 `.info` 檔案看起來可能類似於以下範例。

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## 已定義的資訊檔案欄位 {#info-file-fields-defined}

下表列出並定義 [!UICONTROL CDF] `.info` 檔案。

### 檔案物件

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>啟動包含CDF檔案中繼資料的陣列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小（位元組）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 連字型大小後面的數字顯示了在多部分上傳期間用來建置檔案的部分的數量。 此 <code> ETag</code> 與檔案的MD5總和檢查碼不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>檔案名稱。 另請參閱 <a href="#cdf-naming-conventions"> 客戶資料摘要檔案命名慣例</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每個檔案的索引編號。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 總計物件

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>啟動包含所有CDF檔案之彙總資料的物件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>資料可用的日期。 使用 <i>yyyy-mm-dd</i> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>有資料可用的小時。 使用UTC時區設定的24小時格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>該日期所有CDF檔案的總大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上傳至S3目錄的檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案名稱時間與檔案內容時間不同 {#different-processing-times}

您的 [!UICONTROL CDF] 檔案包含檔案名稱和檔案內容的時間戳記。 這些時間戳記會針對相同專案記錄不同的事件程式 [!UICONTROL CDF] 檔案。 在同一個檔案的名稱和內容中看到不同的時間戳記是很常見的現象。 瞭解每個時間戳記可協助您在使用此資料或嘗試依時間排序資料時避免常見錯誤。

## 定位 [!UICONTROL CDF] 檔案時間戳記 {#locating-timestamps}

[!UICONTROL CDF] 檔案在2個不同的位置記錄時間的方式不同。

![](assets/cdf-timestamp.png)

## 瞭解時間戳記之間的差異 {#understanding-timestamps}

下表提供您專屬的 [!UICONTROL CDF] 檔案時間戳記以及如何正確使用的相關資訊。

| 時間戳記位置 | 描述 |
|--- |--- |
| 文件名 | 中的時間戳記 [!DNL CDF] 檔案名稱會標籤時間： [!DNL Audience Manager] 已開始準備檔案以進行傳送。 此時間戳記設定於 [!DNL UTC] 時區。 它會使用 `hour=` 引數，時間格式為24小時標籤法的2位數小時。 此時間可能與檔案內容中記錄的事件時間不同。 使用時 [!DNL CDF] 檔案，有時您會注意到 [!DNL S3] 值區在特定小時內為空白。 空白貯體表示可能有下列其中一種情況：<ul><li>沒有該特定小時的資料。 </li><li> 我們的伺服器負載過重，無法在特定小時內處理檔案。 當伺服器趕上進度時，會將原本應該放在較早時段檔案中的檔案放入具有較晚時間值的貯體中。 例如，當應在17小時貯體中的檔案出現在18小時貯體時(具有 `hour=18` （在檔案名稱中）。 在這種情況下，伺服器可能在17小時內開始處理您的檔案，但無法在該時間間隔內完成它。 相反地，檔案會推送至下一個每小時時段。</li></ul><br>**重要**：請勿使用檔案名稱時間戳記，依時間將事件分組。 如果您需要依時間分組，請使用 `EventTime` 檔案內容中的時間戳記。 |
| 檔案內容 | 中的時間戳記 [!DNL CDF] 檔案內容會標籤時間 [!DNL Data Collection Servers] 已開始處理檔案。 此時間戳記設定於 [!DNL UTC] 時區。 它會使用 `EventTime` 欄位，時間格式為 *`yyyy-mm-dd hh:mm:ss`*. 此时间与页面中事件的实际时间接近，但它可以不同于文件名中的小时指示器。 <br> **提示** ：与文件名中的 `hour=` 时间戳不同，您可以 `EventTime` 按时间群组数据。 |

>[!MORELIKETHIS]
>
>* [客户数据信息源常见问题解答](../faq/faq-cdf.md)

