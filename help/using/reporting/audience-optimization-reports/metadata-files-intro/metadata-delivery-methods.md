---
description: 发送或更新元数据文件，方法是将其发送到Audience Manager帐户的特殊Amazon S目录。有关交付/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-description: 发送或更新元数据文件，方法是将其发送到Audience Manager帐户的特殊Amazon S目录。有关交付/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-title: 元数据文件的交付方法
solution: Audience Manager
title: 元数据文件的交付方法
uuid: 5199ee9b-920d-423d-8070-05a017et562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

发送或更新元数据文件，方法是将其发送到Audience Manager帐户的特殊Amazon S目录。有关交付/目录路径、文件处理时间和更新的信息，请参阅本节。

## Delivery Path Syntax and Examples {#syntax}

数据在Amazon S目录中为每个客户存储在单独的命名空间中。文件路径遵循下面显示的语法。Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. 其他元素是常量，不会更改。

**语法：**
<pre><code>…/log_ ingfease/pid=<i>AAM ID</i>/dpid= <i>d_ src</i>/[meta| status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col2"> <p>此键值对包含在事件调用上传入的数据源ID。数据源ID是将文件中所有内容与其所属的实际数据相关联的值。 </p> <p>例如，假设您有一个ID123和名称“Advertiser Creative A”的创意。作为一个活动调用，只需要在元数据文件中加入“advertiser Creative A”所需的ID。营销活动和创意属于数据源。数据源ID是将这些数据绑定到一起，并允许我们准确地将文件内容关联到事件调用中发送的ID。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> 是文件上传/存储目录。 </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> 状态</code> 是指向已处理文件的成功或失败信息的目录的路径。After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. 状态文件包含JSON对象中的数据。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>这是文件名。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例上传和状态路径**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

元数据文件每天处理四次，定期处理四次。

要更新元数据记录，只需发送包含新信息的文件。每次都不需要发送完全更新。
