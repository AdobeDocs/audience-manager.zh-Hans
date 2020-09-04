---
description: 描述向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。 将数据发送到Audience ManagerFTP目录时，根据这些规范设置文件的名称和大小。
seo-description: 描述向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。 将数据发送到Audience ManagerFTP目录时，根据这些规范设置文件的名称和大小。
seo-title: 入站数据文件的 FTP 名称和文件大小要求
solution: Audience Manager
title: 入站数据文件的 FTP 名称和文件大小要求
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: adab01a81c0002d28c2387a20d8ae284e11a5e41
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 9%

---


# [!DNL FTP]入站数据文件的 名称和文件大小要求{#ftp-name-and-file-size-requirements-for-inbound-data-files}

描述向发送数据时需要遵循的必填字段、语法、命名约定和文件大小 [!DNL Audience Manager]。 将数据发送到Audience Manager目录时，根据这些规范设置文件的名称和大 [!DNL FTP] 小。

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. 有关详细信息，请参阅[入站数据文件的 Amazon S3 名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）在此文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 文件名语法 {#file-name-syntax}

[!DNL FTP] 文件名包含以下必需和可选元素：

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有关其他已接受的文件名格式，请参阅自 [定义合作伙伴集成](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>[!DNL Audience Manager] 仅处理 [!DNL ASCII] 和编 [!DNL UTF-8] 码文件。

### 命名元素

表定义文件名中 [!DNL FTP] 的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Audience ManagerFTP目录的路径 <span class="keyword"> 和名</span> 称。 请与客户经理联系以获取FTP目录和凭据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>一个D，告诉 <span class="keyword"> Audience Manager</span> ，数据文件是否包含您自己的用户ID、Android或iOS ID。 接受以下选项： </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>数据合作伙伴ID:</b> 这是Audience Manager分配给您的公司或组织的唯一ID。 在发送包含您自己的用户ID的数据时，请在文件名中使用此分配的ID。 例如，告 <code>...ftp_dpm_21_123456789.sync</code> 诉Audience Manager <span class="keyword"> ID为</span> 21的合作伙伴发送了文件并包含该合作伙伴分配的用户ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> 如果数据文件包含Android ID，请在数据文件名中使用ID 20914。 例如，告 <code>...ftp_dpm_20914_123456789.sync</code> 诉 <span class="keyword"> Audience Manager</span> ，数据文件仅包含Android ID。 </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA):</b> 如果数据文件包含iOS ID，请在其数据文件名中使用ID 20915。 例如，告 <code>...ftp_dpm_20915_123456789.sync</code> 诉 <span class="keyword"> Audience Manager</span> ，数据文件仅包含iOS ID。 </li> 
    </ul> <p> <p>注意： 请勿在数据文件中混合使用ID类型。 例如，如果您的文件名包含Android标识符，则不要将iOS ID或您自己的ID放入数据文件中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>ID的占位符。 例如，如果将DPID设置为数 <span class="keyword"> 据源</span> ID、Android或iOS ID，则可以将其设置为Audience ManagerID。 这样， <span class="keyword"> Audience Manager</span> 就可以将文件数据链接回您的组织。 </p> <p>例如： </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> 显示ID为21的合作伙伴已从使用ID 33的数据源发送数据。 </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> 显示ID为21的合作伙伴已发送包含Android ID的数据。 </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> 显示ID为21的合作伙伴已发送包含iOS ID的数据。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步选项包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:第三方数据提供者按用户发送要在Audience Manager系统中添加或删除的特征时的正常情况。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:允许客户和数据提供者按用户发送一列表特征，该特征应覆盖Audience Manager中给定数据源的此用户的所有现有特征。 无需将所有用户都包含在覆盖文件中。 仅包含要更改的用户。 未分配给目标数据源的特征将不被擦除。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。 将大型文件拆分为多个部分以缩短处理时间时使用。 数字表示要发送的原始文件的哪个部分。 </p> <p>为了有效处理文件，请按照以下说明拆分数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">压缩：200-300 MB </li> 
    </ul> <p>请参阅下面的前 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> 2个文件名示例</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10位数的UTC UNIX时间戳（秒）。 时间戳有助于使每个文件名都是唯一的。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip是允许的FTP文件名压缩格式。 如果使用文件压缩，请确保文件名的扩展名正确。 </p> <p>压缩文件必须为3 GB或更小。 如果文件较大，请咨询客户服务。 尽管Audience Manager可以处理大型文件，但我们可能可以帮助您减小文件大小并提高数据传输效率。 请参阅<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">入站数据传输文件的文件压缩</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件名示例 {#file-name-examples}

以下示例显示格式正确的文件名。 您的文件名可能看起来类似。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[如果您](assets/ftp_dpm_1234_1445374061.overwrite) 需要其他示例，请下载示例文件。 此文件以文件扩展名 `.overwrite` 保存。 使用简单的文本编辑器打开它。

## 接受的文件大小 {#accepted-file-sizes}

请考虑下图，以便最快／最早地处理文件，以及将数据发送到／目录时的文件大小 [!DNL Audience Manager] 限 [!DNL FTP] 制。

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件类型 </th> 
   <th colname="col2" class="entry"> 最佳大小 </th> 
   <th colname="col3" class="entry"> 最大大小 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressed（已压缩）</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>未压缩</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

