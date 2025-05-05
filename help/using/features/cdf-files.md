---
description: 有关客户数据信息源(CDF)文件的基本信息以及如何入门的说明。 如果您对接收CDF文件感兴趣，或者只是想了解更多信息，请从此处开始。
keywords: 第二方数据；第二方；第二方数据；第二方
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: 客户数据信息源
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有关[!UICONTROL Customer Data Feed] ([!UICONTROL CDF])文件的基本信息以及如何开始的说明。 如果您对接收[!UICONTROL CDF]文件感兴趣，或者只是想了解更多信息，请从此处开始。

## 文件内容和用途 {#file-contents-purpose}

[!UICONTROL CDF]文件包含的数据与[!DNL Audience Manager]事件调用(`/event`)发送到我们服务器的数据相同。 这包括用户ID、[!UICONTROL trait IDs]、[!UICONTROL segment IDs]等数据以及事件调用捕获的所有其他参数。 内部[!DNL Audience Manager]系统将事件数据处理到[!UICONTROL CDF]文件中，其内容按设置的顺序组织到各个字段中。 [!DNL Audience Manager]尝试每小时生成[!UICONTROL CDF]个文件，并将其存储在[!DNL Amazon S3]服务器上的安全、特定于客户的存储段中。 我们提供这些文件，以便您可以不受用户界面限制地使用[!DNL Audience Manager]数据。

>[!IMPORTANT]
>
>使用CDF文件时请注意以下限制：
>
>* 在设置CDF文件投放之前，请确保您从第三方数据提供商那里获得了导出第三方特征的适当权限。 Audience Manager当前不支持在用户界面中向第三方数据提供商请求CDF文件投放导出权限的功能，因此请单独联系他们。
>* 您不应使用[!UICONTROL CDF]文件作为代理来监视页面流量、协调报表差异或记帐等。

## 入门指南 {#getting-started}

没有自助服务进程可启动[!UICONTROL CDF]文件投放。 请联系您的[!DNL Audience Manager]顾问或客户关怀团队以开始使用这些报表。 在实施过程中，您的[!DNL Audience Manager]代表将：

* 设置您的[!DNL Amazon S3]存储段。
* 向文件存储段提供只读[!DNL S3]身份验证凭据。 您将无法查看或访问属于其他客户的目录和文件。

