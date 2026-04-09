---
description: 查看指定目标和时间期的出站批处理作业历史记录信息。
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: 出站文件历史记录
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
TQID: https://experienceleague.adobe.com/bAoUgntw3hZBsEuyPQV6yX2ftNRFV9HIv9QbierOgmA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 152
ht-degree: 1%

---

# 出站文件历史记录 {#outbound-file-history}

查看指定目标和时间期的出站批处理作业历史记录信息。

<!-- 

t_reports_outbound_history.xml

 -->

1. 单击&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**。

   ![步骤结果](assets/outbound_history.png)

1. 在&#x200B;**[!UICONTROL Search for a Destination]**&#x200B;框中，开始键入并选择所需的目标。
1. 在&#x200B;**[!UICONTROL Select a Date Range]**&#x200B;框中，指定报告的开始日期和结束日期，然后单击&#x200B;**[!UICONTROL Apply Date Filter]**。

   ![步骤结果](assets/outbound_history_stats.png)

   下表包含与报表中的列对应的信息：

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 线形图 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 数据同步文件名 </td> 
   <td colname="col2"> <p><span class="keyword"> Adobe</span>为此目标生成的所有一起处理的出站文件列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功 </td> 
   <td colname="col2"> <p>从<span class="keyword"> Audience Manager</span>成功发送到目标的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 失败 </td> 
   <td colname="col2"> <p>无法发送到目标的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已接收的记录 </td> 
   <td colname="col2"> <p>文件中生成并尝试发送到目标的记录总数<span class="keyword"> Adobe</span>。 在大多数情况下，这应该是成功文件和失败文件的总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
