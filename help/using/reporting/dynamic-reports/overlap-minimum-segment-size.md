---
description: 描述重叠报表更新流程所需的区段大小和创建时间要求。
seo-description: 描述重叠报表更新流程所需的区段大小和创建时间要求。
seo-title: 重叠报表更新计划和最小区段大小
solution: Audience Manager
title: 重叠报表更新计划和最小区段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: 重叠报表
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# 重叠报表：更新计划和最小区段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

描述重叠报表更新流程所需的特征和区段大小以及创建时间要求。

## 更新计划和要求{#update-schedule}

[!UICONTROL Overlap] 每周日的报告更新。报表预处理从星期六开始。 这会影响周一重叠报表中新区段或现有区段的显示方式。 要包含在重叠报表中：

* 在过去14天内，区段必须至少包含70,000个实时用户总数。
* 在过去14天内，特征必须包含28,000 [唯一特征实现](/help/using/features/traits/trait-and-segment-qualification-reference.md)。
* 必须在UTC星期四上午12点之前（每周重叠报告更新流程开始前2天）创建区段。
* 您的公司必须是完整[!DNL Audience Manager]客户。 请联系您的[!DNL Audience Manager]顾问或客户服务部门以了解更多信息。

## 区段大小和/或创建时间影响报告{#segment-size}

如果您在某个[!UICONTROL Overlap]报表中未看到区段，则可能是因为区段不符合这些最低要求。

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
   <td colname="col2"> <p>假设您在UTC星期四上午12点之前创建了一个区段，但它包含的实时用户总数少于70,000。 此区段在满足用户阈值要求之前不会显示在<span class="wintitle">重叠报表</span>中。 另请注意，该区段必须在星期四截止期间或之前满足所需的用户计数。 如果不符合每周截止日期，则在即将运行的星期日数据运行后的一周内，该区段将显示在<span class="wintitle">重叠报表</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段创建太迟</b> </p> </td> 
   <td colname="col2"> <p>假设您在星期五创建了一个区段，它包含70,000个以上实时用户。 此区段不会在下周的<span class="wintitle">重叠报表</span>中显示，因为它是在报表更新期前不到2天创建的。 但是，在下一周更新后，该区段将显示在<span class="wintitle">重叠报表</span>中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特征到特征重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特征重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

