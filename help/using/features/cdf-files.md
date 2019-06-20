---
description: 有关客户数据馈送(CMS)文件的基本信息以及入门说明。如果您有兴趣接收CMS文件或只想了解更多信息，请从此处开始。
keywords: 第二方数据；第二方；第二方数据；第二方
seo-description: 有关客户数据馈送(CMS)文件的基本信息以及入门说明。如果您有兴趣接收CMS文件或只想了解更多信息，请从此处开始。
seo-title: 客户数据馈送
solution: Audience Manager
title: 客户数据馈送
uuid: a5de1630-2c7a-4862-9ba0-f8343 cdd2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you&#39;re interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

[!UICONTROL CDF] 文件包含一个 [!DNL Audience Manager] 事件调用( `/event`)发送到我们服务器的相同数据。这包括用户ID、特征ID、细分ID以及事件调用捕获的所有其他参数等数据。Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] 尝试每小时生成 [!UICONTROL CDF] 文件，并将它们存储在 [!DNL Amazon S3] 服务器上的安全特定于客户的桶中。We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## 快速入门 {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. 您将无法查看或访问属于其他客户的目录和文件。

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they&#39;re ready for download. You&#39;re responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## 后续步骤 {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## 定义 {#definitions}

<!-- cdf-contents-defined.xml -->

[!UICONTROL CDF] 文件包括下面定义的部分或全部字段。For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

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
   <td colname="col1"> <p><code> 活动时间</code> </p> </td> 
   <td colname="col2"> <p>时间戳 </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">页面事件或活动本身的时间，尽管可能接近这些时间。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">与文件名称中DCS小时相关。See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 设备</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. 另请参阅 <a href="../reference/ids-in-aam.md">Audience Manager 中的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 容器 ID</code> </p> </td> 
   <td colname="col2"> <p>数值 </p> </td> 
   <td colname="col3"> <p>触发ID同步的容器的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 已实现的特征</code> </p> </td> 
   <td colname="col2"> <p>数字数组 </p> </td> 
   <td colname="col3"> <p>一组特征ID，其中包含访客在事件调用中实现(符合资格)的所有特征。 </p> <p>请注意，该数组可以包含访客在之前符合条件的条件，并可通过此活动调用重新确定其资格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 已实现的区段</code> </p> </td> 
   <td colname="col2"> <p>数字数组 </p> </td> 
   <td colname="col3"> <p>一组区段ID，其中包含访客在活动调用中实现(符合资格)的所有区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 请求参数</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>捕获所有参数(变量、ID、键-值对等)的字符串传入。 </p> <p>缩短的示例： </p> <p> <code> d_ rtbd：json，c_ ContextData. a. CallerName：mobile，c_ ContextData. a. ayo：92D56353-49C5-431E-B474-FC528 D585810，c_ ContextData. a，RunMode：应用程序，c_ ContextData. a.daysSinceLast升级：61，d_ cid_ ic：xid%01EACB6E40-AC65-4012-9FE9-ABD59965 E9 C4%011，c_ ContextData. a. prepsessionLength：583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 参照数据类型</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>引用页面的未编码URL(如果有)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP数据类型</code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>在活动调用中捕获的访客的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> McDevice </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 所有区段</code> </p> </td> 
   <td colname="col2"> <p>数字数组 </p> </td> 
   <td colname="col3"> <p>区段ID数组，其中包含之前已创建的区段和访客符合条件的新区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 所有特征</code> </p> </td> 
   <td colname="col2"> <p>数字数组 </p> </td> 
   <td colname="col3"> <p>第一个和第三方特征ID的数组，该ID包含访客自上次生成的数据源以来符合条件的特征和新特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. 这包括数据序列、字段分隔符和分隔符、数据文件映射和示例文件。

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] 文件不包含标记的列或字段标题。Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. 了解字段标识符和顺序可帮助您正确解析文件。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CMS文件元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>字段分隔符和分隔符 </p> </td> 
   <td colname="col2"> <p>这些非打印字符定义CMS文件的元素和结构： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段序列 </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. 这意味着，您的文件分析系统的技术设计不应采用固定数量的列数(尽管可能对现有列采用固定订单)。 </p> </p> <p>CMS文件中的数据显示按以下顺序显示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">活动时间 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">设备 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已实现的特征 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已实现的区段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">请求参数 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 地址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud设备ID(或MID)。See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有区段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特征 </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] 文件数据显示如下所示。