文件通知和[!UICONTROL CDF]文件在可供下载时将显示在您的[!DNL S3]存储段中。 您负责监视和下载分配[!DNL S3]目录中的文件。 请参阅[客户数据信息源文件处理通知](#cdf-file-processing-notifications)。

## 后续步骤 {#next-steps}

以下部分和[客户数据馈送常见问题解答](../faq/faq-cdf.md)可以帮助您更熟悉此服务。

## 已定义[!UICONTROL Customer Data Feed]内容 {#cdf-defined}

按外观顺序列出并定义[!UICONTROL CDF]文件中的数据元素和数组。 定义包括数据类型，但此信息不是[!UICONTROL CDF]文件的一部分。

>[!IMPORTANT]
>
>默认情况下，CDF配置中排除事件像素。 如果您希望在CDF文件中包含事件像素，请确保在发送给客户关怀团队的请求中指定。 每个事件像素都将作为CDF文件中的唯一行填充。

## 定义 {#definitions}

[!UICONTROL CDF]文件包含下面定义的部分或全部字段。 有关内部文件组织的信息，请参阅[客户数据信息源文件结构](#cdf-file-structure)。

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 数据类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>时间戳 </p> </td> 
   <td colname="col3"> <p><span class="wintitle">数据收集服务器</span> (DCS)处理CDF文件的时间。 时间戳使用<i>yyyy-mm-dd hh:mm:ss</i>格式，并以UTC时区设置。 </p> <p> <p>注意：事件时间<i>不是</i>： <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或事件本身调用的时间，但它可能接近这些时间。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名中的DCS小时数相关。 另请参阅<a href="#different-processing-times">客户数据馈送文件名时间和文件内容时间……</a>。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>这是<span class="wintitle">独特用户ID</span> (UUID)，它是网站访客的38位设备ID。 另请参阅Audience Manager</a>中的<a href="../reference/ids-in-aam.md"> ID索引。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>数值 </p> </td> 
   <td colname="col3"> <p>触发ID同步的容器的ID。 只有在网站实施的<i>d_nsid</i>字段中设置了容器ID时，才会填充此字段。 否则，缺省值0将不会包含在CDF文件中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>一个特征ID数组，其中包含访客在事件调用中实现（符合条件）的所有特征。 </p> <p>请注意，数组可以包含访客之前已获得资格的特征，并通过此事件调用重新获得资格的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>区段ID的数组，其中包含访客在事件调用中实现（符合）的所有区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>捕获所有参数（变量、ID、键值对、设备广告ID等）的字符串 已在事件调用中传入。 </p> <p>简短示例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>引用页面的未编码URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>在事件调用中捕获的访客的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>分配给网站访客的<span class="keyword">Experience Cloud</span> ID (MID)。 另请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans" format="https" scope="external"> Cookie和AdobeExperience Platform标识服务</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>一个区段ID数组，其中包含访客符合条件的以前实现的区段和新区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特征ID数组，其中包含访客自上次生成数据馈送以来符合条件的先前实现的特征和新特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]文件结构 {#cdf-file-structure}

列出并定义[!UICONTROL CDF]文件的数据结构。 这包括数据序列、字段分隔符和分隔符、数据文件映射和示例文件。

## 数据字段标识符和序列 {#identifiers-and-sequence}

[!UICONTROL CDF]文件不包含标记的列或字段标题。 相反，[!UICONTROL CDF]文件定义具有非打印[!DNL ASCII]字符的字段和数组。 另外，[!UICONTROL CDF]文件以特定顺序列出了每个字段和数组。 了解字段标识符和顺序将帮助您正确解析文件。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF文件元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>字段分隔符和分隔符 </p> </td> 
   <td colname="col2"> <p>这些非打印字符定义CDF文件的元素和结构： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a （ASCII <code> 001</code>或<code> ^A</code>）使用非打印空格指示符分隔各个字段中的数据。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b （ASCII <code> 002</code>或<code> ^B</code>）将数据与数组和请求参数分开。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c （ASCII <code> 003</code>或<code> ^C</code>）定义键值对。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段序列 </p> </td> 
   <td colname="col2"> <p> <p>重要提示： <span class="keyword">Audience Manager</span>保留在未来版本中向CDF文件末尾添加新字段的权利。 这意味着文件解析系统的技术设计不应假定列数是固定的（尽管它可能假定现有列顺序是固定的）。</p> </p> <p>CDF文件中的数据按以下顺序显示。/N可以代替这些字段中的任何一个，指示空值。</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件时间 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已实现的特征 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已实现区段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud的设备ID（或MID）。 另请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans" format="https" scope="external"> Cookie和Adobe Experience Platform Identity服务</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有区段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特征 </li> 
     </ol> </p> <p>有关字段说明，请参阅<a href="#cdf-defined">定义的客户数据馈送内容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF]文件映射 {#cdf-file-map}

[!UICONTROL CDF]文件数据的显示顺序如下所示。

![](assets/sequence-map.png)

## 标识数组

[!UICONTROL CDF]文件中的数组以`Ctrl + a`字段分隔符开始和结束。 这会使数组中的第一个元素看起来像是一个独立的数据字段。 例如，已实现的[!UICONTROL traits]数组以`^A1234`开头。 数组分隔符和ID `^B5678`遵循此条目。 因此，您可能认为已实现的[!UICONTROL traits]数组中的第一个元素是ID 5678（因为它以`^B`开头）。 但实际情况并非如此，因此您需要熟悉数据文件的顺序和结构。 即使已实现的[!UICONTROL trait]数组中的第一个元素（或[!UICONTROL CDF]文件中的任何其他数组）以`^A`开头，文件中的外观顺序或位置定义数组的开头。 而且，数组中的第一个元素始终以`^A`与前一个条目分开。

## [!UICONTROL CDF]文件示例 {#sample-file}

示例[!UICONTROL CDF]文件可能类似于以下内容。 我们在此示例中插入了换行符，以帮助它适应页面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed]文件命名约定 {#cdf-naming-conventions}

以下部分列出并定义了[!UICONTROL CDF]文件名中的元素。

## [!UICONTROL CDF]文件名：语法和示例 {#cdf-file-name}

典型的[!UICONTROL CDF]文件名包含下列元素。 注意，*斜体*&#x200B;表示变量占位符：

### 语法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### 示例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

在您的[!DNL S3]存储段中，文件按合作伙伴ID ([!UICONTROL PID])、日期和小时以升序排序。

## 已定义[!UICONTROL CDF]文件名元素 {#cdf-file-name-elements}

下表列出并定义了[!UICONTROL CDF]文件名中的元素。

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>这是Amazon S3服务器上CDF文件的默认根存储段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>包含CDF文件的只读S3存储段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>处理文件的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小时表示法表示并以UTC时区设置的时间值。 另请参阅<a href="#different-processing-times">客户数据馈送文件名时间和文件内容时间……</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>标识文件序列的值。 序列按如下方式递增：0_0_0 、 0_1_0 、 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip文件扩展名。 CDF文件经过gzip压缩。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]文件处理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager]将`.info`文件写入您的[!DNL S3]目录，以告知您的[!UICONTROL Customer Data File] ([!UICONTROL CDF])何时可以下载。 `.info`文件还包含有关[!UICONTROL CDF]文件内容的[!DNL JSON]格式化的元数据。 查看此部分以了解有关此通知文件使用的语法和字段的信息。

