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
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# 可寻址受众 {#addressable-audiences}

功能和用 [!UICONTROL Addressable Audience] 例的概述。

## 什么是可寻址受众? {#addressable-audience-description}

该功 [!UICONTROL Addressable Audiences] 能显示您在收集受众的所有属性和选定目标中 [!DNL Audience Manager] 看到的数据之间的重叠。 要帮助您理解此概念，请查看下面的插图。 每个圆之间的重叠表示不同类型的可寻址受众。

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
   <td colname="col1"> <p> <b>Audience Manager的目标可寻址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间与平台级所有Audience Manager客户进行交互且可能与您所选目标匹配的所有设备的计数。 </p> <p>此度量很有用，因为它向您显示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> 受众可在特定目标上访问的 <span class="keyword"> 总可</span> 寻址Audience Manager的大小。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager <span class="keyword"> 用户档案池对于定位平台</span> 、受众规模来说有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中，已从脱机文件中实现基于规则的属性或载入的特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>可寻址受众匹配率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口中实现了基于规则的特征或载入的特征的设备的重叠计数，以及无论同步时间如何，我们已与所选目标同步ID的设备。 </p> 
    </draft-comment> <p>此度量表示以下设备： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">已在回顾窗口AND中实现基于规则或载入的特 <b>征</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">使ID与所选目标同步，而不管同步的时间如何。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众÷客户总受众，以%表示。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>区段总人口</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间，属于您的区段的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>细分可寻址受众</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间属于该区段并在您的网站上同步活动ID的用户数。 区段可以通过Audience Marketplace中获得的特征包含您自己的第一方数据、第二方数据和第三方数 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 据</a>。 </p> <p> <p>提示： 当与1天回顾期一起使用时，此指标可以帮助您了解区段的当前状态。 这是因为“区 <span class="wintitle"> 段可寻址受众</span> ”量度表示在前一天一直停留在某个区段中的用户。 结合这一点，即 <span class="keyword"> Audience Manager每</span> 天刷新 <span class="wintitle"> “可寻址受众”</span> ，将此指标和回顾周期相结合可提供区段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>细分可寻址受众÷细分总人口以%表示。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## 可寻址受众界面 {#addressable-audience-interface}

该功 [!UICONTROL Addressable Audience] 能将这个抽象概念转化为可量化的数据。 在中 [!DNL Audience Manager]，此功能显示受众与数据可视化的重叠，这些数据可视化以表格形式提供一览表信息和数字数据。

[!UICONTROL Addressable Audiences] 位于 **[!UICONTROL Audience Data > Destinations]**。 选择 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可寻址的受众量度。

![](assets/addressable-audiences-landing.png)

您可以在登陆页上看到的三个 [!UICONTROL Addressable Audiences] 指标代表：

