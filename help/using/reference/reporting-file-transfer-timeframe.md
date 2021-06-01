---
description: Audience Manager每天会收到大量数据。 这会影响处理数据和生成报表结果所花费的时间。 此部分中的内容介绍这些时间间隔对您的Audience Manager帐户有何影响。 此外，此处介绍的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-description: Audience Manager每天会收到大量数据。 这会影响处理数据和生成报表结果所花费的时间。 此部分中的内容介绍这些时间间隔对您的Audience Manager帐户有何影响。 此外，此处介绍的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-title: 数据传输和文件处理时间对报表有何影响
solution: Audience Manager
title: 数据传输和文件处理时间对报表有何影响
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: 参考
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# 数据传输和文件处理时间对报表有何影响{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天会收到大量数据。 这会影响处理数据和生成报表结果所花费的时间。 此部分中的内容介绍这些时间间隔对您的Audience Manager帐户有何影响。 此外，此处介绍的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。

## 报表编号{#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出并描述了常规报表和实时报表中的时间间隔。


| 数据类型 | 描述 |
|---|---|
| 实时数据 | 今天的实时数字是从昨天的00:00到23:59:59 UTC的时间。 |
| 常规报表数据 | [常规报表](../reporting/general-reports.md#general-reports-overview)中的数据取决于其他作业进程是否成功完成以及特定日期收到的数据量。 大多数情况下， [!UICONTROL General Report]数据应每天按18:00 UTC进行更新。 |

## 入站和出站文件传输{#inbound-outbound-file-transfers}

[!DNL Audience Manager] 根据本节所述的计划 [!UICONTROL Server-to-Server (S2S)] 处理和发送入站和出站文件传输。鉴于这些计划和截止时间，您可能会看到实时区段数和总区段数之间存在新区段差异。

| 文件类型 | 描述 |
|---|---|
| 入站文件摄取（离线数据） | 文件处理每天执行两次。 这些过程会摄取数据并准备数据以供交付。 文件提交时间因客户需要处理的数据总量而异。 在以Audience Manager上传文件到数据可用于报告和激活之前，您应该会等待最长48小时的延迟。 |
| 出站（导出）文件 | 文件处理和交付每天进行一次，大约在UTC 14:00。 请记住，处理和交付会受这些文件的总数和大小的影响。 在某些情况下，文件处理可能会延迟24小时。 发生这种情况时，Audience Manager将在特定日期发送2个文件，而不是1个文件。 在极少数情况下，Audience Manager必须完全停止处理文件，我们会通知客户。 鉴于这些情况，很难估计出站数据的投放时间。 要确定您是否收到了整套文件，请检查时间戳并查找任何缺失的日期。 这是一个13位的UNIX UTC时间戳，用于记录文件创建的时间。 请参阅[实时出站数据传输](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| 广告服务器日志文件 | 文件处理在每小时文件准备就绪后几乎实时执行，以摄取日志文件记录。 每天执行一次准备报告文件的过程。 文件提交时间因客户需要处理的数据总量而异。 从将文件上传到Audience Manager到数据可用于报告和激活之间，您应该会预计最长延迟48小时。 |

>[!MORELIKETHIS]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)

