---
description: 根据它们各自的键值对搜索一个或多个信号。
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 按键值对搜索信号 {#search-signals-by-key-value-pairs}

根据它们各自的键值对搜索一个或多个信号。
要搜索多个信号，请单击![添加](assets/icon_add.png)按钮。 输入要搜索的键值对，然后使用以下筛选条件缩小结果的范围。

* **信号状态**：搜索特征中包含的信号、未使用的信号或同时搜索两者。
* **查看**&#x200B;的记录：选择搜索接收信号的时间间隔。
* **最小计数**：仅显示选定间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为了提供简化的用户体验，键值对搜索结果基于数据采样。 有关[!DNL Audience Manager]如何使用数据取样以及为什么在比较键值搜索与常规搜索时可能会出现轻微结果差异的详细信息，请参阅[数据取样率和错误率](/help/using/reporting/report-sampling.md)。

使用多个键值对搜索信号时，[!DNL Audience Manager]使用逻辑&#x200B;**AND**&#x200B;运算符链接这些对。 例如，假设您使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回符合同一调用中所有三个筛选条件的结果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 从信号搜索中排除的信号 {#excluded-signals}

[!UICONTROL Signals Search]未显示Audience Manager使用且前缀为`d_`和`h_`的键变量。 有关详细信息，请参阅键变量](../../traits/trait-variable-prefixes.md)的[前缀要求。

## 区分大小写和搜索自动完成 {#case-insensitivity}

键和值搜索字段区分大小写。 关键搜索字段包括自动完成的建议。

![](assets/signal-search-suggestions.png)

假设[!DNL Audience Manager]收到以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

当您在关键搜索字段中输入`product`时，您将收到`productCategory`和`product`的自动完成建议。

同样，当您搜索`product == PHONE`时，[!UICONTROL Data Explorer]仅返回`product == PHONE`的结果。

回填特征实现也区分大小写。 包含键值对`PRODUCT == SMARTPHONE`的信号的特征不符合键值对`product == smartphone`的信号。
