---
description: 有关客户数据信息源(CDF)文件的基本信息以及有关如何入门的说明。 如果您有兴趣接收CDF文件或只是想要了解更多信息，请从此处开始。
keywords: 第二方数据；第二方；第二方数据；第二方数据
seo-description: 有关客户数据信息源(CDF)文件的基本信息以及有关如何入门的说明。 如果您有兴趣接收CDF文件或只是想要了解更多信息，请从此处开始。
seo-title: 客户数据信息源
solution: Audience Manager
title: 客户数据信息源
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: 客户数据信息源
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有关[!UICONTROL Customer Data Feed]([!UICONTROL CDF])文件的基本信息以及如何开始的说明。 如果您希望接收[!UICONTROL CDF]文件或仅希望获得更多信息，请从此处开始。

## 文件内容和用途 {#file-contents-purpose}

[!UICONTROL CDF] 文件包含的数据与 [!DNL Audience Manager] 事件调用 (`/event`) 发送到我们服务器的数据相同。这包括用户ID、[!UICONTROL trait IDs]、[!UICONTROL segment IDs]以及事件调用捕获的所有其他参数等数据。 内部的[!DNL Audience Manager]系统将事件数据处理为一个[!UICONTROL CDF]文件，其中内容按设置顺序组织为各个字段。 [!DNL Audience Manager] 会尝试每小时生 [!UICONTROL CDF] 成一次文件，并将它们存储在服务器上特定于客户的安全存储段 [!DNL Amazon S3] 中。我们提供这些文件，以便您能够处理超出用户界面所规定限制的[!DNL Audience Manager]数据。

>[!IMPORTANT]
>
>使用CDF文件时请注意以下限制：
>
>* 在设置CDF文件交付之前，请确保您拥有第三方数据提供商的相应权限，以导出第三方特征。 Audience Manager当前不支持用户界面中向第三方数据提供商请求CDF文件交付导出权限的功能，因此请单独联系他们。
>* 您不应将[!UICONTROL CDF]文件用作监视页面流量、协调报表差异或计费等的代理。


## 入门指南 {#getting-started}

没有启动[!UICONTROL CDF]文件交付的自助流程。 请联系您的[!DNL Audience Manager]顾问或客户关怀团队以开始使用。 在实施过程中，您的[!DNL Audience Manager]代表将：

* 设置[!DNL Amazon S3]存储段。
* 为文件存储段提供只读[!DNL S3]身份验证凭据。 您将无法查看或访问属于其他客户的目录和文件。

