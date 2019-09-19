---
description: 使用控制板查看有关合作伙伴的独特访客计数的信息，这些访客计数按特征类型和指定时间段的区段细分。
seo-description: 使用控制板查看有关合作伙伴的独特访客计数的信息，这些访客计数按特征类型和指定时间段的区段细分。
seo-title: 报告功能板
solution: Audience Manager
title: 报告功能板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# 报告功能板 {#reports-dashboard}

使用控制板可查看在指定时间范围内按特征类型和区段划分的独特访客计数的相关信息。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到 [!UICONTROL Dashboard]。 用户只能在仪表板上看到他们有权查看的信息。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看的报告数据。

例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。 此功能板可用于解决数据交付问题。

例如，如果您注意到具有唯一用户类型细分的唯一用户总数（基于规则与已载入的用户）中出现了“下降”或“尖峰”，那么，您有一个更好的起点来跟踪潜在的数据交付问题。 如果您注意到唯一用户总数和已载入的唯一用户总数有所下降，您可以转到报告，查看 [!UICONTROL On-boarding Status] 入站文件是否有问题。

**要访问功能板，请执行以下操作：**

1. 在顶部导航菜单中，单击 **[!UICONTROL Dashboard]**。
2. *可选* ，从下拉列表(7天、14天（默认）、30天或60天)中选择上次报告日期的所需时间范围。

   根据所选时间段的不同， &gt;和 [!UICONTROL Largest Traits][!UICONTROL Most Changed Traits][!UICONTROL Largest Segments][!UICONTROL Most Changed Segments] &gt;面板中的增量变化显示了在截至今天的时段与相同长度的前一时段期间受众中唯一访客的变化。 例如，如果选择7天，则增量将比较前七天内到今天为止的唯一访客与七天前结束的七天内的唯一访客。

   >[!NOTE]
   >
   >您可以通过运行报告来调查看似异常的增量变化情 [!UICONTROL Trend] 况。 例如，如果您在过去七天内看到异常大的增量变化，则可以运行过去14天(2 x 7)的 [!UICONTROL Trend] 报表，以便更好地了解数字。

   根据登录用户的权限，将显示以下面板：

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特征／最大更改特征](../reporting/reports-dashboard.md#largest-traits)
   * [最大细分／更改最多的细分](../reporting/reports-dashboard.md#most-changed-segments)

3. *可选* ，单 **[!UICONTROL Normalize]** 击任意图形上方，以同一比例显示所有数据。 您还可以将鼠标悬停在任何数据点上以查看更多信息。

## Partner Uniques {#partner-uniques}

需要权限才能查看： [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

此面板显示指定时间段内的唯一访客数。 使用颜色编码的个人行表示使用算法、基于规则和载入的特征捕获的唯一访客总数和唯一访客数。

>[!NOTE]
>
>唯一访客总数表示通过基于规则或已载入的特征捕获的访客。 但是，唯一访客的总数不等于使用基于规则和已载入的特征捕获的唯一访客的总和。 这两个特征类型中的任意一种可能表示同一唯一用户。

## 最大特征／最大更改特征 {#largest-traits}

需要权限才能查看： [!UICONTROL View Traits].

![](assets/largest_traits.png)

此面板显示由各种特征捕获的唯一访客数。

使用下 **[!UICONTROL Show]** 拉列表显示有关不同类型特征的信息： [!UICONTROL All Traits]、 [!UICONTROL Algorithmic]、 [!UICONTROL Onboarded]或 [!UICONTROL Rule-Based]。

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
   <td colname="col2"> <p>显示有关按数字（从高到低）排序的唯一访客数的信息，还列出指定时间范围内唯一访客的增量变化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的唯一访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大细分／更改最多的细分 {#most-changed-segments}

需要权限才能查看： [!UICONTROL View Segments].

![](assets/largest_segments.png)

此面板实时显示各个区段捕获的唯一访客数。

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
   <td colname="col2"> <p>显示有关指定时间段内唯一访客的数量和增量变化的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的细分</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的唯一访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

