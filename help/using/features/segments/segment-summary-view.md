---
description: 区段摘要页显示详细信息，如名称、区段中的特征、规则、性能数据和目标映射信息。
seo-description: 区段摘要页显示详细信息，如名称、区段中的特征、规则、性能数据和目标映射信息。
seo-title: “区段详细信息”页
solution: Audience Manager
title: “区段详细信息”页
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# “区段详细信息”页 {#segment-summary-view}

单个区段的详细信息页面提供了区段详细信息的概述，例如区段名称、ID、性能度量、定义区段的规则以及目标映射。 要视图这些详细信息， **[!UICONTROL Audience Data]** 请 **[!UICONTROL Segments]** 转到>，然后单击要处理的区段的名称。

## 细分管理工具 {#segment-management-tools}

区段详细信息页面顶部包含可用于管理区段的工具：

1. **[!UICONTROL Add New]**: 使用此选项可激活 [!UICONTROL Segment Builder] 和创建新区段。
2. **[!UICONTROL Edit]**: 使用此选项可更改当前段的配置。
3. **[!UICONTROL Duplicate]**: 使用此选项可创建当前区段的副本。
4. **[!UICONTROL Delete]**: 使用此选项可从您的Audience Manager帐户中删除当前区段。
5. **[!UICONTROL Marketplace Recommendations]**: 使用此选项，您可以从未订阅的数据源中 [!UICONTROL Audience Marketplace] 查找与正在查看的区段相似的区段。 请参 [阅Audience Marketplace数据购买者](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何导航Marketplace并查找类似的细分。

![基本细分信息](assets/basic-segment-information.png)

## 细分信息 {#basics}

在区段管理工具下方，您可以找到以下区段信息：

1. **[!UICONTROL Basic Information]:**显示创建区段时指定的必需和可选详细信息。 有关[这些字段的含义](segment-builder.md)，请参阅区段生成器。
2. **[!UICONTROL Segment Graph]:**以图形方式显示固定1、7、14、30、60和90天间隔的性能数据。 我们在另一篇文章中解释[细分人口数](../../features/segments/segment-builder-data.md)。

   ![细分图](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:**该报告通过计算链接到符合区段条件的设备的跨设备ID和／或外部设备图形ID的数量，显示符合区段条件的人员或家庭数(如[!UICONTROL Total Segment Population]所示)。 此报告中显示的跨设备ID和外部设备图形ID用于将用户档案与用户档案段使用的合并规则合并。 只有在区段使用的用户档案合并规则中选择了跨设备数据源或外部设备图形时，才会显示此报告。

   ![细分图](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager仅在具 [!UICONTROL Identity Type Breakdown] 有符合区段要求的跨设备ID时显示报告。

   请观看以下视频以了解概述 [!UICONTROL Identity Type Breakdown]。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:**列表区段中的特征以及资格规则。
5. **[!UICONTROL Destination Mappings]:**列表段的目标映射。
6. **[!UICONTROL Management Tools]:**用于创建、编辑、克隆和删除区段的控件。