---
description: “可寻址受众”功能及用例的概述。
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
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience]功能和用例概述。

## 什么是[!UICONTROL Addressable Audience]？{#addressable-audience-description}

[!UICONTROL Addressable Audiences]功能显示您在[!DNL Audience Manager]收集数据的所有属性中看到的受众与您选择的目标之间的重叠。 为了帮助您了解此概念，请看下图。 每个圆圈之间的重叠部分表示不同类型的可寻址受众。

![](assets/addressableAudienceVenn.png)


| 量度 | 描述 |
|---|---|
| [!UICONTROL Destination]的[!UICONTROL Audience Manager Addressable Audience] | 在报表回顾期间在平台级别与所有[!DNL Audience Manager]客户交互并且可能与您选择的[!UICONTROL destination]匹配的所有设备的计数。 <br><br>此量度非常有用，因为它向您显示： <ul><li>[!DNL Audience Manager]在特定目标[!UICONTROL destination]上可达到的总[!UICONTROL addressable audience]的大小。</li><li>[!DNL Audience Manager]配置文件池对于定位平台的大小及其受众的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾时间范围内，已在您的属性上实现[!UICONTROL rule-based trait]或从脱机文件中实现[!UICONTROL onboarded trait]的设备计数。 |
| [!UICONTROL Customer Addressable Audience] | 在回顾时间范围内实现[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的设备以及我们与所选[!UICONTROL destination]具有ID同步的设备的重叠计数，不考虑同步时间。<br><br>此量度表示设备：<ul><li>已在回顾时间范围`AND`中实现[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>具有与所选[!UICONTROL destination]同步的ID，而不考虑同步时间。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]÷[!UICONTROL Customer Total Audience]以百分比表示。 |
| [!UICONTROL Total Segment Population] | 报表回顾期间属于[!UICONTROL segment]成员的所有设备的计数。 |
| [!UICONTROL Segment Addressable Audience] | 在报表回顾期间属于[!UICONTROL segment]且在您的网站上具有活动ID同步的用户数。 [!UICONTROL Segments]可以通过在[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)中获取的[!UICONTROL traits]包含您自己的第一方数据以及第二方和第三方数据。 <br><br>提示：与1天回顾期一起使用时，此量度可以帮助您了解[!UICONTROL segments]的当前状态。 这是因为[!UICONTROL Segment Addressable Audience]量度表示前一天在[!UICONTROL segment]中停留的用户。 结合以下事实：[!DNL Audience Manager]每天刷新[!UICONTROL Addressable Audiences]，结合此量度和回顾期间可提供您[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]÷[!UICONTROL Total Segment Population]以百分比表示。 |

## [!UICONTROL Addressable Audiences]接口 {#addressable-audience-interface}

[!UICONTROL Addressable Audience]功能将此抽象概念转换为可量化数据。 在[!DNL Audience Manager]中，此功能显示受众与数据可视化图表的重叠，这些数据可视化图表提供一目了然的信息以及表格形式的数字数据。

[!UICONTROL Addressable Audiences]位于&#x200B;**[!UICONTROL Audience Data > Destinations]**&#x200B;中。 选择&#x200B;**[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;查看可寻址受众量度。

![](assets/addressable-audiences-landing.png)

您可以在[!UICONTROL Addressable Audiences]登陆页面上看到的三个量度表示：

| 量度 | 描述 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度表示过去30天的[!UICONTROL Customer Addressable Audience]（如上表所述）*。* |
| **[!UICONTROL Match Rate]** | 此量度表示过去30天&#x200B;*的[!UICONTROL Addressable Audience Match Rate]（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在报表回顾期间在平台级别与所有[!DNL Audience Manager]客户交互并且可能与此[!UICONTROL destination]匹配的所有设备的计数。 有关详细信息，请参阅[平台级别量度](/help/using/features/addressable-audiences.md#platform-level-metrics)。 |

单击[!UICONTROL server-to-server destination]的名称可查看可寻址受众数据。 请注意，此功能仅返回[!UICONTROL server-to-server destinations]的数据，访问需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可以帮助您：

* **预测和规划：** [!UICONTROL Segment Addressable Audience]数据为您提供了更多粒度，让您能够了解计划发送到目标以进行受众定位和激活的区段。

* **性能审核：** [!UICONTROL Addressable Audiences]功能也是一种故障排除工具。 通过它，您可以审查营销活动效果，了解营销活动覆盖范围，如果没有看到预期的结果，还可以与定位/激活合作伙伴进行交叉检查。

### 利用第三方数据发现潜在客户以及对匹配率的影响

在购买第三方数据以进行受众获取之前，客户可以验证与其他数据提供商的重叠之处。 这有助于您在购买新数据之前做出明智的决策。 所购买的第三方数据的ID同步不仅依赖于您的数据重叠，还依赖于第三方提供商与所有其他[!DNL Audience Manager]客户的脚注。 您的[!DNL Adobe]顾问可以帮助您确定其他相关数据源，以优化潜在客户活动。

### 移动用户和匹配率

尝试连接[!DNL Safari]或没有第三方[!DNL cookies]的移动应用用户时存在间隙。 这样将很难将用户与某些合作伙伴同步，因为媒体投放日志中仅提供了已同步第三方[!DNL cookies]的[!DNL Adobe] ID。 这就是为什么您可能会看到[!UICONTROL destinations]的[低匹配率](../features/addressable-audiences.md#low-match-rates)的原因。

## [!UICONTROL Addressable Audiences]和[!UICONTROL Destinations]中的日期范围 {#date-ranges}

请阅读以下各节，了解[!UICONTROL Addressable Audience]或[!UICONTROL Destination]的可用日期范围以及报表中数据如何在每个间隔内过期。

## 可用日期范围和时区 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences]和[目标](../features/destinations/destinations.md)的报告使用相同的日期范围间隔。 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此间隔从前24小时的午夜到午夜运行。 它不是实时或当前量度。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期范围都设定在[!DNL UTC]时区内。 查看Audience Manager[&#128279;](../reference/aam-time-zones.md)中的时区。

## 日期范围间隔中的数据 {#date-range-intervals}

[!UICONTROL Addressable Audience]和[!UICONTROL Destination]量度返回选定时间间隔内的独特用户计数。 例如，一位访客仅计数一次，即使他们多次访问您的网站也是如此。 第一次访问是独一无二的访问，会被记录。 后续访问属于回访，由于不唯一，因此不计算在内。

日期范围包含选定时间间隔或更早时间范围的数据。 而且，随着时间推移，数据会超过每个报表时间间隔。 例如，假设您在选择[!UICONTROL Last 30 Days]选项后看到2位访客。 在报表中，这些访客将：

* *将包含在较长时间间隔（60天、90天和存留期）返回的结果中*。
* *不会包含在[!UICONTROL Last 30 Day]选项之前的较短间隔内（当前、7天和14天）*。

在第31天，这些访客仅在60天、90天和[!UICONTROL Lifetime]个结果中显示。 他们已超过30天间隔。 访客不会超过[!UICONTROL Lifetime]间隔。

## [!UICONTROL Addressable Audiences]个量度 {#addressable-audience-metrics}

此部分介绍[!UICONTROL Addressable Audiences]提供的度量类型。

### 客户级别量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些量度会返回访客访问您的网站或向[!DNL Audience Manager]发送入站数据文件时所实现特征的数据。 这些量度为您的帐户提供受众规模的全面视图。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顾时间范围内实现[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的设备以及我们与所选目标具有ID同步的设备的重叠计数，不考虑同步时间。<br><br>此量度表示设备：<ul><li>已在回顾时间范围`AND`中实现[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>具有与所选[!UICONTROL destination]同步的ID，而不考虑同步时间。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顾时间范围内，已在您的属性上实现[!UICONTROL rule-based trait]或从脱机文件中实现[!UICONTROL onboarded trait]的设备计数。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]÷[!UICONTROL Customer Total Audience]以百分比表示。 |

### 区段级别匹配量度 {#segment-level-metrics}

这些量度返回[!UICONTROL segment]成员资格的数据。 它们有助于提供每个[!UICONTROL segments]的受众规模的更细粒度和更准确的视图。

>[!NOTE]
>
>在[!UICONTROL segment]级别应用回顾窗口的方式与客户级别的应用方式不同。 访客可在10天前访问网站并实现[!UICONTROL trait]，此后即可符合[!UICONTROL segment]资格并退出[!UICONTROL segment] 2天前。 当应用7天回顾时，这些访客将在[!UICONTROL segment]级别进行计数，但不在客户级别进行计数。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 在报表回顾期间属于[!UICONTROL segment]且在您的网站上具有活动ID同步的用户数。 通过在[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)中获取的[!UICONTROL traits]，区段可以包括您自己的第一方数据以及第二方数据和第三方数据。<br><br>提示：与1天回顾期一起使用时，此量度可以帮助您了解[!UICONTROL segments]的当前状态。 这是因为[!UICONTROL Segment Addressable Audience]量度表示前一天在[!UICONTROL segment]中停留的用户。 结合以下事实：[!DNL Audience Manager]每天刷新[!UICONTROL Addressable Audiences]，结合此量度和回顾期间可提供您[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Total Segment Population] | 报表回顾期间属于[!UICONTROL segment]成员的所有设备的计数。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]÷[!UICONTROL Total Segment Population]以百分比表示。 |

### 平台级别的量度 {#platform-level-metrics}

此量度返回有关在所有[!DNL Audience Manager]客户中收集的活动数据。 与汇总的[!DNL Audience Manager]客户相比，他们可以更全面地查看客户的受众。

| 量度 | 描述 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在报表回顾期间在平台级别与所有[!DNL Audience Manager]客户交互并且可能与您选择的[!UICONTROL destination]匹配的所有设备的计数。 <br><br>此量度非常有用，因为它向您显示：<ul><li>[!DNL Audience Manager]可以到达特定目标位置的[!UICONTROL total addressable audience]的大小。</li><li>[!DNL Audience Manager]配置文件池对于定位平台的大小及其受众的大小。</li></ul> |

## 正在比较[!UICONTROL Customer]和[!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

不应比较[!UICONTROL Customer Addressable Audience]和[!UICONTROL Segment Addressable Audience]量度以确定一个量度是否比另一个量度更重要。 这些是不同的、独立的量度。 如上述定义中所述，其中每个数据源自不同的数据集。 因此，如果一个量度大于另一个量度，则应避免得出任何结论。 在比较这些内容时，你能说的是：

* [!UICONTROL Customer Addressable Audiences]基于您自己的第一方数据&#x200B;*的[!UICONTROL trait]实现*。 此量度可让您广泛、全面地了解您与数据合作伙伴的集成。

* [!UICONTROL Segment Addressable Audiences]基于您自己的第一方数据的区段资格&#x200B;*以及第二方和第三方数据*。 此量度可让您在定位平台上更精确地查看[!UICONTROL addressable audiences]。

## [!UICONTROL Addressable Audiences]匹配率较低的原因 {#low-match-rates}

导致低[!UICONTROL Addressable Audience]匹配率或报告数量差异的通用元素。

| 原因 | 描述 |
|---|---|
| 移动流量 | 大多数[!UICONTROL server-to-server]集成都依赖于第三方[!DNL cookies]所促成的同步进程。 但是，移动环境不使用第三方[!DNL cookies]。 因此，与[!UICONTROL segment]大小相比，您的[!UICONTROL Addressable Audiences]数字可能显得太小。 <br><br>自2018年1月起，您可以在为[!UICONTROL cookie-based]受众设置的相同[!DNL Google]和[!DNL Adobe Advertising Cloud]目标中激活移动设备受众。 虽然这意味着您可以将[!UICONTROL segments]以及合并的[!DNL cookie]和移动ID成员资格发送到您的[!DNL Google]和[!DNL Advertising Cloud]目标，但请注意，[!UICONTROL Addressable Audiences]仅显示[!DNL cookie] ID与目标之间的重叠。 [!DNL Audience Manager]将100%的移动设备受众发送至[!UICONTROL destinations]，但移动设备受众并非由[!UICONTROL Addressable Audience]指标测量。 <br><br>**注意**：例如，取总人口为1,000,000的[!UICONTROL segment]。 如果将此[!UICONTROL segment]映射到[!DNL Google]或[!DNL Adobe Advertising Cloud]目标，您可能会看到700,000台设备的[!UICONTROL Addressable Audience]和70%的[!UICONTROL Match Rate]。 700,000成员资格由[!DNL cookie] ID组成，这些ID与[!UICONTROL destination]同步。 实际上，您的[!UICONTROL Addressable Audience]可能更高，因为可寻址移动ID未出现在此量度中。 |
| [!DNL Safari]流量 | [!DNL Safari]阻止第三方[!DNL cookies]。 这会阻止[!DNL Audience Manager]与[!UICONTROL destination]同步ID。 随着[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)的引入，您可以期望您的[!UICONTROL addressable audiences]不包含[!DNL Safari]用户。 |
| 跟踪的媒体展示次数 | 由于广告服务器最佳实践，无法在广告标记中进行ID同步。 进行大量站外广告的客户不会将用户同步到这些环境中的第三方集成。 此外，大量收集的媒体展示数据可能会减少[!UICONTROL addressable audience]个数字。 |

## [!UICONTROL Addressable Audiences]疑难解答 {#troubleshooting}

除了显示匹配率之外，您还可以使用[!UICONTROL Addressable Audiences]作为故障排除工具。

例如，假设您向[!UICONTROL destination]发送了一个区段，但[!UICONTROL destination]显示的报表数量较低。 检查[!UICONTROL Addressable Audience]结果将显示这是技术问题，还是匹配率较低。 低匹配率表明您的[!UICONTROL destination]对于您选择的区段并不是那么好。 但是，[!DNL Audience Manager]和[!UICONTROL destination]之间的[!UICONTROL total addressable audience]数字的差异表示存在集成、同步或其他技术问题。 在这些情况下，请联系您的客户经理。
