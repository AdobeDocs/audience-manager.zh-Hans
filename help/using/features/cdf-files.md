---
description: 有关客户数据馈送(CDF)文件的基本信息以及如何开始的说明。 开始此处，如果您对接收CDF文件感兴趣或只想了解更多信息。
keywords: second party data;2nd party;2nd party data;second party
seo-description: 有关客户数据馈送(CDF)文件的基本信息以及如何开始的说明。 开始此处，如果您对接收CDF文件感兴趣或只想了解更多信息。
seo-title: 客户数据信息源
solution: Audience Manager
title: 客户数据信息源
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 4%

---


# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有关()文 [!UICONTROL Customer Data Feed] 件的[!UICONTROL CDF]基本信息以及如何入门的说明。 开始此处，如果您对接收文件感 [!UICONTROL CDF] 兴趣或只想了解更多信息。

## 文件内容和用途 {#file-contents-purpose}

[!UICONTROL CDF] 文件包含的数据与 [!DNL Audience Manager] 事件调用 (`/event`) 发送到我们服务器的数据相同。This includes data like user IDs, [!UICONTROL trait IDs], [!UICONTROL segment IDs], and all the other parameters captured by an event call. 内部 [!DNL Audience Manager] 系统将事件数据处理为 [!UICONTROL CDF] 一个文件，其中内容组织为按设置顺序显示的字段。 [!DNL Audience Manager] 尝试每小时生 [!UICONTROL CDF] 成一个文件，并将它们存储在服务器上一个安全、特定于客户的存储 [!DNL Amazon S3] 桶中。 我们提供这些文件，以便您能够 [!DNL Audience Manager] 处理超出我们用户界面限制的数据。

>[!NOTE]
>
>您不应将文 [!UICONTROL CDF] 件用作监视页面流量、调节报表差异或计费等的代理。

## 快速入门 {#getting-started}

没有自助过程来开始文 [!UICONTROL CDF] 件投放。 Contact your [!DNL Audience Manager] consultant or Customer Care to get started. 在实施过程中，您的 [!DNL Audience Manager] 代表将：

* 设置您的 [!DNL Amazon S3] 存储桶。
* 为文件存储存储 [!DNL S3] 桶提供只读身份验证凭据。 您将无法查看或访问属于其他客户的目录和文件。

