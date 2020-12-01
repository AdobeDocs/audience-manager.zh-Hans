---
description: 视图指定目标和时间段的出站批处理作业历史记录信息。
seo-description: 视图指定目标和时间段的出站批处理作业历史记录信息。
seo-title: 出站文件历史记录
solution: Audience Manager
title: 出站文件历史记录
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 7%

---


# 出站文件历史记录 {#outbound-file-history}

视图指定目标和时间段的出站批处理作业历史记录信息。

<!-- 

t_reports_outbound_history.xml

 -->

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![步骤结果](assets/outbound_history.png)

1. 在&#x200B;**[!UICONTROL Search for a Destination]**&#x200B;框中，开始键入并选择所需的目标。
1. 在&#x200B;**[!UICONTROL Select a Date Range]**&#x200B;框中，指定报表的开始和结束日期，然后单击&#x200B;**[!UICONTROL Apply Date Filter]**。

   ![步骤结果](assets/outbound_history_stats.png)

   下表包含与报告中的列对应的信息：

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折线图 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 数据同步文件名 </td> 
   <td colname="col2"> <p>为此目标生成的<span class="keyword">Adobe</span>的所有出站文件的列表，这些文件一起处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功 </td> 
   <td colname="col2"> <p>成功从<span class="keyword">Audience Manager</span>发送到目标的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 失败 </td> 
   <td colname="col2"> <p>无法发送到目标的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已接收记录 </td> 
   <td colname="col2"> <p>文件中生成并尝试发送到目标的记录<span class="keyword">Adobe</span>的总数。 在大多数情况下，这应该是成功文件和失败文件的总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
