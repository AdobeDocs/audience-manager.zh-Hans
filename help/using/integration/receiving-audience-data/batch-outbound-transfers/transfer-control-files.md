---
description: 传输控制(.info)文件提供了有关文件传输的元数据信息，以便合作伙伴能够验证Audience Manager是否正确处理了文件传输。
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: 用于日志文件传输的传输控制文件
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 用于日志文件传输的传输控制文件 {#transfer-control-files-for-log-file-transfers}

传输控制([!DNL .info])文件提供了有关文件传输的元数据信息，以便合作伙伴能够验证Audience Manager是否正确处理了文件传输。

[!DNL Audience Manager]在每次文件传输时向合作伙伴发送传输控制文件。 由于[!DNL FTP]发布者的多线程特性，传输控制文件可能会在实际文件传输完成之前发送。

[!DNL .info]文件中的元数据允许合作伙伴：

* 确定完整传输周期何时结束（已传送序列中的文件总数）；
* 确定序列中的任何给定文件是否完整/正确(通过检查文件大小（以字节为单位）和总行数)；
* 验证原始文件中的行数与文件在接收端加载到数据库中的行数（文件大小，以行为单位）相对应。

## 文件命名约定 {#file-naming-conventions}

传输控制文件的名称与具有[!DNL .info]文件扩展名的批次/序列的根相同。

例如，如果序列中的第一个文件名为： [!DNL ftp_12345_67890_full_1500727351632-1.sync]，则控制文件将名为[!DNL ftp_12345_67890_iter_1500727351632.info]。

## 文件格式 {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> 批处理总数不包括[!DNL .info]文件本身。 即，总计不包括[!DNL .info]文件、其字节大小或行数。
>
> 文件的字节大小和行数包含任何标题和分隔符（空白）行/行。 要获取实际数据行/行的计数，请减去标题。
>
> 批处理中的总行数和总字节数包含任何标题行和空格行。
