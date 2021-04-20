---
description: 使用仪表板可视图有关合作伙伴在指定时间范围内按特征类型和区段划分的独特访客计数的信息。
seo-description: 使用仪表板可视图有关合作伙伴在指定时间范围内按特征类型和区段划分的独特访客计数的信息。
seo-title: 报表仪表板
solution: Audience Manager
title: 报表仪表板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# 报表仪表板 {#reports-dashboard}

使用仪表板可视图有关指定时间范围内按特征类型和区段划分的唯一访客计数的信息。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用[!UICONTROL RBAC]()将用户组权限扩展到 [!UICONTROL Dashboard]。用户只能看到关于他们对仪表板具有权限的视图的信息。 [!UICONTROL RBAC] 功能，您可以控制内部团队能够视图的报告数据。

例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。 此仪表板可用于解决投放问题。

例如，如果您注意到按唯一用户类型划分的唯一用户总数（基于规则的与已登载的）出现了下降（或尖峰），则跟踪潜在数据投放问题有一个更好的起点。 如果您注意到唯一用户总数和已上载的唯一用户总数有所下降，则可以转到[!UICONTROL On-boarding Status]报告，查看入站文件是否存在问题。

**要访问仪表板:**

1. 在顶部导航菜单中，单击&#x200B;**[!UICONTROL Dashboard]**。
2. *可* 选从下拉列表(7天、14天（默认）、30天或60天)中从最后一个报告日期选择所需的时间范围。

   根据所选的时段，[!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits]和[!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments]面板中的增量变化显示在今天结束的受众与相同长度的前一时段中唯一访客的变化。 例如，如果您选择7天，则增量将比较在今天结束的前七天内的唯一访客与在七天前结束的七天内的唯一访客。

   >[!NOTE]
   >
   >您可以通过运行[!UICONTROL Trend]报告来调查看似异常的增量更改。 例如，如果您在过去七天内看到异常大的增量变化，则您可以运行最近14天(2 x 7)的[!UICONTROL Trend]报表以更好地了解数字。

   根据登录用户的权限，将显示以下面板：

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特征/最改变特征](../reporting/reports-dashboard.md#largest-traits)
   * [最大细分/更改最多的细分](../reporting/reports-dashboard.md#most-changed-segments)

3. *可* 选单 **[!UICONTROL Normalize]** 击任意图形上方显示相同比例的所有数据。您还可以将鼠标悬停在任何数据点上以查看更多信息。

## 合作伙伴唯一值{#partner-uniques}

视图所需权限：[!UICONTROL View All Traits]。

![](assets/partner_uniques.png)

此面板显示指定时间范围内的唯一访客数。 个人、颜色编码行表示使用算法、基于规则和载入的特征捕获的唯一访客的总数和唯一访客的数量。

>[!NOTE]
>
>唯一访客的总数表示通过基于规则或已载入的特征捕获的访客。 但是，唯一访客的总数不等于使用基于规则和载入的特征捕获的唯一访客的总和。 这两个特征类型中的任意一种可能表示同一唯一用户。

## 最大特征/最改变特征{#largest-traits}

视图所需权限：[!UICONTROL View Traits]。

![](assets/largest_traits.png)

此面板显示由各种特征捕获的唯一访客的数量。

使用&#x200B;**[!UICONTROL Show]**&#x200B;下拉列表显示有关不同类型特征的信息：[!UICONTROL All Traits]、[!UICONTROL Algorithmic]、[!UICONTROL Onboarded]或[!UICONTROL Rule-Based]。

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
   <td colname="col2"> <p>显示有关按数字（从高到低）排序的唯一访客数的信息，并列表在指定时间范围内唯一访客的增量更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的唯一访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大区段/更改最多的区段{#most-changed-segments}

视图所需权限：[!UICONTROL View Segments]。

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
   <td colname="col2"> <p>显示有关指定时间范围内唯一访客数和唯一访客增量变化的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的唯一访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>
