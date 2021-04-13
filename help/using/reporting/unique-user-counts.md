---
description: 描述相同特征和时间段的报表之间唯一用户总数的变化。
seo-description: 描述Adobe Audience Manager中相同特征和时间段的报表之间唯一用户总数的变化
seo-title: 对AAM中重叠和一般报表中的唯一用户计数
solution: Audience Manager
title: 对重叠报表和常规报表中的独特用户进行计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: 报告参考
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 10%

---

# 对重叠报表和常规报表中的独特用户进行计数{#counting-unique-users-in-overlap-and-general-reports}

本页描述相同特征和时间段的报表之间唯一用户总数的变化。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报表：唯一用户计数

重叠报表在用户符合某个特征时将其计为唯一：

* 在报表的选定时间间隔内。
* 其值[到活时间](../features/traits/segment-ttl-explained.md)比报表的选定时间间隔长。
* 如果在我们的系统中，它们被视为活动（即，符合任何其他特征的条件，具有ID同步等） 60天之内。

## 一般报告：唯一用户计数

如果站点访客在选定时间段内符合特征，则“常规”报表会将其计为唯一。

>[!MORELIKETHIS]
>
>* [交互式报表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [常规报表](../reporting/general-reports.md#general-reports-overview)

