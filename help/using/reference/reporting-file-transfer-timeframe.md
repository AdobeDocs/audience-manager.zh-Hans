---
description: Audience Manager每天接收大量数据。这会影响处理数据和生成报告结果所花费的时间。本节中的内容介绍了这些时间间隔对Audience Manager帐户的影响。此外，此处所述的时间范围和时间表仅为指导方针。这些计划不构成服务级协议(SLA)或与数据交付相关的承诺。Adobe保留随时更改时间范围和时间表的权利，恕不另行通知。
seo-description: Audience Manager每天接收大量数据。这会影响处理数据和生成报告结果所花费的时间。本节中的内容介绍了这些时间间隔对Audience Manager帐户的影响。此外，此处所述的时间范围和时间表仅为指导方针。这些计划不构成服务级协议(SLA)或与数据交付相关的承诺。Adobe保留随时更改时间范围和时间表的权利，恕不另行通知。
seo-title: 数据交付和文件处理时间影响报告
solution: Audience Manager
title: 数据交付和文件处理时间影响报告
uuid: 4b975512-f67 e-4749-a7 ef-16841559782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天接收大量数据。这会影响处理数据和生成报告结果所花费的时间。本节中的内容介绍了这些时间间隔对Audience Manager帐户的影响。此外，此处所述的时间范围和时间表仅为指导方针。这些计划不构成服务级协议(SLA)或与数据交付相关的承诺。Adobe保留随时更改时间范围和时间表的权利，恕不另行通知。

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出了我们一般和实时报告中的时间间隔并描述了时间间隔。

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
   <td colname="col2"> <p> 今天的实时数字在昨天为00：00至23：59：59UTC。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>一般报告数据</b> </p> </td> 
   <td colname="col2"> <p><a href="../reporting/general-reports.md#general-reports-overview"> 一般报告中的数据</a> 取决于其他作业流程的成功完成以及特定天收到的数据量。Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 按照本节所述的计划，处理和发送入站和出站 [!UICONTROL Server-to-Server (S2S)] 文件传输。鉴于这些计划和截止时间，您可能会发现实时细分编号和总细分编号之间存在新的细分偏差。

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>入站文件摄取(脱机数据)</b> </p> </td> 
   <td colname="col2"> <p>文件处理每天执行两次。这些程序收录数据并准备分发。 </p> <p>文件交付时间因需要处理的客户数据总量而有所不同。You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>出站(导出)文件</b> </p> </td> 
   <td colname="col2"> <p>文件处理和交付每天发生一次，约14：00UTC。请记住，处理和交付受这些文件的总数和大小的影响。在某些情况下，最长可能会有24小时的文件处理延迟。When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. 在这些情况下，很难评估出站数据的交付时间。 </p> <p>要确定您是否已收到一组完整的文件，请检查时间戳并查找任何缺少的天数。这是一个13位数的UNIX UTC时间戳，用于记录创建文件的时间。See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)

