---
description: 面向希望从Audience manager中购买第三方数据的数据购买者的概述和工作流
seo-description: 面向希望从Audience manager中购买第三方数据的数据购买者的概述和工作流
seo-title: 面向数据购买者的受众市场
solution: Audience Manager
title: 面向数据购买者的受众市场
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: f66c5a0fb6ea1b0e89b804e56fa7045978427ab8

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

该功 [!UICONTROL Marketplace] 能适用于数 [!DNL Audience Manager] 据购买者，它列出了您可以订阅的数据馈送。 它列出统一的速 [!DNL CPM]率、私有数据源。 这些源由用于销售数据的第三方供应 [!DNL Audience Manager] 商提供。

在报 [!UICONTROL Marketplace]告工具中，您可以跟踪源使用情况以及特征与订阅数据源中的特征之间的重叠。 最后， [!UICONTROL Audience Marketplace]您会 [!DNL Adobe] 处理发票和费用支付（尽管订阅源时您必须自行报告使用情况） [!DNL CPM] 。 利用这些功能，您无需浪费时间寻找数据提供者即可找到有效的数据源。

>[!TIP]
>
>使用 **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** ，查找可订阅的高质量数据源。 然后，返回Audience Manager UI或使用 [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) ，订阅您找到的源。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

该 [!UICONTROL Marketplace] 列表包含可进行排序和搜索以查找适合您的数据源的信息。 采购员列 [!UICONTROL Marketplace] 表中的项目包括：

* **[!UICONTROL Search]**:按名称或文本说明查找数据源。
* **[!UICONTROL Similar Traits]**:显示数据源中类似特征的数量。 在部分中输入要筛选的特征或区段后，将显示此 **[!UICONTROL Similarity To]** 列。
* **[!UICONTROL Name]**:数据馈送的名称。
* **[!UICONTROL Description]**:有关数据馈送内容的信息。
* **[!UICONTROL Provider]**:数据提供者的名称。
* **[!UICONTROL Traits]**:数据馈送中的特征数。
* **[!UICONTROL 30 Day Provider Unique Users]**:最近30天内查看的唯一用户数。
* **[!UICONTROL 30 Day Overlapped Uniques]**:您帐户中与提供者帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]**:30天重叠的唯一值，以百分比显示，计算为：数据购买者30天重叠的唯一值／数据购买者30天唯一值)x 100。
* **[!UICONTROL Private Feeds]**:请参 [阅专用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:您与数据提供者的订阅数。

 

要轻松找到满足您需求的最佳数据源，请使用页面左侧的以下过滤器 [!UICONTROL Marketplace] :

* **[!UICONTROL Similarity To]**:根据与所选特征或区段的相似性过滤数据源。 在输入要进行比较的特征或区段时，可以使用特征或区段ID或其各自的名称。
* **[!UICONTROL Similarity Cutoff]**:拖动滑块，根据数据馈送的特征与所选特征或区段的相似程度过滤数据馈送。 要进一步了解特征相似性得分，请参阅特 [征相似性得分](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:根据您的订阅状态过滤数据服务。
* **[!UICONTROL Plan Use Case]**:根据支持的用例过滤数据服务： **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**:根据定价类型过滤数据馈送。

## 查找相似特征 {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 允许您根据与现有特征或区段的相似性从各种数据源中查找特征。 下面介绍如何实现此操作：

1. 转到 **[!UICONTROL Audience Marketplace]** &gt; **[!UICONTROL Marketplace]**。
2. 使用选 **[!UICONTROL Similarity To]** 择器在基于特征或区段的筛选之间进行选择。 您可以根据特征／区段ID或名称进行筛选。 搜索框会根据您的输入自动向您显示相关建议。
3. 确定要筛选的特征或区段后，在建议列表中单击它。
4. 要缩小结果范围，请使用滑 **[!UICONTROL Similarity Cutoff]** 块从较不相似的特征向较相似的特征移动。

过滤完成后，您会在结果页面中看到一个新列： **[!UICONTROL Similar Traits]**. 此列显示符合筛选条件的每个数据馈送中与筛选依据的相似特征的数量。

要查看类似特征的完整列表，请单击列中的数 **[!UICONTROL Similar Traits]** 字。

>[!NOTE]
>
> Audience Marketplace显示了来自所有数据源的500个类似特征结果。

观看以下视频，了解如何查找类似特征的完整概述。

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=chi_hans)

## 专用数据信息源 {#private-data-feeds}

在列表中， [!UICONTROL Marketplace] 有时提供者的名称和特征数据会标记为私有。 这表示专 [用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人数据馈送允许卖家限制买家访问其数据。 当销售者提供特价、折扣或隐私和访问控制对他们很重要时，他们可以将源设为私有。 作为买方，如果您希望访问私人源，则必须向卖方发送订阅请求。 有关 [详细信息，请参阅订阅专用数据源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 。

>[!MORELIKETHIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

