---
description: 根据一个或多个信号各自的键值对搜索这些信号。
seo-description: 根据一个或多个信号各自的键值对搜索这些信号。
seo-title: 按键值对搜索信号
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 2206b5e40f7024084953fed52bb02fcc46ea36f1

---


# 按键值对搜索信号 {#search-signals-by-key-value-pairs}

根据一个或多个信号各自的键值对搜索这些信号。
要搜索多个信号，请单击“添 ![加](assets/icon_add.png) ”按钮。 输入要搜索的键值对，然后使用以下过滤器缩小结果范围。

* **信号状态**:搜索包含在特征、未使用信号或两者中的信号。
* **查看以下记录**:选择搜索接收信号的时间间隔。
* **最小计数**:仅显示在选定间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为简化用户体验，键值对搜索结果基于数据采样。 有关如 [何使用数据采样以及在将键值搜索与常规搜索进行比较时](/help/using/reporting/report-sampling.md)[!DNL Audience Manager] 可能出现细微结果变化的原因的详细信息，请参阅数据采样和错误率。

当使用多个键值对搜索信号时，使用 [!DNL Audience Manager] 逻辑 **AND** 运算符链接这些对。 例如，假设您使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回同一调用中符合所有三个过滤器条件的结果： `c_creative == "12345"``AND``c_product == "smartphone"` `AND``c_location == "europe"`..

![](assets/signals-search.png)

## 从信号搜索中排除的信号 {#excluded-signals}

Audience manager使用的、由前缀和前缀 `d_` 前缀引 `h_` 用的关键变量不会浮出水面 [!UICONTROL Signals Search]。 有关详 [细信息，请参阅关键变量的前缀要求](../../traits/trait-variable-prefixes.md) 。

## 区分大小写并自动完成搜索 {#case-insensitivity}

键和值搜索字段不区分大小写。 键搜索字段包括自动完成的建议。

![](assets/signal-search-suggestions.png)

假设接收 [!DNL Audience Manager] 到了以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在键搜 `product` 索字段中输入后，您会收到自动完成的 `productCategory`、 `newProduct`、 `PRODUCT`和建议 `product`。

同样，当您搜索时， `product == phone`将 [!UICONTROL Data Explorer] 返回和的结果 `PRODUCT == phone` 结果 `product == PHONE`。
回填的特征实现不区分大小写。 包含具有键值对的信号的特征也 `PRODUCT == SMARTPHONE` 使具有键值对的信号有条件 `product == smartphone`。