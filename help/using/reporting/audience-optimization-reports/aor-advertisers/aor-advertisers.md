---
description: 面向广告商的受众优化可以帮助您在付费媒体营销活动中为Audience manager细分识别潜在的绩效机会。 这些报告将日志级营销活动绩效数据与Audience manager细分指标相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-description: 面向广告商的受众优化可以帮助您在付费媒体营销活动中为Audience manager细分识别潜在的绩效机会。 这些报告将日志级营销活动绩效数据与Audience manager细分指标相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-title: 面向广告商的受众优化
solution: Audience Manager
title: 面向广告商的受众优化
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

面向广告商的受众优化可以帮助您在付费媒体营销活动中为Audience manager细分识别潜在的绩效机会。 这些报告将日志级营销活动绩效数据与Audience manager细分指标相结合，以指导以细分为中心的优化和有效的渠道组合。

## 数据摄取方法 {#data-ingestion-methods}

您可以通过以下任 [!DNL Audience Manager] 一方法发送数据以用于这些报告。 有时，客户会通过两种方法发送数据。 这有助于确保您的报告包含有关访客的最全面和准确的信息。 要使用报 [!UICONTROL Audience Optimization] 告，活动调用必须包括“ *Overview and Mappings for Metadata Files* （元数据文件的概述和映射）”文 [档中列出的所有参数](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 。 您可以通过以下列出的方法发送数据。

* 像素调用：要传递所需的元数据参数以查看通 [!DNL Audience Manager] 过像素调 [用捕获营销活动点击数据和通](../../../integration/media-data-integration/click-data-pixels.md) 过像素调用捕获营销活动印象数据 [](../../../integration/media-data-integration/impression-data-pixels.md)。

* 数据文件：如果要使用这些报告分析来自未集成的源的您自己的数据或数据 [!DNL Audience Manager]，您需要为该数据创建并上传数据和元数据文件。 有关详细信息，请参 [阅受众优化报告的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) ，以 [及受众优化报告的数据和元数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## 基于角色的访问控制(RBAC) {#rbac}

您可以查看的报告类型取决于您 [!UICONTROL RBAC] 分配到的组。 有关详 [细信息](../../../features/administration/administration-overview.md) ，请参 [阅管理和创建组](../../../features/administration/administration-overview.md#create-group) 。

[!UICONTROL RBAC] 组必须设置一些数据源才能查看报 [!UICONTROL Audience Optimization] 告。 您 [!DNL Audience Manager] 的顾问将为您设置这些数据源。 每个用户组中的数据源越 [!UICONTROL RBAC] 多，这些用户组成员将有权访问的数据就越多。 您的顾问至少将设置以下数据源之一：

* 广告商数据源
* 品牌数据源
* 平台数据源

属于多个用户组的用 [!UICONTROL RBAC] 户可以在每个用户组的视图之间切换。 显示的数据将根据所选组进行更新。 如果您的公司未使用， [!UICONTROL RBAC]则所有用户将拥有管理员权限并有权访问所有数据源（转化组）。

## 转化组 {#conversion-groups}

在报告 [!UICONTROL Audience Optimization] 中， **[!UICONTROL Conversion Groups]** 与至少包含一个转换特征的数据源同义。 不包含至少一个转换特征的数据源不会显示在报告中 [!UICONTROL Audience Optimization] 。 您可以在“报告的转化特征”报表中查看转化组 [的转化特征](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 。
