---
description: 描述同一特征和时间段的不同报表之间的独特用户总数差异。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 对重叠报表和常规报表中的独特用户进行计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 1%

---

# 对重叠报表和常规报表中的独特用户进行计数{#counting-unique-users-in-overlap-and-general-reports}

此页面描述了同一特征和同一时间段内不同报表之间的独特用户总数差异。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报表：独特用户计数

当用户符合某个特征时，重叠报表会将其计为唯一用户：

* 在报告的选定时间间隔内。
* 其存留时间[值为](../features/traits/segment-ttl-explained.md)且长于报告的选定时间间隔。
* 如果在过去60天内他们被视为在我们的系统中处于活动状态（即，符合任何其他特征的条件，具有ID同步等），

## 常规报表：独特用户计数

如果网站访客在选定时间段内符合特征条件，则常规报表会将他们计为独特访客。

>[!MORELIKETHIS]
>
>* [交互式报表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [常规报表](../reporting/general-reports.md#general-reports-overview)
