---
description: 数据文件包含印象、单击或转换数据。 格式正确后，您可以将此数据导入Audience Manager并在“受众优化”报告中查看。 根据本节中的这些规范设置数据文件的格式。
seo-description: 数据文件包含印象、单击或转换数据。 格式正确后，您可以将此数据导入Audience Manager并在“受众优化”报告中查看。 根据本节中的这些规范设置数据文件的格式。
seo-title: 用于受众优化报告的数据文件
solution: Audience Manager
title: 用于受众优化报告的数据文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
translation-type: tm+mt
source-git-commit: 6e504dabacff9be40633d6c91856b57c6e653f71

---


# 用于受众优化报告的数据文件{#data-files-for-audience-optimization-reports}

数据文件包含印象、单击或转换数据。 格式正确后，您可以将此数据导入Audience Manager并在“受众优化”报告中查看。 根据本节中的这些规范设置数据文件的格式。

## 概述 {#overview}

通过正确命名和格式化的数据文件，可将印象、单击或转换数据导入受众优 [化报告中](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 这在与未集成的合作伙伴合作并且您希望使用该 [!DNL Audience Manager] 报表包中的数据时很有用。 此过程需要单独的文件来获取印象、单击和转换数据。 请勿将这些事件混合到单个文件中。

数据文件必须与元数据文件相附。 元数据文件内容将数据文件信息与报告菜单中相关的、可读标签相匹配。 有关详细信息，请参 [阅元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

## 数据文件的命名约定 {#naming-conventions}

以下语法定义格式良好的数据文件名的结构。 注意，斜 *体表示* ，变量占位符会根据文件内容而改变。

**语法：** <pre><code><i>event type</i>_<i>yyyymmdd</i></code></pre>

在文件名中：

* 事件类型指示文件包含展示次数、点击次数或转换次数。 为每个事件类型创建单独的文件。
* 下划线将事件类型和年月日期时间戳分隔开来。
* 在上传之前，请使用gzip压缩文件，然后使用文件扩展名 `.gz` 保存它们。

根据这些要求，根据数据文件的内容命名它们，如下所示：

* 印象数据： <pre><code>impressions_<i>yyyymmdd<i>.gz</code></pre>
* 单击数据： <pre><code>clicks_<i>yyymmdd</i>.gz</code></pre>
* 转换数据： <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## 数据文件的内容格式 {#content-format}

以下语法定义格式良好的数据文件中的内容结构。 注意， *斜体表示* 变量占位符，并替换为实际数据文件中的标签。

**语法：** <pre><code><i>标题标签1</i> |标 <i>题标签2</i> ...标 <i>题标签n</i> |版 <i>本</i></code></pre>

在文件内容中：

* 标题标签必须按下表所示的顺序显示。 印象和点击使用相同的标签。 转换文件包含额外的标题。
* 如果您没有特定列的数据，请用一个 `-1`

* 文 *件必须以* 版本号结尾。 当前版本为1.1。
* 用非打印ASCII 001字符分隔文件标题和内容。 如果不能使用ASCII 001，则用制表符分隔标题和数据。 由于这些字符是非打印字符，因此上面的语法示例仅显示 `"|"` 用于显示目的的管道。

**字段标签**

下表列出并描述了数据文件的列标题。 标题区分大小写，并且必须按表中的顺序显示。 除非另有指明，否则所有数据类型都是整数(INT)。

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
   <td colname="col2"> <p>UTC印象、单击或转化事件的日期和时间。 使用 <code> yyyy-dd-mm hh:mm:ss</code> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户ID </p> </td> 
   <td colname="col2"> <p>站点访客的ID，也称为数据提供者唯 <span class="term"> 一用户ID</span> 或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>广告商ID </p> </td> 
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>业务单位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>系列活动ID </p> </td> 
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
   <td colname="col1"> <p>放置ID </p> </td> 
   <td colname="col2"> <p> 广告服务器中的数字放置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入顺序ID </p> </td> 
   <td colname="col2"> <p>插入顺序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>策略ID </p> </td> 
   <td colname="col2"> <p>策略ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>行业垂直或类别的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数量 </p> </td> 
   <td colname="col2"> <p> 转化事件中售出的项目数。 </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>购买或其他转化金额。 数据类型：浮动。 </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他数据 </p> </td> 
   <td colname="col2"> <p>转换登陆页面的URL。 数据类型：字符串. </p> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件类型 </p> </td> 
   <td colname="col2"> <p>转换类型。 指示转换是否匹配。 选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>:印象 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>:单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:未归属或未知 </li> 
    </ul> <p> <i>仅适用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在印象、单击或转换数据文件中每行末尾显示的所需版本号。 当前版本为1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据文件的交付方法 {#delivery-methods}

将您的印象、单击或转换数据文件上传到您帐户的Amazon S3目 [!DNL Audience Manager] 录。 有关交付／目录路径、文件处理时间和更新的信息，请参阅本节。

**交付路径语法和示例**

数据存储在Amazon S3目录中每个客户的单独命名空间中。 文件路径遵循下面显示的语法。 Note, *italics* indicates a variable placeholder. 其他元素是常量或键，不会更改。

**语法：** <pre><code>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>file type</i>_<i>yyymmdd</i></code></pre>

下表定义了文件传送路径中的每个元素。

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>这是目录存储路径的开始。 设置完毕后，您将获得完整路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含您的 <span class="keyword"> Audience Manager客户ID</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含在事件调用中传入的数据源ID。 它标识数据来自的机构，并将该数据绑定到支持元数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 日志</code> </p> </td> 
   <td colname="col2"> <p> 数据文件的更高级别目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 文 <i>件类型</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一种文件类型名称，用于指示它包含的数据类型和传送时间戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上传路径和文件名示例**

上传文件时，路径的外观将类似于：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**文件处理时间和更新**

数据文件每天处理四次，间隔为定期。

要更新数据，请发送一个文件，其中包含特定日期的所有印象、点击或转换。 在这种情况下，一天是从午夜12点到下一天的24小时。 作为最佳实践，您可能希望使用UTC时间定义日间隔。

## 后续步骤 {#next-steps}

查看命名和创建元数据文件的要求。 要开始，请参阅元 [数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。
