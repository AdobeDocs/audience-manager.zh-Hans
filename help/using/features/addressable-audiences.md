---
description: 可寻址受众功能和使用案例的概述。
keywords: DIL
seo-description: 可寻址受众功能和使用案例的概述。
seo-title: 可寻址受众
solution: Audience Manager
title: 可寻址受众
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# 可寻址受众 {#addressable-audiences}

可寻址受众功能和使用案例的概述。

## 什么是可寻址受众？ {#addressable-audience-description}

该功 [!UICONTROL Addressable Audiences] 能显示您在收集数据的所有属性中看到的受众与选定目标 [!DNL Audience Manager] 之间的重叠情况。 要帮助您理解此概念，请查看下面的插图。 每个圈子之间的重叠表示不同类型的可寻址受众。

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience manager的目标潜在受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间，在平台级别与所有Audience manager客户进行交互且可能与所选目标匹配的所有设备的计数。 </p> <p>此度量很有用，因为它向您显示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience manager可触及特定目标的可寻 <span class="keyword"> 址受众总数</span> 。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager配置文 <span class="keyword"></span> 件池对于定位平台和受众规模而言有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中，从脱机文件中实现基于规则的属性或已载入特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>可寻址的受众匹配率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口期间实现基于规则的特征或已载入的特征的设备的重叠计数，以及无论同步的时间如何，我们与所选目标ID都同步的设备。 </p> 
    </draft-comment> <p>此度量表示： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">已在回顾窗口 <b>AND中实现基于规则的特征或已载入的特征</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">使ID与所选目标同步，而不管同步的时间如何。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众÷客户总受众以%表示。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>区段总人数</b> </p> </td> 
   <td colname="col2"> <p>在报表回顾期间，属于您的区段成员的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>细分可寻址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间属于该区段并在您的站点上同步活动ID的用户数。 区段可以通过在Audience Marketplace中获得的特征包括您自己的第一方数据、第二方数据和第 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 三方数据</a>。 </p> <p> <p>提示：当与1天回顾期一起使用时，此指标可以帮助您了解区段的当前状态。 这是因为“区段 <span class="wintitle"> 可寻址受众</span> ”量度代表在前一天内一直在某个区段中停留的用户。 结合这一点， <span class="keyword"> Audience Manager每天刷新可寻址受众</span><span class="wintitle"></span> ，将此指标和回顾期结合在一起，可提供区段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>细分可寻址受众÷细分总人口以%表示。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## 可寻址的受众界面 {#addressable-audience-interface}

该功 [!UICONTROL Addressable Audience] 能将这个抽象概念转化为可量化的数据。 在 [!DNL Audience Manager]中，此功能显示受众与数据可视化的重叠部分，这些数据可视化以表格形式提供一览表信息以及数字数据。

[!UICONTROL Addressable Audiences] 位于 **[!UICONTROL Audience Data > Destinations]**。 选择 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可寻址的受众指标。

![](assets/addressable-audiences-landing.png)

您可以在“可寻址受众”登陆页面上看到的三个指标代表：

