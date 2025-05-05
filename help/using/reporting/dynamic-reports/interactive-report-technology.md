---
description: 描述支持交互式报表的基础软件和数据更新计划。
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: 报表技术
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# 报表技术{#report-technology}

描述支持交互式报表的基础软件和数据更新计划。

<!-- 

c_report_technology.xml

 -->

## 交互式报表使用Tableau技术

[!DNL Audience Manager]使用[Tableau](https://www.tableausoftware.com/)软件在交互式报表中显示数据。 通过[!DNL Tableau]，[!UICONTROL Delivery and Overlap]报告使用视觉提示和符号来帮助您：

* 查找高性能和低性能特征。
* 找出独特访客重叠率较低和较高的特征和区段。
* 使用重叠数据构建目标区段。
* 通过识别低重叠的相关特征来扩展范围。

## 数据更新计划

报告数据每周星期日更新一次。 更新会处理从星期六（前一天）到前一个星期日的数据。

## 交互式报表中使用的形状、颜色和大小 {#shapes-colors-sizes}

大多数交互式报表使用不同大小和颜色的形状来显示结果。 此显示格式旨在帮助您直观地理解数据，而不必费力地浏览数字的行和列。

<!-- 

r_legend.xml

 -->

### 报表图例

下表定义了动态报表中使用的形状、大小和颜色。

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圆圈表示您自己的第一方特征。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方块表示第三方特征。 </li> 
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
   <td colname="col2"> 大小成正比增加或减少，以达到（特征或区段中的点击次数或点击百分比或独特用户）。 </td> 
  </tr> 
 </tbody> 
</table>

## 表格文档 {#tableau-documentation}

要了解有关可在我们的交互式报表中看到的Tableau控件的更多信息，请参阅有关Linux 2018.2[&#128279;](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)上的Tableau服务器的官方文档
