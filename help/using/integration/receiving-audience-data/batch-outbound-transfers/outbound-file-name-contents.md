---
description: 介绍用于命名出站数据文件的必填字段、语法和约定。
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: 出站数据文件名语法和示例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---

# 出站数据文件名：语法和示例{#outbound-data-file-name-syntax-and-examples}

介绍用于命名出站数据文件的必填字段、语法和约定。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>样式元素（`monospaced text`、*斜体*、括号`[ ]` `( )`等） 本文档中说明了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 语法和文件名元素 {#syntax-file-name}

出站文件名包含以下元素。 以下所有元素都是可选的。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 参数

该表定义出站数据文件名中的元素。

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
   <td colname="col2"> <p>请参阅数据传输方法。 传输方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP — 使用SFTP传输 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> — 转移到<span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目标ID。 </p> <p>在<span class="keyword">Audience Manager</span>中，目标是集成实例，您可以在其中映射可定位区段。 客户可以有多个目标，具体取决于业务需求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>数据提供程序或数据源ID。 此ID标识文件内容中存在的用户ID类型。 最常见的用户ID键为： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google广告商ID </span> （原始，未哈希） </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 — 广告商</span>的<span class="keyword"> Apple ID （原始，未哈希） </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">供应商ID — 第三方用户ID (Web/Cookie) </li> 
     </ul> </p> <p>有关更多详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html">全局数据源</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 来自第三方平台的客户标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一个宏占位符，它根据同步类型向文件名添加标签。 同步类型包括完整同步和增量同步。 它们将在文件名中显示为<code> iter </code>或<code> full </code>。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>：表示“迭代”同步或增量同步。 增量文件仅包含自上次同步以来收集的新数据。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>：表示“完全”同步。 完全同步的文件包含自上次同步以来收集的旧数据和任何新数据。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>以UTC时区表示的13位数UNIX时间戳（以毫秒为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整数。 标识被拆分为多个部分的文件部分，以缩短处理时间。 数字表示数据属于原始文件的哪个部分。</p>  <p>如果拆分大小小于100份，则整数必须至少包含3位数字，前面加零。</p>  <p>原始文件将不具有任何拆分编号。 第一个拆分文件将以001结尾。 请参阅下面的示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP压缩。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件名示例 {#file-name-examples}

### 场景1

文件已发送到[!DNL Amazon S3]位置，文件内容中包含&#x200B;*`PID_ALIAS="XYZCustomer"`*&#x200B;和[!DNL Google Advertiser IDs]。

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

文件已发送到[!DNL FTP]位置，文件内容中不包含&#x200B;*`PID_ALIAS`*&#x200B;和[!DNL Apple Advertiser IDs]：

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

**方案3**：文件已发送到[!DNL FTP]位置，在文件内容(*`Vendor ID=45454`*)中具有&#x200B;*`PID_ALIAS="XYZCustomer"`*&#x200B;和第三方用户ID：

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

介绍用于在出站数据文件中组织信息的必填字段、语法和约定。 根据这些规范格式化数据。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>样式元素（`monospaced text`、*斜体*、括号`[ ]` `( )`等） 本文档中说明了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

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
   <td colname="col2"> <p><span class="keyword">用户</span>分配的Audience ManagerID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>用空格分隔UUID和区段数据 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>访客所属的区段ID。 用逗号分隔多个区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>用户被取消资格的区段ID。 用逗号分隔多个区段。 通过完全同步，您可以忽略已删除的区段，因为数据文件将包含用户当前区段的完整列表。 通常，您会希望了解用户所属的区段，而不是用户被删除的区段。 另请参阅<a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples">出站数据文件名：语法和示例</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 示例：基本文件格式

正确格式化的数据文件可能类似于以下示例。 此文件条目表示用户符合区段24、26和27的条件。 根据需要，使用空格分隔`UUID`和区段ID。 另一个空格用于分隔区段ID集。 在此示例中，用户属于区段24、26和27。 它们已从区段25和28中删除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
