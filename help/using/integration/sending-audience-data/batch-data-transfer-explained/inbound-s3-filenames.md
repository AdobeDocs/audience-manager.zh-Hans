---
description: 說明將資料傳送至Audience Manager時，必須遵循的欄位、語法、命名慣例和檔案大小。 將資料傳送至Audience Manager/Amazon S3目錄時，請根據這些規格設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 入站数据文件的 Amazon S3 名称和文件大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 4%

---

# [!DNL Amazon S3] 傳入資料檔案的名稱和檔案大小要求 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

說明將資料傳送至時需要遵循的必要欄位、語法、命名慣例和檔案大小 [!DNL Audience Manager]. 將資料傳送至時，請根據這些規格設定檔案的名稱和大小 [!DNL Audience Manager] / [!DNL Amazon S3] 目錄。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）檔案中會指示程式碼元素和選項。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 檔案名稱語法 {#file-name-syntax}

[!DNL S3] 檔案名稱包含下列必要和選用元素：

* **[!DNL S3]前置詞：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **文件名称元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有关其他已接受的文件名格式，请参阅 [ 自定义合作伙伴集成 ](/help/using/integration/sending-audience-data/custom-partner-integrations.md) 。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] 仅处理 [!DNL ASCII] 和 [!DNL UTF-8] 编码文件。

### 命名元素

此表格會定義 [!DNL S3] 檔案名稱。

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3貯體的路徑和名稱。 請連絡您的帳戶管理員，取得您的S3目錄名稱、路徑和認證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>将文件发送到 S3 存储段时的时间戳（基于 UTC 时间）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>一个 lD，告知 <span class="keyword"> Audience Manager </span> 数据文件是否包含您自己的用户 Id、Android Id、iOS id 或属于 <a href="/help/using/features/global-data-sources.md"> 全局数据源 </a> 的其他 id。 接受以下选项：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料來源ID （也稱為資料提供者ID）：</b> 這是Audience Manager指派給資料來源的唯一ID (請參閱Audience Manager <a href="/help/using/reference/ids-in-aam.md"> ID索引 </a>)。 傳送包含您自己的使用者ID的資料時，在檔案名稱中使用此指派的ID。 例如， <code>...ftp_dpm_21_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 將資料內建至屬於資料來源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID)：</b> 如果資料檔案包含Android ID，請在資料檔案名稱中使用ID 20914。 您需要使用欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 使用Android ID時。 例如， <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID，且這些ID應符合屬於以下類別的特徵： <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料來源。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA)：</b> 如果資料檔案包含iOS ID，請在資料檔案名稱中使用ID 20915。 您需要使用欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 當您使用iOS ID時。 例如， <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOS ID，且這些ID應符合屬於以下類別的特徵： <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料來源。</li>
     <li> <b>屬於其他全域資料來源的ID</b>：您可以加入Roku ID for Advertising (RIDA)、Microsoft Advertising ID (MAID)和其他ID。 使用與每個資料來源相對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全域資料來源文章</a>.</li> 
    </ul> <p> <p>注意：請勿在資料檔案中混用ID型別。 例如，如果您的檔案名稱包含Android識別碼，請勿在資料檔案中放入iOS ID或您自己的ID。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位會告訴Audience Manager要將資料上線到的資料來源。 如果您將DPID設為Android ID或iOS ID或其他屬於全域資料來源的ID，則此欄位為必填欄位。 這可讓Audience Manager將檔案資料連結回您的組織。 <br> 此目標資料來源必須由您的公司擁有。 对于第二方数据共享目的，为了将数据插入属于其他公司的目标数据源，您必须在公司和目标数据源之间进行访问映射。 要设置映射，请联系您的 Adobe Systems 顾问或客户支持。</p> <p><b>重要说明： </b> 您 <i> 不 </i> 需要请求现有数据共享关系的映射（对于属于您在3月14日2022之前载入数据的其他公司的目标数据源）。 將資料上線至屬於您的PID的目標資料來源時，也不一定需要對應。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告訴Audience Manager您符合資料來源33的客戶ID資格，符合資料來源21的特徵或訊號。 </li> 
     <li> <b>Android ID (GAID)：</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID，且這些ID應符合屬於資料來源21的特徵資格。</li> 
     <li> <b>iOS ID (IDFA)：</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOS ID，且這些ID應符合屬於資料來源21的特徵資格。</li>
     <li> <b>属于其他全局数据源 </b> 的 id： <code>...ftp_dpm_121963_21_1234567890.sync</code> 通知 <span class="keyword"> Audience Manager </span> 数据文件仅包含 Roku id，而 id 应符合属于数据源21的特征。 请使用对应于每个数据源的 ID，如全局数据源文章 </a> 中 <a href="/help/using/features/global-data-sources.md"> 所述。</a></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在 Audience Manager </span> 中 <span class="keyword"> 使用的公司或组织名称。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>一个10位数的 UTC UNIX 时间戳（以秒为单位）。 时间戳有助于使每个文件名具有唯一性。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：第三方資料提供者傳送要新增至Audience Manager系統或從中移除的特徵給個別使用者的正常案例。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：可讓資料提供者傳送每個使用者的特徵清單，清單應會覆寫Audience Manager中此資料提供者的所有現有協力廠商特徵。 您不需要在覆寫檔案中包含所有使用者。 僅包含您要變更的使用者。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 當您將大型檔案分割成多個部分以縮短處理時間時使用。 數字表示您傳送的原始檔案的哪個部分。 </p> <p>为了高效地进行文件处理，请按指示拆分您的数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩： 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">已压缩： 200-300 MB </li> 
    </ul> <p>请参阅下面的前 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> 个文件名示例 </a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>将文件发送到 Amazon S3 时，仅使用 gzip 压缩。 压缩后，这些文件将 <code> .gz</code> 获得扩展。 請勿使用.zip壓縮。 </p> <p>壓縮檔案大小必須為3 GB或以下。 如果您的檔案較大，請洽詢客戶服務。 雖然Audience Manager可以處理大型檔案，但我們或許可以協助您縮減檔案大小，並提高資料傳輸效率。 请参阅<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">入站数据传输文件的文件压缩</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件名称示例 {#file-name-examples}

以下示例显示格式正确的文件名称。 您的文件名看起来可能类似。

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

您可以 [下載](assets/ftp_dpm_1234_1445374061.overwrite) 範例檔案（如果您需要其他範例）。 此檔案已與 `.overwrite` 副檔名。 使用簡單的文字編輯器將其開啟。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，以瞭解處理檔案的速度最快/最早，以及在您將資料傳送至時檔案大小限制 [!DNL Audience Manager] / [!DNL Amazon S3] 目錄。

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


>[!NOTE]
>
>入站数据验证过程会将空文件标记为无效，而不会处理它们。

## 行長度限制 {#line-limits}

傳入資料檔案的行長度限製為102400個位元組。 超出此限制的行會從傳輸中排除。

>[!MORELIKETHIS]
>
>* [入站数据文件的 FTP 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

