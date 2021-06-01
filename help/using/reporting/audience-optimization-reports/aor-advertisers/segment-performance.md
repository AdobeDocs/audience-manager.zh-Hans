---
description: 区段性能报表会按展示次数和转化率比较已映射和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。 在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。
seo-description: 区段性能报表会按展示次数和转化率比较已映射和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。 在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。
seo-title: 区段绩效报表
solution: Audience Manager
title: 区段绩效报表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization 报表
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# 区段绩效报表{#segment-performance-report}

[!UICONTROL Segment Performance]报表按展示次数和转化率比较已映射和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。 在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。

## 如何读取映射的区段结果{#read-mapped-segment-results}

映射的[!UICONTROL Segment Performance]报表显示您创建的所有区段，并将这些区段发送到目标进行定位。映射的区段在报表中的位置可以告诉您很多有关哪些区段表现良好以及可能需要进行一些调整的位置。

要阅读报告，它有助于将结果分为4个部分，其中包含虚线（以红色表示）和下面示例报告中显示的类别。

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
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>转化率良好。 </p> <p>通过增加展示次数，您可能能够获得更多转化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>转化率低。 </p> <p>您可能需要避免定位这些区段。 此部分中的区段非常适合与未映射的区段结果中的区段进行比较。 某些未映射的区段可能比您已定位的区段的性能更好。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>性能强劲。 不管这些区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>转化率低，展示次数高。 </p> <p>此部分中的区段表现不佳。 您可能希望将预算从这些区段转移到报表左上方象限的区段中。 这将有助于减少展示次数，并且可能有助于提高此右下角部分区段的转化率。 此外，还可将这些映射的区段与未映射的区段进行比较。 某些未映射的区段可能比您已定位的区段的性能更好。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何读取未映射的区段结果{#read-unmapped-segment-results}

在[!UICONTROL Segment Performance]报表中查看未映射的区段是查找未考虑进行定位的新区段的绝佳方法。 事实上，其中某些区段的表现可能优于映射的区段。 这是因为未映射的区段必须满足要包含在此报表中的一组资格标准。 要包含在此报表中，未映射的区段必须：

* 转化率大于所有映射区段的平均值。
* 按转化率排在前100个未映射区段中。

要阅读此报告，它有助于将结果分为4个部分，其中虚线（以红色表示）和类别显示在下面的示例报告中。

![](assets/unmapped-segment-performance.png)

在此报表中，您只想关注左上角那些未映射的区段。 与其他三个部分中的区段相比，这些未映射的区段具有较高的转化率，且展示次数较低。

>[!NOTE]
>
>7天和30天回顾时段仅适用于星期日&#x200B;**[!UICONTROL Date Through]**&#x200B;日期。
