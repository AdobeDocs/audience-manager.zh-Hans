---
description: '基于人的目的地将可共享受众的概念引入Audience Manager。 此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件地址数。 '
seo-description: '基于人的目的地将可共享受众的概念引入Audience Manager。 此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件地址数。 '
seo-title: 可共享的受众
solution: Audience Manager
title: 可共享的受众
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 可共享的受众 {#shareable-audiences}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都是法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 把概念带到 [!DNL Shareable Audiences] Audience Manager。此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件地址数。

[!DNL Shareable Audiences] 是帮助您在上下文中解释受众数据的量度 [!DNL People-Based Destinations]您可以在[!UICONTROL Destinations]页和[!UICONTROL Segment]页中查看此量度。

## 区段可共享受众{#segment-shareable-audiences}

区段页中的[!DNL Segment Shareable Audience]量度指示来自数据源的哈希电子邮件地址数，这些地址与[ DPUUID](../../reference/ids-in-aam.md)匹配，在给定回顾期间，如果应用了用户档案合并规则，该Audience Manager也符合定义的区段的条件，并且该数据可以与目标平台共享。

此量度有1天回顾期。 这有助于您了解特定目标中区段的受众范围。

## 目标可共享受众{#destination-shareable-audience}

基于人员的目标页面中的[!DNL Destination Shareable Audience]量度指示Audience Manager可与目标平台共享的来自数据源的哈希电子邮件地址总数，这些地址来自映射到该目标的所有区段。[](../../reference/ids-in-aam.md)

![可共享的受众](assets/dest-shareable-audiences.png)

此量度具有生命周期回顾期。 这有助于您了解从散列电子邮件地址数据源可以访问的受众的规模。

## 示例

Audience Manager客户的数据源为110,000 [DPUUIDs](../../reference/ids-in-aam.md)(CRM ID)。 他们将100,000个哈希电子邮件地址收录到Audience Manager中，以将其与多个基于人员的目标一起使用，并针对CRM ID对100,000个哈希电子邮件地址执行ID同步。 客户可使用[!DNL All Cross-Device Profiles]合并规则创建三个受众段：

* 区段A，人口计数为10,000，映射到目标A;
* 区段B，人口计数为20,000，映射到目标A;
* 区段C，人口计数为50,000，映射到目标B。

在此方案中：

* A类可共享受众= 10,000;
* B区段可共享受众= 20,000;
* C区段可共享受众= 50,000;
* 目标A可共享受众=区段A可共享受众+区段B可共享受众= 30,000;
* 目标B可共享受众=区段C可共享受众= 50,000。

![可共享受众图](assets/shareable-audiences.png)

>[!NOTE]
>
>在上例中，这并不意味着三个区段中的所有80,000个哈希电子邮件地址都与目标平台中的现有帐户匹配。 它仅表示Audience Manager将散列标识符从三个区段发送到其各自的目标。 将受众区段发送到基于人的目标时，受众匹配会在合作伙伴端发生。 目标A最多可有30,000个匹配用户帐户，而目标B最多可有50,000个匹配用户帐户，但无法保证匹配率。 Adobe无权访问特定于合作伙伴的量度。 有关“基于人的目标”在匹配率方面的可见性的常见问题，请参阅[匹配率](../../faq/faq-people-based-destinations.md#match-rates)。
