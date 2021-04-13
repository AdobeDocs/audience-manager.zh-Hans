---
description: Audience Optimization广告商可帮助您为付费媒体活动中的Audience Manager细分确定潜在的表现机会。 这些报表将日志级活动性能数据与Audience Manager细分量度相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-description: Audience Optimization广告商可帮助您为付费媒体活动中的Audience Manager细分确定潜在的表现机会。 这些报表将日志级活动性能数据与Audience Manager细分量度相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-title: 适用于广告商的 Audience Optimization
solution: Audience Manager
title: 适用于广告商的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization 报表
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] 面向广告商{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 对于广告商，您可以帮助您在付费媒体活动中为Audience Manager细分确定潜在的表现机会。这些报表将日志级活动性能数据与Audience Manager[!UICONTROL segment]量度相结合，以指导以细分为中心的优化和有效的渠道组合。

## 数据摄取方法{#data-ingestion-methods}

您可以通过以下任一方法将数据发送到[!DNL Audience Manager]以在这些报表中使用。 有时，客户会通过两种方法发送数据。 这有助于确保您的报告包含有关访客的最全面和准确的信息。 要使用[!UICONTROL Audience Optimization]报表，您的事件调用必须包含[元数据文件概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)文档中列出的参数的&#x200B;*all*。 您可以通过以下列出的方法发送数据。

* 像素调用：要将所需的元数据参数传递到[!DNL Audience Manager]，请参阅[通过像素调用捕获活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)和[通过像素调用捕获活动印象数据](../../../integration/media-data-integration/impression-data-pixels.md)。

* 数据文件：如果要使用这些报表分析未与[!DNL Audience Manager]集成的源中您自己的数据或数据，您需要为该数据创建并上传数据和元数据文件。 有关详细信息，请参阅[Audience Optimization报告的Audience Optimization文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[报告的数据和元数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

您可以视图的报告类型取决于您分配到的[!UICONTROL RBAC]组。 有关详细信息，请参阅[管理](../../../features/administration/administration-overview.md)和[创建组](../../../features/administration/administration-overview.md#create-group)。

[!UICONTROL RBAC] 要视图报表，组必须设置一些数据 [!UICONTROL Audience Optimization] 源。您的[!DNL Audience Manager]顾问将为您设置这些[!UICONTROL data sources]。 每个[!UICONTROL RBAC]用户组中[!UICONTROL data sources]越多，这些用户组成员访问的数据就越多。 您的顾问至少将设置以下[!UICONTROL data sources]中的至少一个：

* 广告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

属于多个[!UICONTROL RBAC]用户组的用户可以在每个用户组的视图之间切换。 显示的数据将更新以与选定的组保持一致。 如果您的公司未使用[!UICONTROL RBAC]，则所有用户都将拥有管理员权限并有权访问所有[!UICONTROL data sources]（转换组）。

## 转换组{#conversion-groups}

在[!UICONTROL Audience Optimization]报表中，**[!UICONTROL Conversion Groups]**&#x200B;与[!UICONTROL data sources]同义，它们至少包含一个转换特征。 [!UICONTROL Data sources] 不包含至少一个转换特征的转换特征不显示在报 [!UICONTROL Audience Optimization] 表中。您可以在[报告的转换特征](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)报表中视图转换组的转换特征。
