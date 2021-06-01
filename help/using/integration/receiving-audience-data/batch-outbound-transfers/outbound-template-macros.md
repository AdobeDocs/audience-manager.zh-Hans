---
description: 列出可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。
seo-description: 列出可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。
seo-title: 出站模板宏
solution: Audience Manager
title: 出站模板宏
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: 出站数据传输
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 3%

---

# 出站模板宏 {#outbound-template-macros}

列出可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。

## 文件名和文件头宏{#file-name-header-macros}

该表列出并描述了可在文件名中使用的宏以及定义标题字段。 有关代码示例，请参阅[出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>非打印ASCII字符。 它指示行或内容部分的开始。 它还可用于分隔文件中的数据列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>用户ID密钥数据提供程序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> 允许为出站订单创建多行标头。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>订单/目标ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>订单/目标ID的别名。 </p> <p>别名在管理员UI中设置。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>指示将出站文件拆分为多个部分。 将文件名中的SPLITNUM部分替换为前面为零的部件号，确保SPLITNUM部分至少有三个字符。</p>
   <p>SPLITNUM宏不需要被&lt;&gt;字符包围。</p><p>示例: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>上例中最后三位(001,002,003)是SPLITNUM标识符。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型，包括： </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>:完全同步。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>:增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>指示数据传输方法，包括： </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此宏用作分隔符，用于在字段之间插入制表符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>10位UTC、Unix时间戳。 </p> <p>也可以按照Java日期/时间戳格式规则，将其格式设置为<code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code>。 </p> </td> 
  </tr>

</tbody> 
</table>

## 内容宏{#content-macros}

用于格式化数据文件内容的宏。 有关代码示例，请参阅[出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>插入右大括号<code>}</code>字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 数据提供程序唯一用户标识 </span>符。 </p> <p>这是您在出站文件中将数据发送到的数据合作伙伴的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回一个列表，其中包含数据合作伙伴的多个ID。 如果您有一个大型组织，其中包含多个子部门或允许您与其共享数据的其他组织组，则此功能非常有用。 此宏会返回这些下属组的ID列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>此宏的输出会将数据提供程序ID(DPID)映射到相关的唯一用户ID(DPUUID)。 此宏必须具有格式字符串才能控制其输出。 示例输出应类似于以下内容： </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p><code> maxMappings </code>设置确定您希望宏返回的映射数。 当<code> maxMappings=0 </code>时，此宏会返回每个指定DPID的所有映射。 数据按时间戳（最近的第一个）排序，并首先返回时间戳最大的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>此宏组合会创建一个条件语句，其中列出了用户所属的区段以及从中删除的区段。 如果两个条件都不满足或没有数据，则返回空字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>插入左大括号<code>{</code>字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>已弃用。请勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>订单或目标ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>已弃用。请勿使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>返回<code> 1 </code>作为静态的硬编码值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>订单/目标ID的别名。 </p> <p>别名在管理员UI中设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回已删除的区段列表（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回列表中的区段列表。 接受以下可选参数： </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>:区段ID。已弃用。使用 <code> sid </code>。 </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>:客户区段ID。已弃用。使用 <code> sid </code>。 </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>:区段ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>:返回 <code> 5 </code>一个静态的硬编码值，用于将数据标识为区段数据。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: 已弃用. 请勿使用。 </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>:Unix时间戳，指示上次实现区段的时间。 </li> 
    </ul> <p>将这些变量放在宏后面的大括号中。 例如，此代码用管道字符“|”分隔结果：<code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>返回<code> 1 </code>作为静态硬编码值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型，包括： </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>:完全同步。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>:增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>指示数据传输方法，包括： </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此宏用作分隔符，用于在字段之间插入制表符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回特征列表。 接受以下可选参数： </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>:按数字ID标识特征类型。返回结果: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> 用于标识DPM特征（离线，由入站作业载入）。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> 用于标识基于规则的特征（实时，通过DCS载入）。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>:特征ID。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>:上次实现特征时。Unix时间戳。 </li> 
    </ul> <p>将这些变量放在宏后面的大括号中。 例如，此代码用管道字符“|”分隔结果：<code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> 用户ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

