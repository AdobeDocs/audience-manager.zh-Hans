---
description: 介绍重叠报告更新过程所需的区段大小和创建时间要求。
seo-description: 介绍重叠报告更新过程所需的区段大小和创建时间要求。
seo-title: 重叠报告更新计划和最小区段大小
solution: Audience Manager
title: 重叠报告更新计划和最小区段大小
uuid: 35c1cb39-e28 d-4d20-88c-5ff4 fe154 e9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

介绍重叠报告更新过程所需的区段大小和创建时间要求。

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] 报告将在周日更新。报告预处理从星期六开始。这会影响星期一或现有区段在星期一重叠报告中的显示方式。要包含在重叠报告中，请执行以下操作：

* 在过去14天内，区段必须至少包含70,000名实时用户。Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* 区段必须在星期四12AM UTC之前(每周重叠报告更新流程开始前的两天)之前创建。
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

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
   <td colname="col2"> <p>假设您在星期四12AM UTC之前创建了一个区段，但它包含的实时用户少于70,000。This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. 请注意，区段必须满足在星期四截止日期或星期四截止日期之前的要求。If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>创建的区段太迟</b> </p> </td> 
   <td colname="col2"> <p>假设您在星期五创建了一个细分，它包含70,000多个实时用户。This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [特质到特质重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特质重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

