---
description: 可寻址受众功能和用例概述。
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: 可寻址受众
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

概述 [!UICONTROL Addressable Audience] 功能和用例。

## 什么是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

的 [!UICONTROL Addressable Audiences] 功能可显示您在所有资产中看到的受众之间的重叠，其中 [!DNL Audience Manager] 收集数据和您选择的目标。 要帮助您了解此概念，请查看下图。 每个圆圈之间的重叠表示不同类型的可寻址受众。

![](assets/addressableAudienceVenn.png)


| 量度 | 描述 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] a [!UICONTROL Destination] | 对与所有设备进行交互的设备的计数 [!DNL Audience Manager] 报表回顾期间在平台级别的客户，且可能与您选择的 [!UICONTROL destination]. <br><br>此量度非常有用，因为它会向您显示： <ul><li>总计的大小 [!UICONTROL addressable audience] the [!DNL Audience Manager] 可以访问特定定位 [!UICONTROL destination].</li><li>多大 [!DNL Audience Manager] 配置文件池用于定位平台及其受众的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已实现 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 从脱机文件。 |
| [!UICONTROL Customer Addressable Audience] | 已实现 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 在回顾窗口期间，以及我们与所选的 [!UICONTROL destination] 无论同步的时间。<br><br>此量度表示设备满足以下条件：<ul><li>已经意识到 [!UICONTROL rule-based] 或 [!UICONTROL onboarded trait] 回顾窗口期间 `AND`</li><li>与所选的同步ID [!UICONTROL destination] 无论同步的时间。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 属于您的 [!UICONTROL segment] 在报表回顾期间。 |
| [!UICONTROL Segment Addressable Audience] | 属于 [!UICONTROL segment] 在报表回顾期间，且您的网站上具有活动ID同步。 [!UICONTROL Segments] 可以通过 [!UICONTROL traits] 在 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>提示：当与1天回顾期一起使用时，此量度可以帮助您了解 [!UICONTROL segments]. 这是因为 [!UICONTROL Segment Addressable Audience] 量度表示在 [!UICONTROL segment] 前一天。 结合以下事实 [!DNL Audience Manager] 刷新 [!UICONTROL Addressable Audiences] 每日，结合此量度和回顾期可提供您的最新快照 [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 界面 {#addressable-audience-interface}

的 [!UICONTROL Addressable Audience] 功能可将此抽象概念转换为可量化的数据。 在 [!DNL Audience Manager]，则此功能会显示受众与数据可视化图表的重叠部分，这些数据可视化图表以表格形式提供了概览信息以及数字数据。

[!UICONTROL Addressable Audiences] 位于 **[!UICONTROL Audience Data > Destinations]**. 选择 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可寻址受众量度。

![](assets/addressable-audiences-landing.png)

您可以在 [!UICONTROL Addressable Audiences] 登陆页面表示：

| 量度 | 描述 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度表示 [!UICONTROL Customer Addressable Audience] （如上表所述） *过去30天。* |
| **[!UICONTROL Match Rate]** | 此量度表示 [!UICONTROL Addressable Audience Match Rate] （如上表所述） *过去30天*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 对与所有设备进行交互的设备的计数 [!DNL Audience Manager] 报表回顾期间在平台级别的客户，可与此相匹配 [!UICONTROL destination]. 请参阅 [平台级别量度](/help/using/features/addressable-audiences.md#platform-level-metrics) 以了解更多信息。 |

单击 [!UICONTROL server-to-server destination] 以查看可寻址受众数据。 请注意，此功能会返回 [!UICONTROL server-to-server destinations] 只有和需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可帮助您：

* **预测和规划：** [!UICONTROL Segment Addressable Audience] 通过数据，您可以在计划发送到目标的区段中实现更多粒度，以便进行受众定位和激活。

* **绩效审查：** 的 [!UICONTROL Addressable Audiences] 功能也是故障诊断工具。 它可让您查看营销活动效果、了解营销活动的范围，并在看不到预期结果时与定位/激活合作伙伴进行交叉检查。

### 使用第三方数据寻找客户及其对匹配率的影响

在为受众获取购买第三方数据之前，客户可以验证与其他数据提供商的重叠。 这有助于您在购买新数据之前做出明智的决策。 购买的第三方数据的ID同步不仅依赖于数据的重叠，还依赖于第三方提供商在所有其他数据上的足迹 [!DNL Audience Manager] 客户。 您的 [!DNL Adobe] 顾问可以帮助您确定其他相关数据源，以优化潜在客户活动。

### 移动设备用户和匹配率

尝试连接时存在差距 [!DNL Safari] 或没有第三方的移动设备应用程序用户 [!DNL cookies] 礼物。 这使得用户很难与某些合作伙伴同步，因为只有那些合作伙伴 [!DNL Adobe] 已同步的第三方的ID [!DNL cookies] 在媒体投放日志中提供。 这就是为什么你可能 [低匹配率](../features/addressable-audiences.md#low-match-rates) , [!UICONTROL destinations].

## 中的日期范围 [!UICONTROL Addressable Audiences] 和 [!UICONTROL Destinations] {#date-ranges}

请阅读以下部分，了解可用的日期范围以及数据在报表中的每个间隔之外的老化情况 [!UICONTROL Addressable Audience] 或 [!UICONTROL Destination].

## 可用的日期范围和时区 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

报表 [!UICONTROL Addressable Audiences] 和 [目标](../features/destinations/destinations.md) 使用相同的日期范围间隔。 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此间隔在前24小时时段的午夜到午夜之间运行。 它不是实时或当前时间量度。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期范围均在 [!DNL UTC] 时区。 请参阅 [时区Audience Manager](../reference/aam-time-zones.md).

## 日期范围间隔中的数据 {#date-range-intervals}

的 [!UICONTROL Addressable Audience] 和 [!UICONTROL Destination] 量度会返回在选定时间间隔内的独特用户计数。 例如，访客只被计数一次，即使他们多次访问您的网站。 第一次访问是独特访问并被记录。 后续访问是回访，并且不会计数，因为它们并不唯一。

日期范围包含选定时间间隔或更早时间段的数据。 而且，数据会随着时间的流逝而在每个报表间隔之外老化。 例如，假设您在选择 [!UICONTROL Last 30 Days] 选项。 在报表中，这些访客：

* *将为* 包含在较长时间间隔（60天、90天和生命周期）返回的结果中。
* *不会* 包含在 [!UICONTROL Last 30 Day] 选项（当前、7天和14天）。

而在第31天，这些访客仅在60天、90天和 [!UICONTROL Lifetime] 结果。 他们在30天的间隔中已经老了。 访客不会在 [!UICONTROL Lifetime] 间隔。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本节介绍提供的量度类型 [!UICONTROL Addressable Audiences].

### 客户级别量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些量度会返回访客访问您的网站或将入站数据文件发送至的特征的数据 [!DNL Audience Manager]. 这些量度可全面了解您帐户的受众规模。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 已实现 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 在回顾窗口和设备期间，无论同步的时间如何，我们都已与选定的目标进行ID同步。<br><br>此量度表示设备满足以下条件：<ul><li>已经意识到 [!UICONTROL rule-based] 或 [!UICONTROL onboarded trait] 回顾窗口期间 `AND`</li><li>与所选的同步ID [!UICONTROL destination] 无论同步的时间。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已实现 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 从脱机文件。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 区段级别匹配量度 {#segment-level-metrics}

这些量度将返回 [!UICONTROL segment] 会员资格。 它们有助于更精细、更准确地查看每个 [!UICONTROL segments].

>[!NOTE]
>
>在 [!UICONTROL segment] 级别与客户级别不同。 访客可以访问网站，并实现 [!UICONTROL trait] 10天前，他们有资格 [!UICONTROL segment] 从那时起就退出了 [!UICONTROL segment] 2天前。 应用7天回顾时，这些访客将计入 [!UICONTROL segment] 级别，但不在客户级别。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 属于 [!UICONTROL segment] 在报表回顾期间，且您的网站上具有活动ID同步。 区段可以通过 [!UICONTROL traits] 在 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>提示：当与1天回顾期一起使用时，此量度可以帮助您了解 [!UICONTROL segments]. 这是因为 [!UICONTROL Segment Addressable Audience] 量度表示在 [!UICONTROL segment] 前一天。 结合以下事实 [!DNL Audience Manager] 刷新 [!UICONTROL Addressable Audiences] 每日，结合此量度和回顾期可提供您的最新快照 [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | 属于您的 [!UICONTROL segment] 在报表回顾期间。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台级别量度 {#platform-level-metrics}

此量度可返回所有收集的活动数据 [!DNL Audience Manager] 客户。 与汇总的 [!DNL Audience Manager] 客户。

| 量度 | 描述 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 对与所有设备进行交互的设备的计数 [!DNL Audience Manager] 报表回顾期间在平台级别的客户，且可能与您选择的 [!UICONTROL destination]. <br><br>此量度非常有用，因为它会向您显示：<ul><li>的大小 [!UICONTROL total addressable audience] the [!DNL Audience Manager] 可以访问特定定位目标。</li><li>多大 [!DNL Audience Manager] 配置文件池用于定位平台及其受众的大小。</li></ul> |

## 比较 [!UICONTROL Customer] 和 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不应将 [!UICONTROL Customer Addressable Audience] 和 [!UICONTROL Segment Addressable Audience] 量度来确定其中一个比另一个重要。 这些量度是单独的、不同的和独立的量度。 如上面的定义所述，其中每个数据集都源自不同的数据集。 鉴于此，如果一个量度大于另一个量度，则应避免得出任何结论。 在比较这些值时，您只能说：

* [!UICONTROL Customer Addressable Audiences] 基于 [!UICONTROL trait] 实现 *针对您自己的第一方数据*. 此量度可全面全面地概述您与数据合作伙伴的集成。

* [!UICONTROL Segment Addressable Audiences] 基于区段资格 *，以及第二方和第三方数据*. 此量度可提供更精确的粒度视图 [!UICONTROL addressable audiences] 定位平台中。

## 匹配率较低的原因 [!UICONTROL Addressable Audiences] {#low-match-rates}

对低负责的常见元素 [!UICONTROL Addressable Audience] 匹配率或报告数字中的差异。

| 原因 | 描述 |
|---|---|
| 移动流量 | 最多 [!UICONTROL server-to-server] 集成依赖由第三方提供的同步过程 [!DNL cookies]. 但是，移动设备环境不使用第三方 [!DNL cookies]. 因此，您的 [!UICONTROL Addressable Audiences] 数字与 [!UICONTROL segment] 大小。 <br><br>自2018年1月起，您可以在同一 [!DNL Google] 和 [!DNL Adobe Advertising Cloud] 目标设置 [!UICONTROL cookie-based] 受众。 而这意味着您可以 [!UICONTROL segments] 组合 [!DNL cookie] 和移动ID会员资格 [!DNL Google] 和 [!DNL Advertising Cloud] 目标，请记住 [!UICONTROL Addressable Audiences] 仅显示 [!DNL cookie] ID和目标。 [!DNL Audience Manager] 向 [!UICONTROL destinations]，但移动设备受众不受 [!UICONTROL Addressable Audience] 量度。 <br><br>**注意**:例如， [!UICONTROL segment] 人口有100万。 如果映射此 [!UICONTROL segment] 至 [!DNL Google] 或 [!DNL Adobe Advertising Cloud] 目标，您可能会看到 [!UICONTROL Addressable Audience] 70万台设备和 [!UICONTROL Match Rate] 70%。 70万会员包括 [!DNL cookie] ID与 [!UICONTROL destination]. 您的 [!UICONTROL Addressable Audience] 事实上可能要高得多，因为可寻址移动ID不显示在此量度中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 阻止第三方 [!DNL cookies]. 这可防止 [!DNL Audience Manager] 从将ID与 [!UICONTROL destination]. 通过 [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)，您可以 [!UICONTROL addressable audiences] 不包含 [!DNL Safari] 用户。 |
| 跟踪的媒体展示次数 | 由于广告服务器最佳实践，广告标记中不会进行ID同步。 执行大量域外广告的客户将无法将用户与这些环境中的第三方集成同步。 此外，大量收集的媒体展示数据可能会减少 [!UICONTROL addressable audience] 数字。 |

## 疑难解答 [!UICONTROL Addressable Audiences] {#troubleshooting}

除了显示匹配率外，您还可以使用 [!UICONTROL Addressable Audiences] 作为故障诊断工具。

例如，假设您将区段发送到 [!UICONTROL destination] 和 [!UICONTROL destination] 显示低报表数。 检查 [!UICONTROL Addressable Audience] 结果将显示这是技术问题还是仅是匹配率较低的情况。 低匹配率显示 [!UICONTROL destination] 并不是对您选定的区段都那么好。 但是， [!UICONTROL total addressable audience] 介于 [!DNL Audience Manager] 和 [!UICONTROL destination] 表示集成、同步或其他技术问题。 在这些情况下，请联系您的客户经理。
