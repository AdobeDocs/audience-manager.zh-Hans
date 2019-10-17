---
description: 描述用于命名出站数据文件的必填字段、语法和约定。
seo-description: 描述用于命名出站数据文件的必填字段、语法和约定。
seo-title: 出站数据文件名语法和示例
solution: Audience Manager
title: 出站数据文件名语法和示例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# 出站数据文件名：语法和示例{#outbound-data-file-name-syntax-and-examples}

描述用于命名出站数据文件的必填字段、语法和约定。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>样式元素(`monospaced text`斜 *体*、括 `[ ]``( )`号等)在本文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 语法和文件名元素 {#syntax-file-name}

出站文件名包含以下元素。 以下所有元素都是可选的。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 参数

该表定义了出站数据文件名中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>指数据传输方法。 传输方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP —— 使用SFTP传输 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> -传输到 <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目标ID。 </p> <p>在 <span class="keyword"> Audience Manager中，目 </span>标是集成的实例，您可以在其中映射目标区段。 根据业务需求，客户可以有多个目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>数据提供者或数据源ID。 此ID标识文件内容中存在的用户ID的类型。 最常见的用户ID密钥有： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google广告商ID( </span> 原始，未哈希) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers(原始 </span> 、未哈希) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">供应商ID —— 第三方用户ID(Web/cookie) </li> 
     </ul> </p> <p>有关更 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">多详细信息</a> ，请参阅全局数据源。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 来自第三方平台的客户标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一个宏占位符，用于根据同步类型向文件名添加标签。 同步类型包括完全和增量。 它们将以或的形式出现在文件名 <code> iter </code> 中 <code> full </code>。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>:表示“迭代”或增量同步。 增量文件仅包含自上次同步以来收集的新数据。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>:指示“完全”同步。 完全同步的文件包含旧数据和自上次同步以来收集的任何新数据。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>UTC时区中的13位UNIX时间戳（以毫秒为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整数。 识别被分割为多个部分的文件的一部分，以缩短处理时间。 数字指示数据所属的原始文件的哪一部分。</p>  <p>如果拆分大小小于100个部分，则该整数必须至少长3位，前面加零。</p>  <p>原始文件没有任何拆分号。 第一个拆分文件将以001结束。 请参阅以下示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP压缩。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件名示例 {#file-name-examples}

### 场景1

将文件发送到某个 [!DNL Amazon S3] 位置，包含文 *`PID_ALIAS="XYZCustomer"`* 件内 [!DNL Google Advertiser IDs] 容中的文件和内容。

例如，增量文件：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

例如，完整文件：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 场景2

将文件发送到位 [!DNL FTP] 置，文件内 *`PID_ALIAS`* 容中 [!DNL Apple Advertiser IDs] 不包含和包含：

例如，增量文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如，完整文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**场景3**:将文件发送到位 [!DNL FTP] 置，文件内 *`PID_ALIAS="XYZCustomer"`* 容中包含第三方用户ID和第三方用户ID( *`Vendor ID=45454`*):

例如，增量文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如，完整文件：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 出站数据文件内容：语法和参数 {#outbound-contents-syntax}

描述用于组织出站数据文件中信息的必填字段、语法和约定。 根据这些规范设置数据格式。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>样式元素(`monospaced text`斜 *体*、括 `[ ]``( )`号等)在本文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

### 语法

数据文件中的字段按以下顺序显示：

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 参数

该表列出了定义数据文件内容的变量。

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
   <td colname="col2"> <p>由 <span class="keyword"> Audience Manager分配的唯一用户ID </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>用空格分隔UUID和段数据 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>访客所属的区段ID。 用逗号分隔多个区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>用户被取消资格的区段ID。 用逗号分隔多个区段。 通过完全同步，您可以忽略删除的区段，因为数据文件将包含用户当前区段的完整列表。 通常，您需要了解用户所属的区段，而不是已从中删除的区段。 另请参阅 <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 出站数据文件名：语法和示例 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 示例：基本文件格式

格式正确的数据文件可能与以下示例类似。 此文件条目表示用户有资格使用区段24、26和27。 根据需要，空格将分隔ID `UUID` 和段ID。 另一个空格将区段ID集分开。 在此示例中，用户属于区段24、26和27。 它们已从第25和28个区段中删除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
