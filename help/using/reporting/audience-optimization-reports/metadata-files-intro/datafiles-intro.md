---
description: 数据文件包含展示、点击或转化数据。 如果格式正确，您可以将此数据导入Audience Manager，并将其用于Audience Optimization报表和可操作的日志文件。 根据本节中的规范格式化数据文件。
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Audience Optimization报表的数据文件以及可操作的日志文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Audience Optimization报表的数据文件以及可操作的日志文件 {#data-files-for-audience-optimization-reports}

数据文件包含展示、点击或转化数据。 如果格式正确，您可以将此数据导入Audience Manager，以便在[Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)中查看它，并通过[可操作的日志文件](/help/using/integration/media-data-integration/actionable-log-files.md)使用这些数据创建特征。 根据本节中的这些规范格式化数据文件。

## 概述 {#overview}

一个正确命名且格式化的数据文件可让您将展示次数、点击次数或转化数据导入[Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 当与未与[!DNL Audience Manager]集成的合作伙伴合作，而您希望在该报表包中处理其数据时，此功能非常有用。 此过程需要单独的展示、点击和转化数据文件。 请勿在一个文件中混合使用这些事件。

数据文件必须附有元数据文件。 元数据文件内容将数据文件信息与报表菜单中人工可读的相关标签相匹配。 有关详细信息，请参阅[元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

## 数据文件的命名约定 {#naming-conventions}

以下语法定义了格式正确的数据文件名的结构。 注意，*斜体*&#x200B;表示根据文件内容而更改的变量占位符。

**语法：** <pre><code><i>事件类型</i>_<i>yyyymmdd</i></code></pre>

在文件名中：

* 事件类型指示文件包含展示次数、点击次数或转化次数。 为每个事件类型创建单独的文件。
* 事件类型和年 — 月 — 日时间戳使用下划线分隔。
* 在上载之前，请使用gzip压缩文件并使用`.gz`文件扩展名保存它们。

根据这些要求，根据数据文件的内容命名数据文件，如下所示：

* 展示数据： <pre><code>展示次数_<i>yyyymmdd</i>.gz</code></pre>
* 单击数据： <pre><code>点击_<i>yyyymmdd</i>.gz</code></pre>
* 转化数据： <pre><code>转化_<i>yyyymmdd</i>.gz</code></pre>

## 数据文件的内容格式 {#content-format}

以下语法定义格式正确的数据文件中的内容结构。 请注意，*斜体*&#x200B;表示变量占位符，在实际数据文件中被替换为标签。

**语法：** <pre><code><i>标题标签1</i> | <i>标头标签2</i> ... <i>标头标签n</i> | <i>版本</i></code></pre>

在文件内容中：

* 标题标签必须按照下表所示的顺序显示。 展示和点击使用相同的标签。 转换文件包含额外的标头。
* 如果没有特定列的数据，请用`-1`填充该字段。

* 文件&#x200B;*必须*&#x200B;以版本号结尾。 当前版本为1.1。
* 使用非打印ASCII 001字符分隔文件标题和内容。 如果您无法使用ASCII 001，请使用制表符分隔符分隔标头和数据。 由于它们是非打印字符，因此上述语法示例显示仅用于显示的管道`"|"`。

**字段标签**

下表列出并描述了数据文件的列标题。 标头区分大小写，并且必须按表中的顺序显示。 除非另有说明，否则所有数据类型都是整数(INT)。

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
   <td colname="col2"> <p>展示、点击或转化事件的UTC日期和时间。 使用<code> yyyy-MM-dd HH:mm:ss</code>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户ID </p> </td> 
   <td colname="col2"> <p>您的网站访客ID，也称为<span class="term">数据提供程序唯一用户ID</span>或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>业务部门ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>营销活动ID </p> </td> 
   <td colname="col2"> <p>营销活动ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>创作ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>站点ID </p> </td> 
   <td colname="col2"> <p>站点ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> 广告服务器上的数字版面ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>插入订单ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>战术ID </p> </td> 
   <td colname="col2"> <p>策略ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>垂直行业或类别的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数量 </p> </td> 
   <td colname="col2"> <p> 转化事件中出售的物料数。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>购买或其他转化金额。 数据类型：浮点数。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他数据 </p> </td> 
   <td colname="col2"> <p>转化登陆页面的URL。 数据类型：字符串。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件类型 </p> </td> 
   <td colname="col2"> <p>转换类型。 指示转化是否匹配。 选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>：展示 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>：单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>：未归因或未知 </li> 
    </ul> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在展示、点击或转化数据文件中每行的末尾显示的必需版本号。 当前版本为1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据文件的提交方法 {#delivery-methods}

将您的展示、点击或转换数据文件上传到[!DNL Audience Manager]帐户的Amazon S3目录。 有关投放/目录路径、文件处理时间和更新的信息，请参阅此部分。

>[!IMPORTANT]
>
> 请联系您的Audience Manager顾问或客户关怀团队以开始使用并为数据文件设置[!DNL Amazon S3]目录。

**投放路径语法和示例**

在[!DNL Amazon S3]目录中为每个客户将数据存储在单独的命名空间中。 文件路径遵循如下所示的语法。 请注意，*斜体*&#x200B;表示变量占位符。 其他元素为常量或键，不会更改。

**语法：** <pre><code>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>文件类型</i>_<i>yyyymmdd</i></code></pre>

下表定义了文件投放路径中的这些元素。

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
   <td colname="col2"> <p>这是目录存储路径的开头。 一切设置完成后，您将收到完整路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含您的<span class="keyword">Audience Manager</span>客户ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含事件调用中传入的数据源ID。 它可以标识数据来自的代理，并将该数据绑定到支持的元数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 数据文件的更高级目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>指示其中包含的数据类型和投放时间戳的文件类型名称。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例上载路径和文件名**

上传文件时，路径将类似于以下内容：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**文件处理时间和更新**

数据文件每天处理四次，每次都定期进行。

要更新数据，请发送一个文件，其中包含特定日期的所有展示次数、点击次数或转化次数。 在这种情况下，一天是从一个午夜到下一个午夜的24小时时段。 作为最佳实践，您可能希望使用UTC时间来定义日期间隔。

## 后续步骤 {#next-steps}

查看命名和创建元数据文件的要求。 要开始操作，请参阅[元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。
