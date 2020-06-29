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
要搜索多个信号，请单击“添加 ![”按](assets/icon_add.png) 钮。 输入要搜索的键值对，然后使用以下过滤器缩小结果范围。

* **信号状态**: 搜索包含在特征、未使用信号或两者中的信号。
* **视图记录**: 选择搜索接收信号的时间间隔。
* **最小计数**: 仅显示所选时间间隔内具有指定最小总计数的信号。

>[!IMPORTANT]
>
>为简化用户体验，键值对搜索结果基于数据采样。 有关 [使用数据采样的方](/help/using/reporting/report-sampling.md)[!DNL Audience Manager] 式以及在将键值搜索与一般搜索进行比较时可能出现细微结果变化的原因的详细信息，请参阅数据采样和错误率。

当使用多个键值对搜索信号时， [!DNL Audience Manager] 使用逻辑AND运算符链 **接这些** 对。 例如，假设您使用以下键值对执行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索将仅返回符合同一呼叫中所有三个过滤器资格的结果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 信号搜索中排除的信号 {#excluded-signals}

由Audience Manager使用并由前缀和前缀 `d_` 前缀 `h_` 前缀的关键变量不会由呈现 [!UICONTROL Signals Search]。 有关详 [细信息，请参阅关键变量的](../../traits/trait-variable-prefixes.md) 前缀要求。

## 大小写不敏感和搜索自动完成 {#case-insensitivity}

键和值搜索字段不区分大小写。 键搜索字段包括自动完成的建议。

![](assets/signal-search-suggestions.png)

假设接收 [!DNL Audience Manager] 到以下信号：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在键搜 `product` 索字段中输入时，您会收到自动完成的 `productCategory`、 `newProduct`、 `PRODUCT`和建议 `product`。

同样，在搜索时， `product == phone`会 [!UICONTROL Data Explorer] 返回和的 `PRODUCT == phone` 结果 `product == PHONE`。
回填特征实现不区分大小写。 包含带有键值对的信号的特征 `PRODUCT == SMARTPHONE` 也使用键值对限定信号 `product == smartphone`。