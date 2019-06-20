---
description: 介绍用于命名出站数据文件的必填字段、语法和约定。
seo-description: 介绍用于命名出站数据文件的必填字段、语法和约定。
seo-title: 出站数据文件名语法和示例
solution: Audience Manager
title: 出站数据文件名语法和示例
uuid: efdcaf6-c37 c-45f3-9d2 f-a938 a9 da47 a6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Outbound Data File Name: Syntax and Examples{#outbound-data-file-name-syntax-and-examples}

介绍用于命名出站数据文件的必填字段、语法和约定。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) 本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## Syntax and File Name Elements {#syntax-file-name}

出站文件名包含以下必需和可选元素：

```
SYNC-TYPE_ DID_ MASTER-DPID_ [PID-ALIAS]_ SYNC-MODE_ TIMESTAMP[- SPLIT_NUMBER].sync[.gz]
```

### 参数

表定义出站数据文件名中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>同步-类型 </i></code> </p> </td> 
   <td colname="col2"> <p>引用数据传输方法。传输方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP-使用SFTP传输 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S </span> -传输到 <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目标ID。 </p> <p><span class="keyword"> 在Audience Manager </span>中，目标是可映射可搜索区段的集成实例。客户可以有多个目标，具体取决于业务需求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER-DPID </i></code> </p> </td> 
   <td colname="col2"> <p>数据提供者或数据源ID。此ID标识文件内容中存在的用户ID类型。大多数常用的用户ID键都是： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">供应商ID-第三方用户ID(Web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID-ALIAS </i></code> </p> </td> 
   <td colname="col2"> 第三方平台的客户标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>同步模式 </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一个宏占位符，它根据同步类型为文件名添加标签。同步类型包括完整和递增。They'll appear in the file name as <code> iter </code> or <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>：表示“迭代”或增量同步。增量文件只包含自上次同步以来收集的新数据。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>：表示“完整”同步。完全同步的文件包含旧数据和自上次同步以来收集的任何新数据。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>时间戳 </i></code> </p> </td> 
   <td colname="col2"> <p>UTC时区中的13位UNIX时间戳(以毫秒为单位)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [<code><i>-SPLIT_NUMBER </i></code>] </p> </td> 
   <td colname="col2"> <p>整数。识别拆分为多个部分的文件部分，从而缩短处理时间。数字指示数据所属的原始文件的哪一部分。 </p> <p>原始文件不会有任何拆分编号。第一个拆分文件将从1开始。请参见下面的示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz(可选) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP压缩。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

### 场景1

Files sent over to an [!DNL Amazon S3] location, with *`PID-ALIAS="XYZCustomer"`* and with [!DNL Google Advertiser IDs] in the file content.

E.g. 增量文件：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-1.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-10.sync.gz </code> </li> 
</ul>

E.g. 完整文件：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000-1.sync.gz </code> </li> 
</ul>

### 场景2

Files sent over to [!DNL FTP] location, without *`PID-ALIAS`* and with [!DNL Apple Advertiser IDs] in the file content:

E.g. 增量文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000-1.sync.gz </code> </li> 
</ul>

E.g. 完整文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000-1.sync.gz </code> </li> 
</ul>

**场景3**：发送到 [!DNL FTP] 位置的文件，以及 *`PID-ALIAS="XYZCustomer"`* 文件内容( *`Vendor ID=45454`*)中的第三方用户ID：

E.g. 增量文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-1.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-10.sync.gz </code> </li> 
</ul>

E.g. 完整文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200-1.sync.gz </code> </li> 
</ul>

## Outbound Data File Contents: Syntax and Parameters {#outbound-contents-syntax}

介绍用于在出站数据文件中组织信息的必填字段、语法和约定。根据这些规范格式化您的数据。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) 本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

### 语法

数据文件中的字段以此顺序显示：

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 参数

下表列出了定义数据文件内容的变量。

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager分配的唯一用户ID </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>用空格分隔UUID和区段数据 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Segment_ N </i></code> </p> </td> 
   <td colname="col2"> <p>访客所属的区段ID。用逗号分隔多个区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SERVER_ N </i></code> </p> </td> 
   <td colname="col2"> <p>从中取消资格的区段ID。用逗号分隔多个区段。通过完全同步，您可以忽略删除的区段，因为数据文件将包含用户当前区段的完整列表。通常，您需要了解用户属于的区段，而不是从中删除的区段。See also <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 示例：基本文件格式

格式正确的数据文件可能类似于以下示例。此文件条目表示用户对区段24、26和27有资格。As required, a space separates the `UUID` and segment IDs. 另一空间分隔区段ID集。在此示例中，用户属于区段24、26和27。它们已从25节和28节中删除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
