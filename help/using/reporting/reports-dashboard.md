---
description: 使用功能板可查看有关合作伙伴在指定时间段内按特征类型和区段划分的独特访客计数的信息。
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: 报表仪表板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# 报表仪表板 {#reports-dashboard}

使用功能板可查看有关在指定的时间范围内按特征类型和区段细分的独特访客计数的信息。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager]使用[!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到[!UICONTROL Dashboard]。 用户只能在功能板上查看他们有权查看的信息。 通过[!UICONTROL RBAC]功能，您可以控制内部团队可以查看哪些报表数据。

例如，管理不同广告商帐户的机构可以配置用户组权限，这样管理广告商A帐户的团队将无法查看广告商B的报表数据。 此仪表板可用于对数据投放问题进行故障诊断。

例如，如果您注意到独特用户总数出现下降或峰值，并且划分了独特用户类型（基于规则的与已载入），则您有一个更好的起点来跟踪潜在的数据交付问题。 如果您注意到独特用户总数和已载入的独特用户数出现下降，则可以转到[!UICONTROL On-boarding Status]报表以查看入站文件是否存在问题。

**访问仪表板：**

1. 在顶部导航菜单中，单击&#x200B;**[!UICONTROL Dashboard]**。
2. *可选*&#x200B;从下拉列表中选择上一个报告日期所需的时间范围(7天、14天（默认）、30天或60天)。

   根据所选时段，[!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits]和[!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments]面板中的增量更改显示今天结束的时段与相同长度的上一时段受众中独特访客的更改。 例如，如果您选择7天，则差值会将截至今天之前的7天内的独特访客与截至七天前的7天内的独特访客进行比较。

   >[!NOTE]
   >
   >您可以通过运行[!UICONTROL Trend]报告来调查异常的增量更改。 例如，如果您看到过去7天内差异变化异常大，则可以在过去14天(2 x 7)内运行[!UICONTROL Trend]报告以更好地了解这些数字。

   根据登录用户的权限，将显示以下面板：

   * [合作伙伴唯一值](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特征/更改最多的特征](../reporting/reports-dashboard.md#largest-traits)
   * [最大区段/更改最多的区段](../reporting/reports-dashboard.md#most-changed-segments)

3. *可选*&#x200B;单击任意图形上方的&#x200B;**[!UICONTROL Normalize]**&#x200B;以显示相同比例的所有数据。 您还可以将鼠标悬停在任意数据点上以查看更多信息。

## 合作伙伴独特性 {#partner-uniques}

查看所需的权限： [!UICONTROL View All Traits]。

![](assets/partner_uniques.png)

此面板显示指定时间段内的独特访客数量。 单个颜色编码的行表示使用算法、基于规则和载入的特征捕获的独特访客总数和独特访客数。

>[!NOTE]
>
>独特访客的总数表示通过基于规则的特征或载入的特征捕获的访客。 但是，独特访客的总数并不等于使用基于规则的特征和载入的特征捕获的独特访客数之和。 同一独特用户可能会以这两种特征类型中的任意一种来表示。

## 最大特征/变化最频繁的特征 {#largest-traits}

查看所需的权限： [!UICONTROL View Traits]。

![](assets/largest_traits.png)

此面板显示由各种特征捕获的独特访客数。

使用&#x200B;**[!UICONTROL Show]**&#x200B;下拉列表显示有关不同类型的特征的信息： [!UICONTROL All Traits]、[!UICONTROL Algorithmic]、[!UICONTROL Onboarded]或[!UICONTROL Rule-Based]。

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
   <td colname="col1"> <p><span class="wintitle">最大特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按数量排序（从高到低）的独特访客数的信息，并列出指定时间段内独特访客的差异变化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">更改最频繁的特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的独特访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大区段/更改最多的区段 {#most-changed-segments}

查看所需的权限： [!UICONTROL View Segments]。

![](assets/largest_segments.png)

此面板可实时显示各个区段捕获的独特访客数。

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
   <td colname="col1"> <p><span class="wintitle">最大区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关指定时间段内独特访客数量和独特访客增量更改的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">更改最多的区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的独特访客数的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>
