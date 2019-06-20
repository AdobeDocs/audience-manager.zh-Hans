---
description: 传输控制(.info)文件提供有关文件传输的元数据信息，以便合作伙伴能够验证Audience Manager是否正确处理了文件传输。
seo-description: 传输控制(.info)文件提供有关文件传输的元数据信息，以便合作伙伴能够验证Audience Manager是否正确处理了文件传输。
seo-title: 为日志文件传输传输控制文件
solution: Audience Manager
title: 为日志文件传输传输控制文件
uuid: ef58213e-7b37-4c5a-855-0de695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] 将传输控制文件发送给每个文件传输的合作伙伴。Due to the multi-thread nature of the [!DNL FTP] publisher, the transfer-control file might be sent before the actual files are finished transferring.

[!DNL .info] 文件中的元数据允许合作伙伴：

* 确定完整传输周期何时完成(已交付序列中的文件总数)；
* 确定序列中给定文件是否完整/正确(通过按字节数和行数检查文件大小)；
* 验证在接收结束的数据库中加载文件后，原始文件中的行数记录行数(以行的文件大小)。

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

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

>[Note]
>
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> 文件和行计数的字节大小包括任何标题和分隔符(空白)行/行。为了获得实际的数据线/行的计数，减少标题。
>
> 批处理和总字节大小中的总行数包括任何标题和空间行。