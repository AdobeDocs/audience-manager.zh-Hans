---
description: Audience Optimization广告商可以帮助您识别在付费媒体促销活动中Audience Manager区段的潜在效果机会。 这些报表将日志级别的促销活动效果数据与Audience Manager区段量度相结合，为以区段为中心的优化和有效渠道组合提供信息。
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: 适用于广告商的Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# 广告商的[!UICONTROL Audience Optimization]{#audience-optimization-for-advertisers}

广告商的[!UICONTROL Audience Optimization]可以帮助您识别在付费媒体促销活动中Audience Manager区段的潜在效果机会。 这些报表将日志级别的促销活动效果数据与Audience Manager[!UICONTROL segment]量度相结合，为以区段为中心的优化和有效渠道组合提供信息。

## 数据摄取方法 {#data-ingestion-methods}

您可以通过以下任一方法将数据发送到[!DNL Audience Manager]以在这些报表中使用。 有时，客户通过这两种方法发送数据。 这有助于确保您的报表包含有关访客的最全面和准确的信息。 要使用[!UICONTROL Audience Optimization]报表，您的事件调用必须包括[元数据文件概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)文档中所列出的参数中的&#x200B;*所有*&#x200B;个参数。 您可以通过下面列出的以下方法发送数据。

* 像素调用：要将所需的元数据参数传递给[!DNL Audience Manager]，请参阅[通过像素调用捕获营销活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)和[通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)。

* 数据文件：如果要使用这些报表来分析您自己的数据或来自未与[!DNL Audience Manager]集成的源的数据，您需要为该数据创建和上载数据和元数据文件。 有关详细信息，请参阅[Audience Optimization报表的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[Audience Optimization报表的数据和元数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以查看的报告类型取决于您分配到的[!UICONTROL RBAC]组。 有关详细信息，请参阅[管理](../../../features/administration/administration-overview.md)和[创建组](../../../features/administration/administration-overview.md#create-group)。

[!UICONTROL RBAC]组必须设置一些数据源才能查看[!UICONTROL Audience Optimization]报告。 您的[!DNL Audience Manager]顾问将为您设置这些[!UICONTROL data sources]。 每个[!UICONTROL RBAC]用户组中的[!UICONTROL data sources]越多，这些组成员有权访问的数据就越多。 您的顾问至少应设置以下[!UICONTROL data sources]中的一个：

* 广告商[!UICONTROL data source]
* 品牌[!UICONTROL data source]
* 平台[!UICONTROL data source]

属于多个[!UICONTROL RBAC]用户组的用户可以在每个组的视图之间切换。 显示的数据将更新以符合所选组。 如果贵公司不使用[!UICONTROL RBAC]，则所有用户都将拥有管理员权限以及所有[!UICONTROL data sources]（转化组）的访问权限。

## 转化组 {#conversion-groups}

在[!UICONTROL Audience Optimization]报表中，**[!UICONTROL Conversion Groups]**&#x200B;与至少包含一个转化特征的[!UICONTROL data sources]同义。 不包含至少一个转化特征的[!UICONTROL Data sources]不会出现在[!UICONTROL Audience Optimization]报表中。 您可以在[报告的转化特征](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)报表中查看转化组的转化特征。
