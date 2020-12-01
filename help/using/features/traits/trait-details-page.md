---
description: 单个特征的详细信息页面提供特征名称、ID、性能度量、定义特征的表达式、它所属的区段和特征审核日志等信息的概述。 要查看这些详细信息，请转至“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-description: 单个特征的详细信息页面提供特征名称、ID、性能度量、定义特征的表达式、它所属的区段和特征审核日志等信息的概述。 要查看这些详细信息，请转至“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-title: 特征详细信息页面
solution: Audience Manager
title: 特征详细信息页面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] 详细信息页  {#trait-details-page}

单个[!UICONTROL trait]的详细信息页面概述了[!UICONTROL trait]详细信息，如[!UICONTROL trait]名称、ID、性能度量、定义[!UICONTROL trait]的表达式、它所属的区段和[!UICONTROL trait]审核日志。 要视图这些详细信息，请转至&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然后单击要处理的[!UICONTROL trait]的名称。

## [!UICONTROL Trait] 管理工具  {#trait-management-tools}

[!UICONTROL trait]详细信息页面顶部存放可用于管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**:使用此选项可创建 [!UICONTROL rule-based]新 [!UICONTROL algorithmic]的、或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**:使用此选项可更改当前配置 [!UICONTROL trait]。
3. **[!UICONTROL Delete]**:使用此选项从您的Audience Manager帐 [!UICONTROL trait] 户中删除当前帐户。
4. **[!UICONTROL Marketplace Recommendations]**:使用此选项可 [!UICONTROL traits] 以根据您未订阅的数 [!UICONTROL Audience Marketplace] 据费用查找与您正在查看的类似内容。请参阅[Audience Marketplace数据购买者](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，了解如何导航[!UICONTROL Marketplace]并查找类似特征。

![基本特征信息](assets/basic-trait-information.png)

## [!UICONTROL Trait] 信息 {#basics}

[!UICONTROL Trait Information]部分显示有关在构建[!UICONTROL trait]时完成的必填字段和可选字段的详细信息。 这包括[!UICONTROL trait]类型、[!UICONTROL trait] ID、说明、[!UICONTROL data source]和其他元数据。 这些详细信息因[!UICONTROL trait]类型（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而异。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供所选[!UICONTROL trait]的一览表性能指标。 将光标悬停在趋势线上可查看所选[!UICONTROL trait]的其他数据。

[!UICONTROL Unique Trait Realizations] 表示在给定时间范围内将其添加 [!UICONTROL trait] 到用户档案的唯一用户计数。[!UICONTROL Total Trait Population]表示当前符合此[!UICONTROL trait]条件的唯一用户数。

对于[!UICONTROL rule-based traits],[!UICONTROL trait]资格会实时发生，因为用户在其浏览器中有资格获得[!UICONTROL trait]。

对于[!UICONTROL onboarded traits]，在处理入站文件后会发生[!UICONTROL trait]资格，即，入站文件是[输入到Audience Manager](../../faq/faq-inbound-data-ingestion.md)中，即当[!UICONTROL trait]资格发生时。

[!UICONTROL Trait Graph]显示以下信息：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:选择此选项可查看为已验 [!UICONTROL traits] 证用户档案收集数据的结果。选择此选项后，您只能在[!UICONTROL Cross-Device ID]报告中看到数据，而在[!UICONTROL Device ID]报告中不会显示任何数据。
   * **[!UICONTROL Device ID]**:选择此选项可查看收 [!UICONTROL traits] 集设备用户档案数据的结果。选择此选项后，您只能在[!UICONTROL Device ID]报告中看到数据，而在[!UICONTROL Cross-Device ID]报告中不会显示任何数据。

      ![特征图](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:在给定时间范围内将其添加 [!UICONTROL trait] 到用户档案的唯一用户数。
* **[!UICONTROL Total Trait Population]**:当前符合此条件的唯一用户数 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**:前三个条目以降序显 [!UICONTROL cross-device data sources] 示符合条件的前三个人口 [!UICONTROL trait]数最高的条目。第四个条目显示符合[!UICONTROL trait]条件的所有其他[!DNL DPUUIDs]([!DNL CRM IDs])的和，其中[!UICONTROL cross-device data sources]不在前三个条目中。 只有在页面右上方的[!UICONTROL Show Results By]下拉菜单中选择[!UICONTROL Cross-device ID]时，才会显示此报告。 默认的下拉选项为[!UICONTROL Device ID]，其中不显示此报告。

   ![特征图](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager仅在[!UICONTROL cross-device] ID符合[!UICONTROL trait]条件时显示[!UICONTROL Identity Type Breakdown]报告。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]表达式{#trait-expression}

[!UICONTROL Trait Expression]部分显示用户必须满足的条件才能符合[!UICONTROL trait]的条件。 在[创建或编辑特征](../../features/traits/about-trait-builder.md)时设置这些规则。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 区段 {#trait-segments}

[!UICONTROL Segments with this Trait]部分列表选定[!UICONTROL trait]所属的所有段。 您可以单击区段名称以查看该区段的详细信息。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 审核／历史记录日志  {#trait-audit-history}

对于[!UICONTROL rule-based]和[!UICONTROL onboarded traits],[!UICONTROL Trait Expression Change History]将显示对[!UICONTROL trait]表达式规则进行的最近10项更改，以及这些更改由谁进行。 如果您的[!UICONTROL trait]有10项以上更改，请单击&#x200B;**[!UICONTROL Export to CSV]**&#x200B;下载整个审核日志。 审核日志不可用于[!UICONTROL folder]或[!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available] 在列 [!UICONTROL By User] 中表示该用户的帐户已被删除。

![](assets/traitHistory.png)