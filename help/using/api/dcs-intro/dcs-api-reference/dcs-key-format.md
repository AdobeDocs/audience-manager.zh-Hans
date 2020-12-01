---
description: 发出呼叫时，DCS以标准或序列化格式接受密钥值数据。 有关如何格式化标准和序列化键值数据的信息，请查阅本节。
seo-description: 发出呼叫时，DCS以标准或序列化格式接受密钥值数据。 有关如何格式化标准和序列化键值数据的信息，请查阅本节。
seo-title: 格式化 DCS 调用中的键值对
solution: Audience Manager
title: 格式化 DCS 调用中的键值对
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---


# 格式化 DCS 调用中的键值对 {#formatting-key-value-pairs-in-dcs-calls}

发出呼叫时，[!DNL DCS]以标准或序列化格式接受键值数据。 有关如何格式化标准和序列化键值数据的信息，请查阅本节。

## 标准和序列化密钥值对{#standard-serialized}

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
   <td colname="col2"> <p>标准键值对由单个键和值组成。 此结构将数据组织成单独的键值对。 每个键都明确表示，即使再次用于定义不同的值也是如此。 这是向DCS发送数据的最常见方式。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化</b> </td> 
   <td colname="col2"> <p>序列化键值对由单个键和多个值组成。 这可以是组织数据的有效方式，但序列化键值对需要特定符号来分隔每个键和每个键值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化键值对{#delimiters-separators}的分隔符和分隔符

对于序列化键值对，必须指定这些变量内和变量之间的值分隔的标记。 Audience Manager需要以下分隔符和分隔符：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对 </th> 
   <th colname="col2" class="entry"> 符号 </th> 
   <th colname="col3" class="entry"> 分离个人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> &amp;符号和 </td> 
   <td colname="col3"> <p>键值对： </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> 逗号 , </td> 
   <td colname="col3"> <p>键值对中的值： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [将数据发送到 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS支持的键值前缀和变量](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [键值对说明](../../../reference/key-value-pairs-explained.md)

