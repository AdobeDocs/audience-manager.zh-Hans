---
description: Audience Manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节内容介绍这些时间间隔对您的Audience Manager帐户的影响。 此外，此处描述的时间范围和计划仅是一般准则。 这些计划不构成与数据投放相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-description: Audience Manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节内容介绍这些时间间隔对您的Audience Manager帐户的影响。 此外，此处描述的时间范围和计划仅是一般准则。 这些计划不构成与数据投放相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-title: 数据传输和文件处理时间对报表有何影响
solution: Audience Manager
title: 数据传输和文件处理时间对报表有何影响
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# 数据传输和文件处理时间对报表有何影响{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节内容介绍这些时间间隔对您的Audience Manager帐户的影响。 此外，此处描述的时间范围和计划仅是一般准则。 这些计划不构成与数据投放相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。

## 报告编号{#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列表了一般和实时报告中的时间间隔。


| 数据类型 | 描述 |
|---|---|
| 实时数据 | 今天的实时数是从昨天开始的00:00到23:59:59 UTC的时间。 |
| 一般报告数据 | [常规报告](../reporting/general-reports.md#general-reports-overview)中的数据取决于其他作业进程的成功完成情况以及特定日期接收的数据量。 大多数情况下， [!UICONTROL General Report]数据应每天在18:00 UTC前更新。 |

## 入站和出站文件传输{#inbound-outbound-file-transfers}

[!DNL Audience Manager] 根据本节所述的计划 [!UICONTROL Server-to-Server (S2S)] 处理和发送入站和出站文件传输。鉴于这些计划和中断时间，您可能会发现实时细分与总细分数之间的新细分存在差异。

| 文件类型 | 描述 |
|---|---|
| 入站文件摄取（脱机数据） | 每天执行两次文件处理。 这些过程会收集数据并准备投放。 文件投放时间因需要处理的客户数据总量而异。 从文件以Audience Manager上载到报告和激活数据之前，您应该预计最长等待48小时。 |
| 出站（导出）文件 | 文件处理和投放每天进行一次，大约在14:00 UTC。 请记住，处理和投放受这些文件的总数和大小的影响。 在某些情况下，文件处理可能会延迟24小时。 发生这种情况时，Audience Manager将发送2个文件，而不是1个。 在Audience Manager必须完全停止处理文件的少数情况下，我们会通知客户。 鉴于这些情况，很难估计出站投放的时间。 要确定您是否收到完整的文件集，请检查时间戳并查找任何缺少的日期。 这是一个13位的UNIX UTC时间戳，记录文件创建的时间。 请参阅[实时出站数据传输](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| 广告服务器日志文件 | 文件处理几乎实时执行，以在每小时文件准备就绪时收录日志文件记录。 每天执行一次文件准备报告的过程。 文件投放时间因需要处理的客户数据总量而异。 从您将文件上传到Audience Manager到数据可供报告和激活之间，您应该预计最长等待48小时。 |

>[!MORELIKETHIS]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)

