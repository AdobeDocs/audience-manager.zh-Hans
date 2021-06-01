---
description: '基于人员的目标引入了可共享受众的概念来进行Audience Manager。 此量度可帮助您了解Audience Manager可以与目标平台共享多少个经过哈希处理的电子邮件地址。 '
seo-description: '基于人员的目标引入了可共享受众的概念来进行Audience Manager。 此量度可帮助您了解Audience Manager可以与目标平台共享多少个经过哈希处理的电子邮件地址。 '
seo-title: 可共享的受众
solution: Audience Manager
title: 可共享的受众
feature: 基于人员的目标
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 可共享的受众 {#shareable-audiences}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 把概念 [!DNL Shareable Audiences] Audience Manager。此量度可帮助您了解Audience Manager可以与目标平台共享多少个经过哈希处理的电子邮件地址。

[!DNL Shareable Audiences] 是一个量度，可帮助您在上下文中解释受众数 [!DNL People-Based Destinations]据。您可以在[!UICONTROL Destinations]页面和[!UICONTROL Segment]页面中看到此量度。

## 区段可共享受众{#segment-shareable-audiences}

区段页面中的[!DNL Segment Shareable Audience]量度指示数据源中与[DPUUID](../../reference/ids-in-aam.md)匹配的经过哈希处理的电子邮件地址数量，该地址也符合给定回顾期内定义的区段的条件（假定对其应用了配置文件合并规则），且该Audience Manager可以与目标平台共享。

此量度具有1天的回顾期。 这有助于您了解特定目标中区段的受众访问。

## 目标可共享受众{#destination-shareable-audience}

基于人员的目标页面中的[!DNL Destination Shareable Audience]量度指示数据源中与[DPUUID](../../reference/ids-in-aam.md)匹配的经过哈希处理的电子邮件地址总数，该Audience Manager可以从映射到该目标的所有区段与目标平台共享该电子邮件地址。

![可共享受众](assets/dest-shareable-audiences.png)

此量度具有生命周期回顾期。 这有助于您了解从经过哈希处理的电子邮件地址数据源访问的受众规模。

## 示例

Audience Manager客户的数据源为110,000 [DPUUIDs](../../reference/ids-in-aam.md)(CRM ID)。 他们将100,000个经过哈希处理的电子邮件地址摄取到Audience Manager中，以将其与多个基于人员的目标结合使用，并针对CRM ID为100,000个经过哈希处理的电子邮件地址执行ID同步。 客户可以使用[!DNL All Cross-Device Profiles]合并规则创建三个受众区段：

* 区段A，群体计数为10,000，且已映射到目标A;
* 区段B，人口计数为20,000，被映射到目标A;
* 区段C的群体计数为50,000，已映射到目标B。

在此方案中：

* 对可共享受众进行分段= 10,000;
* 区段B可共享受众= 20,000;
* 区段C可共享受众= 50,000;
* 目标A可共享受众=对可共享受众进行分段+对可共享受众进行分段= 30,000;
* 目标B可共享受众=区段C可共享受众= 50,000。

![可共享受众 — 图](assets/shareable-audiences.png)

>[!NOTE]
>
>在以上示例中，这并不意味着三个区段中所有80,000个经过哈希处理的电子邮件地址都与目标平台中的现有帐户匹配。 它仅意味着Audience Manager将三个区段中经过哈希处理的标识符发送到其各自的目标。 将受众区段发送到基于人员的目标时，会在合作伙伴方进行受众匹配。 目标A最多可以有30,000个匹配用户帐户，而目标B最多可以有50,000个匹配用户帐户，但无法保证匹配率。 Adobe无权访问特定于合作伙伴的量度。 请参阅[匹配率](../../faq/faq-people-based-destinations.md#match-rates) ，以了解有关匹配率中基于人员的目标可见性的常见问题解答。
