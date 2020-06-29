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

特征( [!UICONTROL time-to-live] )间[!DNL TTL]隔如何影响段成员关系。

<!-- segment-ttl-explained.xml -->

## 生存时间

[!DNL TTL] 定义在最后一个特征资格访客后，站点事件在区段中保留的时间。 [!DNL TTL] 是针对特征而非区段设置的。Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. 新特 [!DNL TTL] 征的默认值为120天。 设置为0天时，特征永不过期。 [在特征创建界](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 面的部分创建或编辑特征 [!UICONTROL Advanced Options] 时，设置TTL值。

### 1天TTL已解释

当设置为 [!DNL TTL] 1天时，TTL定时器在特征实现后的第二天开始，而不计算特征实现日的剩余时间。

Audience Manager根 [!DNL TTL] 据以下公式计算1 [!DNL TTL] 天特征的过期时间：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**: 1:00,1天 [!DNL UTC]内发现一个特质 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 1 = 47小时后过期。
* **示例2**: 23:00,1 [!DNL UTC]天的特质 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 23 = 25小时后过期。

## [!DNL TTL] 和从区段中删除

如果用户在时间间隔内没有资格获得其任何特征，则会从区段中 [!DNL TTL] 掉出。 例如，如果您有一个1特征段，其长度为30 [!DNL TTL]天，则如果用户在接下来的30天内不再符合该特征的资格，则该用户将从该段中退出。

![](assets/ttl-explained.png)

## [!DNL TTL] 和细分续订

如 [!DNL TTL] 果用户符合段内该段特征的条件，则会重置该段，并且该用户仍保留在段 [!DNL TTL] 中。 此外，由于大多数区段包含具有其自己的时间间隔的 [!DNL TTL] 多个特征，因此用户可以保留在区段中，并重置 [!DNL TTL] 该间隔，前提是他们必须保持与区段关联的任何特征的资格。

例如，假设您有由特征A（30天）和特征B(15 [!DNL TTL]天)组成的区段1 [!DNL TTL]。 假设访客仅对每个特征进行一次资格鉴定，下图将概括介绍续订 [!DNL TTL] 过程和总的段内持续时间。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL与第三方TTL设置无关

请记住， [!DNL TTL] 像素上的 [!DNL Audience Manager] 设置与第三方( [!DNL TTL] 广告网络等)使用的其他像素上[!DNL DSP]的设置独立运行。

>[!MORELIKETHIS]
>
>* [设置特征到期间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

