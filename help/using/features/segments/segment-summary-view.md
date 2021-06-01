---
description: 区段摘要页面显示详细信息，如名称、区段中的特征、规则、性能数据和目标映射信息。
seo-description: 区段摘要页面显示详细信息，如名称、区段中的特征、规则、性能数据和目标映射信息。
seo-title: “区段详细信息”页面
solution: Audience Manager
title: “区段详细信息”页面
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: 身份类型划分、身份划分、受众身份报告、跨设备、跨设备ID、设备ID
feature: 区段
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# 区段详细信息页面{#segment-summary-view}

单个区段的详细信息页面提供了区段详细信息的概述，例如区段名称、ID、性能量度、定义区段的规则以及目标映射。 要查看这些详细信息，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**，然后单击要处理的区段名称。

## 区段管理工具{#segment-management-tools}

区段详细信息页面顶部托管可用于管理区段的工具：

1. **[!UICONTROL Add New]**:使用此选项可激活并 [!UICONTROL Segment Builder] 创建新区段。
2. **[!UICONTROL Edit]**:使用此选项可更改当前区段的配置。
3. **[!UICONTROL Duplicate]**:使用此选项可创建当前区段的副本。
4. **[!UICONTROL Delete]**:使用此选项可从您的Audience Manager帐户中删除当前区段。
5. **[!UICONTROL Marketplace Recommendations]**:使用此选项可从您未订阅的数据馈送中查找与您正在 [!UICONTROL Audience Marketplace] 查看的区段类似的区段。请参阅[面向数据购买者的Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何导航市场并查找类似的区段。

![基本区段信息](assets/basic-segment-information.png)

## 区段信息 {#basics}

在区段管理工具下方，您可以找到以下区段信息：

1. **[!UICONTROL Basic Information]:** 显示创建区段时指定的必需和可选详细信息。请参阅[区段生成器](segment-builder.md) ，以详细了解这些字段的含义。
2. **[!UICONTROL Segment Graph]:** 以图形方式显示固定时间间隔为1、7、14、30、60和90天的性能数据。我们在[单独的文章](../../features/segments/segment-builder-data.md)中解释区段人口数。

   ![区段 — 图形](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** 报表通过计数链接到符合区段资格的设备的跨设备ID和/或外部设备图ID的数量，来显示符合区段资格条件的人员或家庭数量(如 [!UICONTROL Total Segment Population]所示)。此报表中显示的跨设备ID和外部设备图ID用于将配置文件与区段所使用的配置文件合并规则合并。 仅当您在区段所使用的配置文件合并规则中选择了跨设备数据源或外部设备图时，才会显示此报表。

   ![区段 — 图形](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager仅在具有符合区段资格条件的跨设备ID时显示[!UICONTROL Identity Type Breakdown]报表。

   请观看以下视频，了解[!UICONTROL Identity Type Breakdown]的概述。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** 在区段中列出特征和鉴别规则。
5. **[!UICONTROL Destination Mappings]:** 列出区段的目标映射。
6. **[!UICONTROL Management Tools]:** 用于创建、编辑、克隆和删除区段的控件。
