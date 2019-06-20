---
description: 格式化入站特征数据文件时应遵循的必填字段、语法和规则。
seo-description: 格式化入站特征数据文件时应遵循的必填字段、语法和规则。
seo-title: 入站数据文件内容语法、无效字符、变量和示例
solution: Audience Manager
title: 入站数据文件内容语法、无效字符、变量和示例
uuid: 88699b29-1502-4183-a9 a4 be70692 a02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

格式化入站特征数据文件时应遵循的必填字段、语法和规则。

## File Content Syntax {#file-content-syntax}

入站数据文件中的字段必须以以下顺序显示。In this example, the `<` `>` symbols have been added to help separate each element visually. 您无需在数据文件中包含这些内容。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>对于在入站数据文件中发送的每个用户ID，我们可以处理200行的限制。例如，如果您为某个用户ID发送300行，则会保留前200行，并丢弃另外100行。在下面的示例中，您很好，因为您为用户ID和用户ID发送了个行。我们不对您包含在某行中的特征数或键值对执行限制。
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

表列出并定义了格式正确的入站数据文件中使用的变量。*斜体*表示变量占位符。

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>用户 ID </i> </code> </p> </td> 
   <td colname="col2"> <p>用户ID可以是： </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B"><span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>)分配的唯一用户ID。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">移动Android或iOS设备ID中的移动操作系统公开的未修改的表单。 </li> 
     </ul> </p> <p>对于移动ID： </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式：ID必须是大写的，而不是散列的。For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式：ID必须为小写字母，而不是散列。For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用单个选项卡分隔符分隔用户ID和特征ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>特征ID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span> 特征ID。We ask that you include <i>only onboarded traits</i> in inbound data files. 我们不会处理入站数据传输中的任何其他特征类型。 </p> <p> <p>注意：特征ID可通过使用返回有关所有特征的详细信息的GET方法找到。For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

下表描述了在入站数据文件中识别特征名称或ID的前缀。See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 前缀 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid= </code> </p> </td> 
   <td colname="col2"> <p><code> d_ sid </code> 前缀告诉我们的系统ID是 <span class="keyword"> Audience Manager </span> 特征ID。这与用户界面中显示的ID相同。You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid= </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p><code> d_ unsid= </code> 前缀告诉我们的系统ID是 <span class="keyword"> Audience Manager </span> 特征ID。这与用户界面中显示的ID相同。You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 特征规则 </a> 允许您设置特征资格资格条件。If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>例如，假设您创建了以下三个特征规则： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic==“123” </code> </li>
      <li> <code> ic==“456” </code> </li>
      <li> <code> ic==“789” </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. 这允许您在数据文件中创建更简单的特征列表。And, you do not need to include the <code> ic </code> prefix. 因此，数据文件的内容可能如下所示： </p> <p>
     <code><i>用户ID</i>&lt; TAB&gt;123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>键值对 </p> </td> 
   <td colname="col2"> <p>特征数据可以使用字母数字字符串格式设置为键值对。格式化键值对的方式有若干种，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key= value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> “key”= value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key=“value” </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> “key”=“value” </code> </li> 
     </ul><code> “age”=“32” </code> 、 <code> “性别”= m </code> 、 <code> model=“cick truck” </code> 、 <code> product= tablet </code> 都是正确格式化的键值对的示例。 </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### 特征ID

特征ID仅包含数字字符。We ask that you include *only onboarded traits* in inbound data files. 我们不会处理入站数据传输中的任何其他特征类型。

### 用户 ID

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 类型 </th> 
   <th colname="col2" class="entry"> 要求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>请勿</i> 使用编码冒号( <code> %3A </code>)或未编码的冒号(以下简称：)符号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile iOS(IDFA)或Android设备ID </p> </td> 
   <td colname="col2"> <p>移动设备ID必须严格格式化，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式：ID必须是大写的，而不是散列的。For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式：ID必须为小写字母，而不是散列。For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 关键值对

