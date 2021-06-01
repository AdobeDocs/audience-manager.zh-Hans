---
description: 描述同一特征和时间段的报表之间独特用户总数的变化。
seo-description: 描述Adobe Audience Manager中同一特征和时间段的报表之间独特用户总数的变化
seo-title: 在AAM中对重叠报表和常规报表中的独特用户进行计数
solution: Audience Manager
title: 对重叠报表和常规报表中的独特用户进行计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: 报表参考
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# 对重叠报表和常规报表中的独特用户进行计数{#counting-unique-users-in-overlap-and-general-reports}

此页面描述同一特征和时间段的报表之间独特用户总数的变化。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报表：独特用户计数

重叠报表在用户符合某个特征时会将他们计为独特用户：

* 在报表的选定时间间隔内。
* 值[生存时间](../features/traits/segment-ttl-explained.md)的时间长于报表的选定时间间隔。
* 如果在我们的系统中被视为活动特征（即，符合任何其他特征的条件，进行了ID同步等） 过去60天内。

## 一般报告：独特用户计数

如果网站访客在选定的时间段内符合该特征，则常规报表会将其计为独特访客。

>[!MORELIKETHIS]
>
>* [交互式报表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
* [常规报表](../reporting/general-reports.md#general-reports-overview)

