---
description: 通过将元数据文件发送到Audience Manager帐户的特殊Amazon S3目录，发送或更新元数据文件。 有关交付／目录路径、文件处理时间和更新的信息，请参阅本节。
seo-description: 通过将元数据文件发送到Audience Manager帐户的特殊Amazon S3目录，发送或更新元数据文件。 有关交付／目录路径、文件处理时间和更新的信息，请参阅本节。
seo-title: 元数据文件的交付方法
solution: Audience Manager
title: 元数据文件的交付方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# 元数据文件的交付方法{#delivery-methods-for-metadata-files}

通过将元数据文件发送到Audience Manager帐户的特殊Amazon S3目录，发送或更新元数据文件。 有关交付／目录路径、文件处理时间和更新的信息，请参阅本节。

## 交付路径语法和示例 {#syntax}

数据存储在Amazon S3目录中每个客户的单独命名空间中。 文件路径遵循下面显示的语法。 Note, *italics* indicates a variable placeholder. 括号 `[ ]` 表示可选参数。 其他元素是常量，不会更改。

**语法：**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col2"> <p>此键值对包含在事件调用中传入的数据源ID。 数据源ID是将文件中的所有内容与其所属的实际数据关联起来的值。 </p> <p>例如，假设您有一个ID为123的创意，并且名称为“Advertiser Creative A”。 当活动调用仅传递到ID时，您需要在元数据文件中包含“广告商创意A”。 营销活动和创意属于数据源。 数据源ID是将这些内容关联在一起的，它使我们能够准确地将文件内容与在事件调用中发送的ID关联起来。 请参 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> 阅活动调用ID如何确定文件名、内容和交付路径</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是文件名。 请参 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 阅元数据文件的命名约定</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件处理时间和更新 {#processing-times}

每天处理四次元数据文件，间隔为定期。

要更新元数据记录，只需发送包含新信息的文件。 您无需每次发送完整更新。
