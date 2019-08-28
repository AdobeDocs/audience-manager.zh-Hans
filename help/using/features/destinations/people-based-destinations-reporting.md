---
description: '基于人群的目标将可共享受众的概念引入Audience Manager。此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件中有多少。 '
seo-description: '基于人群的目标将可共享受众的概念引入Audience Manager。此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件中有多少。 '
seo-title: 可共享受众
solution: Audience Manager
title: 可共享受众
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 可共享受众 {#shareable-audiences}

[!DNL People-Based Destinations] 了解Audience [!DNL Shareable Audiences] Manager的概念。此量度可帮助您了解Audience Manager可与目标平台共享的散列电子邮件中有多少。

[!DNL Shareable Audiences] 是帮助您在情境 [!DNL People-Based Destinations]中解读受众数据的指标。您可以在 [!UICONTROL Destinations] 页面和 [!UICONTROL Segment] 页面中看到此量度。

## 细分可共享受众 {#segment-shareable-audiences}

区段页面中的 [!DNL Segment Shareable Audience] 指标表示来自数据源的散列电子邮件地址的哈希值与匹配 [的DPUUID相匹配](../../reference/ids-in-aam.md)，该数据也符合给定的回顾期内定义的区段，并且Audience Manager可以与目标平台共享，从而在给定的回顾期内符合定义的区段。

此量度的回顾期为天。这有助于您了解特定目标中区段受众的触及范围。

## 目标可共享受众 {#destination-shareable-audience}

基于人群的目标页面中的 [!DNL Destination Shareable Audience] 量度指示来自数据源的数据源的散列电子邮件地址的总数量， [该](../../reference/ids-in-aam.md)数据源与目标平台共享，来自映射到该目标的所有区段的目标平台。

![可共享受众](assets/dest-shareable-audiences.png)

此量度具有终身回顾期。这有助于您了解可通过哈希电子邮件访问的受众规模，以满足数据源需求。

## 示例

Audience Manager客户的数据源为110,000 [dPuID](../../reference/ids-in-aam.md) (CRM ID)。他们将100，000封哈希电子邮件地址收录到Audience Manager中，将其与多个基于人群的目标一起使用，并针对CRM ID为100,000个散列电子邮件地址执行ID同步。客户可使用 [!DNL All Cross-Device Profiles] 合并规则创建三个受众细分：

* 人口总数为10,000，映射到目标A的区段A；
* 人口计数为20,000的区段B，映射到目标A；
* 人口计数为50,000的区段C映射到目标B。

在此方案中：

* 区段A可共享受众=10,000；
* 区段B可共享受众=20,000；
* 区段C可共享受众=50,000；
* 目标一个可共享受众=区段A可共享受众+区段B可共享受众=30,000；
* 目标B可共享受众=区段C可共享受众=50,000。

![sharable-audiences-app](assets/shareable-audiences.png)

> [!NOTE]
>
> 在上面的示例中，这并不意味着三个区段中的所有80,000个哈希电子邮件地址与目标平台中的现有帐户相匹配。这只意味着Audience Manager将哈希标识符从三个区段发送到各自的目标。将受众细分发送到基于人员的目标时，受众匹配在合作伙伴端发生。目标A最多可有30,000个匹配用户帐户，而目标B最多可有50,000个匹配用户帐户，但不保证匹配费率。Adobe无权访问合作伙伴特定指标。请参阅 [有关基于People的目标目标可见率常见问题的匹配率](../../faq/faq-people-based-destinations.md#match-rates) 。
