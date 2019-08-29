---
description: 列出可用于创建出站模板的宏。其中包括文件名、标题宏和内容宏。
seo-description: 列出可用于创建出站模板的宏。其中包括文件名、标题宏和内容宏。
seo-title: 出站模板宏
solution: Audience Manager
title: 出站模板宏
uuid: c082d3-306b-4ff5-afb2-418bd543 d8 d0
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# 出站模板宏 {#outbound-template-macros}

列出可用于创建出站模板的宏。其中包括文件名、标题宏和内容宏。

## 文件名和文件头宏 {#file-name-header-macros}

表列表列出并描述可在文件名中使用的宏以及定义标题字段。有关代码示例，请参阅 [出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>非打印ASCII字符。它指示一行的开始或内容的一部分。它还可用于在文件中分隔数据列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>用户ID密钥数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>订单/目标ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ ALIAS </code> </p> </td> 
   <td colname="col2"> <p>订单/目标ID的别名。 </p> <p>别名在管理员UI中设置。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SplitNUM </code> </p> </td> 
   <td colname="col2"> <p>指示将出站文件拆分为多个部分。将文件名中的SPLITNUM部分替换为前面的部件号，以确保SUSITNUM部分至少有三个字符。</p>
   <p>SUSITNUM宏不需要被&lt;&gt;字符所包围。</p><p>示例： <code>&lt; SYNC_ TYPE&gt;_&lt; ORDER_ ID&gt;_&lt; DPID&gt;_&lt; SYNC_ MODE&gt;_&lt;时间戳&gt; SUSITNUM. csv</code>
<p>s3_123456_9999_ full_1566906141.csv</p> 
<p>s3_123456_9999_ full_1566906142.csv</p> 
<p>s3_123456_9999_ full_1566906143.csv</p> 
<p>以上示例中的最后三位数字(001,002,003)为SPLITNUM标识符。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步模式 </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型，包括： </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>：完全同步。 </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>：增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>指示数据传输方法，包括： </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此宏用作分隔符，在字段之间插入一个选项卡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 时间戳 </code> </p> </td> 
   <td colname="col2"> <p>A10-digital，UTC，Unix时间戳。 </p> <p>它还可以设置为 <code> &lt; TIMESTAMP；format=“yyyyMMddHmmss”&gt; </code> &gt; after Java date/timestamp格式设置规则。 </p> </td> 
  </tr>

</tbody> 
</table>

## 内容宏 {#content-macros}

宏用于格式化数据文件的内容。有关代码示例，请参阅 [出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)。

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_ COLLY_ STOLUSTER </code> </p> </td> 
   <td colname="col2"> <p>插入一个右大括号}字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 数据提供者唯一用户标识符 </span>。 </p> <p>这是您向出站文件中发送数据的数据合作伙伴的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>返回一个列表，其中包含数据合作伙伴的多个ID。如果您拥有多个子部门或允许您共享数据的其他组织组，则此功能很有用。此宏返回这些下级用户组的ID列表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUDS </code> </p> </td> 
   <td colname="col2"> <p>此宏的输出将数据提供者ID(DPID)映射到相关的唯一用户ID(DPUUID)。此宏必须具有格式字符串才能控制其输出。示例输出类似于以下内容： </p> <p> <code> “dpds= dpid1，dpid2，… dpid n| maxMapTypes= n| format= json” </code> </p> <p><code> maxMapTypes </code> 设置确定您希望宏返回的映射数。<code> 当maxMapTypes=时 </code>，此宏返回每个指定DPID的所有映射。数据由时间戳(最近一次)排序，并首先返回最大时间戳的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(Segment_ LIST&amp;&amp; REMOVED_ SERVER_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>这种宏组合创建了一个条件语句，它列出了用户属于并且已从中删除的区段。如果这两种条件均未达到或没有数据，则它会返回一个空字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_ CURLY_ STOLUCK </code> </p> </td> 
   <td colname="col2"> <p>插入一个左大括号{字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>已弃用。不要使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>订单或目标ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ TERMATY_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>已弃用。不要使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ TERMATY_ VALUE </code> </p> </td> 
   <td colname="col2"> <p>返回 <code> 1 </code> 作为静态硬编码值。 </p> </td> 
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
   <td colname="col1"> <p> <code> REMOVED_ SERVER_ LIST </code> </p> </td> 
   <td colname="col2"> <p>返回已删除的区段列表(如果有)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Segment_ LIST </code> </p> </td> 
   <td colname="col2"> <p>返回列表中区段的列表。接受以下可选参数： </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> SegmentiID </code>：区段ID。已弃用。使用 <code> sid </code>。 </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>：客户细分ID。已弃用。使用 <code> sid </code>。 </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>：区段ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> 类型 </code>：返回 <code> 5 </code>，一个静态硬编码值，它将数据标识为区段数据。 </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> 别名 </code>：已弃用。不要使用。 </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> laxDisdateTime </code>：指示上次区段被识别时间的Unix时间戳。 </li> 
    </ul> <p>将这些变量放在宏之后大括号中。例如，此代码将结果与管道分开”||“字符： <code> &lt; SUNTERGE_ LIST：{seg||&lt; seg. type&gt;，&lt; seg. sid&gt;}；separator="，"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ TERMATS </code> </p> </td> 
   <td colname="col2"> <p>返回 <code> 1 </code>，作为静态的硬编码值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 同步模式 </code> </p> </td> 
   <td colname="col2"> <p>指示同步类型，包括： </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>：完全同步。 </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>：增量同步。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>指示数据传输方法，包括： </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>此宏用作分隔符，在字段之间插入一个选项卡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>返回特征列表。接受以下可选参数： </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> 类型 </code>：通过数字ID标识特征类型。返回结果: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 标识DPM特征(脱机，由入站作业载入)的10 </code> 。 </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> 标识基于规则的特征(实时通过DCS载入)。 </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> 陷印ID </code>：特征ID。 </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastEnabled </code>：上次识别特征的时间。Unix时间戳。 </li> 
    </ul> <p>将这些变量放在宏之后大括号中。例如，此代码将结果与管道分开”||“字符： <code> &lt; TRAIT_ LIST：{traentity||&lt; traentity. id&gt;，&lt; traventiate. lastEnabled&gt;}；separator=”，“ </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> 用户ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [出站宏示例](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

