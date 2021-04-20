---
description: 数据文件包含印象、点击或转换数据。 格式正确后，您可以将此数据导入Audience Manager，并在Audience Optimization报告和可操作日志文件中使用。 根据本节中的规范设置数据文件的格式。
seo-description: 数据文件包含印象、点击或转换数据。 格式正确后，您可以将此数据导入Audience Manager，并在Audience Optimization报告和可操作日志文件中使用。 根据本节中的规范设置数据文件的格式。
seo-title: Audience Optimization 报表的数据文件以及可操作的日志文件
solution: Audience Manager
title: Audience Optimization 报表的数据文件以及可操作的日志文件
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 5%

---

# Audience Optimization 报表的数据文件以及可操作的日志文件 {#data-files-for-audience-optimization-reports}

数据文件包含印象、点击或转换数据。 格式正确后，您可以将此数据导入Audience Manager，以在[Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)中视图它，并通过[可操作日志文件](/help/using/integration/media-data-integration/actionable-log-files.md)使用数据创建特征。 根据本节中的这些规范设置数据文件的格式。

## 概述 {#overview}

通过正确命名且格式正确的Audience Optimization文件，可以将印象、单击或转换数据导入[报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 当与未与[!DNL Audience Manager]集成的合作伙伴合作，并且您希望使用该报表包中的数据时，此功能非常有用。 此过程需要单独的文件来显示、单击和转换数据。 请勿将这些事件混合到单个文件中。

数据文件必须附带元数据文件。 元数据文件内容将数据文件信息与报表菜单中的相关、可读标签相匹配。 有关详细信息，请参阅[元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

## 数据文件{#naming-conventions}的命名约定

以下语法定义格式良好的数据文件名的结构。 请注意，*斜体*&#x200B;表示一个变量占位符，该占位符会根据文件内容而发生变化。

**语法：** <pre><i>事件类型</i>_<i>yyyymmdd</i></code></pre>

在文件名中：

* 事件类型指示文件包含展示次数、点击次数或转换次数。 为每个事件类型创建一个单独的文件。
* 下划线将事件类型和年月日期时间戳分隔开。
* 在上传之前，请使用gzip压缩文件，并使用`.gz`文件扩展名保存它们。

根据这些要求，根据数据文件的内容命名它们，如下所示：

* 印象数据： <pre>印象_<i>yyyymmdd</i>gz</code></pre>
* 单击数据： <pre>clicks_<i>yyyymmdd</i>.gz</code></pre>
* 转换数据： <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## 数据文件{#content-format}的内容格式

以下语法定义格式良好的数据文件中的内容结构。 请注意，*斜体*&#x200B;表示变量占位符，并替换为实际数据文件中的标签。

**语法：** <pre><i>标题标签1</i> |标 <i>题标签2</i> ...标 <i>题标签n</i> | <i>版本</i></code></pre>

在文件内容中：

* 标题标签必须按下表中所示的顺序显示。 展示次数和点击次数使用相同的标签。 转换文件包含额外的标题。
* 如果您没有特定列的数据，请用`-1`填充该字段。

* 文件&#x200B;*必须*&#x200B;以版本号结尾。 当前版本为1.1。
* 用非打印的ASCII 001字符分隔文件头和内容。 如果不能使用ASCII 001，则使用制表符分隔符分隔标题和数据。 由于这些字符是非打印字符，上面的语法示例仅显示用于显示目的的管道`"|"`。

**字段标签**

下表列表了您的数据文件的列标题。 标题区分大小写，且必须按表中的顺序显示。 除非另有指明，否则所有数据类型都是整数(INT)。

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
   <td colname="col2"> <p>UTC的印象、单击或转换事件的日期和时间。 使用<code> yyyy-MM-dd HH:mm:ss</code>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户ID </p> </td> 
   <td colname="col2"> <p>站点访客的ID，也称为<span class="term">数据提供程序唯一用户ID</span>或DPUUID。 </p> </td> 
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
   <td colname="col1"> <p>活动-ID </p> </td> 
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
   <td colname="col1"> <p>位置ID </p> </td> 
   <td colname="col2"> <p> 广告服务器中的数字位置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入 — 顺序 — ID </p> </td> 
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
   <td colname="col2"> <p> 转换事件中销售的项目数。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>购买或其他转换金额。 数据类型：浮动。 </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他数据 </p> </td> 
   <td colname="col2"> <p>转换登陆页的URL。 数据类型：字符串. </p> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件类型 </p> </td> 
   <td colname="col2"> <p>转换类型。 指示是否匹配转换。 选项包括： </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 展示次数 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 单击 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:未归属或未知 </li> 
    </ul> <p> <i>仅用于转换数据文件。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在印象、单击或转换数据文件中每行末尾显示的所需版本号。 当前版本为1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 投放文件{#delivery-methods}的方法

将您的印象、单击或转换数据文件到[!DNL Audience Manager]帐户的Amazon S3目录。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。

>[!IMPORTANT]
>
> 请与Audience Manager顾问或客户关怀部门联系，开始为您的数据文件设置[!DNL Amazon S3]目录。

**投放路径语法和示例**

数据存储在[!DNL Amazon S3]目录中每个客户的单独命名空间中。 文件路径遵循下面显示的语法。 注意，*斜体*&#x200B;表示变量占位符。 其他元素是常量或键，不会更改。

**语法：** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>文件类型</i>_<i>yyymmdd</i></code></pre>

下表定义了文件投放路径中的每个元素。

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
   <td colname="col2"> <p>此键值对包含您的<span class="keyword">Audience Manager</span>客户ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此键值对包含在事件调用中传入的数据源ID。 它识别数据所来自的机构，并将该数据绑定到支持的元数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 数据文件的更高级别目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一种文件类型名称，指示它包含的数据类型和投放时间戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上载路径和文件名示例**

上载文件时，路径将类似于：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**文件处理时间和更新**

每天处理四次数据文件，每隔一定时间。

要更新数据，请发送包含特定日期的所有展示次数、点击次数或转换次数的文件。 在这种情况下，一天是从午夜到下一个午夜的24小时。 作为最佳实践，您可能希望使用UTC时间定义天间隔。

## 后续步骤 {#next-steps}

查看命名和创建元数据文件的要求。 要开始，请参阅[元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。
