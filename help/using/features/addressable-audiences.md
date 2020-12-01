---
description: 可寻址受众功能和用例概述。
keywords: DIL
seo-description: 可寻址受众功能和用例概述。
seo-title: 可寻址受众
solution: Audience Manager
title: 可寻址受众
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience]功能和用例概述。

## 什么是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences]功能显示您在[!DNL Audience Manager]收集数据的所有属性和选定目标上看到的受众之间的重叠。 要帮助您理解此概念，请查看下面的插图。 每个圆之间的重叠表示不同类型的可寻址受众。

![](assets/addressableAudienceVenn.png)


| 量度 | 描述 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 对于  [!UICONTROL Destination] | 在报告回顾期间与平台级所有[!DNL Audience Manager]客户进行交互且可与所选[!UICONTROL destination]匹配的所有设备的计数。 <br><br>此度量很有用，因为它向您显示： <ul><li>[!DNL Audience Manager]可针对特定目标[!UICONTROL destination]访问的总[!UICONTROL addressable audience]的大小。</li><li>[!DNL Audience Manager]用户档案池对于目标平台的大小及其受众的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾窗口中，对您的属性或脱机文件实现[!UICONTROL rule-based trait]的设备计数。[!UICONTROL onboarded trait] |
| [!UICONTROL Addressable Audience Match Rate] | 在回顾窗口期间实现[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的设备的重叠计数，以及无论同步时间如何，我们已与所选[!UICONTROL destination]同步ID的设备的重叠计数。<br><br>此度量表示以下设备：<ul><li>已在回顾窗口`AND`期间实现[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>使ID与所选[!UICONTROL destination]同步，而不管同步的时间。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 报告回顾期间，属于[!UICONTROL segment]成员的所有设备的计数。 |
| [!UICONTROL Segment Addressable Audience] | 在报告回顾期间属于[!UICONTROL segment]并在您的站点上同步活动ID的用户数。 [!UICONTROL Segments] 可以包含您自己的第一方数据以及第二方和第三方数据， [!UICONTROL traits] 具体方式请 [见Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。<br><br>提示：当与1天回顾期一起使用时，此指标可以帮助您了解您的当前状态 [!UICONTROL segments]。这是因为[!UICONTROL Segment Addressable Audience]度量表示在前一天中一直在[!UICONTROL segment]中的用户。 将此与[!DNL Audience Manager]每天刷新[!UICONTROL Addressable Audiences]相结合，将此度量与回顾周期相结合可提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 界面 {#addressable-audience-interface}

[!UICONTROL Addressable Audience]功能将此抽象概念转换为可量化的数据。 在[!DNL Audience Manager]中，此功能显示受众与数据可视化的重叠，这些数据可视化以表格形式提供一览表信息和数字数据。

[!UICONTROL Addressable Audiences] 位于 **[!UICONTROL Audience Data > Destinations]**。选择&#x200B;**[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;可查看可寻址的受众量度。

![](assets/addressable-audiences-landing.png)

您在[!UICONTROL Addressable Audiences]登陆页上可以看到的三个指标代表：

| 量度 | 描述 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此度量表示过去30天的[!UICONTROL Customer Addressable Audience]（如上表所述）*。* |
| **[!UICONTROL Match Rate]** | 此度量表示过去30天&#x200B;*的[!UICONTROL Addressable Audience Match Rate]（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在报告回顾期间与平台级所有[!DNL Audience Manager]客户进行交互且可与此[!UICONTROL destination]匹配的所有设备的计数。 有关详细信息，请参阅[平台级度量](/help/using/features/addressable-audiences.md#platform-level-metrics)。 |

单击[!UICONTROL server-to-server destination]的名称以视图可寻址的受众数据。 注意，此功能仅返回[!UICONTROL server-to-server destinations]的数据，并且访问需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可帮助您：

* **预测和计划：** [!UICONTROL Segment Addressable Audience] 数据可让您更精细地处理要发送到目标受众定位和激活的区段。

* **性能评论：** 该功 [!UICONTROL Addressable Audiences] 能还是一个疑难解答工具。它允许您查看活动绩效、了解活动触及范围，并允许您与定位/激活合作伙伴交叉检查（如果看不到预期结果）。

### 第三方数据的潜在客户及其对匹配率的影响

在购买第三方数据进行受众获取之前，客户可以验证与其他数据提供商的重叠。 这有助于您在购买新数据之前做出明智的决策。 购买的第三方数据的ID同步不仅依赖于数据的重叠，还依赖于第三方提供商与所有其他[!DNL Audience Manager]客户的足迹。 您的[!DNL Adobe]顾问可以帮助您确定其他相关数据源以优化潜在活动。

### 移动用户和匹配率

尝试连接没有第三方[!DNL Safari]的移动应用程序用户时，存在间隙。 [!DNL cookies]这使得用户很难与某些合作伙伴进行同步，因为媒体投放日志中只提供同步的第三方[!DNL cookies]的[!DNL Adobe] ID。 这是您可能看到[!UICONTROL destinations]的[低匹配率](../features/addressable-audiences.md#low-match-rates)的原因。

## [!UICONTROL Addressable Audiences]和[!UICONTROL Destinations] {#date-ranges}中的日期范围

请阅读以下各节，了解[!UICONTROL Addressable Audience]或[!UICONTROL Destination]报告中的可用日期范围以及数据在每个间隔之外的老化情况。

## 可用日期范围和时区{#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences]和[目标](../features/destinations/destinations.md)的报告使用相同的日期范围间隔。 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此间隔从前一个24小时时间段的午夜到午夜。它不是实时或当前时间指标。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期范围均在[!DNL UTC]时区中设置。 请参阅Audience Manager](../reference/aam-time-zones.md)中的[时区。

## 日期范围间隔{#date-range-intervals}中的数据

[!UICONTROL Addressable Audience]和[!UICONTROL Destination]度量返回所选时间间隔内的唯一用户计数。 例如，访客只计数一次，即使他们多次访问您的网站。 第一次访问是独特的访问并被录制。 后续访问是返回访问，不计数，因为它们并不唯一。

日期范围包含所选时间间隔或更早时间段的数据。 而且，随着时间的流逝，数据会在每个报告间隔中老化。 例如，假设您在选择[!UICONTROL Last 30 Days]选项后看到2个访客。 在报告中，这些访客:

* *将* 包含在较长时间间隔（60天、90天和生命周期）返回的结果中。
* *不会包* 括在选项之前的较短间 [!UICONTROL Last 30 Day] 隔中（当前、7天和14天）。

第31天，这些访客只在60天、90天和[!UICONTROL Lifetime]结果中出现。 他们在30天的间隔期中过了年。 访客不会超出[!UICONTROL Lifetime]间隔。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本节介绍由[!UICONTROL Addressable Audiences]提供的度量类型。

### 客户级别指标{#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些度量返回访客访问您的站点或将入站数据文件发送到[!DNL Audience Manager]时所实现的特征的数据。 这些指标为您的帐户提供了全面的受众大小视图。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顾窗口期间实现[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的设备的重叠计数，以及无论同步时间如何，我们已与所选目标同步ID的设备的重叠计数。<br><br>此度量表示以下设备：<ul><li>已在回顾窗口`AND`期间实现[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>使ID与所选[!UICONTROL destination]同步，而不管同步的时间。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾窗口中，对您的属性或脱机文件实现[!UICONTROL rule-based trait]的设备计数。[!UICONTROL onboarded trait] |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 区段级别匹配度量{#segment-level-metrics}

这些度量返回[!UICONTROL segment]成员资格的数据。 它们有助于为每个[!UICONTROL segments]提供更精细、更准确的受众大小视图。

>[!NOTE]
>
>在[!UICONTROL segment]级别应用回顾窗口的方式与在客户级别不同。 访客可以在10天前来到站点并实现[!UICONTROL trait]，并且自那以后他们有资格获得[!UICONTROL segment]，并在2天前退出[!UICONTROL segment]。 应用7天回顾后，这些访客将计入[!UICONTROL segment]级别，但不计入客户级别。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 在报告回顾期间属于[!UICONTROL segment]并在您的站点上同步活动ID的用户数。 区段可以通过[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)中获取的[!UICONTROL traits]包含您自己的第一方数据、第二方数据和第三方数据。<br><br>提示：当与1天回顾期一起使用时，此指标可以帮助您了解您的当前状态 [!UICONTROL segments]。这是因为[!UICONTROL Segment Addressable Audience]度量表示在前一天中一直在[!UICONTROL segment]中的用户。 将此与[!DNL Audience Manager]每天刷新[!UICONTROL Addressable Audiences]相结合，将此度量与回顾周期相结合可提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Total Segment Population] | 报告回顾期间，属于[!UICONTROL segment]成员的所有设备的计数。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台级度量{#platform-level-metrics}

此度量返回所有[!DNL Audience Manager]客户所收集的活动数据。 与聚集的[!DNL Audience Manager]客户相比，它们可以提供更广泛的受众视图。

| 量度 | 描述 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在报告回顾期间与平台级所有[!DNL Audience Manager]客户进行交互且可与所选[!UICONTROL destination]匹配的所有设备的计数。 <br><br>此度量很有用，因为它向您显示：<ul><li>[!DNL Audience Manager]可以到达特定目标的[!UICONTROL total addressable audience]的大小。</li><li>[!DNL Audience Manager]用户档案池对于目标平台的大小及其受众的大小。</li></ul> |

## 比较[!UICONTROL Customer]和[!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不应比较[!UICONTROL Customer Addressable Audience]和[!UICONTROL Segment Addressable Audience]度量，以确定其中一个指标是否比另一个指标更重要。 这些指标是单独、不同和独立的。 如上述定义所述，每个数据集都来自不同的数据集。 因此，如果一个指标大于另一个指标，您应避免得出任何结论。 在比较这些内容时，您可以说的只是：

* [!UICONTROL Customer Addressable Audiences] 是基于 [!UICONTROL trait] 您 *自己的第一方数据的实现*。此指标为您与数据合作伙伴的集成提供了全面的视图。

* [!UICONTROL Segment Addressable Audiences] 基于您自己的第 *一方数据的细分资格以及第二方和第三方数据*。此指标可为定位平台中的[!UICONTROL addressable audiences]提供更精细、更准确的视图。

## [!UICONTROL Addressable Audiences] {#low-match-rates}匹配率低的原因

导致[!UICONTROL Addressable Audience]匹配率低或报告数字出现差异的常见元素。

| 原因 | 描述 |
|---|---|
| 移动流量 | 大多数[!UICONTROL server-to-server]集成都依赖由第三方[!DNL cookies]提供的同步过程。 但是，移动环境不使用第三方[!DNL cookies]。 因此，与[!UICONTROL segment]大小相比，您的[!UICONTROL Addressable Audiences]数字可能看起来很低。 <br><br>从2018年1月起，您可以在为受众设置的相同 [!DNL Google] 和 [!DNL Adobe Advertising Cloud] 目标中激活移动 [!UICONTROL cookie-based] 受众。这意味着您可以将[!DNL cookie]和移动ID成员资格组合的[!UICONTROL segments]发送到[!DNL Google]和[!DNL Advertising Cloud]目标，但请记住，[!UICONTROL Addressable Audiences]只显示[!DNL cookie] ID与目标之间的重叠。 [!DNL Audience Manager] 将100%的移动受众发 [!UICONTROL destinations]送给，但移动受众不按度量 [!UICONTROL Addressable Audience] 来衡量。<br><br>**注意**:以人口 [!UICONTROL segment] 一百万为例如果将此[!UICONTROL segment]映射到[!DNL Google]或[!DNL Adobe Advertising Cloud]目标，您可能会看到[!UICONTROL Addressable Audience]，共700,000台设备，[!UICONTROL Match Rate]为70%。 700,000的会员资格由[!DNL cookie] ID组成，这些ID与[!UICONTROL destination]同步。 事实上，您的[!UICONTROL Addressable Audience]可能更高，因为可寻址移动ID不显示在此度量中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 阻止第三方 [!DNL cookies]。这会阻止[!DNL Audience Manager]将ID与[!UICONTROL destination]同步。 引入[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)后，您可能希望您的[!UICONTROL addressable audiences]不包括[!DNL Safari]用户。 |
| 跟踪的媒体印象 | 由于广告服务器最佳实践，ID同步不会在广告标记中进行。 进行大量非现场广告的客户不会将用户同步到这些环境中的第三方集成。 此外，大量收集的媒体印象数据可能会减少[!UICONTROL addressable audience]数量。 |

## [!UICONTROL Addressable Audiences] {#troubleshooting}疑难解答

除了显示匹配率外，还可以使用[!UICONTROL Addressable Audiences]作为故障排除工具。

例如，假设您向[!UICONTROL destination]发送一个段，且[!UICONTROL destination]显示的报告数较低。 检查[!UICONTROL Addressable Audience]结果将显示这是技术问题还是只是匹配率低的问题。 低匹配率表明[!UICONTROL destination]对于所选区段来说并不是那么好。 但是，[!DNL Audience Manager]和[!UICONTROL destination]之间的[!UICONTROL total addressable audience]数字的差异表明存在集成、同步或其他技术问题。 在这些情况下，请联系您的客户经理。
