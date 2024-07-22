---
description: 适用于希望在Audience Manager内购买第三方数据的数据购买者的概述和工作流
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: 面向数据购买者的Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

---

# 面向数据购买者的[!UICONTROL Audience Marketplace] {#audience-marketplace-for-data-buyers}

适用于希望从[!DNL Audience Manager]内购买第三方数据的数据购买者的概述和工作流。

>[!NOTE]
>[基于角色的权限](../../../reporting/reports-dashboard.md)控制对[!UICONTROL Audience Marketplace]功能的访问。
>
>* 管理员可以创建数据馈送、管理订阅者，以及订阅数据馈送。
>* 用户只能搜索和查看信息源。

## [!UICONTROL Marketplace]：关于 {#about-marketplace}

[!UICONTROL Marketplace]是数据购买者的[!DNL Audience Manager]功能，其中列出了您可以订阅的数据馈送。 它列出了统一费率、[!DNL CPM]和专用数据馈送。 这些馈送由使用[!DNL Audience Manager]销售数据的第三方供应商提供。

在[!UICONTROL Marketplace]中，报告工具允许您跟踪馈送使用情况以及[!UICONTROL traits]与订阅数据馈送中的馈送之间的重叠。 最后，通过[!UICONTROL Audience Marketplace]，[!DNL Adobe]负责发票和费用支付（不过在订阅[!DNL CPM]信息源时，您必须自行报告使用情况）。 利用这些功能，您可以找到有效的数据源，而无需浪费时间寻找数据提供商。

>[!TIP]
>
>使用&#x200B;**[AdobeAudience Finder](https://www.adobe-audience-finder.com/)**&#x200B;查找可订阅的高质量数据馈送。 然后，返回到[!DNL Audience Manager]用户界面或使用[Audience Marketplace购买者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)订阅您找到的信息源。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace]列表包含您可以进行排序和搜索以查找适合您的数据馈送的信息。 [!UICONTROL Marketplace]购买者列表中的项目包括：

* **[!UICONTROL Search]**：按名称或文本描述查找数据馈送。
* **[!UICONTROL Similar Traits]**：显示数据馈送中类似[!UICONTROL traits]的数字。 在&#x200B;**[!UICONTROL Similarity To]**&#x200B;部分中输入要作为筛选依据的[!UICONTROL trait]或[!UICONTROL segment]后，将显示此列。
* **[!UICONTROL Name]**：数据馈送的名称。
* **[!UICONTROL Description]**：有关数据馈送内容的信息。
* **[!UICONTROL Provider]**：数据提供程序的名称。
* **[!UICONTROL Traits]**：数据馈送中的[!UICONTROL traits]数。
* **[!UICONTROL 30 Day Provider Unique Users]**：过去30天内查看的唯一用户数。
* **[!UICONTROL 30 Day Overlapped Uniques]**：您的帐户中与提供商帐户中的用户重叠的用户数。
* **[!UICONTROL Feed Overlap]**： 30天重叠唯一值，以百分比显示，计算为：数据购买者30天重叠唯一值/数据购买者30天唯一值)x 100。
* **[!UICONTROL Private Feeds]**：查看[私有数据馈送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**：您在数据提供程序中的订阅数。

 

要轻松找到符合您需求的最佳数据馈送，请使用[!UICONTROL Marketplace]页面左侧的以下过滤器：

* **[!UICONTROL Similarity To]**：根据数据馈送与您选择的[!UICONTROL trait]或[!UICONTROL segment]的相似性筛选数据馈送。 输入要比较的[!UICONTROL trait]或区段时，您可以使用[!UICONTROL trait]或[!UICONTROL segment] ID或其各自的名称。
* **[!UICONTROL Similarity Cutoff]**：拖动滑块以根据数据馈送的[!UICONTROL traits]与您所选的[!UICONTROL trait]或[!UICONTROL segment]的相似性筛选数据馈送。 要了解有关[!UICONTROL trait]相似性得分的更多信息，请参阅[特征相似性得分](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**：根据您的订阅状态筛选数据馈送。
* **[!UICONTROL Plan Use Case]**：根据支持的用例筛选数据馈送：**[!UICONTROL Activation]**、**[!UICONTROL Segments and Overlap]**&#x200B;和&#x200B;**[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**：根据定价类型筛选数据馈送。

## 查找类似[!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace]允许您根据与现有[!UICONTROL traits]或区段的相似性，从各种数据馈送中查找[!UICONTROL traits]。 以下是操作方法：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用&#x200B;**[!UICONTROL Similarity To]**&#x200B;选择器根据[!UICONTROL trait]或[!UICONTROL segment]进行筛选。 您可以根据[!UICONTROL trait]/[!UICONTROL segment] ID或名称进行筛选。 搜索框会根据您的输入自动向您显示相关建议。
3. 确定要作为筛选依据的特征或区段后，在建议列表中单击该特征或区段。
4. 若要缩小结果范围，请使用&#x200B;**[!UICONTROL Similarity Cutoff]**&#x200B;滑块从不太相似的[!UICONTROL traits]移动到比较相似的。

筛选完成后，您将在结果页面中看到一个新列：**[!UICONTROL Similar Traits]**。 此列显示符合筛选条件的每个数据馈送中与您筛选的相似[!UICONTROL traits]的数量。

要查看相似特征的完整列表，请单击&#x200B;**[!UICONTROL Similar Traits]**&#x200B;列中的数字。

>[!NOTE]
>
> Audience Marketplace显示来自所有数据馈送的前500个类似[!UICONTROL trait]结果。

观看以下视频，全面了解如何查找类似[!UICONTROL traits]。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 专用数据信息源 {#private-data-feeds}

在[!UICONTROL Marketplace]列表中，有时将提供商的名称和[!UICONTROL trait]数据标记为私有。 这表示[私有数据馈送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 通过私有数据馈送，卖方可以限制买方对其数据的访问。 当卖家提供特别优惠、折扣，或者当隐私和访问控制对他们来说很重要时，卖家可以将馈送设为私有。 作为买方，如果您希望访问专用信息源，则必须向卖方发送订阅请求。 有关详细信息，请参阅[订阅私有数据馈送](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

>[!MORELIKETHIS]
>
>* [了解受众市场中的计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* 数据购买者[折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
