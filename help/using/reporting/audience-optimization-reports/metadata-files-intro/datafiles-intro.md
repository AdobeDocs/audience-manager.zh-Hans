---
description: 数据文件包含展示、点击或转化数据。 格式正确后，您可以将此数据导入Audience Manager，并在Audience Optimization报表和可操作的日志文件中使用。 根据此部分中的规范设置数据文件的格式。
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Audience Optimization 报表的数据文件以及可操作的日志文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Audience Optimization 报表的数据文件以及可操作的日志文件 {#data-files-for-audience-optimization-reports}

数据文件包含展示、点击或转化数据。 格式正确后，您可以将此数据导入Audience Manager，以便在 [Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 和通过 [可操作的日志文件](/help/using/integration/media-data-integration/actionable-log-files.md). 根据本节中的这些规范设置数据文件格式。

## 概述 {#overview}

一个名称正确且格式正确的数据文件，允许您将展示、点击或转换数据导入 [Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). 在与未与集成的合作伙伴合作时，此功能非常有用 [!DNL Audience Manager] 并且您想要在该报表包中处理其数据。 此过程需要单独的文件来获取展示、点击和转化数据。 请勿将这些事件混合到单个文件中。

数据文件必须附有元数据文件。 元数据文件内容将数据文件信息与报表菜单中相关的人类可读标签相匹配。 有关更多信息，请参阅 [元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## 数据文件的命名约定 {#naming-conventions}

以下语法定义格式正确的数据文件名的结构。 注意， *斜体* 指示根据文件内容发生更改的变量占位符。

**语法：** <pre><i>事件类型</i>_<i>yyyymmdd</i></code></pre>

在文件名中：

* 事件类型表示文件包含展示次数、点击次数或转化次数。 为每个事件类型创建单独的文件。
* 下划线用于分隔事件类型和年份 — 月份日期时间戳。
* 在上传之前，请使用gzip压缩文件，然后使用 `.gz` 文件扩展名。

根据这些要求，请根据数据文件的内容命名数据文件，如下所示：

* 展示数据： <pre>展示次数_<i>yyyymmdd</i>.gz</code></pre>
* 单击数据： <pre>点击量_<i>yyyymmdd</i>.gz</code></pre>
* 转化数据： <pre>转化_<i>yyyymmdd</i>.gz</code></pre>

## 数据文件的内容格式 {#content-format}

以下语法定义格式正确的数据文件中的内容结构。 注意， *斜体* 指示变量占位符，并在实际数据文件中替换为标签。

**语法：** <pre><i>标题标签1</i> | <i>标题标签2</i> ... <i>标题n</i> | <i>版本</i></code></pre>

在文件内容中：

* 标题标签必须按如下表所示的顺序显示。 展示次数和点击次数使用相同的标签。 转换文件包含额外的标题。
* 如果没有特定列的数据，请使用 `-1`.

* 文件 *必须* 以版本号结束。 当前版本为1.1。
* 使用非打印ASCII 001字符来分隔文件头和内容。 如果不能使用ASCII 001，则使用制表符分隔标题和数据。 由于这些字符是非打印字符，因此上面的语法示例显示管道字符 `"|"` 仅供显示。

**字段标签**

下表列出并描述了数据文件的列标题。 标题区分大小写，且必须在表中按顺序显示。 除非另有指示，否则所有数据类型均为整数(INT)。

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
   <td colname="col2"> <p>展示、点击或转化事件的UTC日期和时间。 使用 <code> yyyy-MM-dd HH:mm:ss</code> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户ID </p> </td> 
   <td colname="col2"> <p>网站访客的ID，也称为 <span class="term"> 数据提供程序独特用户ID</span> 或DPUUID。 </p> </td> 
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
   <td colname="col1"> <p>促销活动ID </p> </td> 
   <td colname="col2"> <p>促销活动 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>创作ID </p> </td> 
   <td colname="col2"> <p>创作 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>网站 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版面ID </p> </td> 
   <td colname="col2"> <p> 广告服务器中的数字版面ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>插入订单ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>策略ID </p> </td> 
   <td colname="col2"> <p>战术ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>垂直行业或类别的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数量 </p> </td> 
   <td colname="col2"> <p> 转化事件中售出的项目数。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>购买或其他转化金额。 数据类型：浮动。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他数据 </p> </td> 
   <td colname="col2"> <p>转化登陆页面的URL。 数据类型：字符串. </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件类型 </p> </td> 
   <td colname="col2"> <p>转化类型。 指示转化是否匹配。 选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 展示次数 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:未归因或未知 </li> 
    </ul> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在展示、点击或转化数据文件中每行末尾显示所需的版本号。 当前版本为1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据文件的提交方法 {#delivery-methods}

将您的展示、点击或转化数据文件上传到Amazon S3目录，以便 [!DNL Audience Manager] 帐户。 有关投放/目录路径、文件处理时间和更新的信息，请参阅此部分。

>[!IMPORTANT]
>
> 请联系您的Audience Manager顾问或客户关怀团队，以开始设置 [!DNL Amazon S3] 的目录。

**传递路径语法和示例**

数据存储在 [!DNL Amazon S3] 目录访问Advertising Cloud的帮助。 文件路径遵循下面显示的语法。 注意， *斜体* 指示变量占位符。 其他元素是常量或键，不会发生更改。

**语法：** <pre>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>文件类型</i>_<i>yyyymmdd</i></code></pre>

下表定义了文件提交路径中的每个元素。

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
   <td colname="col2"> <p>这是目录存储路径的开始。 设置完所有内容后，您将收到完整路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含 <span class="keyword"> Audience Manager</span> 客户ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含在事件调用中传入的数据源ID。 它可标识数据来自的代理，并将该数据绑定到支持的元数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 数据文件的更高级别目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>文件类型名称，用于指示其包含的数据类型和提交时间戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上载路径和文件名示例**

上传文件时，路径将类似于以下内容：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**文件处理时间和更新**

数据文件每天处理四次，间隔为定期。

要更新数据，请发送包含特定日期的所有展示次数、点击次数或转化次数的文件。 在这种情况下，一天是从午夜1点到下一点的24小时时间段。 作为最佳实践，您可能希望使用UTC时间来定义天间隔。

## 后续步骤 {#next-steps}

查看命名和创建元数据文件的要求。 要开始配置，请参阅 [元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
