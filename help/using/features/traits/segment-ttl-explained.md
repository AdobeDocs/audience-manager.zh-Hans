---
description: 特征存留期(TTL)间隔如何影响区段成员资格。
seo-description: 特征存留期(TTL)间隔如何影响区段成员资格。
seo-title: 区段和特征存留期说明
solution: Audience Manager
title: 区段存留期说明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 特征
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# 区段和特征存留期说明 {#segment-time-to-live-explained}

特征[!UICONTROL time-to-live]([!DNL TTL])间隔如何影响区段成员资格。

<!-- segment-ttl-explained.xml -->

## 生存时间

[!DNL TTL] 定义网站访客在上次特征鉴别事件后在区段中停留的时长。[!DNL TTL] 是针对特征而非区段设置的。如果访客在[!DNL TTL]间隔结束前不符合某个特征的条件，则访客会从区段中流失。 新特征的默认值[!DNL TTL]为120天。 如果设置为0天，则特征永不过期。 [在特征创](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 建界面的部分中创建或编辑特 [!UICONTROL Advanced Options] 征时，设置TTL值。

### 1天TTL说明

将[!DNL TTL]设置为1天时，TTL计时器将在特征实现后的第二天启动，而不会计算特征实现日中剩余的小时数。

Audience Manager根据以下公式计算具有1天[!DNL TTL]的特征的[!DNL TTL]过期时间：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**:特征在1:00实 [!DNL UTC]现，1天 [!DNL TTL]。[!DNL TTL] 24 + 24 - 1 = 47小时后过期。
* **示例2**:特征在23:00实 [!DNL UTC]现，1天 [!DNL TTL]。[!DNL TTL] 24 + 24 - 23 = 25小时后过期。

## [!DNL TTL] 和从区段中删除

如果用户不符合[!DNL TTL]间隔内的任何特征，则会从区段中流失。 例如，如果您有一个30天[!DNL TTL]的1个特征区段，如果用户在接下来的30天内不再符合该特征，则该用户将从该区段中退出。

![](assets/ttl-explained.png)

## [!DNL TTL] 和区段续订

[!DNL TTL]会重置，如果用户符合该区段在[!DNL TTL]时段内的特征，则用户会保留在区段中。 此外，由于大多数区段包含具有各自[!DNL TTL]间隔的多个特征，因此用户可以保留在区段中，并重置[!DNL TTL]间隔，前提是它们继续符合与区段关联的任何特征。

例如，假设您的区段1由特征A（30天[!DNL TTL]）和特征B（15天[!DNL TTL]）组成。 假设访客仅符合每个特征一次，下图概述了[!DNL TTL]续订流程和区段内总持续时长。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL与第三方TTL设置无关

请记住，在[!DNL Audience Manager]像素上设置的[!DNL TTL]独立于在第三方使用的其他像素（[!DNL DSP]s、广告网络等）上设置的[!DNL TTL]操作。

>[!MORELIKETHIS]
>
>* [设置特征过期间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

