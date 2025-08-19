---
description: 特征生存时间(TTL)间隔对区段成员资格有何影响。
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: 区段存留时间说明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 区段和特征存留期说明 {#segment-time-to-live-explained}

特征[!UICONTROL time-to-live] ([!DNL TTL])间隔如何影响区段成员资格。

<!-- segment-ttl-explained.xml -->

## 存留时间

[!DNL TTL]定义网站访客在最后一个特征资格事件后保留在区段中的时间。 [!DNL TTL]是针对特征而非区段设置的。 如果访客在[!DNL TTL]间隔结束前没有资格访问某个特征，则会从区段中移除。 新特征的默认[!DNL TTL]为120天。 如果设置为0天，则特征永不过期。 在特征创建界面的[部分中创建或编辑特征时，](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)设置TTL值[!UICONTROL Advanced Options]。

### 1天TTL解释

将[!DNL TTL]设置为1天时，TTL计时器将在特征实现后的第二天启动，而不计算特征实现日期中剩余的小时数。

Audience Manager根据以下公式计算1天[!DNL TTL]的特征的[!DNL TTL]过期时间：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**：特征在1:00 [!DNL UTC]实现，包含1天[!DNL TTL]。 [!DNL TTL]将在24 + 24 - 1 = 47小时后过期。
* **示例2**：在23:00 [!DNL UTC]实现的特征，包含1天[!DNL TTL]。 [!DNL TTL]将在24 + 24 - 23 = 25小时后过期。

## [!DNL TTL]并退出区段

如果用户在[!DNL TTL]间隔内没有资格获得任何特征，则会退出区段。 例如，如果您有一个包含30天[!DNL TTL]的1个特征区段，那么如果用户在未来30天内再次不符合该特征的资格，则将退出该区段。

![](assets/ttl-explained.png)

## [!DNL TTL]和区段续订

如果[!DNL TTL]在[!DNL TTL]时段内符合区段特征资格，则会重置，并且用户将保留在区段中。 此外，由于大多数区段包含多个具有自己[!DNL TTL]间隔的特征，因此用户可以保留在区段中，并重置[!DNL TTL]间隔，前提是他们保留与该区段关联的任何特征的资格。

例如，假设您的区段1由特征A （30天[!DNL TTL]）和特征B （15天[!DNL TTL]）组成。 假设访客仅符合每个特征一次资格，下图概述了[!DNL TTL]续订流程和总区段内持续时间。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL独立于第三方TTL设置

请记住，在[!DNL TTL]像素上设置的[!DNL Audience Manager]独立于在第三方（[!DNL TTL]、广告网络等）使用的其他像素上设置的[!DNL DSP]运行。

>[!MORELIKETHIS]
>
>* [设置特征过期时间间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
