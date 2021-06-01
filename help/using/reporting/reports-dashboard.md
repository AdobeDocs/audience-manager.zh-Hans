---
description: 使用功能板可查看有关合作伙伴独特访客计数的信息，这些独特访客计数按特征类型和区段在指定时间段内进行划分。
seo-description: 使用功能板可查看有关合作伙伴独特访客计数的信息，这些独特访客计数按特征类型和区段在指定时间段内进行划分。
seo-title: 报表仪表板
solution: Audience Manager
title: 报表仪表板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: 报表参考
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# 报表仪表板 {#reports-dashboard}

使用功能板可查看有关指定时间段内按特征类型和区段划分的独特访客计数的信息。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])将用户群组权限扩展到 [!UICONTROL Dashboard]。用户只能在功能板上看到他们有权查看的信息。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看哪些报表数据。

例如，管理不同广告商帐户的代理可以配置用户群组权限，以便管理广告商A帐户的团队无法查看广告商B的报表数据。 此功能板可用于解决数据交付问题。

例如，如果您发现按独特用户类型（基于规则的用户与已载入的用户）细分的独特用户总数出现下降或尖峰，则您有一个更好的起点来跟踪潜在的数据交付问题。 如果您发现独特用户总数和已载入的独特用户总数出现下降，则可以转到[!UICONTROL On-boarding Status]报表以查看入站文件是否存在问题。

**要访问功能板，请执行以下操作：**

1. 在顶部导航菜单中，单击&#x200B;**[!UICONTROL Dashboard]**。
2. ** 可选从下拉列表(7天、14天（默认）、30天或60天)中选择从上次报告日期开始的所需时间范围。

   根据所选时段，[!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits]和[!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments]面板中的增量变化显示受众中独特访客在今天结束的时段与相同长度的前期之间的变化。 例如，如果选择7天，则差别将比较前七天（今天结束）内的独特访客与七天前（七天结束）七天内的独特访客。

   >[!NOTE]
   >
   >您可以通过运行[!UICONTROL Trend]报表来调查异常的增量更改。 例如，如果您看到过去七天内增量变化异常大，则可以运行最近14天(2 x 7)的[!UICONTROL Trend]报表以更好地了解数字。

   根据登录用户的权限，将显示以下面板：

   * [合作伙伴独特客户](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特征/最大更改特征](../reporting/reports-dashboard.md#largest-traits)
   * [最大区段/更改最多的区段](../reporting/reports-dashboard.md#most-changed-segments)

3. ** 可选单击 **[!UICONTROL Normalize]** 任意图表上方的，可以以相同比例显示所有数据。您还可以将鼠标悬停在任何数据点上以查看更多信息。

## 合作伙伴独特数{#partner-uniques}

查看所需的权限：[!UICONTROL View All Traits]。

![](assets/partner_uniques.png)

此面板显示指定时间范围内的独特访客数。 颜色编码的单个行表示独特访客的总数以及使用算法、基于规则的特征和载入的特征捕获的独特访客的数量。

>[!NOTE]
>
>独特访客总数表示通过基于规则的特征或已载入的特征捕获的访客总数。 但是，独特访客总数不等于使用基于规则的特征和已载入的特征所捕获的独特访客总数。 同一独特用户可能会在这两种特征类型中的任意一种类型中表示。

## 最大特征/最大更改特征{#largest-traits}

查看所需的权限：[!UICONTROL View Traits]。

![](assets/largest_traits.png)

此面板会显示由各种特征捕获的独特访客数量。

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
   <td colname="col2"> <p>显示有关按数字（从最高到最低）排序的独特访客数的信息，并列出指定时间范围内独特访客的增量变化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改最多的特征</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的独特访客数量的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大区段/更改最多的区段{#most-changed-segments}

查看所需的权限：[!UICONTROL View Segments]。

![](assets/largest_segments.png)

此面板可实时显示各个区段捕获的独特访客数量。

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
   <td colname="col1"> <p><span class="wintitle"> 最大区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关指定时间段内独特访客数量和独特访客增量变化的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 更改次数最多的区段</span> </p> </td> 
   <td colname="col2"> <p>显示有关按增量更改排序的独特访客数量的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>
