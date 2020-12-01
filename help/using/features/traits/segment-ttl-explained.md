---
description: 特征生存时间(TTL)间隔如何影响段成员关系。
seo-description: 特征生存时间(TTL)间隔如何影响段成员关系。
seo-title: 细分和特质的有效时间说明
solution: Audience Manager
title: 细分生存时间说明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# 区段和特征存留期说明 {#segment-time-to-live-explained}

特征[!UICONTROL time-to-live]([!DNL TTL])间隔如何影响区段成员关系。

<!-- segment-ttl-explained.xml -->

## 生存时间

[!DNL TTL] 定义在最后一个特征资格访客后，站点事件在区段中保留的时间。[!DNL TTL] 是针对特征而非区段设置的。访客如果在[!DNL TTL]间隔结束前没有资格获得某个特征，则会从段中掉出。 新特征的默认值[!DNL TTL]为120天。 设置为0天时，特征永不过期。 [在特征创](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 建界面的部分创建或编辑特 [!UICONTROL Advanced Options] 征时设置TTL值。

### 1天TTL已解释

当将[!DNL TTL]设置为1天时，TTL计时器将开始特征实现后的第二天，而不计算特征实现日的剩余时间。

Audience Manager根据以下公式计算具有1天[!DNL TTL]的特征的[!DNL TTL]过期时间：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**:1:00,1天 [!DNL UTC]内发现一个特质 [!DNL TTL]。[!DNL TTL] 24 + 24 - 1 = 47小时后过期。
* **示例2**:23:00,1 [!DNL UTC]天的特质 [!DNL TTL]。[!DNL TTL] 24 + 24 - 23 = 25小时后过期。

## [!DNL TTL] 和从区段中删除

如果用户在[!DNL TTL]时间间隔内没有资格获得其任何特征，则该用户会从区段中掉出。 例如，如果您有一个1特征段，其长度为30天[!DNL TTL]，则如果用户未在接下来的30天内再次符合该特征的条件，则该用户将从该段中删除。

![](assets/ttl-explained.png)

## [!DNL TTL] 和细分续订

[!DNL TTL]将重置，如果用户符合该区段在[!DNL TTL]期间内的特征，则该用户将保留在区段中。 此外，由于大多数区段包含具有其自己的[!DNL TTL]时间间隔的多个特征，因此用户可以保留在区段中，并重置[!DNL TTL]时间间隔，只要它们继续符合与区段关联的任何特征的条件。

例如，假设您有由特征A（30天[!DNL TTL]）和特征B（15天[!DNL TTL]）组成的区段1。 假设访客仅对每个特征进行一次资格鉴定，下图将列出[!DNL TTL]续订过程和段内总持续时间。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL与第三方TTL设置无关

请记住，在[!DNL Audience Manager]像素上设置的[!DNL TTL]与在第三方（[!DNL DSP]s、广告网络等）使用的其他像素上设置的[!DNL TTL]独立运行。

>[!MORELIKETHIS]
>
>* [设置特征到期间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

