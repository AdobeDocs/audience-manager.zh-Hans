---
description: 介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。在将数据发送到Audience Manager/Amazon S目录时，根据这些规范设置文件的名称和大小。
seo-description: 介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。在将数据发送到Audience Manager/Amazon S目录时，根据这些规范设置文件的名称和大小。
seo-title: 入站数据文件Amazon S名称和文件大小要求
solution: Audience Manager
title: 入站数据文件Amazon S名称和文件大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

介绍向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## File Name Syntax {#file-name-syntax}

[!DNL S3] 文件名包含以下必需和可选元素：

* **[!DNL S3]前缀：**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **文件名元素：**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {重要性=“high”}
>
>[!DNL Audience Manager] 仅限进程 [!DNL ASCII] 和 [!DNL UTF-8] 编码的文件。

### 名称元素

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>AWS_ directory</i></code> </p> </td> 
   <td colname="col2"> <p>Amazon S bucket的路径和名称。请与您的客户经理联系，了解您的S目录名称、路径和凭据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>将文件发送到S桶时的时间戳(基于UTC时间)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="term"> 数据提供者ID</span> (DPID)是一个标识符，用于告知 <span class="keyword"> Audience Manager</span> ，如果数据文件包含您自己的用户ID或Android ID或iOS ID。接受以下选项： </p> <p> <b>数据合作伙伴ID</b> </p> <p>这是唯一的ID Audience Manager分配给您的公司或组织。在包含您自己的用户ID的数据中发送时，在文件名中使用指定的ID。For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>Android ID(GID)</b> </p> <p> 如果文件包含Android ID，请使用ID20914作为数据文件名中的DPID。When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. 例如，假设您使用Android ID传递文件，而您的数据提供者ID为21。In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>iOS ID(IDFA)</b> </p> <p> 如果文件包含iOS ID，请使用ID20915作为数据文件名中的DPID。When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. 例如，假设您使用Android ID传递文件，而您的数据提供者ID为21。In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>数据合作伙伴ID：</b> 这是唯一的ID Audience Manager分配给您的公司或组织。在包含您自己的用户ID的数据中发送时，在文件名中使用指定的ID。For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GID)：</b> 如果数据文件名包含Android ID，请在数据文件名中使用ID20914。For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. 注意，ID21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA)：</b> 如果数据文件名中包含ID20915，则使用ID20915。For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>注意：请勿在数据文件中混合ID类型。例如，如果您的文件名包含Android标识符，则不要将iOS ID或自己的ID放入数据文件中。 </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
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
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>时间戳</i></code> </p> </td> 
   <td colname="col2"> <p>10秒，UTC UNIX时间戳。时间戳有助于使每个文件名唯一。 </p> 
    <draft-comment> 
     <p> <p>注意：Audience Manager在处理入站文件时不使用时间戳。文件名中的时间戳已在Audience Manager中弃用，但仍需要向后兼容性。 </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync|. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>包括以下功能的同步选项： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> 同步</code>：当第三方数据提供商在Audience Manager系统中添加或删除每个用户的特征时，正常情况下的正常情况。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> 覆盖</code>：允许数据提供商根据每个用户发送特征列表，该列表应覆盖Audience Manager中此数据提供程序的所有现有第三方特征。您无需在覆盖文件中包含所有用户。仅包括要更改的用户。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。将大文件拆分为多个部分以缩短处理时间时使用。数字指示您要发送的原始文件的哪部分。 </p> <p>要进行有效的文件处理，请按指示拆分您的数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩：GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">压缩：200-300MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>将文件发送到Amazon S时，仅使用gzip压缩。When compressed, these files get the <code> .gz</code> extension. 请勿使用.zip压缩。 </p> <p>压缩的文件必须为GB或更小。如果您的文件较大，请咨询客户关怀。虽然Audience Manager可以处理大文件，但我们可能能够帮助您减小文件大小，并提高数据传输效率。See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

以下示例显示格式化正确的文件名。您的文件名可能类似。

<ul class="simplelist"> 
 <li> <code> sn://&lt; AWS_ Bucket&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> sn://&lt; AWS_ Bucket&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> sn://&lt; AWS_ Bucket&gt;/&lt; partner_ name&gt;/date=2016-05-09/ftp_ dpm_478_1366545717.sync</code> </li> 
 <li> <code> sn://&lt; AWS_ Bucket&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> sn://&lt; AWS_ Bucket&gt;/&lt; partner_ name&gt;/date=2016-05-09/ftp_ dpm_478_1366545717.overway</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. 使用简单的文本编辑器打开它。

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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

>[!NOTE]
>
>入站数据验证过程会将空文件标记为无效，不会处理这些文件。

>[!MORE_ LIKE_ This]
>
>* [入站数据文件的 FTP 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

