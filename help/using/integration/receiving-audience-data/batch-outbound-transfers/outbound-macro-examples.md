---
description: 有关如何使用某些常用宏创建出站文件模板的示例。
seo-description: 有关如何使用某些常用宏创建出站文件模板的示例。
seo-title: 出站宏示例
solution: Audience Manager
title: 出站宏示例
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
feature: 出站数据传输
exl-id: 7e3f2b25-7b7c-47fe-aa62-7ebd4e25f9ba
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 14%

---

# 出站宏示例 {#outbound-macro-examples}

有关如何使用某些常用宏创建出站文件模板的示例。

>[!NOTE]
>
>在表中， **boldface**&#x200B;类型使用其相关输出标识每个宏。 对于格式示例，已添加`<` `>`符号，以帮助直观地分隔每个宏。

## 文件名宏{#file-name-macros}

有关可用宏和定义的列表，请参阅[出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和输出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">完全: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">增量：<code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output（输出）: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 标题行宏{#header-macros}

有关可用宏和定义的列表，请参阅[出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和输出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Output（输出）: <code> 888 full.sync </code> </p> <p>在输出中，非打印制表符用于分隔每个元素。 </p> </td>
  </tr>
 </tbody>
</table>

## 文件内容宏{#file-content-macros}

有关可用宏和定义的列表，请参阅[出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)。

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和输出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;UUID&gt; </code> </p> <p>Output（输出）: <code> 123456 07955261652886032950143702505894272138 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output（输出）: <code> 07955261652886032950143702505894272138 DP_UUID1 DP_UUID2 DP_UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>请参阅下面的单独部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output（输出）: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output（输出）: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>格式：</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;",&nbsp;"DataCenterId":&nbsp;2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;}; separator=","&gt;&lt;if(SEGMENT_LIST&nbsp;&amp;&amp;&nbsp;REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; &lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", "TtlInMinutes":0&lt;CLOSE_CURLY_BRACKET&gt;};&nbsp;separator=","&gt;]}
     </code></p><p><b>Output（输出）:</b></p> <p>
     <code>//First&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"4321"}]} //Second&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2,"TDID":"9099e8fe-abab-5114-abaa-28bdaa0539ca","Data":[{"Name":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} 
     </code></p> <p> <p>注意： 在第一个示例中，宏仅返回<code> SEGMENT_LIST </code>的数据，因为<code> REMOVED_SEGMENT_LIST </code>为空。 第二个示例返回两个宏的数据。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>格式: </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </code> </p> <p>Output（输出）: </p> <p> <code> 1159 00088008579683653741516297509717335000 17t0aj01b120hp 1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output（输出）: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>在输出中，非打印制表符用于分隔每个元素。 </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>格式: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output（输出）: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` 示例

为了帮助您了解`DPUUID`宏如何输出数据，我们假定有2个`DPID`映射到`DPUUID`，如下所示：

* DPID `1111`映射到DPUUID `AAAA`（时间戳= 1）和`BBBB`（时间戳= 2）。
* DPID `2222`映射到DPUUID `CCCC`。

根据这些条件，下表枚举了一些可能的格式字符串及其输出。

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 映射条件 </th> 
   <th colname="col2" class="entry"> 宏格式 </th> 
   <th colname="col3" class="entry"> Output（输出） </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>返回单个DPID的所有映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>为所有DPID返回最多1个映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111,2222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","BBBB"],["2222","CCCC"]] </code> </p> <p>对于DPID <code> 1111 </code>，宏仅因为该ID的时间戳较大而映射到DPUUID <code> BBBB </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>为单个DPID返回最多2个映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCCC"]] </code> </p> <p>即使<code> maxMappings=2 </code>，此宏也只会返回1个DPID到DPUUID的映射，因为指定的DPID只有一个DPUUID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

[出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)
