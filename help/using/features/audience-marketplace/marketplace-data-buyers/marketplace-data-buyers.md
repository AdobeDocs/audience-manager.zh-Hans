---
description: 希望从Audience Manager内购买第三方数据的数据购买者的概述和工作流程
seo-description: 希望从Audience Manager内购买第三方数据的数据购买者的概述和工作流程
seo-title: 数据买家的受众市场
solution: Audience Manager
title: 数据买家的受众市场
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128 b540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[基于角色的权限](../../../reporting/reports-dashboard.md) 控制 [!UICONTROL Audience Marketplace] 对功能的访问。
>
>* 管理员可以创建数据服务、管理订阅者和订阅数据源。
>* 用户只能搜索和查看源。


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). 这些功能可让您找到有效的数据源，而无需浪费时间寻找数据提供商。

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] 该列表包含可排序和搜索的信息，以查找适合您的数据源。[!UICONTROL Marketplace] 买方列表中的项目包括：

* **[!UICONTROL Search]：** 按名称或文本描述查找数据源。
* **[!UICONTROL Name]：** 数据源的名称。
* **[!UICONTROL Description]：** 有关数据源内容的信息。
* **[!UICONTROL Provider]：** 数据提供程序的名称。
* **[!UICONTROL Traits]：** 数据馈送中的特征数。
* **[!UICONTROL 30 Day Provider Unique Users]：** 最近30天内唯一用户的查看次数。
* **[!UICONTROL 30 Day Overlapped Uniques]：** 帐户中与提供者帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]：** 30天重叠的唯一值(以百分比表示)，计算为：数据购买者30天重叠唯一数据/数据购买者30天统一) x100。
* **[!UICONTROL Private Feeds]：** 请参阅 [私人数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]：** 数据提供程序的订阅数量。

## 专用数据信息源 {#private-data-feeds}

[!UICONTROL Marketplace] 在列表中，有时提供者的名称和特征数据将标记为私有。This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). 私人数据源允许卖家限制购买者访问其数据。当卖家提供特价交易、折扣或隐私权和访问控制对他们至关重要时，销售人员可以将其设为私有。作为购买者，如果您希望访问私人源，则必须向卖家发送订阅请求。See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ This]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

