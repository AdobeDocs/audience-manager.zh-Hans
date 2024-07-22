---
description: 描述重叠报表更新流程所需的区段大小和创建时间要求。
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 重叠报表更新计划和最小区段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# 重叠报表：更新计划和最小区段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

描述重叠报表更新流程所需的特性和区段大小以及创建时间要求。

## 更新计划和要求 {#update-schedule}

[!UICONTROL Overlap]报告在星期日每周更新。 报表预处理从周六开始。 这会影响新区段或现有区段在星期一在重叠报表中的显示方式。 要包含在重叠报表中，请执行以下操作：

* 区段必须包含过去14天内至少70,000位实时用户。
* 一个特征在过去14天内必须包含28,000个[独特特征实现](/help/using/features/traits/trait-and-segment-qualification-reference.md)。
* 区段必须在UTC星期四凌晨12点（每周重叠报告更新过程开始前2个整天）之前创建。
* 您的公司必须是完整[!DNL Audience Manager]客户。 请联系您的[!DNL Audience Manager]顾问或客户关怀团队以了解更多信息。

## 区段大小和/或创建时间影响报表 {#segment-size}

如果您在某个[!UICONTROL Overlap]报表中没有看到区段，可能是因为该区段不符合这些最低要求。

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
   <td colname="col2"> <p>假设您在UTC星期四凌晨12点之前创建一个区段，但它包含的实时用户总数不到70,000个。 在符合用户阈值要求之前，此区段不会出现在<span class="wintitle">重叠报表</span>中。 另请注意，区段必须满足在星期四截止日期之前或在该日期之前计算出的所需用户数。 如果不符合每周截止日期，则该区段将在即将到来的星期日数据运行后的一周内显示在<span class="wintitle">重叠报表</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段创建太晚</b> </p> </td> 
   <td colname="col2"> <p>假设您在星期五创建一个区段，它总共包含70,000多个实时用户。 该区段在下一周不会出现在<span class="wintitle">重叠报表</span>中，因为它是在报表更新期开始前不到2天创建的。 但是，在下一次每周更新后，该区段将显示在<span class="wintitle">重叠报表</span>中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特征到特征重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特征重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
