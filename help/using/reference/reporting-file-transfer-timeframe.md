---
description: Audience Manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所需的时间。 此部分中的内容将介绍这些时间间隔如何影响您的Audience Manager帐户。 此外，此处介绍的时间范围和时间表只是一般准则。 这些计划不构成与数据传输相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间框架和时间安排的权利，恕不另行通知。
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: 数据传输和文件处理时间对报表有何影响
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# 数据传输和文件处理时间对报表有何影响{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所需的时间。 此部分中的内容将介绍这些时间间隔如何影响您的Audience Manager帐户。 此外，此处介绍的时间范围和时间表只是一般准则。 这些计划不构成与数据传输相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间框架和时间安排的权利，恕不另行通知。

## 报表编号 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出并描述了常规报表和实时报表中的时间间隔。


| 数据类型 | 描述 |
|---|---|
| 实时数据 | 今天的实时数字是昨天的00:00到23:59:59 UTC的小时。 |
| 常规报表数据 | [常规报表](../reporting/general-reports.md#general-reports-overview)中的数据取决于其他作业进程的成功完成情况以及特定日期接收的数据量。 大多数情况下，[!UICONTROL General Report]数据应每天在18:00 UTC更新。 |

## 入站和出站文件传输 {#inbound-outbound-file-transfers}

[!DNL Audience Manager]根据本节中介绍的计划处理并发送入站和出站[!UICONTROL Server-to-Server (S2S)]文件传输。 根据这些时间表和截止时间，您可能会看到实时区段数与总区段数在新的区段上存在差异。

| 文件类型 | 描述 |
|---|---|
| 入站文件摄取（离线数据） | 文件处理每天执行两次。 这些过程摄取数据并准备投放。 文件交付时间会有所不同，因为交付时间受需要处理的客户数据总量的影响。 从文件上传到Audience Manager到数据可用于报表和激活这段时间，您最多可能等待48小时。 |
| 出站（导出）文件 | 文件处理和交付每天大约在14:00 UTC进行。 请记住，处理和提交受这些文件的总数量和大小的影响。 在某些情况下，文件处理可能会延迟长达24小时。 发生这种情况时，Audience Manager将在特定的一天发送2个文件，而不是1个。 在极少数情况下，如果Audience Manager必须完全停止处理文件，我们将通知客户。 鉴于这些条件，很难估计出站数据的投放时间。 要确定您是否已收到一组完整文件，请检查时间戳并查找任何缺失的日期。 这是一个13位数的UNIX UTC时间戳，用于记录文件的创建时间。 请参阅[实时出站数据传输](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| 广告服务器日志文件 | 当每小时文件就绪时，近乎实时地执行文件处理以摄取日志文件记录。 准备文件以进行报告的过程每天执行一次。 文件交付时间会有所不同，因为交付时间受需要处理的客户数据总量的影响。 从将文件上传到Audience Manager到数据可用于报表和激活这段时间，滞后时间最长应为48小时。 |

>[!MORELIKETHIS]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)
