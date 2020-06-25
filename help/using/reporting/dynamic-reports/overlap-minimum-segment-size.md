---
description: 描述重叠报告更新流程所需的区段大小和创建时间要求。
seo-description: 描述重叠报告更新流程所需的区段大小和创建时间要求。
seo-title: 重叠报表更新计划和最小区段大小
solution: Audience Manager
title: 重叠报表更新计划和最小区段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---


# 重叠报表：更新计划和最小区段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

描述重叠报告更新流程所需的区段大小和创建时间要求。

## 更新计划和要求 {#update-schedule}

[!UICONTROL Overlap] 报告每周在周日更新。 报表预处理从星期六开始。 这会影响周一重叠报告中新区段或现有区段的显示方式。 要包含在重叠报告中：

* 在过去14天内，区段必须至少包含70,000个实时用户总数。 阅读有关特 [征和区段的最低唯一访客要求的更多信息](../../reporting/report-sampling.md#data-sampling-ratio)。
* 在UTC周四上午12点之前（每周重叠报告更新流程开始前2天）必须已创建区段。
* 您的公司必须是完整客 [!DNL Audience Manager] 户。 请联系您的 [!DNL Audience Manager] 顾问或客户关怀以了解更多信息。

## 区段大小和／或创建时间影响报告 {#segment-size}

如果您在其中一个报告中未看到 [!UICONTROL Overlap] 区段，可能是因为该区段不符合这些最低要求。

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>区段大小太小</b> </p> </td> 
   <td colname="col2"> <p>假设您在UTC周四的凌晨12点之前创建了一个区段，但它包含的实时用户总数不到70,000。 此区段在满足用户阈值 <span class="wintitle"> 要求前</span> ，才会显示在重叠报表中。 另外，该区段必须在星期四截止期之前或之前达到所需的用户计数。 如果不符合每周截止日期，则在即将到来的周日数据运行后的一 <span class="wintitle"> 周内</span> ，该区段将显示在“重叠报告”中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段创建太迟</b> </p> </td> 
   <td colname="col2"> <p>假设您在星期五创建了一个区段，它包含70,000个以上实时用户。 此区段在下周的重叠报 <span class="wintitle"> 表中不会显示</span> ，因为它是在报表更新期前不到2天创建的。 但是，在下一周更新后，该区段 <span class="wintitle"> 将显示在</span> “重叠报告”中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特征到特征重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特征重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

