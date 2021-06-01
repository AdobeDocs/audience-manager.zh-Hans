---
description: 描述为交互式报表和数据更新计划提供支持的基础软件。
seo-description: 描述为交互式报表和数据更新计划提供支持的基础软件。
seo-title: 报表技术
solution: Audience Manager
title: 报表技术
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: 重叠报表
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# 报表技术{#report-technology}

描述为交互式报表和数据更新计划提供支持的基础软件。

<!-- 

c_report_technology.xml

 -->

## 交互式报表使用表格技术

[!DNL Audience Manager] 使用 [](https://www.tableausoftware.com/) Table软件在交互式报表中显示数据。对于[!DNL Tableau], [!UICONTROL Delivery and Overlap]报表使用视觉提示和符号来帮助您：

* 查找高和低性能特征。
* 发现具有低独特访客和高独特访客重叠的特征和区段。
* 使用重叠数据构建目标区段。
* 通过识别重叠程度较低的相关特征来扩大访问范围。

## 数据更新计划

每个星期日，每周更新报表数据。 该更新会处理星期六（前一天）到上星期日的数据。

## 交互式报表中使用的形状、颜色和大小{#shapes-colors-sizes}

大多数交互式报表使用不同大小和颜色的形状来显示结果。 此显示格式旨在帮助您直观地理解数据，而无需费力地查看数字的行和列。

<!-- 

r_legend.xml

 -->

### 报表图例

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
     <li id="li_371331AE984A4A999CE0596EA13987E0">正方形表示第三方特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>颜色</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">红色阴影表示<i>低</i>重叠。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">绿色阴影表示<i>高</i>重叠。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小以与访问量成正比的比例增加或减少（特征或区段中独特用户的点击次数或百分比）。 </td> 
  </tr> 
 </tbody> 
</table>

## 表格文档{#tableau-documentation}

要进一步了解可在我们的交互式报表中看到的Tableau控件，请参阅Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)上[Tableau Server的官方文档
