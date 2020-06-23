---
description: 希望从Audience Manager内购买第三方数据的数据购买者的概述和工作流
seo-description: 希望从Audience Manager内购买第三方数据的数据购买者的概述和工作流
seo-title: 面向数据购买者的 Audience Marketplace
solution: Audience Manager
title: 面向数据购买者的 Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] 对于数据购买者 {#audience-marketplace-for-data-buyers}

面向希望从内部购买第三方数据的数据购买者的概述和工作流程 [!DNL Audience Manager]。

>[!NOTE]
>[基于角色的权限](../../../reporting/reports-dashboard.md) ，控制对功能的 [!UICONTROL Audience Marketplace] 访问。
>
>* 管理员可以创建数据服务、管理订阅者和订阅数据服务。
>* 用户只能搜索和视图源。


## 以下 [!UICONTROL Marketplace]项： 关于 {#about-marketplace}

该功 [!UICONTROL Marketplace] 能适 [!DNL Audience Manager] 用于列表数据服务的用户，您可以订阅该数据服务。 它列表统一的价 [!DNL CPM]格和专用数据服务。 这些源由用于销售数据的第三方 [!DNL Audience Manager] 供应商提供。

在中， [!UICONTROL Marketplace]报告工具允许您跟踪源使用情况以及您与订阅的 [!UICONTROL traits] 数据源中的数据源之间的重叠。 最后， [!UICONTROL Audience Marketplace]您 [!DNL Adobe] 将处理发票和费用支付(尽管订阅源时您必须自行报告使用情况 [!DNL CPM] )。 利用这些功能，您无需浪费时间寻找数据提供者即可找到有效的数据源。

>[!TIP]
>
>使用 **[Adobe受众查找器](https://www.adobe-audience-finder.com/)**，查找可订阅的高质量数据服务。 然后，返回用户[!DNL Audience Manager]界面或使用[Audience Marketplace购买者](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)API订阅您找到的源。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

该 [!UICONTROL Marketplace] 列表包含您可以排序和搜索以查找适合您的数据源的信息。 采购员列表 [!UICONTROL Marketplace] 中的项目包括：

* **[!UICONTROL Search]**: 按名称或文本说明查找数据源。
* **[!UICONTROL Similar Traits]**: 显示数据源中的 [!UICONTROL traits] 类似数量。 此列在您在部分中输 [!UICONTROL trait] 入或 [!UICONTROL segment] 筛选依据后显 **[!UICONTROL Similarity To]** 示。
* **[!UICONTROL Name]**: 数据源的名称。
* **[!UICONTROL Description]**: 有关数据馈送内容的信息。
* **[!UICONTROL Provider]**: 数据提供程序的名称。
* **[!UICONTROL Traits]**: 数据馈 [!UICONTROL traits] 送中的数量。
* **[!UICONTROL 30 Day Provider Unique Users]**: 最近30天内看到的唯一用户数。
* **[!UICONTROL 30 Day Overlapped Uniques]**: 您帐户中与提供商帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]**: 30天重叠的唯一值（以百分比显示），计算为： 数据购买者30天重叠单位／数据购买者30天单位)x 100。
* **[!UICONTROL Private Feeds]**: 请参 [阅专用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**: 您与数据提供者的订阅数。

 

要轻松找到适合您需求的最佳过滤器源，请使用页面左侧的以下： [!UICONTROL Marketplace]

* **[!UICONTROL Similarity To]**: 根据数据源与您选择的数据源 [!UICONTROL trait] 或数据 [!UICONTROL segment] 源的相似性过滤数据源。 输入或 [!UICONTROL trait] 区段进行比较时，您可以使用或 [!UICONTROL trait] ID [!UICONTROL segment] 或其各自的名称。
* **[!UICONTROL Similarity Cutoff]**: 拖动滑块，根据数据源与选定或数据源 [!UICONTROL traits] 的相似程度筛 [!UICONTROL trait] 选数据 [!UICONTROL segment]源。 要进一步了解相似 [!UICONTROL trait] 性得分，请参 [阅特征相似性得分](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: 根据您的订阅状态过滤数据服务。
* **[!UICONTROL Plan Use Case]**: 根据支持的用例过滤数据服务： **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**: 根据数据服务的定价类型过滤数据服务。

## 查找类似内容 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 允许您根据与现有 [!UICONTROL traits] 或细分的相似性，从各种数据源中 [!UICONTROL traits] 查找。 下面介绍如何实现此操作：

1. 转到 **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用选 **[!UICONTROL Similarity To]** 择器在基于或的筛选之 [!UICONTROL trait] 间进行选 [!UICONTROL segment]择。 您可以根据/ [!UICONTROL trait]ID[!UICONTROL segment] 或名称进行筛选。 搜索框会根据您的输入自动向您显示相关建议。
3. 确定要筛选的特征或区段后，在建议列表中单击它。
4. 要缩小结果范围，请使用 **[!UICONTROL Similarity Cutoff]** 滑块从不太相似的 [!UICONTROL traits]移动到更相似的。

过滤完成后，您将在结果页面中看到一个新列： **[!UICONTROL Similar Traits]**. 此列显示符合筛选条 [!UICONTROL traits] 件的每个数据源中与筛选对象相似的数量。

要查看类似特征的完整列表，请单击列中的 **[!UICONTROL Similar Traits]** 数字。

>[!NOTE]
>
> Audience Marketplace显示数据源 [!UICONTROL trait] 中前500个相似结果。

观看以下视频，了解如何查找类似内容的完整概述 [!UICONTROL traits]。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 专用数据信息源 {#private-data-feeds}

在列表 [!UICONTROL Marketplace] 中，有时提供者的名称和数据 [!UICONTROL trait] 会标记为私有。 这表示专 [用数据源](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人数据馈送允许卖家限制买家访问其数据。 当销售者提供特价、折扣或隐私和访问控制对他们很重要时，他们可以将源变为私有。 作为买方，如果您想要访问私人源，您必须向卖方发送订阅请求。 有关 [详细信息，请参阅订阅](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 专用数据源。

>[!MORELIKETHIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

