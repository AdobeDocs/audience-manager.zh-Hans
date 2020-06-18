---
description: 描述向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。 将数据发送到Audience Manager/Amazon S3目录时，根据这些规范设置文件的名称和大小。
seo-description: 描述向Audience Manager发送数据时需要遵循的必填字段、语法、命名约定和文件大小。 将数据发送到Audience Manager/Amazon S3目录时，根据这些规范设置文件的名称和大小。
seo-title: 入站数据文件的Amazon S3名称和文件大小要求
solution: Audience Manager
title: 入站数据文件的Amazon S3名称和文件大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 2%

---


# 入站数据文件的Amazon S3名称和文件大小要求{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

描述向发送数据时需要遵循的必填字段、语法、命名约定和文件大小 [!DNL Audience Manager]。 将数据发送到／目录时，根据这些规范设置文件的名称 [!DNL Audience Manager] 和大 [!DNL Amazon S3] 小。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）在此文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 文件名语法 {#file-name-syntax}

[!DNL S3] 文件名包含以下必需和可选元素：

* **[!DNL S3]前缀：**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **文件名元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有关其他已接受的文件名格式，请参阅自 [定义合作伙伴集成](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE] {importance=&quot;high&quot;}
>
>[!DNL Audience Manager] 仅处理 [!DNL ASCII] 和编 [!DNL UTF-8] 码文件。

### 命名元素

表定义文件名中 [!DNL S3] 的元素。

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
   <td colname="col2"> <p>Amazon S3存储桶的路径和名称。 请与客户经理联系，了解您的S3目录名称、路径和凭据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>将文件发送到S3存储桶的时间的时间戳（基于UTC时间）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>数 <span class="term"> 据提供者ID</span> (DPID)是一个标识符，用于告知 <span class="keyword"> Audience Manager</span> ，数据文件是否包含您自己的用户ID、Android或iOS ID。 接受以下选项： </p> <p> <b>数据合作伙伴ID</b> </p> <p>这是Audience Manager分配给您的公司或组织的唯一ID。 在发送包含您自己的用户ID的数据时，请在文件名中使用此分配的ID。 例如，告 <code>...ftp_dpm_21_123456789.sync</code> 诉Audience Manager <span class="keyword"> ID为</span> 21的合作伙伴发送了文件并包含该合作伙伴分配的用户ID。 </p> <p> <b>Android ID(GAID)</b> </p> <p> 如果数据文件包含Android ID，请在数据文件名中使用ID 20914作为DPID。 使用ID 20914作为DPID时，仍需要识别公司以进行 <span class="keyword"> Audience Manager</span>。 这意味着文件名必须使用参 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 数来保存您的公司ID。 例如，假设您正在使用Android ID传入文件，且您的数据提供者ID为21。 在这种情况下，文件名会如 <code>...ftp_dpm_20914_21_123456789.sync</code>下。 这会告 <span class="keyword"> 诉Audience Manager</span> ，文件包含Android ID，并且来自由ID 21标识的合作伙伴。 </p> <p> <b>iOS ID(IDFA)</b> </p> <p> 如果数据文件包含iOS ID，请在数据文件名中使用ID 20915作为DPID。 使用ID 20915作为DPID时，您仍需要识别公司以进行 <span class="keyword"> Audience Manager</span>。 这意味着文件名必须使用参 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 数来保存您的公司ID。 例如，假设您正在使用Android ID传入文件，且您的数据提供者ID为21。 在这种情况下，文件名会如 <code>...ftp_dpm_20915_21_123456789.sync</code>下。 这告诉 <span class="keyword"> Audience Manager</span> ，文件包含iOS ID，并且来自ID 21标识的合作伙伴。 </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>数据合作伙伴ID:</b> 这是Audience Manager分配给您的公司或组织的唯一ID。 在发送包含您自己的用户ID的数据时，请在文件名中使用此分配的ID。 例如，告 <code>...ftp_dpm_21_123456789.sync</code> 诉Audience Manager <span class="keyword"> ID为</span> 21的合作伙伴发送了文件并包含该合作伙伴分配的用户ID。 </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> 如果数据文件包含Android ID，请在数据文件名中使用ID 20914。 例如，告 <code>...ftp_dpm_20914_21_123456789.sync</code> 诉 <span class="keyword"> Audience Manager</span> ，数据文件仅包含Android ID。 注意，ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA):</b> 如果数据文件包含iOS ID，请在其数据文件名中使用ID 20915。 例如，告 <code>...ftp_dpm_20915_123456789.sync</code> 诉 <span class="keyword"> Audience Manager</span> ，数据文件仅包含iOS ID。 </li> 
     </ul> 
    </draft-comment> <p> <p>注意：  请勿在数据文件中混合使用ID类型。 例如，如果您的文件名包含Android标识符，则不要在数据文件中放置iOS ID或您自己的ID。 </p> </p><p>有关更 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">多详细信息</a> ，请参阅全局数据源。</p> <p>另请参阅 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 下面的条目。 </p> </td> 
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
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在公司中使用的Audience Manager或组织 <span class="keyword"> 名称</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10位数的UTC UNIX时间戳（秒）。 时间戳有助于使每个文件名都是唯一的。 </p> 
    <draft-comment> 
     <p> <p>注意：  Audience Manager在处理入站文件时不使用时间戳。 文件名中的时间戳在Audience Manager中已弃用，但仍需要时间戳才能实现向后兼容。 </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步选项包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: 第三方数据提供者按用户发送要在Audience Manager系统中添加或删除的特征时的正常情况。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: 允许列表提供者按每个用户发送一个特征，该特征Audience Manager应覆盖该数据提供者的所有用户现有的第三方特征。 无需将所有用户都包含在覆盖文件中。 仅包含要更改的用户。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。 将大型文件拆分为多个部分以缩短处理时间时使用。 数字表示要发送的原始文件的哪个部分。 </p> <p>为了有效处理文件，请按照以下说明拆分数据文件： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未压缩： 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">压缩： 200-300 MB </li> 
    </ul> <p>请参阅下面的前 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> 2个文件名示例</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>将文件发送到Amazon S3时，请仅使用gzip压缩。 压缩后，这些文件将获得扩 <code> .gz</code> 展名。 请勿使用。zip压缩。 </p> <p>压缩文件必须为3 GB或更小。 如果文件较大，请咨询客户服务。 尽管Audience Manager可以处理大型文件，但我们可能可以帮助您减小文件大小并提高数据传输效率。 请参 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> 阅入站数据传输文件的文件压缩</a>。 </p> </td> 
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

如果您 [想要其](assets/ftp_dpm_1234_1445374061.overwrite) 他示例，可以下载示例文件。 此文件已用文件扩展名 `.overwrite` 保存。 使用简单的文本编辑器打开它。

## 接受的文件大小 {#accepted-file-sizes}

请考虑下图，以便最快／最早地处理文件，以及将数据发送到／目录时的文件大小 [!DNL Audience Manager] 限 [!DNL Amazon S3] 制。

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

>[!NOTE]
>
>入站数据验证进程会将空文件标记为无效，并且不会处理它们。

>[!MORELIKETHIS]
>
>* [入站数据文件的 FTP 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

