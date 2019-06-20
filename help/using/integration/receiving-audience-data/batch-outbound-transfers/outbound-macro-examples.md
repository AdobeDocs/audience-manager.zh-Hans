---
description: 一些常用宏如何用于创建出站文件模板的示例。
seo-description: 一些常用宏如何用于创建出站文件模板的示例。
seo-title: 出站宏示例
solution: Audience Manager
title: 出站宏示例
uuid: 823d85d4-d683-45cf-9e60-c12 b7 d52 a498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 出站宏示例 {#outbound-macro-examples}

一些常用宏如何用于创建出站文件模板的示例。

>[!NOTE]
>
>In the tables, **boldface** type identifies each macro with its related output. For the format examples, the `<` `>` symbols have been added to help visually separate each macro.

## File Name Macros {#file-name-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

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
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步模式 </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Full: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremental: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output（输出）: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 时间戳 </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Row Macros {#header-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

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
   <td colname="col2"> <p>Format: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Output: <code> 888 full.sync </code> </p> <p>在输出中，非打印选项卡字符将分隔每个元素。 </p> </td>
  </tr>
 </tbody>
</table>

## File Content Macros {#file-content-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 格式和输出示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUDS </code> </p> </td> 
   <td colname="col2"> <p>请参见下面的单独部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SERVER_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Segment_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(Segment_ LIST&amp;&amp; REMOVED_ SERVER_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p><b>格式：</b> </p> <p> 
     <code>{“advertiseriID”：“&lt; PIDAAS&gt;”、“dataEnterID”：2，“TID”：“&lt; DP_ UUID&gt;”、“数据”：[&lt; SUNTENCE_ LIST：{seg||&lt; OPEN_ COLLY_ STAREN&gt;“名称”：“&lt; seg. alias&gt;”&lt; CLOSE_ COURLY_ HOSTER&gt;}；separator="，"&gt;&lt;(Segment_ LIST&amp;&amp; REMOVED_ SERVER_ LIST)&gt;&lt; COMMMA&gt;&lt; endif&gt;&lt; REMOVED&gt;&lt; REMOVED_ SERVER_ LIST：{seg||&lt; OPEN_ COLLY_ STAREN&gt;“名称”：“&lt; seg. alias&gt;”，“ttlinMinutes”：&lt; CLOSE_ COLLY_ HOSTER&gt;}；separator="，"&gt;]} </code>
 </p><p><b>Output（输出）:</b></p> <p>
     <code>//First示例{“advertiseriID”：“12345”、“dataEnterID”：2，“TID”：“dfd215e4-8d6b-4fdb-90b9-fab4456 f2 c9 d”，“数据”：[{“名称”：“4321”}]}//Second示例{“advertiseriID”：“12345”、“dataEnterID”：2，“TID”：“9099e8fe-abab-5114-aba-28bda0539 ca”，“数据”：[{“名称”：“4321”}、{“Name”：“987”，“ttlinTips”：0}，{“Name”：“654”，“ttlin分钟”：}]}} </code>
 </p> <p> <p>Note:  In the first example, the macro only returns data for <code> SEGMENT_LIST </code> because <code> REMOVED_SEGMENT_LIST </code> is empty. 第二个示例返回两个宏的数据。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ TERMATS </code> </p> </td> 
   <td colname="col2"> <p>格式: </p> <p> <code> &lt; PID&gt;&lt; TAB&gt;&lt; UUID&gt;&lt; UUID&gt;&lt; TAB&gt;&lt; DP_ UUID&gt;&lt; TAB&gt;&lt; SET_ OUTTIONS&gt;&lt; TAB&gt;&lt; OPTION_ OUT&gt;&lt; TAB&gt;&lt; SUNCTION_ LIST：{seg||&lt; seg. type&gt;、&lt; see. alias&gt;、&lt; OUTPUT_ PROGATIBER_ VALUE&gt;、&lt; Seg. laxDisdateTime&gt;&amp;}&gt; </code> </p> <p>Output（输出）: </p> <p> <code> 115900080085796796836537415797507373717T0aj01b120p1，1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>在输出中，非打印选项卡字符将分隔每个元素。 </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` 示例

To help you understand how the `DPUUID` macro outputs data, lets assume we have 2 `DPID`s mapped to `DPUUID`s as shown below:

* DPID `1111` maps to DPUUIDs `AAAA` (timestamp = 1) and `BBBB` (timestamp = 2).
* DPID `2222` maps to DPUUID `CCCC`.

在这些情况下，下表列出了一些可能的格式字符串及其输出。

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
   <td colname="col2"> <p> <code> &lt; DPUUDS；format=“dpds=1111| maxMapTypes=0| format= json”&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[“1111”、“AAAA”]、[“1111”、“BBBB”]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>为所有DPII返回最多个映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUDS；format="dpds=1111,2222| maxMapTypes=1| format= json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[“1111”、“BBBB”]、[“2222”、“CCCC”]] </code> </p> <p>For DPID <code> 1111 </code>, the macro maps to DPUUID <code> BBBB </code> only because that ID has the larger timestamp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>为单个DPID返回最多个映射 </p> </td> 
   <td colname="col2"> <p> <code> &lt; DPUUDS；format="dpds=2222| maxMapTypes=2| format= json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[“2222”，“CCCC”]] </code> </p> <p>Even though <code> maxMappings=2 </code>, this macro returns only 1 DPID to DPUUID mapping because the specified DPID has only one DPUUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[出站模板宏](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)