## 示例信息文件 {#sample-info-file}

每个`.info`文件都包含一个`Files`和`Totals`节。 `Files`部分包含一个数组，其中包含每个小时文件的特定量度。 `Totals`部分包含针对某天的所有[!UICONTROL CDF]文件聚合的量度。 `.info`文件的内容可能类似于以下示例。

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## 定义的信息文件字段 {#info-file-fields-defined}

下表列出并定义[!UICONTROL CDF] `.info`文件中的元素。

### Files对象

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>启动包含有关CDF文件元数据的数组。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小（字节）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 连字符后面的数字显示了在多部分上传期间用于构建文件的部分数。 <code> ETag</code>与文件的MD5校验和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>文件名。 请参阅<a href="#cdf-naming-conventions">客户数据信息源文件命名约定</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每个文件的索引号。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 总计对象

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>启动包含有关所有CDF文件的聚合数据的对象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>数据可用的日期。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>数据可用的小时。 使用UTC时区设置的24小时格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>该日期的所有CDF文件的总大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上载到S3目录的文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]文件名时间和文件内容时间不同 {#different-processing-times}

您的[!UICONTROL CDF]文件在文件名和文件内容中包含时间戳。 这些时间戳为同一[!UICONTROL CDF]文件记录不同的事件进程。 在同一文件的名称和内容中看到不同的时间戳并不少见。 了解每个时间戳可以帮助您避免在处理此数据或尝试按时间对数据进行排序时经常会犯的错误。

## 查找[!UICONTROL CDF]文件时间戳 {#locating-timestamps}

[!UICONTROL CDF]个文件在2个不同位置记录的时间不同。

![](assets/cdf-timestamp.png)

## 了解时间戳之间的差异 {#understanding-timestamps}

下表提供了有关[!UICONTROL CDF]文件时间戳的更多详细信息以及如何正确使用它们。

| 时间戳位置 | 描述 |
|--- |--- |
| 文件名 | [!DNL CDF]文件名中的时间戳标记[!DNL Audience Manager]开始准备文件以进行交付的时间。 此时间戳设置为[!DNL UTC]时区。 它使用`hour=`参数，时间格式为24小时表示法中的2位数小时。 此时间可能与文件内容中记录的事件时间不同。 在使用[!DNL CDF]文件时，有时您会注意到您的[!DNL S3]存储段在某一特定小时内是空的。 空存储桶表示可能具有以下任一值：<ul><li>没有该特定小时的数据。 </li><li> 我们的服务器负载过重，无法在特定的一小时内处理文件。 当服务器恢复时，它将本应存储在较早时段文件中的文件放入具有较晚时间值的存储段中。 例如，当应在17小时时段中的文件出现在18小时时段中（文件名中为`hour=18`）时，您将看到此消息。 在这种情况下，服务器可能在17小时内开始处理您的文件，但无法在该时间间隔内完成它。 相反，文件会推送至下一个每小时存储段。</li></ul><br>**重要信息**：不要使用文件名时间戳按时间对事件进行分组。 如果需要按时间分组，请在文件内容中使用`EventTime`时间戳。 |
| 文件内容 | [!DNL CDF]文件内容中的时间戳标记[!DNL Data Collection Servers]开始处理文件的时间。 此时间戳设置为[!DNL UTC]时区。 它使用`EventTime`字段，时间格式为&#x200B;*`yyyy-mm-dd hh:mm:ss`*。 该时间接近页面上事件的实际时间，但可能与文件名中的小时指示器不同。<br> **提示**：与文件名中的`hour=`时间戳不同，您可以使用`EventTime`按时间分组数据。 |

>[!MORELIKETHIS]
>
>* [客户数据信息源常见问题解答](../faq/faq-cdf.md)
