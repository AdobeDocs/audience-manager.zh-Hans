---
description: 针对广告商的受众优化可以帮助您在付费媒体营销活动中识别Audience Manager细分的潜在绩效机会。这些报告将日志级别营销活动绩效数据与Audience Manager细分指标相结合，以提供以区段为中心的优化和有效的渠道组合。
seo-description: 针对广告商的受众优化可以帮助您在付费媒体营销活动中识别Audience Manager细分的潜在绩效机会。这些报告将日志级别营销活动绩效数据与Audience Manager细分指标相结合，以提供以区段为中心的优化和有效的渠道组合。
seo-title: 广告商的受众优化
solution: Audience Manager
title: 广告商的受众优化
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

针对广告商的受众优化可以帮助您在付费媒体营销活动中识别Audience Manager细分的潜在绩效机会。这些报告将日志级别营销活动绩效数据与Audience Manager细分指标相结合，以提供以区段为中心的优化和有效的渠道组合。

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. 有时，客户会通过两种方法发送数据。这有助于确保报表包含有关访客的最全面、准确的信息。To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. 您可以通过以下列出的方法发送数据。

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Role-Based Access Controls (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] 用户组必须设置一些数据源才能查看 [!UICONTROL Audience Optimization] 报表。[!DNL Audience Manager] 您的顾问将为您设置这些数据源。[!UICONTROL RBAC] 每个用户组中的数据源越多，用户组成员可以访问的数据就越多。您的顾问至少将设置以下任一数据源：

* 广告商数据源
* 品牌数据源
* 平台数据源

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. 显示的数据将更新以尊重选定的组。If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#conversion-groups}

[!UICONTROL Audience Optimization] 在报告中， **[!UICONTROL Conversion Groups]** 与包含至少一个转化特征的数据源同义。Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report.
