---
description: 描述相同特征和时间段的报表之间唯一用户总数的变化情况。
seo-description: 描述Adobe Audience manager中相同特征和时间段的报表之间唯一用户总数的变化情况
seo-title: 在AAM中计算重叠和常规报告中的唯一用户数
solution: Audience Manager
title: 对重叠和一般报告中的唯一用户计数
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 对重叠和一般报告中的唯一用户计数{#counting-unique-users-in-overlap-and-general-reports}

本页描述相同特征和时间段的报表之间唯一用户总数的变化情况。

<!-- 

c_unique_user_counts.xml

 -->

## 重叠报告：唯一用户数

重叠报告在用户符合某个特征时将其计为唯一：

* 在报告的选定时间间隔内。
* 该值的 [实时时间值比报告的选定时间间隔长](../features/traits/segment-ttl-explained.md) 。
* 如果在我们的系统中它们被视为活动（即，符合任何其他特征的条件，具有ID同步等）60天之内。

## 一般报告：唯一用户数

“一般信息”报表将站点访问者计为唯一访客，如果他们在选定的时间段内符合该特征。

>[!MORELIKETHIS]
>
>* [交互式报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般报告](../reporting/general-reports.md#general-reports-overview)

