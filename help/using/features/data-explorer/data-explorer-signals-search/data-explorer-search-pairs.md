---
description: 根据各自的键值对搜索一个或多个信号。
seo-description: 根据各自的键值对搜索一个或多个信号。
seo-title: 按关键值对搜索信号
title: 按关键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9 ec-af9 d4963 d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

根据各自的键值对搜索一个或多个信号。
To search for more than one signal, click the ![Add](assets/icon_add.png) button. 输入要搜索的键值对，然后使用以下过滤器缩小结果的范围。

* **信号状态**：搜索包含在特征、未使用信号或二者中的信号。
* **查看以下内容的记录**：选择用于搜索接收信号的时间间隔。
* **最低计数**：在选定的时间间隔内仅显示具有指定的最小总数的信号。

>[!IMPORTANT]
>
>对于简化的用户体验，键值对搜索结果基于数据采样。See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. 例如，假设您正在执行具有以下键值对的搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

键和值搜索字段区分大小写。密钥搜索字段包含自动完成的建议。

![](assets/signal-search-suggestions.png)

Let&#39;s say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
填充的特征现实化区分大小写。A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.