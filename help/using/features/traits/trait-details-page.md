---
description: 单个特征的详细信息页面提供特征名称、ID、性能度量、定义特征的表达式、它所属的区段和特征审核日志等信息的概述。 要查看这些详细信息，请转至“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-description: 单个特征的详细信息页面提供特征名称、ID、性能度量、定义特征的表达式、它所属的区段和特征审核日志等信息的概述。 要查看这些详细信息，请转至“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-title: “特征详细信息”页
solution: Audience Manager
title: “特征详细信息”页
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: c761682f31c777368a21744b21d7302829007c66
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---


# “特征详细信息”页 {#trait-details-page}

单个特征的详细信息页面提供特征详细信息的概述，如特征名称、ID、性能度量、定义特征的表达式、它所属的区段和特征审核日志。 要视图这些详细信息， **[!UICONTROL Audience Data]** 请 **[!UICONTROL Traits]** 转到>并单击要处理的特征名称。

## 特征管理工具 {#trait-management-tools}

特征详细信息页面顶部包含可用于管理特征的工具：

1. **[!UICONTROL Add New]**: 使用此选项可创建新的基于规则、算法或载入的特征。
2. **[!UICONTROL Edit]**: 使用此选项可更改当前特征的配置。
3. **[!UICONTROL Delete]**: 使用此选项可从受众管理器帐户中删除当前特征。
4. **[!UICONTROL Marketplace Recommendations]**: 使用此选项，您可以根据未订阅的数据费 [!UICONTROL Audience Marketplace] 用找到与所查看的相似特征。 请参 [阅受众市场](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何导航市场并查找类似特征。

![基本特征信息](assets/basic-trait-information.png)

## 特征信息 {#basics}

此部 [!UICONTROL Trait Information] 分显示构建特征时完成的必填字段和可选字段的详细信息。 这包括特征类型、特征ID、描述、数据源和其他元数据。 这些详细信息因特征类型（文件夹、已载入或基于规则）而异。

## 特征图 {#trait-graph}

该 [!UICONTROL Trait Graph] 功能提供所选特征的一览表性能指标。 将光标悬停在趋势线上可查看所选特征的其他数据。

[!UICONTROL Unique Trait Realizations] 表示在给定时间范围内将此特征添加到其用户档案的唯一用户计数。 指 [!UICONTROL Total Trait Population] 示当前符合此特征的唯一用户数。

对于基于规则的特征，特征资格会实时发生，因为用户在其浏览器中有资格获得某个特征。

对于已载入的特征，特征资格在处理入站文件后发生，即将入站文件 [输入受众管理器](../../faq/faq-inbound-data-ingestion.md) ，即特征资格发生时。

显示 [!UICONTROL Trait Graph] 以下信息：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 选择此选项可查看为已验证用户档案收集数据的特征的结果。 选择此选项时，您只能看到报表上的 [!UICONTROL Cross-Device ID] 数据，并且报告下不会显示任何 [!UICONTROL Device ID] 数据。
   * **[!UICONTROL Device ID]**: 选择此选项可查看收集设备用户档案数据的特征结果。 选择此选项时，您只能看到报表上的 [!UICONTROL Device ID] 数据，并且报告下不会显示任何 [!UICONTROL Cross-Device ID] 数据。

      ![特征图](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 在给定时间范围内将此特征添加到其用户档案的唯一用户计数。
* **[!UICONTROL Total Trait Population]**: 当前符合此特征的唯一用户数。

* **[!UICONTROL Identity Type Breakdown]**: 前三个条目以降序显示符合特征的具有最高人口计数的前三个跨设备数据源。 第四个条目显示符合该特 [!DNL DPUUIDs] 征[!DNL CRM IDs]的所有其他()项的和，它们来自不在前三个跨设备数据源。 只有在页面右上方的下拉菜单中选 [!UICONTROL Show Results By] 择“跨设备ID”时，才会显示此报告。 默认下拉选项为， [!UICONTROL Device ID]其中不显示此报告。

   ![特征图](assets/trait-identity.png)

   >[!NOTE]
   >
   >受众管理器仅在 [!UICONTROL Identity Type Breakdown] 您具有符合该特征的跨设备ID时显示报告。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## 特征表达式 {#trait-expression}

此部 [!UICONTROL Trait Expression] 分向您显示用户必须满足才能符合特征的条件。 创建或编辑特征时 [会设置这些规则](../../features/traits/about-trait-builder.md)。

![](assets/traitExpression.png)

## 特征段 {#trait-segments}

该 [!UICONTROL Segments with this Trait] 部分列表选定特征所属的所有区段。 您可以单击区段名称以查看该区段的详细信息。

![](assets/traitSegments.png)

## 特征审核／历史记录日志 {#trait-audit-history}

对于基于规则和已载入的特征， [!UICONTROL Trait Expression Change History] 将显示对特征表达式规则进行的最近10次更改以及更改的对象。 如果您的特征有10个以上的更改，请单 **[!UICONTROL Export to CSV]** 击以下载整个审核日志。 审核日志不可用于文件夹或算法特征。

>[!NOTE]
>
>[!UICONTROL Not Available] 在列 [!UICONTROL By User] 中表示该用户的帐户已被删除。

![](assets/traitHistory.png)