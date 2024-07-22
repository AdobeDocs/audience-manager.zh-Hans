---
description: 定义并描述标准和序列化的键值对。
keywords: 集成代码
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: 键值对说明
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 3%

---

# 键值对说明{#key-value-pairs-explained}

定义并描述标准和序列化的键值对。

<!-- 

c_key_value_explained.xml

 -->

键值对由两个相关的数据元素组成：键值（用于定义数据集的常量，例如，性别、颜色、价格）和值（用于属于数据集的变量，例如，男性/女性、绿色、100）。 格式完整，键值对可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 标准和序列化的键值对 {#standard-serialized-pairs}

目标接受&#x200B;*`standard`*&#x200B;或&#x200B;*`serialized`*&#x200B;格式的键值数据。 标准格式设置将数据整理到单独的键值对中。 每个键都明确地声明，即使再次用来定义不同的值时也是如此。 相反，序列化格式将多个值压缩为由单个键定义的一个集。 此外，在序列化对中，使用特殊指示符来分隔键值集中的值。 最后，标准和序列化的键值可以包含单个或多个值。 下表提供了标准和序列键值格式的示例。

| 格式化 | 单键 | 键值对 |
|---|---|---|
| **标准** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **已序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 键、分隔符和分隔符 {#keys-delimiters-separators}

使用序列化数据时，必须指定将键值对中的值&#x200B;*在*&#x200B;内和&#x200B;*在*&#x200B;之间分隔的字符。 键值对中的元素的定义如下：

* **键：**&#x200B;键值对中的唯一标识符。
* **值分隔符：**&#x200B;用于分隔各个键值对。
* **键值分隔符：**&#x200B;将键与键值对中的值分开。
* **序列分隔符：**&#x200B;用于分隔序列化键值对中的各个值。

## 标准和序列化的键值元素 {#standard-serialized-key-value-elements}


| 类型 | 示例 | 键 | 键值分隔符 | 键值分隔符 | 串行分隔符 |
|---------|----------|---------|---------|----------|---------|
| **单键**（标准） | `x=1&x=2` | `x` | `=` | `&` | 不适用 |
| **键值对** （标准） | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | 不适用 |
| **单键**（串行） | `x=1;2;3` | `x` | `=` | 不适用 | `;` |
| **键值对** （序列） | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
