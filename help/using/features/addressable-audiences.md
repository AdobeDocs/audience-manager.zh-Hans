---
description: 可寻址受众功能和用例概述。
keywords: DIL
seo-description: 可寻址受众功能和用例概述。
seo-title: 可寻址受众
solution: Audience Manager
title: 可寻址受众
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

功能和用 [!UICONTROL Addressable Audience] 例的概述。

## 什么是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

该功 [!UICONTROL Addressable Audiences] 能显示您在收集受众的所有属性和选定目标中 [!DNL Audience Manager] 看到的数据之间的重叠。 要帮助您理解此概念，请查看下面的插图。 每个圆之间的重叠表示不同类型的可寻址受众。

![](assets/addressableAudienceVenn.png)


| 量度 | 描述 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 对于 [!UICONTROL Destination] | 在报告回顾期间与平台级所有 [!DNL Audience Manager] 客户进行交互且可能与您选择的设备相匹配的所有设备计数 [!UICONTROL destination]。 <br><br>此度量很有用，因为它向您显示： <ul><li>特定目标上 [!UICONTROL addressable audience] 可 [!DNL Audience Manager] 以访问的总大小 [!UICONTROL destination]。</li><li>用户档案池 [!DNL Audience Manager] 对于定位平台和受众的大小来说有多大。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾窗口中，已对您的属 [!UICONTROL rule-based trait] 性或脱机文 [!UICONTROL onboarded trait] 件实现的设备计数。 |
| [!UICONTROL Addressable Audience Match Rate] | 在回顾窗口中实现或同步的 [!UICONTROL rule-based trait] 设备 [!UICONTROL onboarded trait] 的重叠计数，以及无论同步时间如何，我们都与选定的设备 [!UICONTROL destination] 进行ID同步的设备。<br><br>此度量表示以下设备：<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 在报告回顾期间，属于您的 [!UICONTROL segment] 所有设备的计数。 |
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. [!UICONTROL Segments] 可以包含您自己的第一方数据以及第二方和第三方数据，具体方 [!UICONTROL traits] 法是在Audience Marketplace [中获取](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。 <br><br>提示： 当与1天回顾期一起使用时，此指标可以帮助您了解您的当前状态 [!UICONTROL segments]。 这是因为 [!UICONTROL Segment Addressable Audience] 该指标代表在前一天中 [!UICONTROL segment] 一直停留的用户。 将此指标与每天刷 [!DNL Audience Manager] 新 [!UICONTROL Addressable Audiences] 的事实相结合，将此指标与回顾周期相结合，可提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 界面 {#addressable-audience-interface}

该功 [!UICONTROL Addressable Audience] 能将这个抽象概念转化为可量化的数据。 在中 [!DNL Audience Manager]，此功能显示受众与数据可视化的重叠，这些数据可视化以表格形式提供一览表信息和数字数据。

[!UICONTROL Addressable Audiences] 位于 **[!UICONTROL Audience Data > Destinations]**。 选择 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可寻址的受众量度。

![](assets/addressable-audiences-landing.png)

您可以在登陆页上看到的三个 [!UICONTROL Addressable Audiences] 指标代表：

| 量度 | 描述 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此度量表示 [!UICONTROL Customer Addressable Audience] 过去30天(如上 *表所述)。* |
| **[!UICONTROL Match Rate]** | 此度量表 [!UICONTROL Addressable Audience Match Rate] 示过去30天 *的（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在报告回顾期间与平台级所有 [!DNL Audience Manager] 客户进行交互且可与之匹配的所有设备的计数 [!UICONTROL destination]。 请参 [阅Platform级度量](/help/using/features/addressable-audiences.md#platform-level-metrics) ，以了解更多信息。 |

单击某个名称以 [!UICONTROL server-to-server destination] 视图可寻址受众数据。 注意，此功能仅返回数 [!UICONTROL server-to-server destinations] 据，并且访问需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可帮助您：

* **预测和规划：** [!UICONTROL Segment Addressable Audience] 数据可让您更精细地进入您计划发送到目标的受众定位和激活。

* **性能评论：** 该功 [!UICONTROL Addressable Audiences] 能还是一个疑难解答工具。 它允许您查看活动绩效、了解活动触及范围，并允许您与定位/激活合作伙伴交叉检查（如果看不到预期结果）。

### 第三方数据的潜在客户及其对匹配率的影响

在购买第三方数据进行受众获取之前，客户可以验证与其他数据提供商的重叠。 这有助于您在购买新数据之前做出明智的决策。 购买的第三方数据的ID同步不仅依赖于数据的重叠，还依赖于第三方提供商对所有其他客户的 [!DNL Audience Manager] 足迹。 您的 [!DNL Adobe] 顾问可以帮助您确定其他相关数据源以优化潜在活动。

### 移动用户和匹配率

尝试连接没有第三方 [!DNL Safari] 的应用程序用户或移动应用程序用户时存在 [!DNL cookies] 差距。 这使得用户难以与某些合作伙伴进行同步，因 [!DNL Adobe] 为媒体投放日志中只提 [!DNL cookies] 供同步的第三方ID。 这就是你可能看到低 [匹配率](../features/addressable-audiences.md#low-match-rates) 的原因 [!UICONTROL destinations]。

## 日期范围(在 [!UICONTROL Addressable Audiences] 和 [!UICONTROL Destinations] {#date-ranges}

请阅读以下各节，了解可用日期范围以及数据在报表中的每个间隔之外的老化 [!UICONTROL Addressable Audience] 情况或 [!UICONTROL Destination]。

## 可用日期范围和时区 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您和目标 [!UICONTROL Addressable Audiences] 的报 [表使用](../features/destinations/destinations.md) 相同的日期范围间隔。 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此间隔从前一个24小时时间段的午夜到午夜。 它不是实时或当前时间指标。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期范围均在时区 [!DNL UTC] 中设置。 See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## 日期范围间隔中的数据 {#date-range-intervals}

和 [!UICONTROL Addressable Audience] 度 [!UICONTROL Destination] 量返回所选时间间隔内的唯一用户计数。 例如，访客只计数一次，即使他们多次访问您的网站。 第一次访问是独特的访问并被录制。 后续访问是返回访问，不计数，因为它们并不唯一。

日期范围包含所选时间间隔或更早时间段的数据。 而且，随着时间的流逝，数据会在每个报告间隔中老化。 例如，假设您在选择选项后看到2个访客 [!UICONTROL Last 30 Days] 符。 在报告中，这些访客:

* *将包含* 在较长时间间隔（60天、90天和生命周期）返回的结果中。
* *选项* (“当前”、“7天”和“ [!UICONTROL Last 30 Day] 14天”)之前的较短时间间隔中不包括。

第31天，这些访客只在60天，90天出现，结果也 [!UICONTROL Lifetime] 是。 他们在30天的间隔期中过了年。 访客不会在间隔内过 [!UICONTROL Lifetime] 时。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本节介绍提供的度量类型 [!UICONTROL Addressable Audiences]。

### 客户级指标 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些指标返回访客访问您的网站或向其发送入站数据文件时所实现特征的数据 [!DNL Audience Manager]。 这些指标为您的帐户提供了全面的受众大小视图。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顾窗口或回顾窗口期间 [!UICONTROL rule-based trait] 实 [!UICONTROL onboarded trait] 现的设备与我们已与所选目标同步的设备的重叠计数，而不管同步的时间。<br><br>此度量表示以下设备：<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾窗口中，已对您的属 [!UICONTROL rule-based trait] 性或脱机文 [!UICONTROL onboarded trait] 件实现的设备计数。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 细分级别匹配指标 {#segment-level-metrics}

这些指标会返回会员资 [!UICONTROL segment] 格数据。 它们有助于为您的每个视图提供更精细、更准确的受众大小 [!UICONTROL segments]。

>[!NOTE]
>
>在级别应用回顾窗口的方 [!UICONTROL segment] 式与在客户级别不同。 访客可以在10天前来 [!UICONTROL trait] 到网站，并且从那时起 [!UICONTROL segment] 就有资格申请退 [!UICONTROL segment] 出2天前。 应用7天回顾后，这些访客将计入级别， [!UICONTROL segment] 而不计入客户级别。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via [!UICONTROL traits] acquired in the [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>提示： 当与1天回顾期一起使用时，此指标可以帮助您了解您的当前状态 [!UICONTROL segments]。 这是因为 [!UICONTROL Segment Addressable Audience] 该指标代表在前一天中 [!UICONTROL segment] 一直停留的用户。 将此指标与每天刷 [!DNL Audience Manager] 新 [!UICONTROL Addressable Audiences] 的事实相结合，将此指标与回顾周期相结合，可提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Total Segment Population] | 在报告回顾期间，属于您的 [!UICONTROL segment] 所有设备的计数。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### Platform级指标 {#platform-level-metrics}

此指标返回所有客户所收集的活动 [!DNL Audience Manager] 数据。 与汇总的客户相比，它们可以提供更广的客户受众 [!DNL Audience Manager] 视图。

| 量度 | 描述 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在报告回顾期间与平台级所有 [!DNL Audience Manager] 客户进行交互且可能与您选择的设备相匹配的所有设备计数 [!UICONTROL destination]。 <br><br>此度量很有用，因为它向您显示：<ul><li>可在特定目 [!UICONTROL total addressable audience] 标 [!DNL Audience Manager] 上访问的大小。</li><li>用户档案池 [!DNL Audience Manager] 对于定位平台和受众的大小来说有多大。</li></ul> |

## 比较 [!UICONTROL Customer] 和 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不应该比较和 [!UICONTROL Customer Addressable Audience] 度量 [!UICONTROL Segment Addressable Audience] 来确定其中一个是否比另一个重要。 这些指标是单独、不同和独立的。 如上述定义所述，每个数据集都来自不同的数据集。 因此，如果一个指标大于另一个指标，您应避免得出任何结论。 在比较这些内容时，您可以说的只是：

* [!UICONTROL Customer Addressable Audiences] 基于您 [!UICONTROL trait] 自 *己的第一方数据的实现*。 此指标为您与数据合作伙伴的集成提供了全面的视图。

* [!UICONTROL Segment Addressable Audiences] 基于您自己的第 *一方数据的细分资格以及第二方和第三方数据*。 此指标可为您在定位平台中提供更精 [!UICONTROL addressable audiences] 细、更准确的视图。

## A.B.C. [!UICONTROL Addressable Audiences] {#low-match-rates}

导致匹配率低或报 [!UICONTROL Addressable Audience] 告数字出现差异的常见元素。

| 原因 | 描述 |
|---|---|
| 移动流量 | 大多 [!UICONTROL server-to-server] 数集成都依赖第三方推动的同步过程 [!DNL cookies]。 但是，移动环境不使用第三方 [!DNL cookies]。 因此，与大小相 [!UICONTROL Addressable Audiences] 比，您的数字可能看起来 [!UICONTROL segment] 很低。 <br><br>从2018年1月起，您可以在为受众设置的相同 [!DNL Google] 和目 [!DNL Adobe Advertising Cloud] 标中激活移动 [!UICONTROL cookie-based] 受众。 这意味着您可以向您和目 [!UICONTROL segments] 标发 [!DNL cookie] 送合并和移动ID会员资格 [!DNL Google] ，但请记住，只 [!DNL Advertising Cloud] 显示ID与目标之间 [!UICONTROL Addressable Audiences][!DNL cookie] 的重叠。 [!DNL Audience Manager] 将100%的移动受众发 [!UICONTROL destinations]送给，但移动受众不按度量来 [!UICONTROL Addressable Audience] 衡量。 <br><br>**注意&#x200B;**: 以人口[!UICONTROL segment]一百万为例 如果将此设[!UICONTROL segment]备映[!DNL Google]射到某个或目[!DNL Adobe Advertising Cloud]标，您可能会看到700,000台[!UICONTROL Addressable Audience]设备和70%[!UICONTROL Match Rate]的设备。 700,000的会员资格由ID[!DNL cookie]组成，ID与同步[!UICONTROL destination]。 事实上[!UICONTROL Addressable Audience]，您的可能性要高得多，因为可寻址移动ID不会出现在此度量中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 阻止第三方 [!DNL cookies]。 这会阻 [!DNL Audience Manager] 止ID与同步 [!UICONTROL destination]。 随着ITP 2. [0的推出](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)，您可以期 [!UICONTROL addressable audiences] 望不会包含用 [!DNL Safari] 户。 |
| 跟踪的媒体印象 | 由于广告服务器最佳实践，ID同步不会在广告标记中进行。 进行大量非现场广告的客户不会将用户同步到这些环境中的第三方集成。 此外，大量收集的媒体印象数据可能会减少 [!UICONTROL addressable audience] 数量。 |

## 疑难解答 [!UICONTROL Addressable Audiences] {#troubleshooting}

除了显示匹配率外，您还可以将 [!UICONTROL Addressable Audiences] 其用作故障排除工具。

例如，假设您向某个区段发送区段， [!UICONTROL destination] 该区段 [!UICONTROL destination] 显示低报告数。 检查结 [!UICONTROL Addressable Audience] 果将显示这是技术问题还是只是匹配率低的问题。 低匹配率表明您 [!UICONTROL destination] 的选定区段并不是那么好。 但是，与之间的数 [!UICONTROL total addressable audience] 字的差 [!DNL Audience Manager] 异表 [!UICONTROL destination] 明存在集成、同步或其他技术问题。 在这些情况下，请联系您的客户经理。
