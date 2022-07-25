---
description: 根据一个或多个信号各自的键值对搜索它们。
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# 按键值对搜索信号 {#search-signals-by-key-value-pairs}

根据一个或多个信号各自的键值对搜索它们。
要搜索多个信号，请单击 ![添加](assets/icon_add.png) 按钮。 输入要搜索的键值对，然后使用以下过滤器缩小结果范围。

* **信号状态**:搜索特征、未使用的信号或两者中包含的信号。
* **查看的记录**:选择搜索接收信号的时间间隔。
* **最小计数**:仅显示在选定间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为了简化用户体验，键值对搜索结果基于数据采样。 请参阅 [数据取样率和错误率](/help/using/reporting/report-sampling.md) 有关如何 [!DNL Audience Manager] 使用数据取样，以及在将键值搜索与常规搜索进行比较时可能出现细微结果变化的原因。

在使用多个键值对搜索信号时， [!DNL Audience Manager] 使用逻辑 **和** 运算符。 例如，假设您正在使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回符合同一调用中所有三个过滤器资格的结果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 从信号搜索中排除的信号 {#excluded-signals}

由Audience Manager使用且前缀为 `d_` 和 `h_` 前缀不显示为 [!UICONTROL Signals Search]. 请参阅 [关键变量的前缀要求](../../traits/trait-variable-prefixes.md) 以了解详细信息。

## 区分大小写并搜索自动完成 {#case-insensitivity}

键和值搜索字段区分大小写。 键搜索字段包含自动完成的建议。

![](assets/signal-search-suggestions.png)

假设 [!DNL Audience Manager] 收到以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

当您输入 `product` 在“键搜索”字段中，您会收到 `productCategory` 和 `product`.

同样，当您搜索 `product == PHONE`, [!UICONTROL Data Explorer] 仅返回结果 `product == PHONE`.

回填的特征实现也区分大小写。 包含具有键值对的信号的特征 `PRODUCT == SMARTPHONE` 不使用键值对限定信号 `product == smartphone`.
