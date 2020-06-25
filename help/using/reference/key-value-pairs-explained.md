---
description: 定义和描述标准和序列化键值对。
keywords: integration code
seo-description: 定义和描述标准和序列化键值对。
seo-title: 键值对说明
solution: Audience Manager
title: 键值对说明
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%

---


# 键值对说明{#key-value-pairs-explained}

定义和描述标准和序列化键值对。

<!-- 

c_key_value_explained.xml

 -->

键值对由两个相关的数据元素组成： 一个键，它是定义数据集（例如，性别、颜色、价格）的常数，以及一个值，它是属于该集的变量（例如，男／女、绿色、100）。 键值对完全成形，可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

目标接受或格式的键 *`standard`* 值 *`serialized`* 数据。 标准格式将数据组织成单独的键值对。 每个键都被显式地表示，即使再次用于定义不同的值。 相反，序列化格式将多个值压缩为由单个键定义的一个集。 此外，在序列化对中，使用特殊指示符来分隔键值集中的值。 最后，标准和序列化键值可以包含一个或多个值。 下表提供标准和序列键值格式的示例。

| 格式化 | 单键 | 键值对 |
|---|---|---|
| **标准** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 键、分隔符和分隔符 {#keys-delimiters-separators}

处理序列化数据时，必须指定在键值对内 *和**键值对* 之间分隔值的字符。 键值对中的元素定义如下：

* **密钥：** 键值对中的唯一标识符。
* **值分隔符：** 分离各个键值对。
* **键值分隔符：** 将键与键值对中的值分开。
* **序列分隔符：** 在序列化键值对中分离单个值。

## 标准和序列化关键值元素 {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 类型 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
   <th colname="col3" class="entry"> 键 </th> 
   <th colname="col4" class="entry"> 键值分隔符 </th> 
   <th colname="col5" class="entry"> 键值分隔符 </th> 
   <th colname="col6" class="entry"> 串行分隔符 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>单键</b> <p>(标准) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>键值对</b> <p>(标准) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>单键</b> <p>（串行） </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> 不适用 </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>键值对</b> （串行） </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

