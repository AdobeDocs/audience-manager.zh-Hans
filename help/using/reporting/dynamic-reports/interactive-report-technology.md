---
description: 描述支持交互式报表和数据更新计划的基础软件。
seo-description: 描述支持交互式报表和数据更新计划的基础软件。
seo-title: 报表技术
solution: Audience Manager
title: 报表技术
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 3%

---


# 报表技术{#report-technology}

描述支持交互式报表和数据更新计划的基础软件。

<!-- 

c_report_technology.xml

 -->

## 交互式报表使用Tableau技术

[!DNL Audience Manager] 使 [用Tableau](https://www.tableausoftware.com/) 软件在交互式报表中显示数据。 报告 [!DNL Tableau]使用 [!UICONTROL Delivery and Overlap] 视觉提示和符号帮助您：

* 查找高性能和低性能特性。
* 发现具有低和高唯一访客重叠的特征和区段。
* 使用重叠数据构建目标细分。
* 通过识别重叠度低的相关特征扩大受众范围。

## 数据更新计划

报告数据每周每周日更新一次。 更新将处理星期六（前一天）至上个星期日的数据。

## 交互式报告中使用的形状、颜色和大小 {#shapes-colors-sizes}

大多数交互式报表都使用不同大小和颜色的形状显示结果。 此显示格式旨在帮助您以可视方式理解数据，无需费力地查看行和列数。

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圆形表示您自己的第一方特征。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方块表示第三方特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>颜色</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">红色阴影表 <i>示低</i> 重叠。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">绿色暗色表 <i>示高</i> 重叠。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小会以直接比例增加或减少（点击次数或百分比，或特征或区段中的唯一用户）。 </td> 
  </tr> 
 </tbody> 
</table>

## Tableau文档 {#tableau-documentation}

要进一步了解您可以在我们的交互式报告中看到的Tableau控件，请参阅Linux 2018.2上 [Tableau Server的官方文档](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)