键值对中不正确的格式化值名称也会造成问题。在键值对中创建或命名值时，请遵循以下规则：

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字符 </th> 
   <th colname="col2" class="entry"> 要求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>报价字符(以下简称) </p> </td> 
   <td colname="col2"> <p>您可以使用键中的引号字符和键值对的值部分，如下所示： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city=“New York”，d_ city=“San Francisco” </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> “d_ city”=“New York”，“d_ city”=“San Francisco” </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>虚线字符(-) </p> </td> 
   <td colname="col2"> <p>我们忽略密钥开头的虚线符号。For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>请勿</i> 在键值对中使用 <code> Tab键 </code> 而不是空值。Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n，\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据文件格式 </th> 
   <th colname="col2" class="entry"> 说明和示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此数据文件显示一个用户符合条件24、26、27，已从特征28和29中删除。 </p> <p> 
     <code>597675591862062067070700700700101098252&amp; amp；nbsp；&amp; amp；nbsp；d_ sid=24，d_ sid=26，d_ sid=27，d_ unsid=28，d_ unsid=29 </code>
  </p> <p>注释:  <p>您还可以使用以下语法从用户配置文件中删除特征，而不是使用d_ unsid： </p> <p> 
      <code>597675591862062067070700700700101098252&amp; amp；nbsp；28：0和amp；nbsp；29：0 </code>
  </p> <p> 
      <code>597675591862062067070700700700101098252&amp; amp；nbsp；28：-1和amp；nbsp；29：-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. 因此，您可以将它们添加到以逗号分隔的数据文件中。选项卡将UUID与特征ID分开。The <code> ic </code> prefix is not required in the file. </p> <p><b>数字ID</b> </p> <p> 
     <code>DBWETE DHFMMgBBH2M4F9ZkJexnNRDD2PXMSI&amp; amp；nbsp；&amp; amp；nbsp；30608,50344,50338,5032,30626 </code>
  </p> <p><b>字符串ID</b> </p> <p> 
     <code>DBWETE DHFMMgBBH2M4F9ZkJexnNRDD2PXMSI&amp; amp；nbsp；&amp; amp；nbsp；ic=52，ic=55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用关键值对 </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>597675591862062067070700700700101098252&amp; amp；nbsp；“性别”=“女性”，“opense_ shopper”=“yes” </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[如果](assets/ftp_dpm_1234_1445374061.overwrite) 需要其他示例，请下载示例数据文件。The download file has a `.overwrite` file extension. 您可以使用简单的文本编辑器将其打开。

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID类型/操作 </th> 
   <th colname="col2" class="entry"> 使用d_ sid为用户配置文件添加特征 </th> 
   <th colname="col3" class="entry"> 使用d_ unsid从用户配置文件中删除特征 </th> 
   <th colname="col4" class="entry"> 在键值对中发送以向用户配置文件添加特征 </th> 
   <th colname="col5" class="entry"> 使用ic前缀为用户配置文件添加特征 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 示例1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 示例2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 示例3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 示例4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Android设备的Google Advertising ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 示例5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 示例6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 示例7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 示例8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>适用于iOS设备的Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 示例9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 示例10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 示例11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 示例12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您自己的CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 示例13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 示例14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 示例15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 示例16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

使用特征ID为Audience Manager UI发送特征资格信息。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

使用特征ID为Audience Manager UI发送特征取消资格信息。

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

或

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

或

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example-3}

发送密钥值对以添加Audience Manager UI的特征资格资格信息。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

使用ic前缀发送Audience Manager UI的特征资格信息。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

使用特征ID为Android设备发送特征资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

使用特征ID为Android设备发送特征取消资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example-7}

在键值对中发送以添加Android设备的特征资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

使用ic前缀发送Android设备的特征资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

使用特征ID为iOS设备发送特征资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

使用特征ID为iOS设备发送特征取消资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example-11}

在键值对中发送以添加iOS设备的特征资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

使用ic前缀发送iOS设备的特征资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

使用特征ID为DPUUID发送特征资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

使用特征ID为DPUUID发送特征取消资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example-15}

在键值对中发送以添加DPUUID的特征资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

使用ic前缀发送DPUUID的特征资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ This]
>
>* [特性生成器](../../../features/traits/about-trait-builder.md)

