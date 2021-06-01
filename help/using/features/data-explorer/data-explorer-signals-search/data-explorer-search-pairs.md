---
description: 根据一个或多个信号各自的键值对搜索它们。
seo-description: 根据一个或多个信号各自的键值对搜索它们。
seo-title: 按键值对搜索信号
title: 按键值对搜索信号
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# 按键值对搜索信号 {#search-signals-by-key-value-pairs}

根据一个或多个信号各自的键值对搜索它们。
要搜索多个信号，请单击![Add](assets/icon_add.png)按钮。 输入要搜索的键值对，然后使用以下过滤器缩小结果范围。

* **信号状态**:搜索特征、未使用的信号或两者中包含的信号。
* **查看**&#x200B;的记录：选择搜索接收信号的时间间隔。
* **最小计数**:仅显示在选定间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为了简化用户体验，键值对搜索结果基于数据采样。 有关[!DNL Audience Manager]如何使用数据采样以及在将键值搜索与常规搜索进行比较时可能出现细微结果差异的原因的详细信息，请参阅[数据采样和错误率](/help/using/reporting/report-sampling.md)。

在使用多个键值对搜索信号时， [!DNL Audience Manager]使用逻辑&#x200B;**AND**&#x200B;运算符链接这些对。 例如，假设您正在使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回符合同一调用中所有三个过滤器资格的结果：`c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 从信号搜索中排除的信号{#excluded-signals}

由Audience Manager使用且前缀为`d_`和`h_`前缀的关键变量不由[!UICONTROL Signals Search]显示。 有关详细信息，请参阅[键变量的前缀要求](../../traits/trait-variable-prefixes.md)。

## 不区分大小写并搜索自动完成{#case-insensitivity}

键和值搜索字段不区分大小写。 键搜索字段包含自动完成的建议。

![](assets/signal-search-suggestions.png)

假设[!DNL Audience Manager]收到了以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在键搜索字段中输入`product`后，您将收到有关`productCategory`、`newProduct`、`PRODUCT`和`product`的自动完成建议。

同样，在搜索`product == phone`时， [!UICONTROL Data Explorer]会返回`PRODUCT == phone`和`product == PHONE`的结果。
回填的特征实现不区分大小写。 包含键值对`PRODUCT == SMARTPHONE`的信号的特征还使用键值对`product == smartphone`来限定该信号。
