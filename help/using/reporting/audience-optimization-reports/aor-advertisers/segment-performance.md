---
description: 区段性能报表按展示次数和转化率比较映射的区段和未映射的区段。 映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较报表内和报表之间的这些不同区段类型有助于优化现有促销活动，并查找您可能希望发送到目标位置以进行定位的被忽略的区段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 区段绩效报表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# 区段绩效报表{#segment-performance-report}

[!UICONTROL Segment Performance]报表按展示次数和转化率比较已映射和未映射的区段。 映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较报表内和报表之间的这些不同区段类型有助于优化现有促销活动，并查找您可能希望发送到目标位置以进行定位的被忽略的区段。

## 如何读取映射的区段结果 {#read-mapped-segment-results}

映射的[!UICONTROL Segment Performance]报表显示了您创建并发送到目标进行定位的所有区段。您的映射区段在报表中的位置可以告知您关于哪些区段表现良好以及在何处您可能需要做出一些调整的详细信息。

要阅读报告，它有助于将结果分为4个部分，其中虚线（红色）与下面示例报告中所示的类别。

![](assets/mapped-segment-performance.png)

示例和下表中的标签可帮助您了解区段性能以及如何响应这些结果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>良好的转化率。 </p> <p>通过增加展示次数，您可能会获得更多转化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>低转化率。 </p> <p>您可能需要避免定位这些区段。 此部分中的区段非常适用于与未映射区段结果中的区段进行比较。 某些未映射区段的性能可能会优于您已定位的区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>性能强劲。 保持这些区段不变。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>低转化率和高展示次数。 </p> <p>此部分中的区段表现不佳。 您可能希望将预算从这些区段转移到报表左上象限中的区段。 这有助于减少展示次数，并且有助于提高此右下角部分中区段的转化率。 此外，将这些映射的区段与未映射的区段进行比较。 某些未映射区段的性能可能会优于您已定位的区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何读取未映射的区段结果 {#read-unmapped-segment-results}

查看[!UICONTROL Segment Performance]报表中的未映射区段是查找尚未考虑定位的新区段的好方法。 事实上，其中某些区段的性能可能会优于您的映射区段。 这是因为未映射的区段必须满足一组限定条件才能包含在此报表中。 要包含在此报表中，未映射的区段必须：

* 其转化率大于所有映射区段的平均数。
* 按转化率排在前100个未映射区段中。

要阅读此报告，它有助于将结果分为4个部分，其中虚线（红色）和类别显示在下面的示例报告中。

![](assets/unmapped-segment-performance.png)

在此报表中，您只想查看左上角的那些未映射区段。 与其他三个部分中的区段相比，这些未映射区段在低展示次数下表现出高转化率。

>[!NOTE]
>
>7天和30天回顾期间仅适用于周日&#x200B;**[!UICONTROL Date Through]**&#x200B;日期。
