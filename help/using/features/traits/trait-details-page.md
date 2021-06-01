---
description: 单个特征的详细信息页面提供了有关以下信息的概述：特征名称、ID、性能量度、定义特征的表达式、其所属的区段以及特征审核日志。 要查看这些详细信息，请转到“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-description: 单个特征的详细信息页面提供了有关以下信息的概述：特征名称、ID、性能量度、定义特征的表达式、其所属的区段以及特征审核日志。 要查看这些详细信息，请转到“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-title: 特征详细信息页面
solution: Audience Manager
title: 特征详细信息页面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: 身份类型划分、身份划分、受众身份报告、跨设备、跨设备ID、设备ID
feature: 特征
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] 详细信息页面  {#trait-details-page}

单个[!UICONTROL trait]的详细信息页面提供了[!UICONTROL trait]详细信息的概述，例如[!UICONTROL trait]名称、ID、性能量度、定义[!UICONTROL trait]的表达式、它所属的区段以及[!UICONTROL trait]审核日志。 要查看这些详细信息，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然后单击要处理的[!UICONTROL trait]的名称。

## [!UICONTROL Trait] 管理工具  {#trait-management-tools}

[!UICONTROL trait]详细信息页面顶部托管可用于管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**:使用此选项可创建新 [!UICONTROL rule-based]、 [!UICONTROL algorithmic]或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**:使用此选项可更改当前的配置 [!UICONTROL trait]。
3. **[!UICONTROL Delete]**:使用此选项可从您的Audience Manager帐 [!UICONTROL trait] 户中删除当前帐户。
4. **[!UICONTROL Marketplace Recommendations]**:使用此选项，您可 [!UICONTROL traits] 以从未订阅的数据 [!UICONTROL Audience Marketplace] 费中找到与您正在查看的类似选项。请参阅[Audience Marketplace数据购买者](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何导航[!UICONTROL Marketplace]并查找类似特征。

![基本特征信息](assets/basic-trait-information.png)

## [!UICONTROL Trait] 信息 {#basics}

[!UICONTROL Trait Information]部分显示有关在构建[!UICONTROL trait]时完成的必填和可选字段的详细信息。 这包括[!UICONTROL trait]类型、[!UICONTROL trait] ID、描述、[!UICONTROL data source]和其他元数据。 这些详细信息因[!UICONTROL trait]类型（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而异。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供所选[!UICONTROL trait]的快速性能量度。 将光标悬停在趋势线上可查看所选[!UICONTROL trait]的其他数据。

[!UICONTROL Unique Trait Realizations] 表示在给定时间范围内向其用户档案 [!UICONTROL trait] 添加此内容的独特用户计数。[!UICONTROL Total Trait Population]表示当前符合此[!UICONTROL trait]条件的独特用户数。

对于[!UICONTROL rule-based traits]，当用户符合浏览器中[!UICONTROL trait]的条件时，会实时进行[!UICONTROL trait]鉴别。

对于[!UICONTROL onboarded traits]，在处理入站文件后会进行[!UICONTROL trait]鉴别，即入站文件是[馈送到Audience Manager](../../faq/faq-inbound-data-ingestion.md)中，也就是在[!UICONTROL trait]鉴别发生时。

[!UICONTROL Trait Graph]显示以下信息：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:选择此选项可查看为已验证 [!UICONTROL traits] 的用户档案收集数据的结果。选择此选项时，您只会在[!UICONTROL Cross-Device ID]报表中看到数据，而[!UICONTROL Device ID]报表下不会显示任何数据。
   * **[!UICONTROL Device ID]**:选择此选项可查看收集设 [!UICONTROL traits] 备配置文件数据的结果。选择此选项时，您只会在[!UICONTROL Device ID]报表中看到数据，而[!UICONTROL Cross-Device ID]报表下不会显示任何数据。

      ![特征图](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:在给定时间范围内向用户档案添 [!UICONTROL trait] 加此维度的独特用户计数。
* **[!UICONTROL Total Trait Population]**:当前符合此条件的独特用户数 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**:前三个条目以降序显 [!UICONTROL cross-device data sources] 示符合条件的前三个群体 [!UICONTROL trait]计数最高。第四个条目显示符合[!UICONTROL trait]条件的所有其他[!DNL DPUUIDs]([!DNL CRM IDs])的总和，其中[!UICONTROL cross-device data sources]不在前三个条目中。 仅当在页面右上方的[!UICONTROL Show Results By]下拉菜单中选择[!UICONTROL Cross-device ID]时，才会显示此报表。 默认下拉选项为[!UICONTROL Device ID]，其中不显示此报表。

   ![特征图](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager仅在[!UICONTROL cross-device] ID符合[!UICONTROL trait]的条件时显示[!UICONTROL Identity Type Breakdown]报表。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]表达式{#trait-expression}

[!UICONTROL Trait Expression]部分显示用户必须满足才能符合[!UICONTROL trait]的条件。 在[创建或编辑特征](../../features/traits/about-trait-builder.md)时，将设置这些规则。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 区段 {#trait-segments}

[!UICONTROL Segments with this Trait]部分列出了选定[!UICONTROL trait]所属的所有区段。 您可以单击区段名称以查看有关该区段的详细信息。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 审核/历史记录日志  {#trait-audit-history}

对于[!UICONTROL rule-based]和[!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History]会显示对[!UICONTROL trait]表达式规则进行的最近10项更改以及这些更改的对象。 如果[!UICONTROL trait]的更改超过10次，请单击&#x200B;**[!UICONTROL Export to CSV]**&#x200B;下载整个审核日志。 审核日志不适用于[!UICONTROL folder]或[!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available] 在列 [!UICONTROL By User] 中，表示该用户的帐户已被删除。

![](assets/traitHistory.png)