![](assets/sequence-map.png)

## 识别数组

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. 这使得数组中的第一个元素像独立数据字段一样显示。For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). 不是这种情况，因此您需要熟悉数据文件的序列和结构。Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. 我们在此示例中插入了换行，以帮助其适合页面。

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **语法**

<pre><code>s3：管理员<i>桶名称</i>/day=<i>yyyy-mm-dd</i>/hr=<i>hh</i>/<i>AAM_ CMS_合作伙伴ID_ AAM流程ID</i>_0.gz</code>
</pre>

* **示例**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件名元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3：//aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>这是Amazon S服务器上的CMS文件的默认根存储桶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>您的S桶名称</i></code> </p> </td> 
   <td colname="col2"> <p>保存CMS文件的只读S坩埚的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>处理文件的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hor=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小时表示表示的时间值，在UTC时区中设置。See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>合作伙伴ID</i></code> </p> </td> 
   <td colname="col2"> <p>您的合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>AAM进程ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip文件扩展名。CMS文件压缩压缩。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] 将 `.info` 文件写入 [!DNL S3] 目录中，以便您了解 [!UICONTROL Customer Data File] ([!UICONTROL CDF])何时可以下载。`.info` 该文件还包含 [!DNL JSON] 有关 [!UICONTROL CDF] 文件内容的格式元数据。查看本节以了解有关此通知文件使用的语法和字段的信息。

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. `Files` 该部分包含一个数组，其中包含每个每小时文件的特定量度。`Totals` 该部分包含特定天内所有 [!UICONTROL CDF] 文件中汇总的指标。`.info` 文件的内容可能类似于下面的示例。

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

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

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
   <td colname="col1"> <p> <code> 文件</code> </p> </td> 
   <td colname="col2"> <p>启动包含有关CMS文件的元数据的数组。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> fileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小(以字节为单位)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3eTag。连字符后面的数字显示在多部上传过程中用于构建文件的部分数量。<code> eTag</code> 与文件的MD校验和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> fileName</code> </p> </td> 
   <td colname="col2"> <p>文件名。See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSquenceNumber</code> </p> </td> 
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
   <td colname="col1"> <p> <code> 总计</code> </p> </td> 
   <td colname="col2"> <p>启动包含有关所有CMS文件的汇总数据的对象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 日</code> </p> </td> 
   <td colname="col2"> <p>数据可用之日。Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 小时</code> </p> </td> 
   <td colname="col2"> <p>提供数据的时间。使用UTC时区设置24小时的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalByteSize</code> </p> </td> 
   <td colname="col2"> <p>该日期的所有CMS文件的总大小(以字节为单位)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上传到S目录的文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

[!UICONTROL CDF] 文件包含文件名和文件内容中的时间戳。These timestamps record different event processes for the same [!UICONTROL CDF] file. 在同一文件的名称和内容中查看不同时间戳不常见。了解每个时间戳可帮助您避免处理此数据时出现常见错误，或尝试按时间排序。

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] 文件在两个不同位置上的记录时间不同。

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| 时间戳位置 | 描述 |
|--- |--- |
| 文件名 | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. 此时间戳设置在UTC时区中。It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. 此时间可能与文件内容中记录的活动时间不同。断点使用CMS文件时，有时您会注意到您的S桶在特定小时内是空的。空桶意味着指以下任一方式：<ul><li>这一特定小时没有数据。 </li><li> 我们的服务器负载很大，无法处理特定小时的文件。当服务器捕获时，它将应在较早的时间桶文件中放置的文件放入具有较高时间值的桶中。For example, you&#39;ll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). 在这种情况下，服务器可能在小时内开始处理您的文件，但在该时间间隔内无法完成。相反，文件会推送到下一小时的桶。</li></ul><br>**重要**：请勿使用文件名时间戳按时间分组事件。If you need to group by time, use the `EventTime` timestamp in the file contents. |
| 文件内容 | CMS文件内容中的时间戳标记了开始处理文件的数据收集服务器的时间。此时间戳设置在UTC时区中。It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **提示**：与文件名中的 `hour=` 时间戳不同，您可以 `EventTime` 按时间分组数据。 |

>[!MORE_ LIKE_ This]
>
>* [客户数据馈送常见问题解答](../faq/faq-cdf.md)

