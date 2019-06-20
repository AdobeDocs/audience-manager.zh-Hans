---
description: 进行呼叫时，DCS以标准或序列化格式接受键值数据。查看本节以了解有关如何格式化标准和序列化密钥值数据的信息。
seo-description: 进行呼叫时，DCS以标准或序列化格式接受键值数据。查看本节以了解有关如何格式化标准和序列化密钥值数据的信息。
seo-title: 在DCS调用中格式化键值对
solution: Audience Manager
title: 在DCS调用中格式化键值对
uuid: af02f2a1-4388-4074-ab4 e-66ee82023 f1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. 查看本节以了解有关如何格式化标准和序列化密钥值数据的信息。

## Standard and Serialized Key-Value Pairs {#standard-serialized}

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
   <td colname="col2"> <p>标准键值对由单个键和值组成。此结构将数据组织到单独的键值对中。每个键显式表示，即使再次使用它定义不同的值也是如此。这是向DCS发送数据最常用的方法。 </p> </td>
   <td colname="col3"> <code> key1= val1&amp; key2= val2&amp; key3= val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化</b> </td> 
   <td colname="col2"> <p>序列化键值对由一个键和多个值组成。这可以是组织数据的有效方法，但序列化密钥值对需要特定符号来分隔每个键和每个键值。 </p> </td> 
   <td colname="col3"> <code> key1= val1，val2，val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

使用序列化密钥值对，您必须指定这些变量内和之间不同值的标记。Audience Manager需要以下分隔符和分隔符：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对对 </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> 分离个人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> &amp;&amp;&amp; </td> 
   <td colname="col3"> <p>密钥值对： </p> <p><code> key1= val1&amp; key2= val2，val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> 逗号 , </td> 
   <td colname="col3"> <p>键值对内的值： </p> <p><code> key1= val1，val2，val&amp; key2= valA，ValB，ValC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [将数据发送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [关键值前缀和由DCS支持的变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [键值对解释](../../../reference/key-value-pairs-explained.md)

