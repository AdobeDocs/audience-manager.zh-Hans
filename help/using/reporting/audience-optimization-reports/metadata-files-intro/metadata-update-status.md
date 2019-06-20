---
description: S状态目录包含一个.info文件，其中包含有关已上传文件的成功和失败信息。该文件包含一个数组中包含状态结果的JSON格式数据。
seo-description: S状态目录包含一个.info文件，其中包含有关已上传文件的成功和失败信息。该文件包含一个数组中包含状态结果的JSON格式数据。
seo-title: 元数据文件的状态更新
solution: Audience Manager
title: 元数据文件的状态更新
uuid: 56a1e88a-41da-4d51a21e21e21e-2ba2fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Status Updates for Metadata Files{#status-updates-for-metadata-files}

The S3 status directory holds a `.info` file with success and failure information about your uploaded files. 该文件包含一个数组中包含状态结果的JSON格式数据。

`.info` 文件的内容将类似于此示例。

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

## Metadata Key-Value Pairs Defined {#key-value-pairs}

The following tables list and define the keys in the `Files` and `Summary` sections of a metadata status file.

**文件数组中的按键**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 描述</code> </p> </td> 
   <td colname="col2"> <p>包含为什么处理失败的简要说明。处理成功时，此字段为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> fileByteSize</code> </p> </td> 
   <td colname="col2"> <p>文件大小(以字节为单位)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The MD 5 checksum for the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> fileName</code> </p> </td> 
   <td colname="col2"> <p>The name of the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> metadataType</code> </p> </td> 
   <td colname="col2"> <p>文件包含的数据类型的人可读名称。它基于文件名中的子ID。 </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent（父项）</code> </p> </td> 
   <td colname="col2"> <p>文件包含的数据类型的人可读名称。它基于文件名中的父ID。 </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 状态</code> </p> </td> 
   <td colname="col2"> <p>返回描述元数据文件处理状态的个文本值： </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**摘要对象中的按键**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 日</code> </p> </td> 
   <td colname="col2"> <p>File processing date in <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> globalStatus</code> </p> </td> 
   <td colname="col2"> <p>返回一个用于整日处理所有文件的处理状态的文本值： </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>未成功处理的文件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numbersuccess</code> </p> </td> 
   <td colname="col2"> <p>成功处理的文件数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>返回处理开始时间的人可读时间戳。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> processingTimePosix</code> </p> </td> 
   <td colname="col2"> <p>用于处理开始时间的UNIX时间戳。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalByteSize</code> </p> </td> 
   <td colname="col2"> <p>当天所有元数据文件的总字节数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>当天处理的所有文件总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
