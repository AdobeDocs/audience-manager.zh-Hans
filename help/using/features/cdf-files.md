---
description: 有关客户数据馈送(CDF)文件的基本信息以及如何入门的说明。 如果您对接收CDF文件感兴趣或只想了解更多信息，请从此处开始。
keywords: second party data;2nd party;2nd party data;second party
seo-description: 有关客户数据馈送(CDF)文件的基本信息以及如何入门的说明。 如果您对接收CDF文件感兴趣或只想了解更多信息，请从此处开始。
seo-title: 客户数据馈送
solution: Audience Manager
title: 客户数据馈送
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 客户数据馈送 {#customer-data-feeds}

有关( [!UICONTROL Customer Data Feed] )文件[!UICONTROL CDF]的基本信息以及如何开始的说明。 如果您对接收文件感兴趣或只想获 [!UICONTROL CDF] 取更多信息，请从此处开始。

## 文件内容和用途 {#file-contents-purpose}

<!-- cdf-intro.xml -->

文 [!UICONTROL CDF] 件包含事件调用()发送 [!DNL Audience Manager] 到我们服务器的 `/event`相同数据。 这包括诸如用户ID、特征ID、区段ID等数据，以及事件调用捕获的所有其他参数。 内部 [!DNL Audience Manager] 系统将事件数据处理为一个文件， [!UICONTROL CDF] 其中内容组织为按固定顺序显示的字段。 [!DNL Audience Manager] 尝试每小时生成 [!UICONTROL CDF] 文件并将它们存储在服务器上的一个安全、特定于客户的存储 [!DNL Amazon S3] 桶中。 我们提供这些文件，以便您能够 [!DNL Audience Manager] 使用超出我们用户界面限制的数据。

>[!NOTE]
>
>您不应将文 [!UICONTROL CDF] 件用作监视页面流量、协调报表差异或计费等的代理。

## 快速入门 {#getting-started}

不存在启动文件交付的自助 [!UICONTROL CDF] 流程。 Contact your [!DNL Audience Manager] consultant or Customer Care to get started. 在实施过程中，您的 [!DNL Audience Manager] 代表将：

* 设置存储 [!DNL Amazon S3] 桶。
* 为文件存储存 [!DNL S3] 储桶提供只读身份验证凭据。 您将无法查看或访问属于其他客户的目录和文件。

文件通知 [!UICONTROL CDF] 和文件在准备好下载 [!DNL S3] 后将显示在存储桶中。 您负责从您分配的目录中监视和下载文 [!DNL S3] 件。 请参阅 [客户数据馈送文件处理通知](#cdf-file-processing-notifications)。

## 后续步骤 {#next-steps}

以下部分和客户数 [据馈送常见问题解答](../faq/faq-cdf.md) ，可以帮助您更熟悉此服务。

## 已定义客户数据馈送内容 {#cdf-defined}

按外观顺序列出和定义文件中 [!UICONTROL CDF] 的数据元素和数组。 定义包括数据类型，但此信息不是文件的一 [!UICONTROL CDF] 部分。

## 定义 {#definitions}

<!-- cdf-contents-defined.xml -->

文 [!UICONTROL CDF] 件包括下面定义的部分或全部字段。 有关内部文件组织的信息，请参阅客 [户数据馈送文件结构](#cdf-file-structure)。

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
   <td colname="col3"> <p>数据收集服务器 <span class="wintitle"></span> (DCS)处理CDF文件的时间。 时间戳使用 <i>yyyy-mm-dd hh:mm:ss</i> 格式，并在UTC时区中设置。 </p> <p> <p>注意：活动时 <i>间不是</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或活动调用本身的时间，尽管可能接近这些时间。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名中的DCS小时数相关。 另请参阅客 <a href="#different-processing-times"> 户数据馈送文件名时间和文件内容时间……</a>. </li> 
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
   <td colname="col3"> <p>触发ID同步的容器的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组特征ID，其中包含访客在事件调用中实现（符合）的所有特征。 </p> <p>请注意，该数组可包含访客在此事件调用中曾获得资格且重新获得资格的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组区段ID，其中包含访客在事件调用中实现（符合条件）的所有区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>捕获所有参数（变量、ID、键值对、设备广告ID等）的字符串在活动调用中传入。 </p> <p>缩短示例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>引用页面的未编码URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>在活动调用中捕获的访客的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>分 <span class="keyword"> 配给网站访客的Experience Cloud</span> ID(MID)。 另请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie和Adobe Experience Platform Identity Service</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组区段ID，其中包含访客符合条件的先前实现的区段和新区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>数组 </p> </td> 
   <td colname="col3"> <p>一组第一方和第三方特征ID，其中包含访客自上次生成的数据馈送以来限定的先前实现的特征和新特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 客户数据馈送文件结构 {#cdf-file-structure}

列出并定义文件的数据结 [!UICONTROL CDF] 构。 这包括数据序列、字段分隔符和分隔符、数据文件映射和示例文件。

## 数据字段标识符和序列 {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] 文件不包含标记的列或字段标题。 相反，文 [!UICONTROL CDF] 件定义具有非打印字符的字段和数 [!DNL ASCII] 组。 此外，文 [!UICONTROL CDF] 件按特定顺序列出每个字段和数组。 了解字段标识符和顺序将有助于您正确解析文件。

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a(ASCII或 <code> 001</code><code> ^A</code>)可使用非打印空间指示符分隔各个字段中的数据。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b(ASCII或 <code> 002</code> ) <code> ^B</code>可将数据与数组和请求参数分离。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c(ASCII或 <code> 003</code><code> ^C</code>)定义键值对。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段序列 </p> </td> 
   <td colname="col2"> <p> <p>重要说明：Audience <span class="keyword"></span> Manager保留在将来版本中向CDF文件末尾添加新字段的权利。 这意味着您的文件分析系统的技术设计不应假定固定的列数（尽管它可能采用固定的现有列顺序）。 </p> </p> <p>CDF文件中的数据按以下顺序显示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">活动时间 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">实现的特征 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">实现的细分 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud设备ID（或MID）。 另请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie和Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有细分 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特征 </li> 
     </ol> </p> <p>有关字段说明，请参阅 <a href="#cdf-defined"> 定义的客户数据馈送内容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF文件映射 {#cdf-file-map}

[!UICONTROL CDF] 文件数据按如下所示的顺序显示。

![](assets/sequence-map.png)

## 识别阵列

文件中的数 [!UICONTROL CDF] 组以字段分隔符开始和结 `Ctrl + a` 束。 这使数组中的第一个元素看起来就像独立的数据字段。 例如，实现的traits数组以开头 `^A1234`。 此条目后面是数组分 `^B5678` 隔符和ID。 因此，您可能会想到，已实现特征数组中的第一个元素是ID 5678(因为它以 `^B`开头)。 但情况并非如此，因此您需要熟悉数据文件的顺序和结构。 即使实现的特征数组（或文件中的任何其他数组）中的第一个元素以开头， [!UICONTROL CDF]`^A`文件中的外观或位置顺序也定义数组的开头。 并且，数组中的第一个元素始终与前面的条目分开 `^A`。

## 示例CDF文件 {#sample-file}

示例文 [!UICONTROL CDF] 件可能类似于以下内容。 我们在此示例中插入了换行符，以帮助它适应页面。

![](assets/CDF-sample.png)

## 客户数据馈送文件命名约定 {#cdf-naming-conventions}

下面的部分列出并定义文件名中 [!UICONTROL CDF] 的元素。

## CDF文件名：语法和示例 {#cdf-file-name}

<!-- cdf-file-name.xml -->

典型文 [!UICONTROL CDF] 件名包含以下列出的元素。 Note, *italics* indicates a variable placeholder:

### 语法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### 示例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

在存储 [!DNL S3] 存储段中，文件按合作伙伴ID([!UICONTROL PID])、日和小时的升序排序。

## CDF文件名元素已定义 {#cdf-file-name-elements}

下表列出并定义文件名中的 [!UICONTROL CDF] 元素。

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
   <td colname="col2"> <p>这是Amazon S3服务器上CDF文件的默认根存储存储桶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>只读存储CDF文件的S3存储段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>文件的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小时表示法表示并在UTC时区中设置的时间值。 另请参阅客 <a href="#different-processing-times"> 户数据馈送文件名时间和文件内容时间……</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>内部Audience Manager <span class="keyword"> 流程</span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip文件扩展名。 CDF文件压缩为gzip。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 客户数据馈送文件处理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 将文 `.info` 件写入目 [!DNL S3] 录，以便在( [!UICONTROL Customer Data File][!UICONTROL CDF])准备下载时通知您。 该文 `.info` 件还包含有 [!DNL JSON] 关文件内容的格式化元数据 [!UICONTROL CDF] 。 有关此通知文件使用的语法和字段的信息，请查看此部分。

## 示例信息文件 {#sample-info-file}

<!-- cdf-notifications.xml -->

每个 `.info` 文件都包含 `Files` 和 `Totals` 部分。 该部 `Files` 分包含一个数组，其中包含每个每小时文件的特定度量。 该部 `Totals` 分包含特定日期所有文件 [!UICONTROL CDF] 中汇总的指标。 文件的内 `.info` 容可能与以下示例类似。

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

下表列出并定义文件中的 [!UICONTROL CDF]`.info` 元素。

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
   <td colname="col2"> <p>启动包含有关CDF文件的元数据的数组。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 连字符后面的数字显示在多部件上传期间用于构建文件的部件数。 与 <code> ETag</code> 文件的MD5校验和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>文件名。 请参阅 <a href="#cdf-naming-conventions"> 客户数据馈送文件命名约定</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每个文件的索引编号。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totals对象

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
   <td colname="col2"> <p>启动包含所有CDF文件的聚合数据的对象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>数据可用的日期。 使用 <i>yyyy-mm-dd格式</i> 。 </p> </td> 
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
   <td colname="col2"> <p>上传到S3目录的文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 客户数据馈送文件名时间和文件内容时间不同 {#different-processing-times}

您的 [!UICONTROL CDF] 文件在文件名和文件内容中包含时间戳。 这些时间戳记录同一文件的不同事件 [!UICONTROL CDF] 进程。 在同一文件的名称和内容中看到不同的时间戳并不少见。 了解每个时间戳有助于避免在处理这些数据或尝试按时间排序时出现的常见错误。

## 查找CDF文件时间戳 {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] 文件在两个不同位置记录的时间不同。

![](assets/cdf-timestamp.png)

## 理解时间戳之间的差异 {#understanding-timestamps}

下表提供了有关文件时间戳的更 [!UICONTROL CDF] 多详细信息以及如何正确使用它们的信息。

| 时间戳位置 | 描述 |
|--- |--- |
| 文件名 | CDF文件名中的时间戳标记开始准备文 [!DNL Audience Manager] 件以进行交付的时间。 此时间戳以UTC时区设置。 它使用该 `hour=` 参数，时间格式设置为24小时表示法的2位数小时。 此时间可以不同于文件内容中记录的事件时间。 处理CDF文件时，有时您会注意到S3存储段在特定小时内为空。 空桶装置可以表示以下任一情况：<ul><li>那个小时没有数据。 </li><li> 我们的服务器负载很重，在某个小时内无法处理文件。 当服务器启动时，它将本应在较早时间段中存储的文件放入一个稍后时间值的存储段中。 例如，您会看到，应该在17小时存储段中的文件出现在18小时存储段中(文件名 `hour=18` 中包含)。 在这种情况下，服务器可能在17小时内开始处理您的文件，但无法在该时间间隔内完成它。 相反，文件会被推到下一个每小时的时段。</li></ul><br>**重要说明&#x200B;**:请勿使用文件名时间戳按时间对事件分组。 如果需要按时间分组，请使用文`EventTime`件内容中的时间戳。 |
| 文件内容 | CDF文件内容中的时间戳标记数据收集服务器开始处理文件的时间。 此时间戳以UTC时区设置。 它使用字 `EventTime` 段，时间格式设置为 *`yyyy-mm-dd hh:mm:ss`*。 此时间接近页面上活动的实际时间，但可能与文件名中的小时指示符不同。 <br> **提示**:与文件名 `hour=` 中的时间戳不同，您可以按时间 `EventTime` 使用数据分组。 |

>[!MORELIKETHIS]
>
>* [客户数据馈送常见问题解答](../faq/faq-cdf.md)

