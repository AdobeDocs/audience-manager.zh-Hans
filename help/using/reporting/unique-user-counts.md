---
description: 描述同一特征和时间段内报表之间独特用户总数的变化。
seo-description: 描述Adobe Audience Manager中相同特征和时间段的独特用户总数变化情况
seo-title: 在AAM中计算重叠和常规报告中的唯一用户
solution: Audience Manager
title: 在重叠和常规报告中计算唯一用户
uuid: 450f6a8c-f363-43de-b2 d8-3a156 f14 ee
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

本页描述同一特征和时间段内报表之间独特用户总数的变化。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报告：唯一用户计数

重叠报告会计算用户是否有资格获得特征：

* 在所选报表的选定时间间隔内。
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* 如果他们在我们的系统中被视为活动状态(即符合任何其他特征，有ID同步等)。过去60天。

## 一般报告：唯一用户计数

在选定的时间段内，“一般”报告将网站访客视为唯一的特征。

>[!MORE_ LIKE_ This]
>
>* [交互式报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般报告](../reporting/general-reports.md#general-reports-overview)

