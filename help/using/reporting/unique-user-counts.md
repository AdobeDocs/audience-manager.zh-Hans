---
description: 說明相同特徵和時段報告之間的不重複使用者總數差異。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 对重叠报表和常规报表中的独特用户进行计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 12%

---

# 对重叠报表和常规报表中的独特用户进行计数{#counting-unique-users-in-overlap-and-general-reports}

此頁面說明相同特徵和時段報表之間的不重複使用者總數差異。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：不重複使用者計數

重疊報表會將符合特徵資格的使用者計為不重複：

* 在報表的選取時間間隔內。
* 這有 [存留時間](../features/traits/segment-ttl-explained.md) 值大於報告的所選時間間隔。
* 如果系統將這些特徵視為作用中（亦即符合任何其他特徵的資格、具有ID同步等） 過去60天內。

## 一般報告：不重複使用者計數

如果網站訪客在選取的時段符合特徵資格，「一般」報表會將網站訪客計為不重複。

>[!MORELIKETHIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [常规报表](../reporting/general-reports.md#general-reports-overview)

