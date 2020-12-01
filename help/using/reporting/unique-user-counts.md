---
description: 描述同一特征和时间段的报表之间唯一用户总数的变化。
seo-description: 描述Adobe Audience Manager相同特征和时间段报表之间唯一用户总数的变化
seo-title: 对AAM中重叠和一般报告中的唯一用户进行计数
solution: Audience Manager
title: 对重叠报表和常规报表中的独特用户进行计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 10%

---


# 对重叠报表和常规报表中的独特用户进行计数{#counting-unique-users-in-overlap-and-general-reports}

此页描述相同特征和时间段的报表之间唯一用户总数的变化。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报告：唯一用户计数

重叠报告在用户符合某个特征时将其视为唯一：

* 在报告的选定时间间隔内。
* 其值[live](../features/traits/segment-ttl-explained.md)比报告的所选时间间隔长。
* 如果在我们的系统中它们被视为活动（即，符合任何其他特征的条件，具有ID同步等） 60天内。

## 一般报告：唯一用户计数

如果站点访客符在所选时间段内符合特征，则“常规”报表会将其计为唯一。

>[!MORELIKETHIS]
>
>* [交互式报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [常规报表](../reporting/general-reports.md#general-reports-overview)

