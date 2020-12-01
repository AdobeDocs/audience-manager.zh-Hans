---
description: 根据各自的键值对搜索一个或多个信号。
seo-description: 根据各自的键值对搜索一个或多个信号。
seo-title: 按键值对搜索信号
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# 按键值对搜索信号 {#search-signals-by-key-value-pairs}

根据各自的键值对搜索一个或多个信号。
要搜索多个信号，请单击![添加](assets/icon_add.png)按钮。 输入要搜索的键值对，然后使用以下过滤器缩小结果范围。

* **信号状态**:搜索包含在特征、未使用信号或两者中的信号。
* **视图记录**:选择搜索接收信号的时间间隔。
* **最小计数**:仅显示所选时间间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为简化用户体验，键值对搜索结果基于数据采样。 有关[!DNL Audience Manager]如何使用数据采样以及在将键值搜索与一般搜索进行比较时可能出现细微结果差异的详细信息，请参阅[数据采样和错误率](/help/using/reporting/report-sampling.md)。

当使用多个键值对搜索信号时，[!DNL Audience Manager]使用逻辑&#x200B;**AND**&#x200B;运算符链接这些对。 例如，假设您使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回符合同一呼叫中所有三个过滤器资格的结果：`c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 信号搜索中排除的信号{#excluded-signals}

由`d_`和`h_`前缀Audience Manager使用的、前缀为&lt;a0/>的关键变量不由[!UICONTROL Signals Search]呈现。 有关详细信息，请参阅[关键变量的前缀要求](../../traits/trait-variable-prefixes.md)。

## 大小写不敏感和搜索自动完成{#case-insensitivity}

键和值搜索字段不区分大小写。 键搜索字段包括自动完成的建议。

![](assets/signal-search-suggestions.png)

假设[!DNL Audience Manager]接收了以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在键搜索字段中输入`product`后，您会收到针对`productCategory`、`newProduct`、`PRODUCT`和`product`的自动完成建议。

同样，在搜索`product == phone`时，[!UICONTROL Data Explorer]会返回`PRODUCT == phone`和`product == PHONE`的结果。
回填特征实现不区分大小写。 包含键值对`PRODUCT == SMARTPHONE`的信号的特征还使用键值对`product == smartphone`限定信号。