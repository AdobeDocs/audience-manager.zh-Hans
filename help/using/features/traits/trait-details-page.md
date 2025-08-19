---
description: 单个特征的“详细信息”页面提供了如下信息的概述：特征名称、ID、性能指标、定义特征的表达式、特征所属的区段以及特征审核日志。 要查看这些详细信息，请转到受众数据>特征，然后单击要处理的特征名称。
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: 特征详细信息页面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: 身份类型划分、身份划分、受众身份报告、跨设备、跨设备ID、设备ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait]详细信息页面 {#trait-details-page}

单个[!UICONTROL trait]的详细信息页面提供了[!UICONTROL trait]详细信息的概述，如[!UICONTROL trait]名称、ID、性能指标、定义[!UICONTROL trait]的表达式、它所属的区段以及[!UICONTROL trait]审核日志。 要查看这些详细信息，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然后单击要使用的[!UICONTROL trait]的名称。

## [!UICONTROL Trait]管理工具 {#trait-management-tools}

[!UICONTROL trait]详细信息页面顶部承载了可用于管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**：使用此选项创建新[!UICONTROL rule-based]、[!UICONTROL algorithmic]或[!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**：使用此选项更改当前[!UICONTROL trait]的配置。
3. **[!UICONTROL Delete]**：使用此选项可从您的Audience Manager帐户中删除当前[!UICONTROL trait]。
4. **[!UICONTROL Marketplace Recommendations]**：使用此选项查找与您正在查看的数据类似[!UICONTROL traits]，但您未订阅[!UICONTROL Audience Marketplace]数据费用。 请参阅[面向数据购买者的Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，了解如何导航[!UICONTROL Marketplace]并查找相似特征。

![基本特征信息](assets/basic-trait-information.png)

## [!UICONTROL Trait]信息 {#basics}

[!UICONTROL Trait Information]部分显示有关您在构建[!UICONTROL trait]时完成的必填字段和可选字段的详细信息。 这包括[!UICONTROL trait]类型、[!UICONTROL trait] ID、描述、[!UICONTROL data source]和其他元数据等。 这些详细信息因[!UICONTROL trait]类型（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而异。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供所选[!UICONTROL trait]的性能指标概览。 将光标悬停在趋势线上可查看选定[!UICONTROL trait]的其他数据。

[!UICONTROL Unique Trait Realizations]表示在给定时间范围内将此[!UICONTROL trait]添加到其配置文件的独特用户计数。 [!UICONTROL Total Trait Population]表示当前符合此[!UICONTROL trait]资格的独特用户数。

对于[!UICONTROL rule-based traits]，将实时进行[!UICONTROL trait]鉴别，因为用户在其浏览器中符合[!UICONTROL trait]的资格。

对于[!UICONTROL onboarded traits]，[!UICONTROL trait]鉴别会在处理入站文件后发生，即入站文件是[馈送到Audience Manager](../../faq/faq-inbound-data-ingestion.md)，此时发生[!UICONTROL trait]鉴别。

[!UICONTROL Trait Graph]显示以下信息：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**：选择此选项可查看[!UICONTROL traits]收集已验证配置文件数据的结果。 选择此选项后，您只能在[!UICONTROL Cross-Device ID]报表中看到数据，而[!UICONTROL Device ID]报表下不会有任何数据。
   * **[!UICONTROL Device ID]**：选择此选项可查看正在收集设备配置文件数据的[!UICONTROL traits]的结果。 选择此选项后，您只能在[!UICONTROL Device ID]报表中看到数据，而[!UICONTROL Cross-Device ID]报表下不会有任何数据。

     ![特征图](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**：在给定时间范围内将此[!UICONTROL trait]添加到其配置文件的独特用户计数。
* **[!UICONTROL Total Trait Population]**：当前符合此[!UICONTROL trait]资格的唯一用户数。

* **[!UICONTROL Identity Type Breakdown]**：前三个条目按降序显示符合[!UICONTROL cross-device data sources]条件的前3个[!UICONTROL trait]，具有最高的群体计数。 第四个条目显示来自[!DNL DPUUIDs]且不在前三个中的所有其他符合[!DNL CRM IDs]资格的[!UICONTROL trait] ([!UICONTROL cross-device data sources])的总和。 仅当您在页面右上方的[!UICONTROL Cross-device ID]下拉菜单中选择[!UICONTROL Show Results By]时，才会显示此报告。 默认下拉选项为[!UICONTROL Device ID]，其中不显示此报告。

  ![特征图](assets/trait-identity.png)

  >[!NOTE]
  >
  >仅当您有[!UICONTROL Identity Type Breakdown]个ID符合[!UICONTROL cross-device]条件时，Audience Manager才会显示[!UICONTROL trait]报告。

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]表达式 {#trait-expression}

[!UICONTROL Trait Expression]部分显示用户符合[!UICONTROL trait]资格所必须满足的条件。 这些规则是在[创建或编辑特征](../../features/traits/about-trait-builder.md)时设置的。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 区段 {#trait-segments}

[!UICONTROL Segments with this Trait]部分列出了选定[!UICONTROL trait]所属的所有区段。 您可以单击区段名称来查看有关该区段的详细信息。

![](assets/traitSegments.png)

## [!UICONTROL Trait]审核/历史记录日志 {#trait-audit-history}

对于[!UICONTROL rule-based]和[!UICONTROL onboarded traits]，[!UICONTROL Trait Expression Change History]会显示对[!UICONTROL trait]表达式规则进行的最后10次更改以及这些更改的执行者。 如果您的[!UICONTROL trait]有超过10个更改，请单击&#x200B;**[!UICONTROL Export to CSV]**&#x200B;下载整个审核日志。 审核日志不适用于[!UICONTROL folder]或[!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available]列中的[!UICONTROL By User]表示该用户的帐户已被删除。

![](assets/traitHistory.png)
