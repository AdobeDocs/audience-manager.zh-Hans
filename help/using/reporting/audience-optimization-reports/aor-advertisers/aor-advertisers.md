---
description: Audience Optimization广告商可以帮助您针对付费媒体促销活动中的Audience Manager区段确定潜在的效果机会。 这些报表将日志级别的促销活动效果数据与Audience Manager区段量度相结合，以支持以区段为中心的优化以及有效的渠道组合。
seo-description: Audience Optimization广告商可以帮助您针对付费媒体促销活动中的Audience Manager区段确定潜在的效果机会。 这些报表将日志级别的促销活动效果数据与Audience Manager区段量度相结合，以支持以区段为中心的优化以及有效的渠道组合。
seo-title: 适用于广告商的 Audience Optimization
solution: Audience Manager
title: 适用于广告商的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization 报表
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] （广告商）{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] （广告商）可帮助您针对付费媒体促销活动中的Audience Manager区段确定潜在的效果机会。这些报表将日志级别的促销活动效果数据与Audience Manager[!UICONTROL segment]量度相结合，以支持以区段为中心的优化以及有效的渠道组合。

## 数据摄取方法{#data-ingestion-methods}

您可以通过以下任一方法将数据发送到[!DNL Audience Manager]，以便在这些报表中使用。 有时，客户会通过两种方法发送数据。 这有助于确保您的报表包含有关访客的最全面、最准确的信息。 要使用[!UICONTROL Audience Optimization]报表，事件调用必须包含[元数据文件的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)文档中列出的参数的&#x200B;*所有*。 您可以通过下面列出的以下方法发送数据。

* 像素调用：要将所需的元数据参数传递到[!DNL Audience Manager]，请参阅[通过像素调用捕获营销活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)和[通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)。

* 数据文件：如果要使用这些报表从未与[!DNL Audience Manager]集成的源分析您自己的数据或数据，则需要为该数据创建并上传数据和元数据文件。 有关更多信息，请参阅[Audience Optimization报表的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[Audience Optimization报表的数据和元数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以查看的报表类型取决于您分配到的[!UICONTROL RBAC]组。 有关更多信息，请参阅[管理](../../../features/administration/administration-overview.md)和[创建组](../../../features/administration/administration-overview.md#create-group)。

[!UICONTROL RBAC] 群组必须设置一些数据源才能查看报 [!UICONTROL Audience Optimization] 表。您的[!DNL Audience Manager]顾问将为您设置这些[!UICONTROL data sources]。 每个[!UICONTROL RBAC]用户组中[!UICONTROL data sources]越多，这些组成员有权访问的数据就越多。 您的顾问至少会设置以下其中的一个[!UICONTROL data sources]:

* 广告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

属于多个[!UICONTROL RBAC]用户组的用户可以在每个组的视图之间切换。 显示的数据将根据所选组进行更新。 如果您的公司不使用[!UICONTROL RBAC]，则所有用户都将拥有管理员权限并有权访问所有[!UICONTROL data sources]（转化组）。

## 转化组{#conversion-groups}

在[!UICONTROL Audience Optimization]报表中， **[!UICONTROL Conversion Groups]**&#x200B;与至少包含一个转化特征的[!UICONTROL data sources]同义。 [!UICONTROL Data sources] 其中，至少包含一个转化特征的转化特征不会显示在报 [!UICONTROL Audience Optimization] 表中。您可以在[报告的转化特征](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)报表中查看转化组的转化特征。
