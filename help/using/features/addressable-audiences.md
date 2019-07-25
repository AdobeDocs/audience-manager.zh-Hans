---
description: 可寻址受众功能和用例的概述。
keywords: DIL
seo-description: 可寻址受众功能和用例的概述。
seo-title: 可寻址受众
solution: Audience Manager
title: 可寻址受众
topic: DIL API
uuid: 3eb1335a-6949-452b-b77 a-697c2256 cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

可寻址受众功能和用例的概述。

## What is an Addressable Audience? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 该功能显示您在所有属性中看到的受众之间的重叠，这些属性 [!DNL Audience Manager] 在集合中收集数据和选定目标。为帮助您理解此概念，请参阅下面的插图。每个圆之间的重叠表示不同类型的可寻址受众。

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
   <td colname="col1"> <p> <b>Audience Manager面向目标的受众受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期内与所有Audience Manager客户交互的所有设备的计数，该计算时间可与选定目标相匹配。 </p> <p>此量度很有用，因为它会显示您： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager</span> 可在特定目标目标上访问的可寻址受众总数。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055"><span class="keyword"> Audience Manager</span> 档案池的大小针对定位平台和受众规模。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中已经认识到基于规则的特征或脱机文件中的随附特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>可解决的受众匹配率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口和设备期间已识别基于规则的特征或带载入特征的设备的重叠计数，而不管同步的时间如何，我们都有ID与选定目标同步。 </p> 
    </draft-comment> <p>此量度表示以下设备： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">无论同步的时间如何，都可以与所选目标同步ID。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众›客户总受众表示为%。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>总细分人口</b> </p> </td> 
   <td colname="col2"> <p>报表回顾期间属于区段成员的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>细分地址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间内属于区段并在您的站点上具有有效ID同步的用户数。Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>提示：与天回顾期一起使用时，此量度可帮助您了解区段的当前状态。This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>区段可寻址受众：表示为%的受众总数。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

[!UICONTROL Addressable Audience] 该功能将此抽象概念转变为可量化的数据。In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences]**[!UICONTROL Audience Data > Destinations]**&#x200B;所处位置。Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

您可以在“可寻址受众登陆页面”上看到的三个指标表示：

| 量度 | 描述 |
---------|----------|
| **可寻址受众(设备)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **匹配率** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **终身可解决的受众(设备)** | 在报告回顾期内与所有Audience Manager客户互动的所有设备的计数，并且可以与此目标匹配。See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

单击服务器到服务器目标的名称可查看您的可寻址受众数据。注意，此功能只返回服务器到服务器目标的数据，访问权限需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可帮助您：

* **预测和规划：**[!UICONTROL Segment Addressable Audience] 数据为您计划发送到目标受众定位和激活目标的细分提供更多粒度。

* **性能评论：** 该 [!UICONTROL Addressable Audiences] 功能也是疑难解答工具。它可让您查看营销活动的效果、了解营销活动触及范围，并在未看到期望结果的情况下与定位/激活合作伙伴交叉检查。

### 使用第三方数据和对匹配率的影响

购买第三方数据进行受众赢取之前，客户可以验证与其他数据提供商的重叠。这有助于您在购买新数据之前做出明智决策。The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. [!DNL Adobe] 您的顾问可以帮助您识别其他相关数据源，以优化探索活动。

### 移动用户和匹配率

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. 日期范围选项包括：

