---
description: 基于人员的目标向Audience Manager引入了可共享受众的概念。 此指标有助于您了解Audience Manager可以与目标平台共享多少个经过哈希处理的电子邮件地址。
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: 可共享的受众
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# 可共享的受众 {#shareable-audiences}

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations]将[!DNL Shareable Audiences]的概念引入Audience Manager。 此指标有助于您了解Audience Manager可以与目标平台共享多少个经过哈希处理的电子邮件地址。

[!DNL Shareable Audiences]是一个量度，可帮助您解释[!DNL People-Based Destinations]上下文中的受众数据。 您可以在[!UICONTROL Destinations]页面和[!UICONTROL Segment]页面中看到此量度。

## 对可共享的受众进行分段 {#segment-shareable-audiences}

区段页面中的[!DNL Segment Shareable Audience]量度表示数据源中具有匹配[DPUUID](../../reference/ids-in-aam.md)的经过哈希处理的电子邮件地址数量，这些地址在给定的回顾期间也符合定义的区段的条件（假定对其应用了配置文件合并规则），并且Audience Manager可以与目标平台共享。

此量度具有1天回顾时段。 这有助于您了解特定目标中区段的受众覆盖范围。

## 目标可共享受众 {#destination-shareable-audience}

基于人员的目标页面中的[!DNL Destination Shareable Audience]量度表示数据源中具有匹配[DPUUID](../../reference/ids-in-aam.md)的经过哈希处理的电子邮件地址总数，Audience Manager可以与该目标平台共享这些地址以及映射到该目标的所有区段。

![可共享受众](assets/dest-shareable-audiences.png)

此量度具有生命周期回顾时段。 这有助于您了解从经过哈希处理的电子邮件地址数据源可访问的受众规模。

## 示例

Audience Manager客户具有的数据源具有110,000个[DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他们将100,000个经过哈希处理的电子邮件地址摄取到Audience Manager，将其用于多个基于人员的目标，并根据CRM ID对100,000个经过哈希处理的电子邮件地址执行ID同步。 客户可以使用[!DNL All Cross-Device Profiles]合并规则创建三个受众区段：

* 人口数为10,000的区段A已映射到目标A；
* 人口数为20,000的区段B，已映射到目标A；
* 人口数为50,000的区段C已映射到目标B。

在此方案中：

* 区段A可共享受众= 10,000；
* 区段B可共享受众= 20,000；
* 区段C可共享受众= 50,000；
* 目标A可共享受众=区段A可共享受众+区段B可共享受众= 30,000；
* 目标B可共享受众=区段C可共享受众= 50,000。

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>在以上示例中，这并不意味着三个区段中的所有80,000个经过哈希处理的电子邮件地址与目标平台中的现有帐户相匹配。 这仅意味着Audience Manager将经过哈希处理的标识符从三个区段发送到各自的目的地。 将受众区段发送到基于人员的目标时，会在合作伙伴方进行受众匹配。 目标A最多可以具有30,000个匹配用户帐户，而目标B最多可以具有50,000个匹配用户帐户，但不保证匹配率。 Adobe无权访问特定于合作伙伴的指标。 有关匹配率中基于人员的目标可见性的常见问题，请参阅[匹配率](../../faq/faq-people-based-destinations.md#match-rates)。
