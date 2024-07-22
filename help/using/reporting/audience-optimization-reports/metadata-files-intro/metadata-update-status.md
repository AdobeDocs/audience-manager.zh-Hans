---
description: S3状态目录包含一个.info文件，其中包含有关上载文件的成功和失败信息。 该文件包含JSON格式的数据，其状态结果位于数组中。
seo-description: The S3 status directory holds a .info file with success and failure information about your uploaded files. The file contains JSON-formatted data with status results in an array.
seo-title: Status Updates for Metadata Files
solution: Audience Manager
title: 元数据文件的状态更新
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: Log Files
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# 元数据文件的状态更新{#status-updates-for-metadata-files}

S3状态目录包含一个`.info`文件，其中包含有关您上传文件的成功和失败信息。 该文件包含JSON格式的数据，其状态结果位于数组中。

`.info`文件的内容将与以下示例类似。

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## 定义的元数据键值对 {#key-value-pairs}

下表列出并定义元数据状态文件`Files`和`Summary`节中的键。

文件阵列中的&#x200B;**个键**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>包含处理失败原因的简短描述。 处理成功时，此字段为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小（字节）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>上载到<code> meta</code>目录的元数据文件的MD 5校验和。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>上载到<code> meta</code>目录的元数据文件的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>易于用户识别的文件包含的数据类型名称。 它基于您文件名中的子ID。 </p> <p>请参阅元数据文件的<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">命名约定</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>易于用户识别的文件包含的数据类型名称。 它基于您文件名中的父ID。 </p> <p>请参阅元数据文件的<a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md">命名约定</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>返回2个文本值，这些文本值描述元数据文件的处理状态： </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

摘要对象中的&#x200B;**键**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p><code><i>yyyy-mm-dd</i></code>格式的文件处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>返回2个文本值，这些文本值描述一天内所有文件的处理状态： </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>处理失败的文件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>成功处理的文件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>返回用于处理开始时间的可读时间戳。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>用于处理开始时间的UNIX时间戳。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>当天所有元数据文件的字节总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>当天处理的所有文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
