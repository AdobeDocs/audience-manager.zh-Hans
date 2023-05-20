---
description: 說明重疊報表更新程式所需的區段大小和建立時間需求。
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 重疊報表更新排程和最小區段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# 重叠报表：更新计划和最小区段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

說明重疊報表更新程式所需的特徵和區段大小以及建立時間需求。

## 更新排程和需求 {#update-schedule}

[!UICONTROL Overlap] 報告會在每週日更新。 報表預先處理於星期六開始。 這會影響新區段或現有區段在星期一重疊報表中的顯示方式。 要包含在重疊報表中：

* 區段在過去14天內必須至少包含70,000位即時使用者。
* 特徵必須包含28,000 [不重複特徵實現](/help/using/features/traits/trait-and-segment-qualification-reference.md) 過去14天內。
* 區段必須在UTC星期四上午12點（每週重疊報告更新程式開始前2整天）之前建立。
* 貴公司必須為完整版 [!DNL Audience Manager] 客戶。 請聯絡您的 [!DNL Audience Manager] 諮詢顧問或客戶服務，以瞭解更多資訊。

## 區段大小和/或建立時間會影響報告 {#segment-size}

如果您在其中一個欄位中看不到區段， [!UICONTROL Overlap] 報表，可能是因為區段不符合這些最低需求。

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>區段大小太小</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期四UTC凌晨12:00之前建立區段，但包含少於70,000名即時使用者。 此區段不會出現在 <span class="wintitle"> 重疊報表</span> 直到符合使用者臨界值要求為止。 另外請注意，該區段必須符合星期四截止期間或之前的必要使用者計數。 如果不符合每週的截止日期，則該區段會顯示在 <span class="wintitle"> 重疊報表</span> 適用於即將執行的星期日資料執行後的一週。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段建立得太晚</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立區段，而區段總共包含70,000多名即時使用者。 此區段不會出現在 <span class="wintitle"> 重疊報表</span> 因為是在報告更新期間之前不到2天建立的，所以會保留下一週。 不過，區段會顯示在 <span class="wintitle"> 重疊報表</span> 在下一次每週更新之後。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特征到特征重叠报表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [区段到特征重叠报表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [区段到区段重叠报表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

