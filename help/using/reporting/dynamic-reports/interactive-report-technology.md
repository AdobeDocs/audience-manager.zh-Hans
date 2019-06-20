---
description: 介绍支持交互式报告和数据更新计划的底层软件。
seo-description: 介绍支持交互式报告和数据更新计划的底层软件。
seo-title: Report Technology
solution: Audience Manager
title: Report Technology
uuid: 5f3d815b-e1 e6-42f2-b848-ac035 a5 aa77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

介绍支持交互式报告和数据更新计划的底层软件。

<!-- 

c_report_technology.xml

 -->

## 交互式报告使用Tableau Technology

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) 软件在交互式报告中显示数据。With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* 查找高性能和低性能特征。
* 专色和高独特访客重叠的污点特征和区段。
* 使用重叠数据构建目标细分。
* 通过识别重叠的相关特征来扩大覆盖范围。

## 数据更新计划

报告数据每周每周更新一次。更新将处理从星期六(前一天)返回到上一个星期日的数据。

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

大多数交互式报告使用不同大小和颜色的形状显示结果。此显示格式旨在帮助您直观地了解数据，而无需在行数和列数之间浪费时间。

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圆形指示您自己的第一方特征。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">正方形指示第三方特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>颜色</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 根据触及范围(特性或区段中的点击量或唯一用户数)，大小会增加或减小到直接比例。 </td> 
  </tr> 
 </tbody> 
</table>

## Report Icons and Tools Explained {#icons-tools-explained}

介绍如何搜索和使用动态报告中使用的各种图标工具。

<!-- 

r_icons.xml

 -->

### 数据图标和工具

每个动态报告窗口的底部都有以下图标工具。下图提供了有关这些工具的更多信息。

![](assets/tools_icons90.png)

### 导出数据

使用此工具可从报表中的种不同格式导出数据。

| 导出选项 | 导出数据 |
|---|---|
| **[!UICONTROL Image]** | 作为图像(. png)文件。当您希望以其原始的图形格式下载和共享报告数据时有用。 |
| **[!UICONTROL PDF]** | 作为PDF文件。 |
| **[!UICONTROL Data]** | 在新的浏览器窗口中，以列和行为单位数据。 |
| **[!UICONTROL Crosstab]** | 作为. csv文件。 |

### 还原更改

选择此工具可撤消您对报表执行的任何交互式点击更改。

### 自动更新

[!UICONTROL Delivery-Performance] 报告 [!UICONTROL Trait-to-Trait Overlap] 是动态报告，可根据用户单击操作做出响应和更改。

For example, say you want to select several advertisers in the [!UICONTROL Overlap] report. 启用此功能后，一旦选中复选框，自动更新将开始返回数据。这种动态行为可能会中断您的工作流程，因为您必须等到报表完成处理后再选择其他广告商。使用此工具根据需要关闭(和再次打开)功能。

### 刷新数据

单击刷新图标以运行报表或重新加载数据集。自动更新关闭后，单击刷新以运行或更新报告。

### 搜索工具

搜索由通用放大镜图标(未显示)表示。单击屏幕左侧的选择标签后，搜索字段才会隐藏。下表描述了每个报告的搜索工具位置。

| 报表 | 要查找搜索，请将鼠标悬停在 |
|---|---|
| [!UICONTROL Delivery and Performance] 报表 | “广告商名称”标签。 |
| [!UICONTROL Overlap] 报告 | “SID Name”标签。 |
