---
description: 描述重叠报告更新流程所需的区段大小和创建时间要求。
seo-description: 描述重叠报告更新流程所需的区段大小和创建时间要求。
seo-title: 重叠报告更新计划和最小区段大小
solution: Audience Manager
title: 重叠报告更新计划和最小区段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 重叠报告：更新计划和最小区段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

描述重叠报告更新流程所需的区段大小和创建时间要求。

## 更新计划和要求 {#update-schedule}

[!UICONTROL Overlap] 报道每周日更新。 报表预处理从星期六开始。 这会影响周一的重叠报告中新区段或现有区段的显示方式。 要包含在重叠报告中，请执行以下操作：

* 在过去14天内，区段必须至少包含70,000个实时用户。 阅读有关特征和 [区段的最低唯一访客要求的更多信息](../../reporting/report-sampling.md#data-sampling-ratio)。
* 必须在UTC星期四上午12点（每周重叠报告更新过程开始前2个完整天）之前创建区段。
* 您的公司必须是完整客 [!DNL Audience Manager] 户。 请联系您的 [!DNL Audience Manager] 顾问或客户关怀以了解更多信息。

## 区段大小和／或创建时间影响报表 {#segment-size}

如果您在其中一份报告中未看到 [!UICONTROL Overlap] 区段，则可能是因为区段不符合这些最低要求。

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
   <td colname="col2"> <p>假设您在UTC星期四凌晨12点之前创建了一个区段，但它包含的实时用户总数少于70,000。 此区段在满足用户阈值要求 <span class="wintitle"> 之前</span> ，不会显示在重叠报告中。 另外，该区段必须在星期四截止期间之前或之前满足所需的用户计数。 如果不符合每周的截止期限，则区段将显示在即将运行的周日数据后一周的“重 <span class="wintitle"> 叠报告</span> ”中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段创建太迟</b> </p> </td> 
   <td colname="col2"> <p>假设您在星期五创建了一个区段，它包含70,000多个实时用户。 此区段不会在下周的重叠报 <span class="wintitle"> 表中显示</span> ，因为它是在报表更新期前不到2天创建的。 但是，在下一周更新后，该区段将显示在 <span class="wintitle"> 重叠报表</span> 中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [特质到特质重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特质重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

