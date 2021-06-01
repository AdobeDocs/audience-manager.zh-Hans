---
description: 面向希望从内部购买第三方数据的数据购买者的概述和工作流程Audience Manager
seo-description: 面向希望从内部购买第三方数据的数据购买者的概述和工作流程Audience Manager
seo-title: 面向数据购买者的 Audience Marketplace
solution: Audience Manager
title: 面向数据购买者的 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] 面向数据购买者  {#audience-marketplace-for-data-buyers}

面向希望从[!DNL Audience Manager]内购买第三方数据的数据购买者的概述和工作流程。

>[!NOTE]
>[基于角色的权限](../../../reporting/reports-dashboard.md)控制对[!UICONTROL Audience Marketplace]功能的访问。
>
>* 管理员可以创建数据馈送、管理订阅者和订阅数据馈送。
>* 用户只能搜索和查看信息源。


## [!UICONTROL Marketplace]:关于{#about-marketplace}

[!UICONTROL Marketplace]是一项[!DNL Audience Manager]功能，面向列出可订阅数据馈送的数据购买者。 它列出了固定速率、[!DNL CPM]和专用数据馈送。 这些信息源由使用[!DNL Audience Manager]销售数据的第三方供应商提供。

在[!UICONTROL Marketplace]中，报告工具允许您跟踪馈送使用情况以及[!UICONTROL traits]与订阅数据馈送中的使用情况和重叠。 最后，使用[!UICONTROL Audience Marketplace]时，[!DNL Adobe]会处理发票和费用支付（尽管您在订阅[!DNL CPM]信息源时必须自行报告使用情况）。 通过这些功能，您无需浪费时间寻找数据提供商即可找到有效的数据源。

>[!TIP]
>
>使用&#x200B;**[Adobe受众查找器](https://www.adobe-audience-finder.com/)**&#x200B;查找可订阅的高质量数据馈送。 然后，返回到[!DNL Audience Manager]用户界面或使用[Audience Marketplace购买者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)订阅您找到的馈送。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace]列表包含可进行排序和搜索以查找适合您的数据馈送的信息。 [!UICONTROL Marketplace]采购员列表中的项目包括：

* **[!UICONTROL Search]**:按名称或文本描述查找数据馈送。
* **[!UICONTROL Similar Traits]**:显示数据馈送中 [!UICONTROL traits] 的相似数量。在&#x200B;**[!UICONTROL Similarity To]**&#x200B;部分中输入[!UICONTROL trait]或[!UICONTROL segment]进行筛选后，将显示此列。
* **[!UICONTROL Name]**:数据馈送的名称。
* **[!UICONTROL Description]**:有关数据馈送内容的信息。
* **[!UICONTROL Provider]**:数据提供程序的名称。
* **[!UICONTROL Traits]**:数据馈 [!UICONTROL traits] 送中的数量。
* **[!UICONTROL 30 Day Provider Unique Users]**:过去30天内查看的独特用户数。
* **[!UICONTROL 30 Day Overlapped Uniques]**:您帐户中与提供商帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]**:30天重叠的唯一值（以百分比显示），计算如下：数据购买者30天重叠的独特值/数据购买者30天独特值)x 100。
* **[!UICONTROL Private Feeds]**:请参阅 [专用数据馈送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:您与数据提供商的订阅数。

 

要轻松找到符合您需求的最佳数据馈送，请使用[!UICONTROL Marketplace]页面左侧提供的以下过滤器：

* **[!UICONTROL Similarity To]**:根据数据馈送与您选择的或的 [!UICONTROL trait] 相 [!UICONTROL segment] 似性过滤数据馈送。输入要比较的[!UICONTROL trait]或区段时，可以使用[!UICONTROL trait]或[!UICONTROL segment] ID或其各自的名称。
* **[!UICONTROL Similarity Cutoff]**:拖动滑块以根据数据馈送与您选择的或 [!UICONTROL traits] 的相似程度 [!UICONTROL trait] 过滤 [!UICONTROL segment]数据馈送。要了解有关[!UICONTROL trait]相似度得分的更多信息，请参阅[特征相似度得分](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:根据订阅状态过滤数据馈送。
* **[!UICONTROL Plan Use Case]**:根据支持的用例过滤数据馈送： **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**:根据定价类型过滤数据馈送。

## 查找类似的[!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 允许您根据与现有或区 [!UICONTROL traits] 段的相似性，从各种数据馈送中 [!UICONTROL traits] 查找。下面是如何执行此操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用&#x200B;**[!UICONTROL Similarity To]**&#x200B;选择器可在基于[!UICONTROL trait]或[!UICONTROL segment]的筛选之间进行选择。 您可以根据[!UICONTROL trait]/[!UICONTROL segment] ID或名称进行筛选。 搜索框会根据您的输入自动显示相关建议。
3. 确定要过滤的特征或区段后，在建议列表中单击该特征或区段。
4. 要缩小结果范围，请使用&#x200B;**[!UICONTROL Similarity Cutoff]**&#x200B;滑块从不太相似的[!UICONTROL traits]移动到更相似的。

过滤完成后，您将在结果页面中看到一个新列：**[!UICONTROL Similar Traits]**。 此列显示符合筛选条件的每个数据馈送中与您过滤的[!UICONTROL traits]相似的数量。

要查看类似特征的完整列表，请单击&#x200B;**[!UICONTROL Similar Traits]**&#x200B;列中的数字。

>[!NOTE]
>
> Audience Marketplace显示数据馈送中前500个结果，与[!UICONTROL trait]结果类似。

请观看以下视频，获取有关如何查找类似[!UICONTROL traits]的完整概述。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 专用数据信息源 {#private-data-feeds}

在[!UICONTROL Marketplace]列表中，有时提供程序的名称和[!UICONTROL trait]数据会标记为私有。 这表示[专用数据馈送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私有数据馈送允许销售者限制买方访问其数据。 当卖家提供特价、折扣，或者隐私和访问控制对他们很重要时，他们可以私下提供信息源。 作为买方，如果您想要访问私人馈送，则必须向卖方发送订阅请求。 有关详细信息，请参阅[订阅专用数据馈送](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

>[!MORELIKETHIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

