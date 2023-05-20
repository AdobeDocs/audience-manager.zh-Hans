---
description: 定義並描述標準和序列化的機碼值組。
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
source-wordcount: '267'
ht-degree: 6%

---

# 键值对说明{#key-value-pairs-explained}

定義並描述標準和序列化的機碼值組。

<!-- 

c_key_value_explained.xml

 -->

機碼 — 值組包含兩個相關的資料元素：機碼（用來定義資料集的常數） （例如，性別、顏色、價格），以及值（屬於該集的變數） （例如，男性/女性、綠色、100）。 格式完整，機碼值組可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列化的索引鍵值配對 {#standard-serialized-pairs}

目的地接受中的索引鍵值資料 *`standard`* 或 *`serialized`* 格式。 標準格式會將資料組織成個別的索引鍵/值組。 每個索引鍵都會明確指出，即使再次用來定義不同的值。 相較之下，序列化格式會將多個值壓縮為單一索引鍵所定義的集合。 此外，在序列化配對中，會使用特殊指標來分隔索引鍵值集中的值。 最後，標準和序列化的機碼值可以包含單一或多個值。 下表提供標準和序列索引鍵值格式的範例。

| 格式設定 | 單一金鑰 | 索引鍵值配對 |
|---|---|---|
| **标准** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 索引鍵、分隔符號和分隔符號 {#keys-delimiters-separators}

使用序列化資料時，您必須指定分隔值的字元 *範圍* 和 *介於* 機碼值組。 索引鍵值配對中的元素定義如下：

* **索引鍵：** 機碼值組中的唯一識別碼。
* **值分隔符號：** 分隔個別索引鍵值配對。
* **索引鍵值分隔符號：** 將索引鍵與索引鍵 — 值配對中的值分開。
* **序列分隔符號：** 分隔序列化索引鍵值配對中的個別值。

## 標準與序列化的索引鍵值元素 {#standard-serialized-key-value-elements}


| 类型 | 示例 | 键 | 索引鍵值分隔符號 | 索引鍵值分隔字元 | 序列分隔符號 |
|---------|----------|---------|---------|----------|---------|
| **單一金鑰** （標準） | `x=1&x=2` | `x` | `=` | `&` | 不适用 |
| **索引鍵值配對** （標準） | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | 不适用 |
| **單一金鑰** （序列） | `x=1;2;3` | `x` | `=` | 不适用 | `;` |
| **索引鍵值配對** （序列） | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
