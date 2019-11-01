---
description: Audience manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节中的内容介绍这些时间间隔对Audience manager帐户的影响。 此外，此处描述的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-description: Audience manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节中的内容介绍这些时间间隔对Audience manager帐户的影响。 此外，此处描述的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。
seo-title: 数据交付和文件处理时间对报告的影响
solution: Audience Manager
title: 数据交付和文件处理时间对报告的影响
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 数据交付和文件处理时间对报告的影响{#how-data-delivery-and-file-processing-times-affect-reports}

Audience manager每天都会收到大量数据。 这会影响处理数据和生成报告结果所花费的时间。 本节中的内容介绍这些时间间隔对Audience manager帐户的影响。 此外，此处描述的时间范围和计划只是一般准则。 这些时间表不构成与数据交付相关的服务级别协议(SLA)或承诺。 Adobe保留随时更改时间范围和计划的权利，恕不另行通知。

## 报告编号 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出并描述了一般报告和实时报告中的时间间隔。

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>实时数据</b> </p> </td> 
   <td colname="col2"> <p> 今天的实时数字是从昨天开始的00:00到23:59:59. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>一般报告数据</b> </p> </td> 
   <td colname="col2"> <p>一般报告中的 <a href="../reporting/general-reports.md#general-reports-overview"> 数据取决于</a> ，其他作业进程是否成功完成以及特定日期收到的数据量。 大多数情况下，一般 <span class="wintitle"> 报告数据应在</span> 18:00 UTC前每天更新。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 入站和出站文件传输 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 根据本节所述的计划， [!UICONTROL Server-to-Server (S2S)] 处理和发送入站和出站文件传输。 鉴于这些时间表和中断时间，您可能会发现实时区段数与总区段数之间的新区段存在差异。

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>入站文件摄取（脱机数据）</b> </p> </td> 
   <td colname="col2"> <p>文件处理每天执行两次。 这些过程会收集数据并准备好交付。 </p> <p>文件交付时间因需要处理的客户数据总量而异。 在文件上传到 <span class="keyword"></span> Audience Manager之后，您应该预计在数据可用于报告和激活之前，最长等待48小时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>出站（导出）文件</b> </p> </td> 
   <td colname="col2"> <p>文件处理和交付每天进行一次，大约在UTC的14:00。 请记住，处理和交付会受这些文件的总数和大小的影响。 在某些情况下，文件处理可能会延迟24小时。 发生这种情况时， <span class="keyword"> Audience Manager</span> 将在特定日期发送2个文件，而不是发送1个文件。 在Audience Manager必须完全停止处理文件的罕见情况下 <span class="keyword"></span> ，我们会通知客户。 鉴于这些情况，很难估计出站数据的传送时间。 </p> <p>要确定您是否收到完整的文件集，请检查时间戳并查找任何缺少的日期。 这是一个13位数的UNIX UTC时间戳，它记录文件创建的时间。 请参 <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> 阅实时出站数据传输</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)

