---
description: 說明將資料傳送至Audience Manager時，必須遵循的欄位、語法、命名慣例和檔案大小。 將資料傳送至Audience ManagerFTP目錄時，請根據這些規格設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 入站数据文件的 FTP 名称和文件大小要求
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 6%

---

# [!DNL FTP]入站数据文件的 名称和文件大小要求 {#ftp-name-and-file-size-requirements-for-inbound-data-files}

說明將資料傳送至時需要遵循的必要欄位、語法、命名慣例和檔案大小 [!DNL Audience Manager]. 將資料傳送至Audience Manager時，請依照這些規格設定檔案的名稱和大小 [!DNL FTP] 目錄。

>[!WARNING]
>
>我們正在逐步淘汰對下列專案的支援 [!DNL FTP] 設定。 雖然現有系統仍支援傳入資料檔案擷取 [!DNL FTP] 整合，我們強烈建議使用 [!DNL Amazon S3] 載入離線資料以進行新整合。 有关详细信息，请参阅[入站数据文件的 Amazon S3 名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）檔案中會指示程式碼元素和選項。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 檔案名稱語法 {#file-name-syntax}

[!DNL FTP] 檔案名稱包含下列必要和選用元素：

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

如需其他接受的檔案名稱格式，請參閱 [自訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] 僅限程式 [!DNL ASCII] 和 [!DNL UTF-8] 編碼檔案。

### 為元素命名

此表格會定義 [!DNL FTP] 檔案名稱。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>的路徑和名稱 <span class="keyword"> Audience Manager</span> ftp目錄。 請聯絡您的帳戶管理員，以取得FTP目錄和認證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>一個可以告知 <span class="keyword"> Audience Manager</span> 如果資料檔案包含您自己的使用者ID、Android ID、iOS ID或其他屬於的ID <a href="/help/using/features/global-data-sources.md"> 全域資料來源</a>. 接受下列選項：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料來源ID （也稱為資料提供者ID）：</b> 這是Audience Manager指派給資料來源的唯一ID (請參閱Audience Manager <a href="/help/using/reference/ids-in-aam.md"> ID索引 </a>)。 傳送包含您自己的使用者ID的資料時，在檔案名稱中使用此指派的ID。 例如， <code>...ftp_dpm_21_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 將資料內建至屬於資料來源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID)：</b> 如果資料檔案包含Android ID，請在資料檔案名稱中使用ID 20914。 您需要使用欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 使用Android ID時。 例如， <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID，且這些ID應符合屬於以下類別的特徵： <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料來源。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA)：</b> 如果資料檔案包含iOS ID，請在資料檔案名稱中使用ID 20915。 您需要使用欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 當您使用iOS ID時。 例如， <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOS ID，且這些ID應符合屬於以下類別的特徵： <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料來源。</li>
     <li> <b>屬於其他全域資料來源的ID</b>：您可以加入Roku ID for Advertising (RIDA)、Microsoft Advertising ID (MAID)和其他ID。 使用與每個資料來源相對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全域資料來源文章</a>.</li> 
    </ul> <p> <p>注意：請勿在資料檔案中混用ID型別。 例如，如果您的檔案名稱包含Android識別碼，請勿在資料檔案中放入iOS ID或您自己的ID。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位會告訴Audience Manager要將資料上線到的資料來源。 如果您將DPID設為Android ID或iOS ID或其他屬於全域資料來源的ID，則此欄位為必填欄位。 這可讓 <span class="keyword"> Audience Manager</span> 將檔案資料連結回您的組織。 <br> 此目標資料來源必須由您的公司擁有。 出於第二方資料共用的目的，若要將資料擷取到屬於另一個公司的目標資料來源，您的公司與目標資料來源之間必須有存取對應。 若要設定對應，請聯絡您的Adobe顧問或客戶支援。</p><p><b>重要注意事項：</b> 您 <i>不要</i> 需要請求現有資料共用關係的對應（針對屬於您在2022年3月14日之前將資料上線到的其他公司的目標資料來源）。 將資料上線至屬於您的PID的目標資料來源時，也不一定需要對應。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告訴Audience Manager您符合資料來源33的客戶ID資格，符合資料來源21的特徵或訊號。 </li> 
     <li> <b>Android ID (GAID)：</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID，且這些ID應符合屬於資料來源21的特徵資格。</li> 
     <li> <b>iOS ID (IDFA)：</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOS ID，且這些ID應符合屬於資料來源21的特徵資格。</li>
     <li> <b>屬於其他全域資料來源的ID</b>： <code>...ftp_dpm_121963_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Roku ID，且這些ID應符合屬於資料來源21的特徵資格。 使用與每個資料來源相對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全域資料來源文章</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：第三方資料提供者傳送要新增至Audience Manager系統或從中移除的特徵給個別使用者的正常案例。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：可讓客戶和資料提供者傳送每個使用者的特徵清單，清單應會覆寫Audience Manager中指定資料來源的使用者所有現有特徵。 您不需要在覆寫檔案中包含所有使用者。 僅包含您要變更的使用者。 不會清除未指派給目標資料來源的特徵。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 當您將大型檔案分割成多個部分以縮短處理時間時使用。 數字表示您傳送的原始檔案的哪個部分。 </p> <p>為有效率地處理檔案，請分割您的資料檔案，如下所示： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">已壓縮：200-300 MB </li> 
    </ul> <p>請參閱前2項 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> 檔案名稱範例</a> 下方的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>以秒為單位的10位數UTC UNIX時間戳記。 時間戳記有助於讓每個檔案名稱是唯一的。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip是FTP檔案名稱允許的壓縮格式。 如果您使用檔案壓縮，請確定檔案名稱具有適當的副檔名。 </p> <p>壓縮檔案大小必須為3 GB或以下。 如果您的檔案較大，請洽詢客戶服務。 雖然Audience Manager可以處理大型檔案，但我們或許可以協助您縮減檔案大小，並提高資料傳輸效率。 请参阅<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">入站数据传输文件的文件压缩</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名稱範例 {#file-name-examples}

下列範例顯示格式正確的檔案名稱。 您的檔案名稱可能類似。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[下載](assets/ftp_dpm_1234_1445374061.overwrite) 範例檔案（如果需要其他範例）。 此檔案會與 `.overwrite` 副檔名。 使用簡單的文字編輯器將其開啟。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，以瞭解處理檔案的速度最快/最早，以及在您將資料傳送至時檔案大小限制 [!DNL Audience Manager] / [!DNL FTP] 目錄。

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件类型 </th> 
   <th colname="col2" class="entry"> 最佳大小 </th> 
   <th colname="col3" class="entry"> 大小上限 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressed（已压缩）</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>未壓縮</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

