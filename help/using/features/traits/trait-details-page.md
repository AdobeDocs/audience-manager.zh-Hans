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


# [!UICONTROL Trait] 详细信息页 {#trait-details-page}

个人的详细信息页 [!UICONTROL trait] 面提供详细信息 [!UICONTROL trait] 的概述，如名称、ID、性能 [!UICONTROL trait] 指标、定义其所属的区段的 [!UICONTROL trait]表达式、审核日志 [!UICONTROL trait] 等。 要视图这些详细信息， **[!UICONTROL Audience Data]** 请 **[!UICONTROL Traits]** 转到>并单 [!UICONTROL trait] 击要处理的名称。

## [!UICONTROL Trait] 管理工具 {#trait-management-tools}

详细信息页 [!UICONTROL trait] 面顶部存放可用于管理以下内容的工具 [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: 使用此选项可创建 [!UICONTROL rule-based]新 [!UICONTROL algorithmic]的、或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**: 使用此选项可更改当前配置 [!UICONTROL trait]。
3. **[!UICONTROL Delete]**: 使用此选项从您的Audience Manager帐 [!UICONTROL trait] 户中删除当前帐户。
4. **[!UICONTROL Marketplace Recommendations]**: 使用此选项可 [!UICONTROL traits] 以根据您未订阅的数据 [!UICONTROL Audience Marketplace] 费用找到与您正在查看的类似的内容。 请参 [阅Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何导航和 [!UICONTROL Marketplace] 查找类似特征。

![基本特征信息](assets/basic-trait-information.png)

## [!UICONTROL Trait] 信息 {#basics}

此部 [!UICONTROL Trait Information] 分显示构建时完成的必填字段和可选字段的详细信息 [!UICONTROL trait]。 这包括类型、 [!UICONTROL trait] ID、 [!UICONTROL trait] 描述和其 [!UICONTROL data source]他元数据等内容。 这些详细信息因 [!UICONTROL trait] 类型([!UICONTROL folder]、 [!UICONTROL onboarded]或)而 [!UICONTROL rule-based]异。

## [!UICONTROL Trait Graph] {#trait-graph}

它 [!UICONTROL Trait Graph] 为您的选定内容提供一览表性能指标 [!UICONTROL trait]。 将光标悬停在趋势线上可查看选定数据的其他数据 [!UICONTROL trait]。

[!UICONTROL Unique Trait Realizations] 表示在给定时间范围内将其添加到 [!UICONTROL trait] 其用户档案的唯一用户计数。 指 [!UICONTROL Total Trait Population] 示当前符合此条件的唯一用户数 [!UICONTROL trait]。

因 [!UICONTROL rule-based traits]为 [!UICONTROL trait] 当用户有资格在浏览器中访问时，资 [!UICONTROL trait] 格会实时发生。

对于 [!UICONTROL onboarded traits], [!UICONTROL trait] 在处理入站文件后会进行资格验证，即将入站文件 [输入Audience Manager](../../faq/faq-inbound-data-ingestion.md) ，即当资格 [!UICONTROL trait] 发生时。

显示 [!UICONTROL Trait Graph] 以下信息：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 选择此选项可查看为已验 [!UICONTROL traits] 证用户档案收集数据的结果。 选择此选项时，您只能看到报表上的 [!UICONTROL Cross-Device ID] 数据，并且报告下不会显示任何 [!UICONTROL Device ID] 数据。
   * **[!UICONTROL Device ID]**: 选择此选项可查看收集 [!UICONTROL traits] 设备用户档案数据的结果。 选择此选项时，您只能看到报表上的 [!UICONTROL Device ID] 数据，并且报告下不会显示任何 [!UICONTROL Cross-Device ID] 数据。

      ![特征图](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 在给定时间范围内将其添加到 [!UICONTROL trait] 其用户档案的唯一用户数。
* **[!UICONTROL Total Trait Population]**: 当前符合此条件的唯一用户数 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**: 前三个条目以降序显 [!UICONTROL cross-device data sources] 示符合该条件的前三个人口 [!UICONTROL trait]计数最高。 第四个条目显示符合条 [!DNL DPUUIDs] 件的[!DNL CRM IDs]所有其他( [!UICONTROL trait])项 [!UICONTROL cross-device data sources] 的和，前三项中不包括。 仅当在页面右上 [!UICONTROL Cross-device ID] 方的 [!UICONTROL Show Results By] 下拉菜单中选择时，才会显示此报告。 默认下拉选项为， [!UICONTROL Device ID]其中不显示此报告。

   ![特征图](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager仅在 [!UICONTROL Identity Type Breakdown] 您有符合 [!UICONTROL cross-device] 条件的ID时显示报 [!UICONTROL trait]告。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]表达式{#trait-expression}

此部 [!UICONTROL Trait Expression] 分会向您显示用户必须达到才能符合条件的条件 [!UICONTROL trait]。 创建或编辑特征时 [会设置这些规则](../../features/traits/about-trait-builder.md)。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 区段 {#trait-segments}

该 [!UICONTROL Segments with this Trait] 部分列表选定的所有 [!UICONTROL trait] 区段。 您可以单击区段名称以查看该区段的详细信息。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 审核／历史记录日志 {#trait-audit-history}

对于 [!UICONTROL rule-based] 和 [!UICONTROL onboarded traits]，将显示 [!UICONTROL Trait Expression Change History] 对表达式规则所做的最后10 [!UICONTROL trait] 项更改以及更改对象。 如果您 [!UICONTROL trait] 的更改超过10次，请单 **[!UICONTROL Export to CSV]** 击以下载整个审核日志。 审核日志不可用于 [!UICONTROL folder] 或 [!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available] 在列 [!UICONTROL By User] 中表示该用户的帐户已被删除。

![](assets/traitHistory.png)