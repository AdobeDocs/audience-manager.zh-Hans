---
description: 当报表达到 100 万条记录上限时，您可以为重叠报表申请一个 .csv 文件。当您看到“意外错误”消息时，报告可能已达到此限制。请联系客户关怀以请求压缩的. csv文件，您可以在自己的数据库系统中导入和使用该文件。文件可用于区段到区段、区段到特征以及特征与特征重叠报告。
seo-description: 当报表达到 100 万条记录上限时，您可以为重叠报表申请一个 .csv 文件。当您看到“意外错误”消息时，报告可能已达到此限制。请联系客户关怀以请求压缩的. csv文件，您可以在自己的数据库系统中导入和使用该文件。文件可用于区段到区段、区段到特征以及特征与特征重叠报告。
seo-title: 重叠报告的CSV文件
solution: Audience Manager
title: 重叠报告的CSV文件
uuid: 047e440e-00c5-4d06-a809-51d776326 cd6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# CSV Files for Overlap Reports{#csv-files-for-overlap-reports}

当报表达到 100 万条记录上限时，您可以为重叠报表申请一个 .csv 文件。当您看到“意外错误”消息时，报告可能已达到此限制。请联系客户关怀以请求压缩的. csv文件，您可以在自己的数据库系统中导入和使用该文件。文件可用于区段到区段、区段到特征以及特征与特征重叠报告。

## File Name Metadata {#file-name-metadata}

下表列出了文件命名惯例和文件扩展名，它们在重叠. csv文件中使用。In the examples, *italics* indicates a variable placeholder.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元数据元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文件Extension </p> </td> 
   <td colname="col2"> <p>Overlap report files are gzip compressed and have a <code> .gz</code> file extension. You must add the <code> .csv</code> extension to the file after decompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> <p>文件名语法： </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-to-segment files: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-to-trait files: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait files: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期范围 </p> </td> 
   <td colname="col2"> <p>报表的日期范围是个数字ID，其中包括： </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 700000</code> 用于天报告。 </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> ，报告30天。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个文件 </p> </td> 
   <td colname="col2"> <p>如果报表包含多个文件，我们将增加文件名中的最后一位数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>示例 </p> </td> 
   <td colname="col2"> <p>单个报告的文件名示例： </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Single, 7-day file: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Single, 30-day file: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>包含多个文件的报告的文件名示例： </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Contents {#file-contents}

在文件中，字符串数据包含在双引号中。请参阅下面的模型数据。这已经被截断，并且要适合屏幕。

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-to-Segment Report Records {#segment-segment-records}

[区段与区段重叠报告的数据文件](segment-segment-overlap-report.md) 包含以下记录。

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id1</code> </p> </td> 
   <td colname="col2"> <p>与基线区段比较的区段的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name1</code> </p> </td> 
   <td colname="col2"> <p>与基线区段比较的区段名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id2</code> </p> </td> 
   <td colname="col2"> <p>基线区段的ID。基线区段是您要与其他区段进行比较的区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name2</code> </p> </td> 
   <td colname="col2"> <p>与其他区段相比，基线区段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>可获得天和30天回顾间隔的报告。<code> rangeid</code> 对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>：天 </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>天：30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datetru</code> </p> </td> 
   <td colname="col2"> <p>报告的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques1</code> </p> </td> 
   <td colname="col2"> <p>与基线区段相比，区段中唯一用户的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques2</code> </p> </td> 
   <td colname="col2"> <p>基线区段中唯一用户的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 重叠_统一</code> </p> </td> 
   <td colname="col2"> <p>基线区段与其他区段之间用于比较的唯一用户重叠的总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 重叠_ perc</code> </p> </td> 
   <td colname="col2"> <p>基线区段与其他选定区段之间的百分比重叠表示比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-to-Trait Report Records {#segment-trait-records}

[“区段至特征重叠报告”的数据文件](segment-trait-overlap-report.md) 包含以下记录。

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> traentity_ id</code> </p> </td> 
   <td colname="col2"> <p>特征ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traentity_ name</code> </p> </td> 
   <td colname="col2"> <p>特征名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。ID包括： </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 第一方</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 第三方</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>可获得天和30天回顾间隔的报告。<code> rangeid</code> 对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>：天 </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>天：30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datetru</code> </p> </td> 
   <td colname="col2"> <p>报告的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques</code> </p> </td> 
   <td colname="col2"> <p>选定区段中唯一用户的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 特征_统一</code> </p> </td> 
   <td colname="col2"> <p>特征中唯一用户的数量。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 重叠_统一</code> </p> </td> 
   <td colname="col2"> <p>在选定的区段和特征之间共享的唯一用户数量。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traentity_ uniques_ operating_ perc</code> </p> </td> 
   <td colname="col2"> <p>在特征和区段之间重叠的唯一用户百分比。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques_ operating_ perc</code> </p> </td> 
   <td colname="col2"> <p>属于在区段与特征之间重叠的用户的百分比。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#trait-trait-records}

[您的特征与错误重叠报告的数据文件](trait-trait-overlap-report.md) 包含以下记录。

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> pateralog_ traid_ id</code> </p> </td> 
   <td colname="col2"> <p>与基准特征比较的特征的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> materalog_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>特征与基线特征的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ traid_ id</code> </p> </td> 
   <td colname="col2"> <p>基线特征的ID。基线特征是您要与其他特征进行比较的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>基线特征的名称与其他特征的比较。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。ID包括： </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 第一方</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 第三方</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>可获得天和30天回顾间隔的报告。<code> rangeid</code> 对应于下面显示的时间间隔。 </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>：天 </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>天：30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datetru</code> </p> </td> 
   <td colname="col2"> <p>报告的处理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> creating_ trait_ uniques</code> </p> </td> 
   <td colname="col2"> <p>在选定的特征之间共享的唯一用户的数量。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ unquions</code> </p> </td> 
   <td colname="col2"> <p>基本特征中唯一用户的数量。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 重叠_统一</code> </p> </td> 
   <td colname="col2"> <p>在选定的特征之间共享的唯一用户的数量。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 重叠_ traid_ uniques_ verovers_ perc</code> </p> </td> 
   <td colname="col2"> <p>在选定特征之间重叠的唯一用户百分比。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ traid_ uniques_ verovers_ perc</code> </p> </td> 
   <td colname="col2"> <p>在选定的特征之间重叠的用户的百分比。在UI报告中，当您将鼠标悬停在热图结果中的特征上方时，此数字将显示在弹出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>
