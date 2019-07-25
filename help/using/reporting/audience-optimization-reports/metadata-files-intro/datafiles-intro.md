---
description: 数据文件包含印象、单击或转换数据。格式化正确后，您可以将此数据导入Audience Manager并在受众优化报告中查看。根据这些规范，格式化您的数据文件。
seo-description: 数据文件包含印象、单击或转换数据。格式化正确后，您可以将此数据导入Audience Manager并在受众优化报告中查看。根据这些规范，格式化您的数据文件。
seo-title: 用于受众优化报告的数据文件
solution: Audience Manager
title: 用于受众优化报告的数据文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15 fe04 c379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

数据文件包含印象、单击或转换数据。格式化正确后，您可以将此数据导入Audience Manager并在受众优化报告中查看。根据这些规范，格式化您的数据文件。

## 概述 {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. 此过程需要单独的文件来显示、单击和转换数据。请勿将这些活动混合到单个文件中。

数据文件必须附带一个元数据文件。元数据文件内容将数据文件信息与报告菜单中相关、人工可读标签相匹配。For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

以下语法定义结构良好的数据文件名的结构。Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**语法：** <pre><code><i>event type</i>_<i>yyyymmdd</i></code></pre>

在文件名中：

* 事件类型表示文件包含印象、单击或转换。为每个活动类型创建单独的文件。
* 下划线将分隔活动类型和年日期时间戳。
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

根据这些要求，根据如下内容命名数据文件：

* 印象数据： <pre><code>impresses_<i>yyyymmdd<i>.gz</code></pre>
* 单击数据： <pre><code>clickclick_<i>yyyymmdd</i>.gz</code></pre>
* 转换数据： <pre><code>converts_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

以下语法定义结构良好的数据文件中的内容结构。Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**语法：** <pre><code><i>标题标签1</i> || <i>header label</i> … <i>header标签n</i> || <i>version</i></code></pre>

在文件内容中：

* 标题标签必须按顺序显示，如下表所示。展示和点击使用相同的标签。转换文件包含额外的标题。
* If you don't have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. 当前版本为1.1。
* 使用非打印ASCII001字符分离文件标题和内容。如果您无法使用ASCII001，则将标题和数据与制表符分隔符分开。As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**字段标签**

下表列出并描述了数据文件的列标题。标题区分大小写，并且必须按照表中的顺序显示。除非另有指明，否则所有数据类型都是整数(INT)。

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>时间戳 </p> </td> 
   <td colname="col2"> <p>印象、单击或转换事件的UTC日期和时间。Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>业务单位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>促销活动 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>创作 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>站点ID </p> </td> 
   <td colname="col2"> <p>网站 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placing-ID </p> </td> 
   <td colname="col2"> <p> 广告服务器中的数字放置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入顺序ID </p> </td> 
   <td colname="col2"> <p>插入订单ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>术语ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>行业垂直或类别的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数量 </p> </td> 
   <td colname="col2"> <p> 转换事件中售出的项目数。 </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>购买或其他转化金额。数据类型：浮动。 </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他数据 </p> </td> 
   <td colname="col2"> <p>转换登陆页面的URL。数据类型：字符串. </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件类型 </p> </td> 
   <td colname="col2"> <p>转换类型。指示是否匹配转换。选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code></code>0：印象 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code></code>1：单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>：未知或未知 </li> 
    </ul> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在印象、单击或转换数据文件中每行结尾处所需的版本号。当前版本为1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. 有关交付/目录路径、文件处理时间和更新的信息，请参阅本节。

**交付路径语法和示例**

数据在Amazon S目录中为每个客户存储在单独的命名空间中。文件路径遵循下面显示的语法。Note, *italics* indicates a variable placeholder. 其他元素是常量或密钥，不会更改。

**语法：** <pre><code>…/log_ ingfease/pid= <i>AAM ID<i>/dpid= <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

下表定义了文件交付路径中的每个元素。

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ ingdestion/</code> </p> </td> 
   <td colname="col2"> <p>这是目录存储路径的开始。设置一切时，您将获得完整的路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含在事件调用上传入的数据源ID。它确定了数据来自于何种机构，并将这些数据绑定到支持元数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 数据文件的更高级目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一个文件类型名称，它指示它包含的数据种类和交付时间戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例上传路径和文件名**

上传文件时，路径类似于以下内容：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**文件处理时间和更新**

数据文件每天处理四次，定期处理四次。

要更新数据，请在一个文件中发送，该文件包含特定日期的所有印象、点击或转换。在这种情况下，一天为24小时，从午夜到下一个午夜。作为最佳实践，您可能希望使用UTC时间定义一天间隔。

## 后续步骤 {#next-steps}

查看命名和创建元数据文件的要求。To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
