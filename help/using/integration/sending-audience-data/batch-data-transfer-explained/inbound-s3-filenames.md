---
description: 描述向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。 将数据发送到Audience Manager/Amazon S3目录时，请根据这些规范设置文件的名称和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 入站数据文件的 Amazon S3 名称和文件大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: 3e25db0fc74a0b125f4f0ecd0f45f3fb877be099
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 4%

---

# [!DNL Amazon S3] 入站数据文件的名称和文件大小要求 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

介绍向发送数据时需要遵循的必填字段、语法、命名约定和文件大小 [!DNL Audience Manager]. 在将数据发送到 [!DNL Audience Manager] / [!DNL Amazon S3] 目录访问Advertising Cloud的帮助。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中指示了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 文件名语法 {#file-name-syntax}

[!DNL S3] 文件名包含以下必需和可选元素：

* **[!DNL S3]前缀：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **文件名元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有关其他接受的文件名格式，请参阅 [自定义合作伙伴集成](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] 仅进程 [!DNL ASCII] 和 [!DNL UTF-8] 编码文件。

### 命名元素

该表定义了 [!DNL S3] 文件名。

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3存储段的路径和名称。 有关S3目录名称、路径和凭据，请联系您的客户经理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>将文件发送到S3存储段的时间戳（基于UTC时间）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>一个能说明 <span class="keyword"> Audience Manager</span> 如果数据文件包含您自己的用户ID、Android ID、iOS ID或属于 <a href="/help/using/features/global-data-sources.md"> 全局数据源</a>. 接受以下选项：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>数据源ID（也称为数据提供程序ID）：</b> 这是Audience Manager分配给数据源的唯一ID(请参阅Audience Manager <a href="/help/using/reference/ids-in-aam.md"> ID索引 </a>)。 发送包含您自己的用户ID的数据时，请在文件名中使用此分配的ID。 例如， <code>...ftp_dpm_21_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 将数据载入到属于数据源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> 如果数据文件名中包含Android ID，请在其中使用ID 20914。 您需要使用该字段 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 使用Android ID时。 例如， <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 数据文件仅包含Android ID，且ID应符合属于 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 数据源。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA):</b> 如果数据文件名中包含iOS ID，请在其中使用ID 20915。 您需要使用该字段 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 使用iOS ID时。 例如， <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告知 <span class="keyword"> Audience Manager</span> 数据文件仅包含iOS ID，且ID应符合属于 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 数据源。</li>
     <li> <b>属于其他全局数据源的ID</b>:您可以载入Roku ID for Advertising(RIDA)、Microsoft Advertising ID(MAID)和其他ID。 使用与每个数据源对应的ID，如 <a href="/help/using/features/global-data-sources.md"> 全局数据源文章</a>.</li> 
    </ul> <p> <p>注意：请勿在数据文件中混合使用ID类型。 例如，如果您的文件名包含Android标识符，则不要将iOS ID或您自己的ID放置在数据文件中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此字段告知Audience Manager要将数据载入到哪个数据源。 如果您将DPID设置为Android ID、iOS ID或属于全局数据源的其他ID，则此字段为必填字段。 这允许Audience Manager将文件数据关联回您的组织。 <br> 此目标数据源需要归您的公司所有。 出于第二方数据共享的目的，要将数据摄取到属于其他公司的目标数据源中，您必须在您的公司和目标数据源之间具有访问映射。 请联系您的Adobe顾问或客户支持以设置映射。</p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告知Audience Manager您是否符合属于数据源33的客户ID的资格条件，以识别属于数据源21的特征或信号。 </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 数据文件仅包含Android ID，且ID应符合属于数据源21的特征的条件。</li> 
     <li> <b>iOS ID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 数据文件仅包含iOS ID，且ID应符合属于数据源21的特征的条件。</li>
     <li> <b>属于其他全局数据源的ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> 告知 <span class="keyword"> Audience Manager</span> 数据文件仅包含Roku ID，且ID应符合属于数据源21的特征资格。 使用与每个数据源对应的ID，如 <a href="/help/using/features/global-data-sources.md"> 全局数据源文章</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在中使用的公司或组织名称 <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>以秒为单位的10位UTC UNIX时间戳。 时间戳有助于使每个文件名都是唯一的。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步选项包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:第三方数据提供商按用户发送特征，以在Audience Manager系统中添加或删除的正常情况。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:允许数据提供程序按用户发送一个特征列表，该列表应会覆盖Audience Manager中此数据提供程序的该用户现有的所有第三方特征。 您无需在覆盖文件中包含所有用户。 仅包括那些要更改的用户。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。 将大文件拆分为多个部分时使用，以缩短处理时间。 数字表示您发送的原始文件的哪个部分。 </p> <p>为了高效处理文件，请按照以下指示拆分数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">压缩：200-300兆字节 </li> 
    </ul> <p>请参阅前2个 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> 文件名示例</a> 下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>将文件发送到Amazon S3时，请仅使用gzip压缩。 压缩后，这些文件将获取 <code> .gz</code> 扩展。 请勿使用.zip压缩。 </p> <p>压缩文件必须为3 GB或更小。 如果文件较大，请联系客户关怀团队。 尽管Audience Manager可以处理大文件，但我们可能可以帮助您减小文件大小并提高数据传输效率。 请参阅<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">入站数据传输文件的文件压缩</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件名示例 {#file-name-examples}

以下示例显示格式正确的文件名。 您的文件名可能看起来类似。

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

您可以 [下载](assets/ftp_dpm_1234_1445374061.overwrite) 示例文件（如果需要其他示例）。 此文件已与 `.overwrite` 文件扩展名。 使用简单的文本编辑器将其打开。

## 已接受的文件大小 {#accepted-file-sizes}

请考虑下图，以了解文件处理速度最快/最早的情况，以及在将数据发送到 [!DNL Audience Manager] / [!DNL Amazon S3] 目录访问Advertising Cloud的帮助。

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
   <td colname="col2"> <p>200-300兆字节 </p> </td> 
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
>集客数据验证过程会将空文件标记为无效，且不会处理它们。

## 行长限制 {#line-limits}

入站数据文件的行长限制为102400字节。 超过此限制的行将从转移中排除。

>[!MORELIKETHIS]
>
>* [入站数据文件的 FTP 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

