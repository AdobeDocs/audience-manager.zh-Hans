---
description: 将投放性能报表日志文件中的数据放入仅包含ID的表中。 将非ID元数据放在单独的查找表中，以帮助减少文件大小和处理时间。
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: 使用查找表缩短日志文件处理时间
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
TQID: https://experienceleague.adobe.com/9eLSmpl5-daNV5NgXrPfLThoIlMibaOtbgrsuqfkeCI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 14%

---

# 使用查找表缩短日志文件处理时间{#improve-log-file-processing-times-with-lookup-tables}

将投放性能报表日志文件中的数据放入仅包含ID的表中。 将非ID元数据放在单独的查找表中，以帮助减少文件大小和处理时间。

<!-- 

c_lookup_tables.xml

 -->

## 日志文件元数据会增加文件大小和处理时间

[!UICONTROL Delivery Performance]报表使用的典型日志文件通常包含数千行和数十列。 它由数字ID和易于用户识别的信息（例如创意人员姓名、广告商、插入顺序等）组成。

此非ID信息称为&#x200B;*`metadata`*（即有关其他信息的信息），并写入日志文件的每一行中。

但是，[!UICONTROL Delivery Performance]报表主要处理日志文件中的ID。 元数据很有用，但可重复使用。 这会增加文件大小和数据摄取时间。

## 使用索引表减小文件大小并缩短处理时间

为了帮助提高性能，您的主数据文件应仅包含ID。 将元数据放在单独的查找（或索引）表中，并将这些记录链接到主文件，其中具有这两个文件的共同键变量。

## 查找表如何减小文件大小

假设您有一个与下图类似的数据文件。

| 用户 ID | 广告 ID | 广告名称 | 订单 ID | 订单名称 | 广告商 ID | 广告商名称 |
|---|---|---|---|---|---|---|
| 1 | 111 | 鞋A | 456 | 运动鞋 | 27 | 公司A |
| 2 | 111 | 鞋A | 456 | 运动鞋 | 27 | 公司A |
| 3 | 111 | 鞋A | 456 | 运动鞋 | 27 | 公司A |
| 4 | 222 | 鞋B | 789 | 健行 | 14 | 公司B |
| 5 | 222 | 鞋B | 789 | 健行 | 14 | 公司B |

<br> 

这是删除了元数据的同一日志文件。 如果文件仅包含ID，则它更小且更易于处理。

| 用户 ID | 广告 ID | 订单 ID | 广告商 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

下面的查找文件包含元数据，可以链接回具有广告ID的主文件。 另外请注意大小。 您无需重复每个广告商多次，只需为每个广告商提供一个引用。

| 广告 ID | 广告名称 | 订单名称 | 广告商名称 |
|---|---|---|---|
| 111 | 鞋A | 运动鞋 | 公司A |
| 222 | 鞋B | 健行 | 公司B |

## API可以消除对查找表的需要

如果您的广告服务系统具有API，则可能不需要在查找文件中发送元数据。 我们或许可以通过API获取该信息。 在这种情况下，日志文件应仅包含ID。 我们将与您合作，确定是否可通过API获取元数据。