* [!UICONTROL Last 1 Day] (此时间间隔从午夜24小时到24小时的午夜之间运行。它不是实时的或当前的指标。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

[!UICONTROL Addressable Audience][!UICONTROL Destination] 和指标可在选定的时间间隔内返回唯一用户计数。例如，访客只计数一次，即使多次访问您的网站也是如此。第一次访问是唯一的访问和记录。后续访问正在返回访问，因为它们并非唯一的访问。

日期范围包含选定时间间隔或较早版本的数据。而且，随着时间的过去，每个报告间隔都会超时。For example, let's assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. 在报告中，这些访客：

* *将* 包含在较长时间间隔(60天、90天和生命周期)返回的结果中。
* *不会* 包含在 [!UICONTROL Last 30 Day] 选项前面的较短间隔内(当前、天和14天)。

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. 他们已经经历了30天的间隔。Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. 这些指标全面了解您的帐户的受众规模。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>可接触客户的受众</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口和设备期间已识别基于规则的特征或带载入特征的设备的重叠计数，而不管同步的时间如何，我们都有ID与选定目标同步。 </p> 
    </draft-comment> <p>此量度表示以下设备： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">无论同步的时间如何，都可以与所选目标同步ID。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中已经认识到基于规则的特征或脱机文件中的随附特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众›客户总受众表示为%。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

这些指标返回细分会员资格的数据。它们有助于更精细、准确地查看每个细分的受众规模。

>[!NOTE]
>
>回顾窗口在细分级别上的应用方式与客户级别不同。访客可在10天前进入该网站并实现特征，此后他们可以获得一个区段，并在2天前退出该区段。应用天回顾后，这些访客将计入细分级别，但不计入客户级别。

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>细分地址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间内属于区段并在您的站点上具有有效ID同步的用户数。Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>提示：与天回顾期一起使用时，此量度可帮助您了解区段的当前状态。This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>总细分人口</b> </p> </td> 
   <td colname="col2"> <p>报表回顾期间属于区段成员的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>区段可寻址受众：表示为%的受众总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

此量度返回在所有Audience Manager客户中收集的活动数据。与聚集的Audience Manager客户相比，他们可以提供更广泛的客户受众视图。

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager的可寻址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期内与所有Audience Manager客户交互的所有设备的计数，该计算时间可与选定目标相匹配。 </p> <p>此量度很有用，因为它会显示您： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager</span> 可在特定目标目标上访问的可寻址受众总数。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055"><span class="keyword"> Audience Manager</span> 档案池的大小针对定位平台和受众规模。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn't compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. 这些是独立、不同和独立的指标。如上述定义中所述，每个都来自不同的数据集。鉴于这一点，如果一个指标大于另一个指标，您应避免推断任何结论。进行比较时，您只能说：

* [!UICONTROL Customer Addressable Audiences] 基于特征实时实现 *，即一手数据*。此指标全面、全面地了解了与数据合作伙伴的集成。

* [!UICONTROL Segment Addressable Audiences] 基于您自己的第一方数据、第二方和第三方数据的细分资格 **。此指标可为定位平台中的可寻址受众提供更准确、更准确的视图。

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

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
   <td colname="col1"> <p> <b>移动通信</b> </p> </td> 
   <td colname="col2"> <p>大多数服务器到服务器集成依赖于第三方Cookie推动的同步流程。但是，移动环境不使用第三方cookie。因此，与细分规模相比，您的潜在受众数量看起来可能较低。 </p> <p>自2018年月起，您可以在同一Google和Adobe Advertising Cloud目标中激活面向基于cookie的受众的移动受众。虽然这意味着您可以将带有组合Cookie和移动ID会员资格的区段发送到您的Google和Advertising Cloud目标，但请记住，可寻址受众只会显示cookie ID与目标之间的重叠。Audience Manager将100%的移动受众发送到目标，但移动受众不是由“可寻址受众”指标衡量的。 </p> <p> <p><b>注意</b>：例如，获取1，000,000人口的区段。如果将此区段映射到Google或Adobe Advertising Cloud目标，您可能会看到可寻址的700，000台设备的潜在受众，并且匹配率为70%。700，000的会员资格由Cookie ID组成，其ID与目标同步。实际上，您的可寻址受众更高，因为可寻址的移动ID不会出现在此指标中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari流量</b> </p> </td> 
   <td colname="col2"> <p>Safari阻止第三方cookie。这会阻止Audience Manager与目标同步ID。With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>跟踪媒体印象</b> </p> </td> 
   <td colname="col2"> <p>由于广告服务器最佳实践，ID同步不是在广告标签中进行的。在这些环境中完成大量场外广告的客户不会将用户与第三方集成同步。此外，大量收集的媒体印象数据可以减少可寻址受众数量。 </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

例如，假设您将区段发送到目标，目标显示较低的报表编号。Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. 低匹配率会显示您的目标对您所选的区段并非所有内容都很好。但是，Audience Manager与目标之间的可寻址受众总数差异表示集成、同步或其他技术问题。在这些情况下，请联系您的客户经理。