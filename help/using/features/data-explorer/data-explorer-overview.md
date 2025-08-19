---
description: 使用Data Explorer可以利用历史受众，方法是：根据已用和未使用的信号构建特征，然后使用历史数据回填这些特征，以避免相关受众的潜在损失。
seo-description: Use Data Explorer to capitalize on historical audiences by building traits based on used and unused signals, and backfilling them with historical data to avoid potential loss of relevant audiences.
seo-title: Overview, Benefits, and Use Cases
title: 概述、优点和用例
uuid: 3bd32d4a-ade3-413d-837a-9edd14d415a5
feature: Data Explorer
exl-id: 56c9080b-4b7d-4feb-bddf-521e80bc8fa7
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---

# Data Explorer — 概述、优点和用例 {#overview-benefits-and-use-cases}

使用[!UICONTROL Data Explorer]通过基于已用和未用信号构建特征，并使用历史数据回填这些特征来利用历史受众，以避免相关受众的潜在损失。

## 概述 {#overview}

只要您始终知道受众是谁，就可以根据与受众相关的现有见解创建特征，这是一个相当简单的过程。 但这种情况多久发生一次？

[!UICONTROL Data Explorer]简化了您的特征管理流程，同时为您提供了更高程度的分类管理灵活性。 两个[!UICONTROL Data Explorer]组件可帮助您实现此目标：

* [信号仪表板](../../features/data-explorer/data-explorer-signals-dashboard.md)和[!UICONTROL Signals Search]可帮助您跟踪[!DNL Audience Manager]收到的信号，这些信号可用于构建新特征或添加到现有特征。

* [特征实现回填](../../features/data-explorer/data-explorer-trait-backfill.md)可帮助您使历史受众有资格使用新创建的特征，以便将来定位时可以包含这些受众。

## 优点 {#benefits}

使用[!UICONTROL Data Explorer]以多种方式优化您的受众构建：

* **关注高价值受众**。 监测页面上搜索和浏览行为的趋势变化，然后为其行为创建特定特征。 消除创建“以防万一”特征的需要，并重点关注相关信号。
* **避免数据丢失**。 使用历史实现回填特征，这样您就不会因为未在收到信号之前创建特征而错过受众区段。
* **改进您的工作流**。 发现趋势信号并快速将其转换为可操作特征。

## 用例 {#use-cases-data-explorer}

### 示例 1

全球电子产品retailer具有大量访客流量，但转化率低于预期，尽管他们为多个平台优化了内容。 他们使用[信号仪表板](../../features/data-explorer/data-explorer-signals-dashboard.md)识别大量未使用的信号，这表示访客正在搜索当前没有库存的特定电子品牌。 该公司可以利用此insight，方法是刷新其库存并使用个性化的促销活动定位这些访客。

### 示例 2

旅游服务提供商将新目标添加到其预订网站后，他们希望向历史受众广告这些目标，尽管他们还没有为他们创建任何特征。 他们可以使用信号搜索来识别与新目标相关的未使用信号，将它们包含在新特征中并[回填](../../features/data-explorer/data-explorer-trait-backfill.md)它们与历史实现。 然后，使用新特征创建新区段，并立即使用专用营销活动定位它们。

### 使用Data Explorer验证已载入数据的特征创建

Audience Manager最强大的功能之一是能够载入离线数据，并将其与您的在线数据关联起来。 在下面的视频中，了解如何使用[!UICONTROL Data Explorer]来验证您是否已创建所有必要的特征以利用此载入的数据。

>[!VIDEO](https://video.tv.adobe.com/v/330347?captions=chi_hans)
