---
description: 进行调用时，DCS接受标准格式或序列化格式的键值数据。 有关如何设置标准键值数据和序列化键值数据的格式的信息，请参阅此部分。
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: 格式化DCS调用中的键值对
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# 格式化DCS调用中的键值对 {#formatting-key-value-pairs-in-dcs-calls}

进行调用时，[!DNL DCS]接受标准格式或序列化格式的键值数据。 有关如何设置标准键值数据和序列化键值数据的格式的信息，请参阅此部分。

## 标准和序列化的键值对 {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>标准</b> </td> 
   <td colname="col2"> <p>标准键值对由单个键和值组成。 此结构将数据整理到单独的键值对中。 每个键都明确地声明，即使再次使用该键来定义不同的值也是如此。 这是将数据发送到DCS的最常见方式。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>已序列化</b> </td> 
   <td colname="col2"> <p>序列化的键值对由单个键和多个值组成。 这可以是组织数据的有效方法，但序列化键值对需要特定符号来分隔每个键和每个键值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化键值对的分隔符和分隔符 {#delimiters-separators}

对于序列化的键值对，您必须指定用于分隔这些变量内部和之间值的标记。 Audience Manager需要使用以下分隔符和分隔符：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要求 </th> 
   <th colname="col2" class="entry"> 符号 </th> 
   <th colname="col3" class="entry"> 分隔个人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> &amp;符号&amp; </td> 
   <td colname="col3"> <p>键值对： </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> 逗号， </td> 
   <td colname="col3"> <p>键值对中的值： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [将数据发送到 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [键值对说明](../../../reference/key-value-pairs-explained.md)
