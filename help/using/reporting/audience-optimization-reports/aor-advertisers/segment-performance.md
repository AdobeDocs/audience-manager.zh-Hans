---
description: “区段效果”报表会按印象和转化率比较映射的和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。
seo-description: “区段效果”报表会按印象和转化率比较映射的和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。
seo-title: 细分绩效报告
solution: Audience Manager
title: 细分绩效报告
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# 细分绩效报告{#segment-performance-report}

该报 [!UICONTROL Segment Performance] 告按印象和转化率比较映射的和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。

## 如何阅读映射的区段结果 {#read-mapped-segment-results}

映射的 [!UICONTROL Segment Performance] 报表显示您创建并发送到目标以进行定位的所有区段。报表中映射的区段的位置可以大量告诉您哪些区段表现良好以及可能需要进行一些调整的位置。

要阅读报告，它可帮助将结果分为4个部分，其中虚线（以红色表示）和下面示例报告中显示的类别。

![](assets/mapped-segment-performance.png)

示例和下表中的标签可以帮助您了解细分性能以及如何响应这些结果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>转化率高。 </p> <p>您可能能够通过增加展示次数获得更多转化率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>转化率低。 </p> <p>您可能希望避免定位这些区段。 本节中的区段非常适合与未映射的区段结果中的区段进行比较。 某些未映射的区段的性能可能高于您已定位的区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>出众的性能。 不管这些细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>转化率低，展示次数高。 </p> <p>本节中的区段表现不佳。 您可能希望将预算从这些区段转移到报表左上象限的区段中。 这有助于减少展示次数，并有助于提高右下角部分的区段转化率。 此外，将这些映射的区段与未映射的区段进行比较。 某些未映射的区段的性能可能高于您已定位的区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何阅读未映射的区段结果 {#read-unmapped-segment-results}

在报表中查看未映射的 [!UICONTROL Segment Performance] 区段是查找尚未考虑定位的新区段的极好方法。 事实上，其中某些区段的表现可能优于映射的区段。 这是因为未映射的区段必须满足要包含在此报告中的一组资格标准。 要包含在此报告中，未映射的区段必须：

* 转化率高于所有映射区段的平均值。
* 按转化率排名前100位的未映射区段。

要阅读此报告，它帮助将结果分为4个部分，虚线（以红色表示）和类别如下面的示例报告所示。

![](assets/unmapped-segment-performance.png)

在此报告中，您只需关注左上角未映射的区段。 与其他三个部分中的区段相比，这些未映射的区段显示出较高的转化率，因此印象较低。

>[!NOTE]
>
>7天和30天回顾期仅在星期日日期 **[!UICONTROL Date Through]** 可用。
