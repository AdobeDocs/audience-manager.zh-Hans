---
description: 当重叠报表达到100万条记录上限时，您可以为该报表请求一个.csv文件。 当您看到“发生意外错误”消息时，报表可能已达到此限制。 请联系客户关怀团队以请求压缩的.csv文件，您可以将其导入并在您自己的数据库系统中使用。 文件可用于区段到区段、区段到特征和特征到特征重叠报表。
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: 重叠报表的CSV文件
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 2%

---

# 重叠报表的CSV文件{#csv-files-for-overlap-reports}

当重叠报表达到100万条记录上限时，您可以为该报表请求一个.csv文件。 当您看到“发生意外错误”消息时，报表可能已达到此限制。 请联系客户关怀团队以请求压缩的.csv文件，您可以将其导入并在您自己的数据库系统中使用。 文件可用于区段到区段、区段到特征和特征到特征重叠报表。

## 文件名元数据 {#file-name-metadata}

下表列出并描述了重叠.csv文件中使用的文件命名约定和文件扩展名。 在示例中，*斜体*&#x200B;表示变量占位符。

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元数据元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文件扩展名 </p> </td> 
   <td colname="col2"> <p>重叠报表文件已压缩gzip，文件扩展名为<code> .gz</code>。 解压缩后，必须将<code> .csv</code>扩展名添加到文件中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> <p>文件名语法： </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">区段到区段文件： <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">区段到特征文件： <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">特征到特征文件： <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期范围 </p> </td> 
   <td colname="col2"> <p>报表的日期范围是一个5位数的ID，其中包括： </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> 7天报告的<code> 70000</code>。 </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> 30天报告的<code> 30000</code>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个文件 </p> </td> 
   <td colname="col2"> <p>如果报告包含多个文件，我们将递增文件名中的最后一个数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>示例 </p> </td> 
   <td colname="col2"> <p>单个报表的文件名示例： </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">单个7天文件： <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">单个30天文件： <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>具有多个文件的报表的文件名示例： </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 文件内容 {#file-contents}

在文件中，字符串数据用双引号括起来。 请参阅下面的模拟数据。 为简短起见并适合屏幕，现已截断此字段。

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## 区段到区段报表记录 {#segment-segment-records}

[区段到区段重叠报表](segment-segment-overlap-report.md)的数据文件包含以下记录。

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>要与基线区段进行比较的区段的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>要与基线区段进行比较的区段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>基线区段的ID。 基线区段是您要与其他区段进行比较的区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>要与其他区段进行比较的基线区段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以获取7天和30天回顾间隔的报表。 <code> rangeid</code>对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>： 7天 </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>： 30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>报表的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>要与基线区段进行比较的区段中的独特用户数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>基线区段中的独特用户数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>基线区段与选定进行比较的其他区段之间的独特用户重叠总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>基线区段与选定进行比较的其他区段之间的独特用户重叠百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区段到特征报表记录 {#segment-trait-records}

[区段到特征重叠报表](segment-trait-overlap-report.md)的数据文件包含以下记录。

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>特征ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>特征名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 ID包括： </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以获取7天和30天回顾间隔的报表。 <code> rangeid</code>对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>： 7天 </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>： 30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>报表的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>选定区段中的独特用户数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>特征中的独特用户数。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>在选定区段和特征之间共享的独特用户数。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>特征和区段之间重叠的独特用户的百分比。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>区段和特征之间重叠的唯一用户的百分比。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特征到特征报表记录 {#trait-trait-records}

[特征到特征重叠报表](trait-trait-overlap-report.md)的数据文件包含以下记录。

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>要与基线特征进行比较的特征的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>要与基线特征进行比较的特征名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>基线特征的ID。 基线特征是要与其他特征进行比较的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>要与其他特征进行比较的基线特征的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 ID包括： </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以获取7天和30天回顾间隔的报表。 <code> rangeid</code>对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>： 7天 </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>： 30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>报表的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>在选定特征之间共享的独特用户数。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>基本特征中的独特用户数。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>在选定特征之间共享的独特用户数。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>选定特征之间重叠的独特用户的百分比。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>所选特征之间重叠的不重复用户的百分比。 在UI报表中，当您将鼠标悬停在热图结果中的某个特征上时，此数字会显示在弹出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>
