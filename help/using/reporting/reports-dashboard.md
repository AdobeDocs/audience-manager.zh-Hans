---
description: 使用控制面板查看您合作伙伴的独特访客计数的相关信息，这些信息按特征类型和特定时间段划分。
seo-description: 使用控制面板查看您合作伙伴的独特访客计数的相关信息，这些信息按特征类型和特定时间段划分。
seo-title: 报告控制板
solution: Audience Manager
title: 报告控制板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

使用控制面板查看特定时间范围内按特征类型和区段划分的独特访客计数信息。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展 [!UICONTROL Dashboard]到。用户只能查看其有权查看的仪表板上的信息。[!UICONTROL RBAC] 功能允许您控制内部团队能够查看哪些报告数据。

例如，管理不同广告商帐户的代理可以配置用户组权限，以使管理Advertiser A帐户的团队无法看到Advertiser B的报告数据。此控制板可用于解决数据交付问题。

例如，如果您注意到一个下降或峰值，则在唯一用户的类型划分(基于规则的与载入的模板)中，您有一个更好的起点来跟踪潜在的数据交付问题。If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**访问控制面板：**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *可选从* 下拉列表(默认为天、14天(默认)、30天或60天)中从上一报告日期选择所需的时间范围。

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. 例如，如果您选择天，则delta将在今天的前七天将唯一访客与七天前结束的唯一访客对比。

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   根据登录用户的权限，将显示以下面板：

   * [合作伙伴统一](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特征/更改的特征](../reporting/reports-dashboard.md#largest-traits)
   * [最大细分/最大更改区段](../reporting/reports-dashboard.md#most-changed-segments)

3. *可选* 单击 **[!UICONTROL Normalize]** 任意图形以在同一比例上显示所有数据。您还可以将鼠标悬停在任何数据点上以查看更多信息。

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

此面板显示指定时间段内唯一访客的数量。个人、彩色代码线代表唯一访客总数以及使用算法、基于规则和载入的特征捕获的独特访客数量。

>[!NOTE]
>
>唯一访客总数表示通过基于规则或内置特征捕获的访客。但是，唯一访客总数并不等于使用基于规则和载入的特征捕获的唯一访客总数。同一个唯一用户可能在这两个特征类型中表示。

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

此面板显示通过各种特征捕获的唯一访客数量。

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

此面板包含以下选项卡：

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按数字排序的唯一访客数量(最高到最低)的信息，并列出指定时间段内独特访客的delta更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最更改的特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关通过delta更改排序的唯一访客数量的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

此面板显示实时捕获的各个区段的唯一访客数。

此面板包含以下选项卡：

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大细分</span> </p> </td> 
   <td colname="col2"> <p>显示指定时间段内唯一访客数量和唯一访客的delta更改的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最更改的区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关通过delta更改排序的唯一访客数量的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

