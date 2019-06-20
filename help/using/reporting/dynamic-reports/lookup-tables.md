---
description: 将“交付性能”报告日志文件中的数据放入包含ID的表格中。将非ID元数据放入单独的查找表中，有助于减小文件大小和处理时间。
seo-description: 将“交付性能”报告日志文件中的数据放入包含ID的表格中。将非ID元数据放入单独的查找表中，有助于减小文件大小和处理时间。
seo-title: 使用查找表改进日志文件处理时间
solution: Audience Manager
title: 使用查找表改进日志文件处理时间
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

将“交付性能”报告日志文件中的数据放入包含ID的表格中。将非ID元数据放入单独的查找表中，有助于减小文件大小和处理时间。

<!-- 

c_lookup_tables.xml

 -->

## 日志文件元数据增加文件大小和处理时间

[!UICONTROL Delivery Performance] 报表使用的典型日志文件通常包含数千行和几十列。它包括数字ID和人工可读信息，如创意、广告商、插入订单等。

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. 元数据很有用，但重复了。它增加了文件大小和数据采集时间。

## 使用索引表缩减文件大小并缩短处理时间

为提高性能，主数据文件应仅包含ID。将元数据放入一个单独的查找(或索引)表中，并将这些记录链接到主文件，其中这两个记录都是通用变量。

## 查找表如何减小文件大小

假设您有一个类似于下面的数据文件。

| 用户 ID | 广告 ID | 广告名称 | 订单 ID | 订购名称 | 广告商 ID | 广告商姓名 |
|---|---|---|---|---|---|---|
| 1 | 111 | ShoShoA | 456 | Sneakers | 27 | Company A |
| 2 | 111 | ShoShoA | 456 | Sneakers | 27 | Company A |
| 3 | 111 | ShoShoA | 456 | Sneakers | 27 | Company A |
| 4 | 222 | Shoe B | 789 | Highing | 14 | 公司B |
| 5 | 222 | Shoe B | 789 | Highing | 14 | 公司B |

<br> 

以下是删除了元数据的相同日志文件。仅当文件包含ID时，文件更小、更易于处理。

| 用户 ID | 广告 ID | 订单 ID | 广告商 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

下查找文件保留元数据，并可使用广告ID链接回主文件。请注意大小。您只需对每个广告商进行一次引用，而不是多次重复广告。

| 广告 ID | 广告名称 | 订购名称 | 广告商姓名 |
|---|---|---|---|
| 111 | ShoShoA | Sneakers | Company A |
| 222 | Shoe B | Highing | 公司B |

## API可以消除对查找表的需求

如果广告服务系统有API，则可能无需在查找文件中发送元数据。我们可能能够通过API获取该信息。在这种情况下，您的日志文件应仅包含ID。我们将与您一起确定是否可以通过API获取元数据。

>[!MORE_ LIKE_ This]
>
>* [交付和性能报告](../../reporting/dynamic-reports/delivery-performance-report.md)

