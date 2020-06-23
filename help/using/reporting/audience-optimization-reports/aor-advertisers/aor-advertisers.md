---
description: 受众优化广告商可以帮助您为付费媒体活动中的Audience Manager细分确定潜在的表现机会。 这些报告将日志级活动性能数据与Audience Manager细分指标相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-description: 受众优化广告商可以帮助您为付费媒体活动中的Audience Manager细分确定潜在的表现机会。 这些报告将日志级活动性能数据与Audience Manager细分指标相结合，以指导以细分为中心的优化和有效的渠道组合。
seo-title: 适用于广告商的 Audience Optimization
solution: Audience Manager
title: 适用于广告商的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: 9326b61f27f6c529567ab9b26694998f0b5dafb3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] 面向广告商{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 对于广告商，您可以帮助您在付费媒体活动中为Audience Manager细分确定潜在的表现机会。 这些报告将日志级活动性能数据与Audience Manager指标结 [!UICONTROL segment] 合在一起，以指导以细分为中心的优化和有效的渠道组合。

## 数据获取方法 {#data-ingestion-methods}

您可以通过以下任 [!DNL Audience Manager] 一方法发送数据以用于这些报告。 有时，客户会通过两种方法发送数据。 这有助于确保您的报告包含有关访客的最全面、最准确的信息。 要使用报 [!UICONTROL Audience Optimization] 告，事件调用必须包 *括Overview* and Mappings for Metadata Files文 [档中列出的所有参数](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 。 您可以通过以下列出的方法发送数据。

* 像素调用： 要传递所需的元数据参数，请 [!DNL Audience Manager] 查看 [通过像素调用捕获活动点击](../../../integration/media-data-integration/click-data-pixels.md) 数据和通过像素调用 [捕获活动印象数据](../../../integration/media-data-integration/impression-data-pixels.md)。

* 数据文件： 如果要使用这些报告来分析来自未与集成的源的您自己的数据或 [!DNL Audience Manager]数据，您需要为该数据创建并上传数据和元数据文件。 有关详细信息，请参 [阅受众优化报告的](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 文 [件和受众优化报告的数据和元数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以视图的报告类型取决于 [!UICONTROL RBAC] 您分配到的组。 有关 [详细](../../../features/administration/administration-overview.md)[信息，请参阅管](../../../features/administration/administration-overview.md#create-group) 理和创建组。

[!UICONTROL RBAC] 组必须设置一些数据源，才能视图报 [!UICONTROL Audience Optimization] 告。 你 [!DNL Audience Manager] 的顾问会帮你设 [!UICONTROL data sources] 置这些。 每个用 [!UICONTROL data sources] 户组中 [!UICONTROL RBAC] 的数据越多，这些组成员将有权访问的数据就越多。 您的顾问至少将设置以下其中之一 [!UICONTROL data sources]:

* 广告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

属于多个用户组的 [!UICONTROL RBAC] 用户可以在每个用户组的视图之间切换。 显示的数据将更新为对所选组的尊重。 如果您的公司未使 [!UICONTROL RBAC]用，则所有用户都将拥有管理员权限并有权访 [!UICONTROL data sources] 问所有（转换组）。

## 转换组 {#conversion-groups}

在报表 [!UICONTROL Audience Optimization] 中， **[!UICONTROL Conversion Groups]** 与至少包 [!UICONTROL data sources] 含一个转换特征的同义。 [!UICONTROL Data sources] 不包含至少一个转换特征的报告中不显示该 [!UICONTROL Audience Optimization] 特征。 您可以在“报告的转化特征”报表中视图转 [化组的转化特](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 征。
