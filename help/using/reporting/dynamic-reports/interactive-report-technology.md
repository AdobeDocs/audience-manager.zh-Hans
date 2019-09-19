---
description: 描述支持交互式报表和数据更新计划的底层软件。
seo-description: 描述支持交互式报表和数据更新计划的底层软件。
seo-title: 报告技术
solution: Audience Manager
title: 报告技术
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# 报告技术{#report-technology}

描述支持交互式报表和数据更新计划的底层软件。

<!-- 

c_report_technology.xml

 -->

## 交互式报表使用表格技术

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) software在交互式报告中显示数据。 报告 [!DNL Tableau]使用可 [!UICONTROL Delivery and Overlap] 视提示和符号帮助您：

* 查找高性能和低性能特性。
* 发现具有低独特访客和高独特访客的特征和区段重叠。
* 使用重叠数据构建目标细分。
* 通过识别重叠度低的相关特征扩大受众范围。

## 数据更新计划

每周日更新报告数据。 此更新将处理从星期六（前一天）至上个星期日的数据。

## 交互式报告中使用的形状、颜色和大小 {#shapes-colors-sizes}

大多数交互式报表都使用不同大小和颜色的形状显示结果。 此显示格式旨在帮助您以可视方式理解数据，无需费力地浏览行和列数。

<!-- 

r_legend.xml

 -->

### 报告图例

下表定义了动态报告中使用的形状、大小和颜色。

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>形状</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圈子表示您自己的第一方特征。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方块表示第三方特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>颜色</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">红色阴影表示 <i>重叠</i> 少。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">绿色阴影表示 <i>重叠</i> 。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小会按到达率（点击次数或百分比或特征或区段中的唯一用户）的直接比例增加或减少。 </td> 
  </tr> 
 </tbody> 
</table>

## 说明的报表图标和工具 {#icons-tools-explained}

介绍如何搜索和使用动态报告中使用的各种图标工具。

<!-- 

r_icons.xml

 -->

### 数据图标和工具

每个动态报告窗口的底部提供以下图标——工具。 下图提供了有关这些工具的更多信息。

![](assets/tools_icons90.png)

### 导出数据

此工具允许您以4种不同格式从报表中导出数据。

| 导出选项 | 导出数据 |
|---|---|
| **[!UICONTROL Image]** | 作为图像(.png)文件。 当您希望下载并共享报表数据的原始图形格式时非常有用。 |
| **[!UICONTROL PDF]** | 作为PDF文件。 |
| **[!UICONTROL Data]** | 在新的浏览器窗口中，以列和行中的数字数据的形式显示。 |
| **[!UICONTROL Crosstab]** | 作为。csv文件。 |

### 还原更改

选择此工具可撤消您可能对报告执行的任何交互式单击更改。

### 自动更新

和报 [!UICONTROL Delivery-Performance] 表 [!UICONTROL Trait-to-Trait Overlap] 是动态报表，可根据用户单击操作做出响应和更改。

例如，假设您要在报告中选择多个广告商，则表明您选择的广告商 [!UICONTROL Overlap] 数量有限。 启用后，一旦选中复选框，自动更新将立即开始返回数据。 此动态行为可能会中断您的工作流，因为您必须等到报表完成处理后再选择其他广告商。 根据需要，使用此工具关闭（并再次打开）该功能。

### 刷新数据

单击刷新图标以运行报告或重新加载数据集。 关闭自动更新后，单击刷新以运行或更新报告。

### 搜索工具

搜索由通用放大镜图标表示（未显示）。 在单击屏幕左侧的选择标签之前，搜索字段将处于隐藏状态。 下表描述了每个报告的搜索工具的位置。

| 报表 | 要查找搜索，请将鼠标悬停在 |
|---|---|
| [!UICONTROL Delivery and Performance] 报表 | “广告商名称”标签。 |
| [!UICONTROL Overlap] 报告 | “SID名称”标签。 |
