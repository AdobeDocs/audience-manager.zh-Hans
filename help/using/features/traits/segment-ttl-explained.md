---
description: 特征生存时间(TTL)间隔如何影响段成员关系。
seo-description: 特征生存时间(TTL)间隔如何影响段成员关系。
seo-title: 细分和特质的有效时间说明
solution: Audience Manager
title: 细分有效时间说明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 17906734132813984437216f2a6cbc1c7bf14937

---


# 细分和特征的生效时间说明 {#segment-time-to-live-explained}

特征( [!UICONTROL time-to-live][!DNL TTL])间隔如何影响区段成员关系。

<!-- segment-ttl-explained.xml -->

## 停留时间

[!DNL TTL] 定义网站访客在最后一个特征资格事件后在区段中停留的时间。 [!DNL TTL] 是根据特征而非区段设置的。 如果访客在间隔结束前没有资格获得某个特征，则访客会从区段中 [!DNL TTL] 流失。 新特 [!DNL TTL] 征的默认值为120天。 设置为0天时，特征永不过期。 [在特征创建界面的](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) “部分”中创建或编辑特征 [!UICONTROL Advanced Options] 时，设置TTL值。

### 1天TTL已解释

将TTL定时器设 [!DNL TTL] 置为1天时，TTL定时器从特征实现后的第二天开始，而不计算特征实现日的剩余时间。

Audience manager根据 [!DNL TTL] 以下公式计算1天的 [!DNL TTL] 特征的过期时间：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **示例1**:1:00时，1天 [!DNL UTC]内就发现了一个特质 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 1 = 47小时后过期。
* **示例2**:23:00时，1天 [!DNL UTC]内就发现了一个特质 [!DNL TTL]。 [!DNL TTL] 24 + 24 - 23 = 25小时后过期。

## [!DNL TTL] 和从区段中退出

如果用户在时间间隔内没有资格获得其任何特征，则会从区段中掉 [!DNL TTL] 出。 例如，如果您有一个30天的1个特征段，则如果用户在接下来的30天内不再符合该特征的条件，则该用户将从该段中退出。 [!DNL TTL]

![](assets/ttl-explained.png)

## [!DNL TTL] 和细分续订

如果 [!DNL TTL] 用户在时间段内符合区段的特征，则会重置该区段，并且该用户仍保留在区段 [!DNL TTL] 中。 此外，由于大多数区段包含具有其自身间隔的多个特征，因此，只要用户保持对与区段关联的任何特征的资格，该用户就可以保留在区段中并重置 [!DNL TTL][!DNL TTL] 间隔。

例如，假设您的区段1由特征A（30天）和特征B(15 [!DNL TTL]天)组成 [!DNL TTL]。 假设访客仅获得一次每个特征的资格，下图将概述续 [!DNL TTL] 订过程和区段内总持续时间。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL与第三方TTL设置无关

请记住， [!DNL TTL] 像素上的集 [!DNL Audience Manager] 合独立于第三方( [!DNL TTL] 或广告网络等)使用的其[!DNL DSP]他像素上的集合。

>[!MORE_LIKE_THIS]
>
>* [设置特征到期间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

