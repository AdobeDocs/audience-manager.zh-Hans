---
description: 列出可用于创建出站模板的宏。 其中包括文件名宏、标题宏和内容宏。
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: 出站模板宏
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# 出站模板宏 {#outbound-template-macros}

列出可用于创建出站模板的宏。 其中包括文件名宏、标题宏和内容宏。

## 文件名和文件头宏 {#file-name-header-macros}

该表列出并描述了可在文件名中使用的宏以及定义标题字段的宏。 有关代码示例，请参阅[出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

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
   <td colname="col2"> <p>非打印ASCII字符。 它指示一行或一段内容的开头。 它也可用于分隔文件中的数据列。 </p> </td> 
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
   <td colname="col2"> <p> 允许为出站订单创建多行题头。 </p> </td> 
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
   <td colname="col2"> <p>指示出站文件拆分为多个部分。 将文件名中的SPLITNUM部分替换为前面加零的部件号，确保SPLITNUM部分至少有三个字符。</p>
   <p>SPLITNUM宏不需要用&lt;&gt;字符括起来。</p><p>示例： <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>上述示例中的后三位(001,002,003)是SPLITNUM标识符。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型并包括： </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>：完全同步。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>：增量同步。 </li> 
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
   <td colname="col2"> <p>此宏用作分隔符，在字段之间插入制表符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>10位数的UTC Unix时间戳。 </p> <p>也可以按照Java日期/时间戳格式规则将其格式化为<code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code>。 </p> </td> 
  </tr>

</tbody> 
</table>

## 内容宏 {#content-macros}

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
   <td colname="col2"> <p>插入右花括号<code>&rbrace;</code>字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term">数据提供程序唯一用户标识符</span>。 </p> <p>这是在出站文件中向其发送数据的数据合作伙伴的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回一个列表，其中包含数据合作伙伴的多个ID。 如果您的大型组织具有多个子部门或允许与其共享数据的其他组织组，则此功能非常有用。 此宏返回这些下属组的ID列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>此宏的输出会将数据提供程序ID (DPID)映射到相关的独特用户ID (DPUUID)。 此宏必须具有格式字符串才能控制其输出。 示例输出将类似于以下内容： </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p><code> maxMappings </code>设置决定您希望宏返回多少映射。 当<code> maxMappings=0 </code>时，此宏返回每个指定DPID的所有映射。 数据按时间戳排序（最近的时间戳在前），并首先返回具有最大时间戳的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>此宏组合会创建一个条件语句，其中列出用户属于并且已从其中删除的区段。 如果不满足这两个条件或没有数据，则返回空字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>插入左花括号<code>&lbrace;</code>字符。 </p> </td> 
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
   <td colname="col2"> <p>返回<code> 1 </code>作为静态硬编码值。 </p> </td> 
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
   <td colname="col2"> <p>返回已删除的区段的列表（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回列表中的区段列表。 接受以下可选参数： </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>：区段ID。 已弃用。使用<code> sid </code>。 </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>：客户区段ID。 已弃用。使用<code> sid </code>。 </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>：区段ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>：返回<code> 5 </code>，该值是将数据标识为区段数据的静态硬编码值。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>：已弃用。 请勿使用。 </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>：指示上次更新区段成员资格状态的Unix时间戳。 </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>：指示上次实现区段时间的Unix时间戳。 </li>
    </ul> <p>将这些变量放在宏后面的大括号中。 例如，此代码使用竖线“|”字符分隔结果： <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>返回<code> 1 </code>作为静态硬编码值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型并包括： </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>：完全同步。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>：增量同步。 </li> 
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
   <td colname="col2"> <p>此宏用作分隔符，在字段之间插入制表符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>返回特征列表。 接受以下可选参数： </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>：按数字ID标识特征类型。 返回： 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code>标识DPM特征（脱机，由入站作业载入）。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code>标识基于规则的特征（实时，通过DCS载入）。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>：特征标识。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>：上次实现该特征的时间。 Unix时间戳。 </li> 
    </ul> <p>将这些变量放在宏后面的大括号中。 例如，此代码用竖线“|”字符分隔结果： <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span>用户ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)