| 量度 | 描述 |
---------|----------|
| **可寻址受众（设备）** | 此量度表示过去30天的客户可寻 *址受众（如上表所述）。* |
| **匹配率** | 此量度表示过去30天的可寻址受众匹配率(如上 *表所述)*。 |
| **终生可寻址受众（设备）** | 在报告回顾期间与平台级所有Audience manager客户进行交互且可能与此目标匹配的所有设备的计数。 有关 [更多信息，请参阅平台级度量](/help/using/features/addressable-audiences.md#platform-level-metrics) 。 |

单击服务器到服务器目标的名称可查看可寻址的受众数据。 注意，此功能仅返回服务器到服务器目标的数据，并且访问需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可以帮助您：

* **** 预测和规划：数据 [!UICONTROL Segment Addressable Audience] 可让您更精细地了解您计划发送到目标的细分，以便进行受众定位和激活。

* **** 性能评论：该功 [!UICONTROL Addressable Audiences] 能还是一个疑难解答工具。 它允许您查看营销活动效果，了解营销活动的触及范围，并允许您与定位／激活合作伙伴进行交叉检查（如果看不到预期的结果）。

### 使用第三方数据进行发掘及其对匹配率的影响

在购买第三方数据以获取受众之前，客户可以验证与其他数据提供商的重叠。 这有助于您在购买新数据之前做出明智的决策。 购买的第三方数据的ID同步不仅依赖于数据的重叠，而且依赖于第三方提供商对所有其他客户的 [!DNL Audience Manager] 足迹。 您的 [!DNL Adobe] 顾问可以帮助您确定其他相关数据源以优化潜在客户活动。

### 移动用户和匹配率

尝试连接没有第三方Cookie [!DNL Safari] 的或移动App用户时存在间隙。 这使得用户难以与某些合作伙伴同步，因为媒体交付日志中只提供同步的第 [!DNL Adobe] 三方Cookie的ID。 这也是您可能发现目标 [匹配率较低](../features/addressable-audiences.md#low-match-rates) 的原因。

##  可寻址受众和目标中的日期范围 {#date-ranges}

请阅读以下各节，了解可用日期范围以及数据在报表中的每个间隔之外的使用 [!UICONTROL Addressable Audience] 方式 [!UICONTROL Destination]。

## 可用日期范围和时区 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您和目标的 [!UICONTROL Addressable Audiences] 报 [表使用相同的日期范围](../features/destinations/destinations.md) 。 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此间隔从前一个24小时时间段的午夜到午夜。 它不是实时或当前时间指标。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期范围均在时区 [!DNL UTC] 中设置。 请参 [阅Audience manager中的时区](../reference/aam-time-zones.md)。

## 日期范围间隔中的数据 {#date-range-intervals}

该和 [!UICONTROL Addressable Audience] 度 [!UICONTROL Destination] 量将返回选定时间间隔内的唯一用户计数。 例如，访客只计数一次，即使他们多次访问您的网站。 第一次访问是唯一的访问并记录。 后续访问是返回访问，并且不计数，因为它们并不唯一。

日期范围包含选定时间间隔或更早时间段的数据。 而且，随着时间的流逝，数据会在每个报告间隔之外老化。 例如，假设您在选择选项后看到2个访 [!UICONTROL Last 30 Days] 客。 在报告中，这些访客：

* *将包含在* （60天、90天和生命周期）较长的时间间隔返回的结果中。
* *不会包含在* （当前、7天和14天）选 [!UICONTROL Last 30 Day] 项之前的较短间隔中。

而在第31天，这些访客只在60天、90天和结果中出现 [!UICONTROL Lifetime] 。 他们在30天的间隔期中已经老了。 访客不会在间隔内过 [!UICONTROL Lifetime] 时。

##  可寻址的受众指标 {#addressable-audience-metrics}

本节介绍提供的度量类型 [!UICONTROL Addressable Audiences]。

### 客户级指标 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些指标返回访客访问您的网站或将入站数据文件发送到时所实现的特征的数据 [!DNL Audience Manager]。 这些指标全面了解您帐户的受众规模。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>客户可寻求的受众</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口期间实现基于规则的特征或已载入的特征的设备的重叠计数，以及无论同步的时间如何，我们与所选目标ID都同步的设备。 </p> 
    </draft-comment> <p>此度量表示： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">已在回顾窗口 <b>AND中实现基于规则的特征或已载入的特征</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">使ID与所选目标同步，而不管同步的时间如何。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中，从脱机文件中实现基于规则的属性或已载入特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众÷客户总受众以%表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 区段级匹配指标 {#segment-level-metrics}

这些指标会返回有关细分会员资格的数据。 它们有助于更精细、更准确地查看每个细分的受众规模。

>[!NOTE]
>
>在区段级别应用回顾窗口的方式与在客户级别不同。 访客可以在10天前访问网站并了解某个特征，并且自那之后他们就有资格访问某个区段，并在2天前从该区段中删除。 应用7天回顾后，这些访客将计入区段级别，而不计入客户级别。

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>细分可寻址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间属于该区段并在您的站点上同步活动ID的用户数。 区段可以通过在Audience Marketplace中获得的特征包括您自己的第一方数据、第二方数据和第 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 三方数据</a>。 </p> <p> <p>提示：当与1天回顾期一起使用时，此指标可以帮助您了解区段的当前状态。 这是因为“区段 <span class="wintitle"> 可寻址受众</span> ”量度代表在前一天内一直在某个区段中停留的用户。 结合这一点， <span class="keyword"> Audience Manager每天刷新可寻址受众</span><span class="wintitle"></span> ，将此指标和回顾期结合在一起，可提供区段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段总人数</b> </p> </td> 
   <td colname="col2"> <p>在报表回顾期间，属于您的区段的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>细分可寻址受众÷细分总人口以%表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 平台级指标 {#platform-level-metrics}

此指标可返回所有Audience manager客户中收集的活动的数据。 与汇总的Audience manager客户相比，它们可以更全面地了解客户的受众。

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience manager的潜在受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间，在平台级别与所有Audience manager客户进行交互且可能与所选目标匹配的所有设备的计数。 </p> <p>此度量很有用，因为它向您显示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience manager可触及特定目标的可寻 <span class="keyword"> 址受众总数</span> 。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager配置文 <span class="keyword"></span> 件池对于定位平台和受众规模而言有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 比较客户和细分可寻址受众{#comparing-metrics}

您不应该比较和 [!UICONTROL Customer Addressable Audience] 度量 [!UICONTROL Segment Addressable Audience] 来确定其中一个是否比另一个重要。 这些是单独、不同和独立的指标。 如上述定义所述，每个数据集都源自不同的数据集。 因此，如果一个指标大于另一个指标，您应避免得出任何结论。 在比较这些内容时，您只能说：

* [!UICONTROL Customer Addressable Audiences] 基于您自己的第 *一方数据的特征实现*。 此指标全面地介绍了您与数据合作伙伴的集成情况。

* [!UICONTROL Segment Addressable Audiences] 基于您自己的第 *一方数据的细分资格以及第二方和第三方数据*。 此指标提供了一个更精细、更准确的定位平台中潜在受众视图。

## 潜在受众匹配率低的原因 {#low-match-rates}

导致匹配率低或报 [!UICONTROL Addressable Audience] 告数字出现差异的常见元素。

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>移动流量</b> </p> </td> 
   <td colname="col2"> <p>大多数服务器到服务器集成都依赖于第三方cookie所推动的同步过程。 但是，移动环境不使用第三方Cookie。 因此，与区段大小相比，您的可寻址受众数量可能看起来较低。 </p> <p>自2018年1月起，您可以在为基于cookie的受众设置的同一Google和Adobe Advertising Cloud目标中激活移动受众。 这意味着您可以将具有组合Cookie和移动ID会员资格的区段发送到您的Google和Advertising cloud目标，但请记住，“可寻址受众”仅显示Cookie ID与目标之间的重叠。 Audience manager将100%的移动受众发送到目标，但移动受众不会通过可寻址受众指标来衡量。 </p> <p> <p><b>注意</b>: 例如，以人口为1,000,000的区段为例。 如果将此细分映射到Google或Adobe Advertising cloud目标，您可能会看到700,000台设备的可寻址受众和70%的匹配率。 700,000的会员资格由Cookie ID组成，这些ID与目标同步。 实际上，您的可寻址受众可能更高，因为可寻址移动ID不显示在此指标中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari流量</b> </p> </td> 
   <td colname="col2"> <p>Safari会阻止第三方Cookie。 这会阻止Audience manager将ID与目标同步。 通过推出 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>，您可以期望潜在的受众不包括Safari用户。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>跟踪的媒体印象</b> </p> </td> 
   <td colname="col2"> <p>由于广告服务器最佳实践，ID同步不会在广告标记内进行。 进行大量非现场广告的客户不会将用户同步到这些环境中的第三方集成。 此外，大量收集的媒体印象数据可能会减少可寻址的受众数量。 </p> </td>
  </tr> 
 </tbody> 
</table>

## 可寻址受众疑难解答 {#troubleshooting}

除了表示匹配率外，您还可以将其用 [!UICONTROL Addressable Audiences] 作故障排除工具。

<!-- addressable-audiences-troubleshooting.xml -->

例如，假设您将区段发送到目标，而该目标显示的报告数量较低。 检查结 [!UICONTROL Addressable Audience] 果将显示这是技术问题还是只是匹配率低的问题。 低匹配率表明目标对于选定的区段来说并不是那么好。 但是，Audience Manager与目标之间的可寻址总受众数的差异表明存在集成、同步或其他技术问题。 在这些情况下，请与您的客户经理联系。