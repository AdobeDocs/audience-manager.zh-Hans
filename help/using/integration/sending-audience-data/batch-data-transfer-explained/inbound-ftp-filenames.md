---
description: 介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。在将数据发送到Audience Manager FTP目录时，根据这些规范设置文件的名称和大小。
seo-description: 介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。在将数据发送到Audience Manager FTP目录时，根据这些规范设置文件的名称和大小。
seo-title: 入站数据文件的FTP名称和文件大小要求
solution: Audience Manager
title: 入站数据文件的FTP名称和文件大小要求
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。Set the names and sizes of your files according to these specifications when you send data to an Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>不再支持入站数据文件的FTP传输。请使用Amazon S打开离线数据。See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## File Name Syntax {#file-name-syntax}

[!DNL FTP] 文件名包含以下必需和可选元素：

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {重要性=“high”}
>
>[!DNL Audience Manager] 仅限进程 [!DNL ASCII] 和 [!DNL UTF-8] 编码的文件。

### 名称元素

The table defines the elements in an [!DNL FTP] file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> FTP目录的路径和名称。有关FTP目录和凭据，请与您的客户经理联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. 接受以下选项： </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>数据合作伙伴ID：</b> 这是唯一的ID Audience Manager分配给您的公司或组织。在包含您自己的用户ID的数据中发送时，在文件名中使用指定的ID。For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GID)：</b> 如果数据文件名包含Android ID，请在数据文件名中使用ID20914。For example, <code>...ftp_dpm_20914_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA)：</b> 如果数据文件名中包含ID20915，则使用ID20915。For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>注意：请勿在数据文件中混合ID类型。例如，如果您的文件名包含Android标识符，则不要将iOS ID或自己的ID放入数据文件中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ Owner</i></code> </p> </td> 
   <td colname="col2"> <p>ID的占位符。For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>例如： </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_33_21_1123456790. sync</code> 显示ID21的合作伙伴已从使用ID33的数据源中发送数据。 </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_20914_21_1234567890. sync</code> 显示ID21已在包含Android ID的数据中发送的合作伙伴。 </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_20915_21_1234567890. sync</code> 显示ID21已在包含iOS ID的数据中发送的合作伙伴。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync同步|. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>包括以下功能的同步选项： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> 同步</code>：当第三方数据提供商在Audience Manager系统中添加或删除每个用户的特征时，正常情况下的正常情况。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> 覆盖</code>：允许客户和数据提供商根据每个用户发送特征列表，在Audience Manager中为给定数据源覆盖所有此用户的现有特征。您无需在覆盖文件中包含所有用户。仅包括要更改的用户。未分配给目标数据源的特征将不会被删除。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>整数。将大文件拆分为多个部分以缩短处理时间时使用。数字指示您要发送的原始文件的哪部分。 </p> <p>要进行有效的文件处理，请按指示拆分您的数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩：GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">压缩：200-300MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>时间戳</i></code> </p> </td> 
   <td colname="col2"> <p>10秒，UTC UNIX时间戳。时间戳有助于使每个文件名唯一。 </p> 
    <draft-comment> 
     <p> <p>注意：Audience Manager在处理入站文件时不使用时间戳。文件名中的时间戳已在Audience Manager中弃用，但仍需要向后兼容性。 </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip是FTP文件名允许的压缩格式。如果使用文件压缩，请确保文件名具有适当的扩展名。 </p> <p>压缩的文件必须为GB或更小。如果文件文件较大，请咨询客户服务部门。虽然Audience Manager可以处理大文件，但我们可能能够帮助您减小文件大小，并提高数据传输效率。See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

以下示例显示格式化正确的文件名。您的文件名可能类似。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_478_1366545717.overwrite</code> </li> 
</ul>

[如果](assets/ftp_dpm_1234_1445374061.overwrite) 需要其他示例，请下载示例文件。This file is saved with the `.overwrite` file extension. 使用简单的文本编辑器打开它。

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL FTP] directory.

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
   <td colname="col2"> <p>200-300MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>未压缩</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

