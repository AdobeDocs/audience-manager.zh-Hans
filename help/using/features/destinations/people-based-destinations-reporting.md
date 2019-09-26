---
description: '基于人员的目标向Audience manager引入了可共享受众的概念。 此指标可帮助您了解Audience manager可与目标平台共享的哈希电子邮件地址数。 '
seo-description: '基于人员的目标向Audience manager引入了可共享受众的概念。 此指标可帮助您了解Audience manager可与目标平台共享的哈希电子邮件地址数。 '
seo-title: 可共享的受众
solution: Audience Manager
title: 可共享的受众
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 可共享的受众 {#shareable-audiences}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 将Audience Manager的概 [!DNL Shareable Audiences] 念引入Audience Manager。 此指标可帮助您了解Audience manager可与目标平台共享的哈希电子邮件地址数。

[!DNL Shareable Audiences] 是一种帮助您在情境中解释受众数据的指标 [!DNL People-Based Destinations]。 您可以在页面和页 [!UICONTROL Destinations] 面中查看此 [!UICONTROL Segment] 度量。

## 细分可共享受众 {#segment-shareable-audiences}

区段页 [!DNL Segment Shareable Audience] 面中的量度指示数据源中哈希化电子邮件地址的数量，这些地址具有匹配的 [DPUUID](../../reference/ids-in-aam.md)，在给定的回顾期内，如果应用了配置文件合并规则，这些DPUUID也符合定义的区段，并且Audience manager可以与目标平台共享。

此指标有1天的回顾期。 这有助于您了解特定目标中的细分受众范围。

## 目标可共享受众 {#destination-shareable-audience}

基于 [!DNL Destination Shareable Audience] 人员的目标页面中的度量指示数据源中哈希电子邮件地址的总数，这些地址与Audience manager可以与目标平台共享的 [DPUUID](../../reference/ids-in-aam.md)（从映射到该目标的所有区段）匹配。

![可共享受众](assets/dest-shareable-audiences.png)

此指标具有终生回顾期。 这有助于您了解通过哈希电子邮件地址数据源可以触及的受众规模。

## 示例

Audience manager客户有一个数据源，其中有110,000个 [DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他们将100,000个哈希电子邮件地址收录到Audience Manager中，以将其与多个基于人员的目标结合使用，并针对CRM ID对100,000个哈希电子邮件地址执行ID同步。 客户可以使用合 [!DNL All Cross-Device Profiles] 并规则创建三个受众细分：

* 区段A的人口数为10,000，映射到目标A;
* 区段B，人口数为20,000，映射到目标A;
* 区段C，人口计数为50,000，映射到目标B。

在此方案中：

* 可共享受众细分A = 10,000;
* B区段可共享受众= 20,000;
* C区段可共享受众= 50,000;
* 目标A可共享受众=区段A可共享受众+区段B可共享受众= 30,000;
* 目标B可共享受众=区段C可共享受众= 50,000。

![可共享的受众图](assets/shareable-audiences.png)

> [!NOTE]
>
> 在上例中，这并不意味着三个区段中的所有80,000个哈希电子邮件地址都与目标平台中的现有帐户匹配。 这仅意味着Audience manager将三个区段的哈希标识符发送到各自的目标。 将受众细分发送到基于人员的目标时，合作伙伴会进行受众匹配。 目标A最多可有30,000个匹配用户帐户，而目标B最多可有50,000个匹配用户帐户，但无法保证匹配率。 Adobe无权访问特定于合作伙伴的指标。 有关“ [基于人员的目标](../../faq/faq-people-based-destinations.md#match-rates) ”在匹配率方面的可见性的常见问题解答，请参阅匹配率。