| 量度 | 描述 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此度量表示 [!UICONTROL Customer Addressable Audience] 过去30天(如上 *表所述)。* |
| **[!UICONTROL Match Rate]** | 此度量表 [!UICONTROL Addressable Audience Match Rate] 示过去30天 *的（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在报告回顾期间与平台级所有 [!DNL Audience Manager] 客户进行交互且可能与此目标匹配的所有设备的计数。 请参 [阅Platform级度量](/help/using/features/addressable-audiences.md#platform-level-metrics) ，以了解更多信息。 |

单击服务器到服务器目标的名称以视图可寻址的受众数据。 注意，此功能仅返回服务器到服务器目标的数据，并且访问需要管理员权限。

![](assets/addressableAudiences.png)

查看此数据可帮助您：

* **预测和规划：** [!UICONTROL Segment Addressable Audience] 数据可让您更精细地进入您计划发送到目标的受众定位和激活。

* **性能评论：** 该功 [!UICONTROL Addressable Audiences] 能还是一个疑难解答工具。 它允许您查看活动绩效、了解活动触及范围，并允许您与定位/激活合作伙伴交叉检查（如果看不到预期结果）。

### 第三方数据的潜在客户及其对匹配率的影响

在购买第三方数据进行受众获取之前，客户可以验证与其他数据提供商的重叠。 这有助于您在购买新数据之前做出明智的决策。 购买的第三方数据的ID同步不仅依赖于数据的重叠，还依赖于第三方提供商对所有其他客户的 [!DNL Audience Manager] 足迹。 您的 [!DNL Adobe] 顾问可以帮助您确定其他相关数据源以优化潜在活动。

### 移动用户和匹配率

尝试连接没有第三方 [!DNL Safari] cookie的或移动应用程序用户时存在差距。 这使得用户难以与某些合作伙伴进行同步，因 [!DNL Adobe] 为媒体投放日志中仅提供同步的第三方Cookie的ID。 这也是您可能发现目标 [匹配率](../features/addressable-audiences.md#low-match-rates) 较低的原因。

## 可寻址受众和目标中的日期范围 {#date-ranges}

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

所有日期和日期范围均在时区 [!DNL UTC] 中设置。 请参 [阅Audience Manager中的时区](../reference/aam-time-zones.md)。

## 日期范围间隔中的数据 {#date-range-intervals}

和 [!UICONTROL Addressable Audience] 度 [!UICONTROL Destination] 量返回所选时间间隔内的唯一用户计数。 例如，访客只计数一次，即使他们多次访问您的网站。 第一次访问是独特的访问并被录制。 后续访问是返回访问，不计数，因为它们并不唯一。

日期范围包含所选时间间隔或更早时间段的数据。 而且，随着时间的流逝，数据会在每个报告间隔中老化。 例如，假设您在选择选项后看到2个访客 [!UICONTROL Last 30 Days] 符。 在报告中，这些访客:

* *将包含* 在较长时间间隔（60天、90天和生命周期）返回的结果中。
* *选项* (“当前”、“7天”和“ [!UICONTROL Last 30 Day] 14天”)之前的较短时间间隔中不包括。

第31天，这些访客只在60天，90天出现，结果也 [!UICONTROL Lifetime] 是。 他们在30天的间隔期中过了年。 访客不会在间隔内过 [!UICONTROL Lifetime] 时。

## 可寻址受众指标 {#addressable-audience-metrics}

本节介绍提供的度量类型 [!UICONTROL Addressable Audiences]。

### 客户级指标 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

这些指标返回访客访问您的网站或向其发送入站数据文件时所实现特征的数据 [!DNL Audience Manager]。 这些指标为您的帐户提供了全面的受众大小视图。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>客户可寻址受众</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顾窗口中实现了基于规则的特征或载入的特征的设备的重叠计数，以及无论同步时间如何，我们已与所选目标同步ID的设备。 </p> 
    </draft-comment> <p>此度量表示以下设备： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">已在回顾窗口AND中实现基于规则或载入的特 <b>征</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">使ID与所选目标同步，而不管同步的时间如何。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户总受众</b> </p> </td> 
   <td colname="col2"> <p>在回顾窗口中，已从脱机文件中实现基于规则的属性或载入的特征的设备计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客户匹配率</b> </p> </td> 
   <td colname="col2"> <p>客户可寻址受众÷客户总受众，以%表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 细分级别匹配指标 {#segment-level-metrics}

这些指标返回有关细分会员资格的数据。 它们有助于为每个细分提供更精细、更准确的受众大小视图。

>[!NOTE]
>
>在区段级别应用回顾窗口的方式与在客户级别不同。 访客可以在10天前访问网站并了解某个特征，并且他们可以从2天前开始有资格访问某个区段并退出该区段。 应用7天回顾后，这些访客将计入细分级别，而不计入客户级别。

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
   <td colname="col2"> <p>在报告回顾期间属于该区段并在您的网站上同步活动ID的用户数。 区段可以通过Audience Marketplace中获得的特征包含您自己的第一方数据、第二方数据和第三方数 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> 据</a>。 </p> <p> <p>提示： 当与1天回顾期一起使用时，此指标可以帮助您了解区段的当前状态。 这是因为“区 <span class="wintitle"> 段可寻址受众</span> ”量度表示在前一天一直停留在某个区段中的用户。 结合这一点，即 <span class="keyword"> Audience Manager每</span> 天刷新 <span class="wintitle"> “可寻址受众”</span> ，将此指标和回顾周期相结合可提供区段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段总人口</b> </p> </td> 
   <td colname="col2"> <p>在报告回顾期间，属于您的区段的所有设备的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段匹配率</b> </p> </td> 
   <td colname="col2"> <p>细分可寻址受众÷细分总人口以%表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform级指标 {#platform-level-metrics}

此指标返回所有客户所收集的活动 [!DNL Audience Manager] 数据。 与汇总的客户相比，它们可以提供更广的客户受众 [!DNL Audience Manager] 视图。

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
   <td colname="col2"> <p>在报告回顾期间与平台级所有Audience Manager客户进行交互且可能与您所选目标匹配的所有设备的计数。 </p> <p>此度量很有用，因为它向您显示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> 受众可在特定目标上访问的 <span class="keyword"> 总可</span> 寻址Audience Manager的大小。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager <span class="keyword"> 用户档案池对于定位平台</span> 、受众规模来说有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 比较客户和细分可寻址受众{#comparing-metrics}

您不应该比较和 [!UICONTROL Customer Addressable Audience] 度量 [!UICONTROL Segment Addressable Audience] 来确定其中一个是否比另一个重要。 这些指标是单独、不同和独立的。 如上述定义所述，每个数据集都来自不同的数据集。 因此，如果一个指标大于另一个指标，您应避免得出任何结论。 在比较这些内容时，您可以说的只是：

* [!UICONTROL Customer Addressable Audiences] 基于您自己的第 *一方数据的特征实现*。 此指标为您与数据合作伙伴的集成提供了全面的视图。

* [!UICONTROL Segment Addressable Audiences] 基于您自己的第 *一方数据的细分资格以及第二方和第三方数据*。 此指标可为定位平台中的可寻址视图提供更精细、更准确的受众。

## 可寻址受众匹配率低的原因 {#low-match-rates}

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
   <td colname="col2"> <p>大多数服务器到服务器集成都依赖于第三方cookie所推动的同步过程。 但是，移动环境不使用第三方cookie。 因此，与区段大小相比，可寻址受众数可能看起来很低。 </p> <p>从2018年1月起，您可以在为基于cookie的受众设置的相同Google和AdobeAdvertising Cloud目标中激活移动受众。 这意味着您可以将具有组合Cookie和移动ID会员资格的区段发送到您的Google和Advertising Cloud目标，但请注意可寻址受众只显示Cookie ID与目标之间的重叠。 Audience Manager将100%的移动受众发送到目标，但移动受众不是通过可寻址受众量度来衡量的。 </p> <p> <p><b>注意</b>:  例如，以人口为1,000,000的细分为例。 如果将此区段映射到Google或AdobeAdvertising Cloud目标，您可能会看到700,000台设备的可寻址受众和70%的匹配率。 700,000的会员资格由Cookie ID组成，这些ID与目标同步。 事实上，您的可寻址受众可能更高，因为可寻址移动ID不会显示在此度量中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari流量</b> </p> </td> 
   <td colname="col2"> <p>Safari会阻止第三方Cookie。 这会阻止Audience Manager将ID与目标同步。 随着ITP 2. <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> 0的推出</a>，您可能希望潜在受众不包括Safari用户。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>跟踪的媒体印象</b> </p> </td> 
   <td colname="col2"> <p>由于广告服务器最佳实践，ID同步不会在广告标记中进行。 进行大量非现场广告的客户不会将用户同步到这些环境中的第三方集成。 此外，大量收集的媒体印象数据可能会减少可寻址的受众数。 </p> </td>
  </tr> 
 </tbody> 
</table>

## 可寻址受众疑难解答 {#troubleshooting}

除了显示匹配率外，您还可以将 [!UICONTROL Addressable Audiences] 其用作故障排除工具。

<!-- addressable-audiences-troubleshooting.xml -->

例如，假设您将区段发送到目标，该目标显示的报告数较少。 检查结 [!UICONTROL Addressable Audience] 果将显示这是技术问题还是只是匹配率低的问题。 低匹配率显示您的目标对所选区段来说并不是那么好。 但是，与目标之间可寻址受众总数的 [!DNL Audience Manager] 差异表明集成、同步或其他技术问题。 在这些情况下，请联系您的客户经理。