文件通知和[!UICONTROL CDF]文件在准备下载时将显示在[!DNL S3]存储桶中。 您负责从分配的[!DNL S3]目录中监控和下载文件。 请参阅[客户数据信息源文件处理通知](#cdf-file-processing-notifications)。

## 后续步骤 {#next-steps}

以下部分和[客户数据信息源常见问题解答](../faq/faq-cdf.md)可以帮助您更熟悉此服务。

## [!UICONTROL Customer Data Feed] 定义的内容 {#cdf-defined}

按外观顺序列出并定义[!UICONTROL CDF]文件中的数据元素和数组。 定义包括数据类型，但此信息不属于[!UICONTROL CDF]文件的一部分。

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
   <td colname="col3"> <p><span class="wintitle">数据收集服务器</span>(DCS)处理CDF文件的时间。 时间戳使用<i>yyyy-mm-dd hh:mm:ss</i>格式，以UTC时区设置。 </p> <p> <p>注意：事件时间<i>不</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或事件本身的时间调用，尽管它可能与这些时间接近。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名中的DCS小时相关。 另请参阅<a href="#different-processing-times">客户数据信息源文件名时间和文件内容时间……</a>。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>这是<span class="wintitle">独特用户ID</span>(UUID)，即网站访客的38位设备ID。 另请参阅 <a href="../reference/ids-in-aam.md">Audience Manager 中的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>数值 </p> </td> 
   <td colname="col3"> <p>触发ID同步的容器的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>一个特征ID数组，其中包含访客在事件调用中实现（符合条件）的所有特征。 </p> <p>请注意，数组可以包含访客之前符合条件的特征，以及通过此事件调用重新符合条件的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>区段ID数组，其中包含访客在事件调用中实现（符合条件）的所有区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>一个字符串，可捕获所有参数（变量、ID、键值对、设备广告ID等） 在事件调用中传递。 </p> <p>缩短示例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>引荐页面的未编码URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>在事件调用中捕获的访客的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>分配给网站访客的<span class="keyword">Experience Cloud</span> ID(MID)。 另请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和AdobeExperience PlatformIdentity服务</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>一组区段ID，其中包含访客符合条件的先前实现的区段和新区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>数值数组 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特征ID的数组，其中包含访客自上次生成数据馈送以来符合条件的先前实现的特征和新特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件结构 {#cdf-file-structure}

列出并定义[!UICONTROL CDF]文件的数据结构。 这包括数据序列、字段分隔符和分隔符、数据文件映射和样例文件。

## 数据字段标识符和序列 {#identifiers-and-sequence}

[!UICONTROL CDF] 文件不包含标记列或字段标题。相反，[!UICONTROL CDF]文件定义的字段和数组具有非打印的[!DNL ASCII]字符。 此外，[!UICONTROL CDF]文件还按特定顺序列出了每个字段和数组。 了解字段标识符和顺序将帮助您正确解析文件。

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a（ASCII <code> 001</code>或<code> ^A</code>）使用非打印空间指示器分隔单个字段中的数据。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b（ASCII <code> 002</code>或<code> ^B</code>）可将数据与数组和请求参数分离。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c（ASCII <code> 003</code>或<code> ^C</code>）定义键值对。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段序列 </p> </td> 
   <td colname="col2"> <p> <p>重要信息：<span class="keyword">Audience Manager</span>保留在未来版本中向CDF文件末尾添加新字段的权限。 这意味着文件解析系统的技术设计不应假定列数固定（尽管它可能假定现有列的顺序固定）。 </p> </p> <p>CDF文件中的数据按如下所示的顺序显示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件时间 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已实现的特征 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">实现的区段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud设备ID（或MID）。 另请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Adobe Experience Platform Identity服务</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有区段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特征 </li> 
     </ol> </p> <p>有关字段描述，请参阅<a href="#cdf-defined">定义的客户数据馈送内容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 文件映射 {#cdf-file-map}

[!UICONTROL CDF] 文件数据按如下所示的顺序显示。

![](assets/sequence-map.png)

## 识别阵列

[!UICONTROL CDF]文件中的数组以`Ctrl + a`字段分隔符开始和结束。 这会使数组中的第一个元素看起来像一个独立数据字段。 例如，实现的[!UICONTROL traits]阵列以`^A1234`开头。 数组分隔符和ID `^B5678`遵循此条目。 因此，您可能会想到已实现[!UICONTROL traits]数组中的第一个元素是ID 5678（因为它以`^B`开头）。 但情况并非如此，因此您需要熟悉数据文件的顺序和结构。 即使实现的[!UICONTROL trait]数组（或[!UICONTROL CDF]文件中的任何其他数组）中的第一个元素以`^A`开头，文件中的外观或位置顺序仍定义数组的开头。 并且，数组中的第一个元素始终与前一个条目之间以`^A`分隔。

## 示例[!UICONTROL CDF]文件 {#sample-file}

示例[!UICONTROL CDF]文件可能类似于以下内容。 在此示例中插入了换行符，以帮助它适合页面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 文件命名约定 {#cdf-naming-conventions}

以下部分列出并定义[!UICONTROL CDF]文件名中的元素。

## [!UICONTROL CDF] 文件名：语法和示例 {#cdf-file-name}

典型的[!UICONTROL CDF]文件名包含下面列出的元素。 请注意， *斜体*&#x200B;表示变量占位符：

### 语法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### 示例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

在[!DNL S3]存储存储桶中，文件按合作伙伴ID([!UICONTROL PID])、日和小时的升序排序。

## [!UICONTROL CDF] 定义的文件名元素 {#cdf-file-name-elements}

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
   <td colname="col2"> <p>保存CDF文件的只读S3存储段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>处理文件的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>时间值，以24小时表示，以UTC时区设置。 另请参阅<a href="#different-processing-times">客户数据信息源文件名时间和文件内容时间……</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>内部<span class="keyword">Audience Manager</span>进程ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip文件扩展名。 CDF文件已压缩为gzip文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件处理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 将文 `.info` 件写入 [!DNL S3] 目录，以告知您( [!UICONTROL Customer Data File] )何[!UICONTROL CDF]时可供下载。`.info`文件还包含[!DNL JSON]格式化的元数据，其中包含有关[!UICONTROL CDF]文件内容的元数据。 有关此通知文件使用的语法和字段的信息，请参阅此部分。

## 示例信息文件 {#sample-info-file}

每个`.info`文件都包含`Files`和`Totals`部分。 `Files`部分包含一个数组，其中包含每个每小时文件的特定量度。 `Totals`部分包含特定日期内所有[!UICONTROL CDF]文件中汇总的量度。 `.info`文件的内容可能与以下示例类似。

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

下表列出并定义了[!UICONTROL CDF] `.info`文件中的元素。

### 文件对象

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
   <td colname="col2"> <p>文件大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 连字符后面的数字显示在分块上传期间用于构建文件的分块数量。 <code> ETag</code>与文件的MD5校验和不相同。 </p> </td> 
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
   <td colname="col2"> <p>可用数据的小时。 使用按UTC时区设置的24小时格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>该日期所有CDF文件的总大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上传到S3目录的文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件名时间和文件内容时间不同 {#different-processing-times}

您的[!UICONTROL CDF]文件包含文件名和文件内容中的时间戳。 这些时间戳记录同一[!UICONTROL CDF]文件的不同事件进程。 在同一文件的名称和内容中看到不同的时间戳并不罕见。 了解每个时间戳有助于避免在处理此数据或尝试按时间对其进行排序时出现的常见错误。

## 查找[!UICONTROL CDF]文件时间戳 {#locating-timestamps}

[!UICONTROL CDF] 文件在2个不同位置记录的时间不同。

![](assets/cdf-timestamp.png)

## 了解时间戳之间的差异 {#understanding-timestamps}

下表提供了有关[!UICONTROL CDF]文件时间戳的其他详细信息以及有关如何正确使用这些时间戳的信息。

| 时间戳位置 | 描述 |
|--- |--- |
| 文件名 | [!DNL CDF]文件名中的时间戳标记了[!DNL Audience Manager]开始准备文件以进行提交的时间。 此时间戳在[!DNL UTC]时区中设置。 它使用`hour=`参数，时间格式为2位小时，以24小时表示。 此时间可以与文件内容中记录的事件时间不同。 使用[!DNL CDF]文件时，有时您会注意到[!DNL S3]存储段在特定小时内为空。 空存储段表示可表示以下任一情况：<ul><li>那个小时没有数据。 </li><li> 我们的服务器负载过重，无法处理特定小时的文件。 当服务器启动时，它会将本应在早期存储段文件中的文件放入具有稍后时间值的存储段中。 例如，当应在17小时存储段中的文件显示在18小时存储段中时（文件名中为`hour=18`），您将看到此消息。 在这种情况下，服务器可能在17小时内开始处理您的文件，但在该时间间隔内无法完成它。 文件而是会被推送到下一个每小时存储段。</li></ul><br>**重要信息**:请勿使用文件名时间戳按时间对事件进行分组。如果需要按时间分组，请在文件内容中使用`EventTime`时间戳。 |
| 文件内容 | [!DNL CDF]文件内容中的时间戳标记了[!DNL Data Collection Servers]开始处理文件的时间。 此时间戳在[!DNL UTC]时区中设置。 它使用`EventTime`字段，时间格式为&#x200B;*`yyyy-mm-dd hh:mm:ss`*。 此时间接近页面上事件的实际时间，但可能与文件名中的小时指示器不同。<br> **提示**:与文件 `hour=` 名中的时间戳不同，您可以使 `EventTime` 用按时间对数据进行分组。 |

>[!MORELIKETHIS]
>
>* [客户数据信息源常见问题解答](../faq/faq-cdf.md)

