---
description: 区段摘要页面显示名称、区段中的特征、规则、性能数据和目标映射信息等详细信息。
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: “区段详细信息”页面
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: 身份类型划分、身份划分、受众身份报告、跨设备、跨设备ID、设备ID
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# “区段详细信息”页面 {#segment-summary-view}

单个区段的详细信息页面概述了区段详细信息，如区段名称、ID、绩效指标、定义区段的规则以及目标映射。 要查看这些详细信息，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**，然后单击要处理的区段的名称。

## 区段管理工具 {#segment-management-tools}

“区段详细信息”页面顶部承载着可用于管理区段的工具：

1. **[!UICONTROL Add New]**：使用此选项激活[!UICONTROL Segment Builder]并创建新区段。
2. **[!UICONTROL Edit]**：使用此选项更改当前区段的配置。
3. **[!UICONTROL Duplicate]**：使用此选项创建当前区段的副本。
4. **[!UICONTROL Delete]**：使用此选项可从Audience Manager帐户中删除当前区段。
5. **[!UICONTROL Marketplace Recommendations]**：使用此选项从您未订阅的[!UICONTROL Audience Marketplace]数据馈送中查找与正在查看的区段类似的区段。 请参阅[面向数据购买者的Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，了解如何在Marketplace中导航和查找类似区段。

![基本区段信息](assets/basic-segment-information.png)

## 区段信息 {#basics}

在区段管理工具下方，您可以找到以下区段信息：

1. **[!UICONTROL Basic Information]：**&#x200B;显示创建区段时指定的必需和可选详细信息。 有关这些字段含义的详细概述，请参阅[区段生成器](segment-builder.md)。
2. **[!UICONTROL Segment Graph]：**&#x200B;以图形方式显示固定为1、7、14、30、60和90天的性能数据。 我们在[单独的文章](../../features/segments/segment-builder-data.md)中解释了区段人口数字。

   ![区段 — 图形](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown]：**&#x200B;此报表通过计算链接到符合区段资格条件的设备的跨设备ID和/或外部设备图形ID的数量，来显示符合区段资格条件的用户或家庭数量（由[!UICONTROL Total Segment Population]显示）。 此报告中显示的跨设备ID和外部设备图ID用于将用户档案与区段正在使用的用户档案合并规则合并。 仅当您在区段使用的配置文件合并规则中选择了跨设备数据源或外部设备图时，才会显示此报表。

   ![区段 — 图形](assets/segment-type.png)

   >[!NOTE]
   >
   >仅当您具有符合区段资格的跨设备ID时，Audience Manager才会显示[!UICONTROL Identity Type Breakdown]报表。

   观看以下视频，了解[!UICONTROL Identity Type Breakdown]的概述。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]：**&#x200B;列出区段中的特征以及资格规则。
5. **[!UICONTROL Destination Mappings]：**&#x200B;列出区段的目标映射。
6. **[!UICONTROL Management Tools]：**&#x200B;允许您创建、编辑、克隆和删除区段的控件。
