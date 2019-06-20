---
description: 定义并描述标准和序列化键值对。
keywords: 集成代码
seo-description: 定义并描述标准和序列化键值对。
seo-title: 键值对解释
solution: Audience Manager
title: 键值对解释
uuid: f1435742-81ca-4964-8370-acf2 f1 c47 a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

定义并描述标准和序列化键值对。

<!-- 

c_key_value_explained.xml

 -->

键值对由两个相关数据元素组成：一个键，它是定义数据集(例如性别、颜色、价格)和值的常数，它是属于集合的变量(如男性/女性、绿色、100)。完全构成的键值对如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. 标准格式可将数据组织到单独的键值对中。每个键都显式表示，即使再次使用也可以定义不同的值。相反，序列化格式将多个值压缩为一个键定义的一组。此外，在序列化对中，使用特殊指示符分隔键值集中的值。最后，标准和序列化的键值可以包含单个或多个值。下表提供标准和串行键值格式的示例。

| 格式化 | 单键键 | 关键值对 |
|---|---|---|
| **标准** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. 关键值对中的元素定义如下：

* **密钥：** 键值对中的唯一标识符。
* **值分隔符：** 分离各个键值对。
* **密钥值分隔符：** 将密钥与键值对内的值分开。
* **串行分隔符：** 分离序列化密钥值对内的各个值。

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 类型 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
   <th colname="col3" class="entry"> 键 </th> 
   <th colname="col4" class="entry"> 键值分隔线 </th> 
   <th colname="col5" class="entry"> 密钥值分隔符 </th> 
   <th colname="col6" class="entry"> 串行分隔符 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>单键键</b> <p>(标准) </p> </td> 
   <td colname="col2"> <code> x=1&amp; x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>键值对</b> <p>(标准) </p> </td> 
   <td colname="col2"> <code> x=1&amp; x=2&amp; y=3&amp; y=4 </code> </td> 
   <td colname="col3"> x，y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>单键键</b> <p>(串行) </p> </td> 
   <td colname="col2"> <code> x=1；2；3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> 不适用 </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>键值对</b> (串行) </td> 
   <td colname="col2"> <code> x=1；2&amp; y=3；个 </code> </td> 
   <td colname="col3"> x，y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

