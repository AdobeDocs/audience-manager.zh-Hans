---
description: 面向希望从Audience manager中购买第三方数据的数据购买者的概述和工作流
seo-description: 面向希望从Audience manager中购买第三方数据的数据购买者的概述和工作流
seo-title: 面向数据购买者的受众市场
solution: Audience Manager
title: 面向数据购买者的受众市场
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# 面向数据购买者的受众市场 {#audience-marketplace-for-data-buyers}

面向希望从内部购买第三方数据的数据购买者的概述和工作流 [!DNL Audience Manager]。

>[!NOTE]
>[基于角色的权限](../../../reporting/reports-dashboard.md) ，控制对功能的 [!UICONTROL Audience Marketplace] 访问。
>
>* 管理员可以创建数据馈送、管理订阅者和订阅数据馈送。
>* 用户只能搜索和查看源。


## 市场：关于 {#about-marketplace}

<!-- c_marketplace_about.xml -->

该功 [!UICONTROL Marketplace] 能适用于数 [!DNL Audience Manager] 据购买者，它列出了您可以订阅的数据馈送。 它列出统一率 [!DNL CPM]或专用数据源。 这些源由用于销售数据的第三方供应 [!DNL Audience Manager] 商提供。 在报 [!UICONTROL Marketplace]告工具中，您可以跟踪源使用情况以及特征与订阅数据源中的特征之间的重叠。 最后， [!UICONTROL Audience Marketplace]您会 [!DNL Adobe] 处理发票和费用支付（尽管订阅源时您必须自行报告使用情况） [!DNL CPM] 。 利用这些功能，您无需浪费时间寻找数据提供者即可找到有效的数据源。

>[!TIP]
> 
>使用 **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** ，查找可订阅的高质量数据源。 然后，返回Audience Manager UI或使用 [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) ，订阅您找到的源。

![](assets/buyer_marketplace.png)

该 [!UICONTROL Marketplace] 列表包含可进行排序和搜索以查找适合您的数据源的信息。 采购员列 [!UICONTROL Marketplace] 表中的项目包括：

* **[!UICONTROL Search]** :按名称或文本说明查找数据源。
* **[!UICONTROL Name]** :数据馈送的名称。
* **[!UICONTROL Description]** :有关数据馈送内容的信息。
* **[!UICONTROL Provider]** :数据提供者的名称。
* **[!UICONTROL Traits]** :数据馈送中的特征数。
* **[!UICONTROL 30 Day Provider Unique Users]** :最近30天内查看的唯一用户数。
* **[!UICONTROL 30 Day Overlapped Uniques]** :您帐户中与提供者帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]** :30天重叠的唯一值，以百分比显示，计算为：数据购买者30天重叠的唯一值／数据购买者30天唯一值)x 100。
* **[!UICONTROL Private Feeds]** :请参 [阅专用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]** :您与数据提供者的订阅数。

## 专用数据信息源 {#private-data-feeds}

在列表中， [!UICONTROL Marketplace] 有时提供者的名称和特征数据会标记为私有。 这表示专 [用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人数据馈送允许卖家限制买家访问其数据。 当销售者提供特价、折扣或隐私和访问控制对他们很重要时，他们可以将源设为私有。 作为买方，如果您希望访问私人源，则必须向卖方发送订阅请求。 有关 [详细信息，请参阅订阅专用数据源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 。

>[!MORE_LIKE_THIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