文件通知 [!UICONTROL CDF] 和文件在准备 [!DNL S3] 下载时将显示在存储桶中。 您负责从您分配的目录监视和下载文 [!DNL S3] 件。 请参阅[客户数据信息源文件处理通知](#cdf-file-processing-notifications)。

## 后续步骤 {#next-steps}

以下部分和客户数 [据馈送常见问题解答](../faq/faq-cdf.md) ，可以帮助您更熟悉此服务。

## [!UICONTROL Customer Data Feed] 内容已定义 {#cdf-defined}

列表并按外观顺序定义文 [!UICONTROL CDF] 件中的数据元素和数组。 定义包括数据类型，但此信息不是文件的一 [!UICONTROL CDF] 部分。

## 定义 {#definitions}

文 [!UICONTROL CDF] 件包括下面定义的部分或所有字段。 有关内部文件组织的信息，请参 [阅客户数据馈送文件结构](#cdf-file-structure)。

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
   <td colname="col3"> <p>数据收集服务器(DCS)处 <span class="wintitle"> 理CDF文件</span> 的时间。 时间戳使 <i>用yyyy-mm-dd hh:mm:ss</i> 格式，以UTC时区设置。 </p> <p> <p>注意： 事件时 <i>间不是</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或事件自行调用的时间，但可能接近这些时间。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名中的DCS小时相关。 另请参阅 <a href="#different-processing-times"> 客户数据馈送文件名时间和文件内容时间……</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>这是唯 <span class="wintitle"> 一用户ID</span> (UUID)，它是站点访客的38位设备ID。 另请参阅 <a href="../reference/ids-in-aam.md">Audience Manager 中的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>数值 </p> </td> 
   <td colname="col3"> <p>触发ID的容器的ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组特征ID，包含访客在事件调用中实现（合格）的所有特征。 </p> <p>请注意，该数组可包含访客之前已限定的特征，以及通过此事件调用重新限定的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组段ID，包含访客在事件调用中实现（符合条件）的所有段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>捕获所有参数（变量、ID、键值对、设备广告ID等）的字符串 在事件电话上过。 </p> <p>缩短示例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>引用页面的未编码URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>在访客调用中捕获的事件的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>分配给 <span class="keyword"> 站点</span> Experience Cloud的访客ID(MID)。 另请参阅 <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies和AdobeExperience Platform身份服务</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组段ID，包含访客符合的先前实现的段和新段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组第一方和第三方特征ID，它包含访客自上次生成的数据源以来限定的先前实现的特征和新特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件结构 {#cdf-file-structure}

列表并定义文件的数据结 [!UICONTROL CDF] 构。 这包括数据序列、字段分隔符和分隔符、数据文件映射和示例文件。

## 数据字段标识符和序列 {#identifiers-and-sequence}

[!UICONTROL CDF] 文件不包含标记的列或字段标题。 相反，文件 [!UICONTROL CDF] 定义具有非打印字符的字段和 [!DNL ASCII] 数组。 此外，文 [!UICONTROL CDF] 件按特定顺序列表每个字段和数组。 了解字段标识符和顺序将有助于您正确分析文件。

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
   <td colname="col2"> <p>这些非打印字符定义了CDF文件的元素和结构： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a(ASCII <code> 001</code> 或 <code> ^A</code>)用非打印空间指示符分隔各个字段中的数据。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b(ASCII或 <code> 002</code> ASCII <code> ^B</code>)将数据与数组和请求参数分离。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c(ASCII <code> 003</code> 或 <code> ^C</code>)定义键值对。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段序列 </p> </td> 
   <td colname="col2"> <p> <p>重要： <span class="keyword"> Audience Manager</span> 保留在未来版本中向CDF文件末尾添加新字段的权利。 这意味着文件分析系统的技术设计不应采用固定数量的列（尽管它可能采用固定的现有列顺序）。 </p> </p> <p>CDF文件中的数据按以下顺序显示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件时间 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已实现特征 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已实现细分 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud设备ID（或MID）。 See also, <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有细分 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特征 </li> 
     </ol> </p> <p>有关字段说明，请参 <a href="#cdf-defined"> 阅定义的客户数据馈送内容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 文件映射 {#cdf-file-map}

[!UICONTROL CDF] 文件数据按如下所示的顺序显示。

![](assets/sequence-map.png)

## 识别阵列

数组在文 [!UICONTROL CDF] 件开始中，以字段分隔 `Ctrl + a` 符结束。 这使数组中的第一个元素看起来就像独立数据字段。 例如，实现的 [!UICONTROL traits] 数组开始 `^A1234`。 数组分隔符和ID `^B5678` 位于此条目后。 因此，您可能会想到实现的数组中的第一个元素 [!UICONTROL traits] 是ID 5678(因为它与开始 `^B`一起)。 但情况并非如此，因此您需要熟悉数据文件的顺序和结构。 即使实现的数组(或文 [!UICONTROL trait] 件中的任何其他数组)中的第一个元素 [!UICONTROL CDF] 具有开始 `^A`，文件中的外观或位置顺序也定义数组的开始。 并且，数组中的第一个元素始终与前一个条目分开 `^A`。

## Sample [!UICONTROL CDF] File {#sample-file}

示例文 [!UICONTROL CDF] 件可能类似于以下内容。 我们已在此示例中插入换行符，以帮助它适合页面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 文件命名约定 {#cdf-naming-conventions}

以下各节列表并定义文件名中 [!UICONTROL CDF] 的元素。

## [!UICONTROL CDF] 文件名： 语法和示例 {#cdf-file-name}

典型文 [!UICONTROL CDF] 件名包含以下列出的元素。 Note, *italics* indicates a variable placeholder:

### 语法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### 示例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

在存储 [!DNL S3] 存储段中，文件按合作伙伴ID()、日和小时[!UICONTROL PID]的升序排序。

## [!UICONTROL CDF] 文件名元素已定义 {#cdf-file-name-elements}

下表列表并定义文件名中 [!UICONTROL CDF] 的元素。

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
   <td colname="col2"> <p>这是Amazon S3服务器上CDF文件的默认根存储存储段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>只读存储段的名称，保存CDF文件的S3存储段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>文件的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小时记号表示的时间值，在UTC时区中设置。 另请参阅 <a href="#different-processing-times"> 客户数据馈送文件名时间和文件内容时间……</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>内部的 <span class="keyword"> Audience Manager</span> 进程ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip文件扩展名。 CDF文件压缩为gzip。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件处理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 将文 `.info` 件写入目 [!DNL S3] 录，以告知您() [!UICONTROL Customer Data File] 准备下[!UICONTROL CDF]载时间。 该文 `.info` 件还包含 [!DNL JSON] 有关文件内容的格式化元 [!UICONTROL CDF] 数据。 有关此通知文件使用的语法和字段的信息，请查阅本节。

## 示例信息文件 {#sample-info-file}

每个 `.info` 文件都包含 `Files` 一个 `Totals` 和节。 该部 `Files` 分包含一个数组，其中包含每个小时文件的特定度量。 该 `Totals` 部分包含特定日期所有文 [!UICONTROL CDF] 件中汇总的指标。 文件的内 `.info` 容可能与以下示例类似。

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

## 信息文件字段已定义 {#info-file-fields-defined}

下表列表并定义文件中的 [!UICONTROL CDF] 元 `.info` 素。

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
   <td colname="col2"> <p>开始包含有关CDF文件的元数据的数组。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小（字节）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 连字符后的数字显示在多部件上传期间用于构建文件的部件数量。 与 <code> ETag</code> 文件的MD5校验和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>文件名。 See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每个文件的索引编号。 </p> </td> 
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
   <td colname="col2"> <p>开始包含所有CDF文件的聚合数据的对象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>数据可用的日期。 使 <i>用yyyy-mm-dd</i> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>可用数据的小时数。 使用UTC时区中设置的24小时格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>该日期所有CDF文件的总大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上载到S3目录的文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 文件名时间和文件内容时间不同 {#different-processing-times}

您的 [!UICONTROL CDF] 文件在文件名和文件内容中包含时间戳。 这些时间戳记录同一文件的不同事件 [!UICONTROL CDF] 进程。 在同一文件的名称和内容中看到不同的时间戳并不少见。 了解每个时间戳可以帮助您避免在处理此数据或尝试按时间排序时出现的常见错误。

## 查找文 [!UICONTROL CDF] 件时间戳 {#locating-timestamps}

[!UICONTROL CDF] 文件在两个不同位置记录的时间不同。

![](assets/cdf-timestamp.png)

## 理解时间戳之间的差异 {#understanding-timestamps}

下表提供了有关文件时间戳的 [!UICONTROL CDF] 其他详细信息以及如何正确使用时间戳的信息。

| 时间戳位置 | 描述 |
|--- |--- |
| 文件名 | 文件名中的 [!DNL CDF] 时间戳标记开始准 [!DNL Audience Manager] 备文件进行投放的时间。 此时间戳在时区 [!DNL UTC] 中设置。 它使用参 `hour=` 数，时间格式设置为2位数小时（以24小时表示）。 此时间可以与文件内容中记录的事件时间不同。 处理文 [!DNL CDF] 件时，有时您会注意到您的存储 [!DNL S3] 桶在特定的小时内为空。 空桶装置可以表示以下任一情况：<ul><li>那个小时没有数据。 </li><li> 我们的服务器负载很重，无法处理特定小时的文件。 当服务器启动时，它将本应放在较早时段的文件放入具有稍后时间值的存储桶中。 例如，当本应在17小时存储段中的文件出现在18小时存储段中时（在文件名中），您 `hour=18` 会看到这一点。 在这种情况下，服务器可能在17小时内开始处理您的文件，但无法在该时间间隔内完成它。 相反，文件将推送到下一个小时时段。</li></ul><br>**重要说明&#x200B;**: 请勿使用文件名时间戳按时间对事件分组。 如果需要按时间分组，请使用文`EventTime`件内容中的时间戳。 |
| 文件内容 | 文件内容中 [!DNL CDF] 的时间戳标记开始处 [!DNL Data Collection Servers] 理文件的时间。 此时间戳在时区 [!DNL UTC] 中设置。 它使用字 `EventTime` 段，时间格式设置为 *`yyyy-mm-dd hh:mm:ss`*。 此时间接近页面上事件的实际时间，但可能与文件名中的小时指示符不同。 <br> **提示**: 与文件 `hour=` 名中的时间戳不同，您可以 `EventTime` 按时间对数据分组。 |

>[!MORELIKETHIS]
>
>* [客户数据信息源常见问题解答](../faq/faq-cdf.md)

