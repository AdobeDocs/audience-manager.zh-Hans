---
description: 数据导出标签可与您在数据源上设置的导出控件配合使用。 数据导出标签会阻止您将受限制的特征添加到区段，并阻止您将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的Cookie或URL目标。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: 添加或编辑服务器到服务器目标的区段
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# 添加或编辑服务器到服务器目标的区段 {#add-edit-segments}

您只能添加或编辑服务器到服务器([!DNL S2S])目标的区段。 无法使用[!DNL S2S]创建[[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md)目标。 请联系您的顾问以设置[!DNL S2S]目标。 按照以下说明添加或编辑[!DNL S2S]目标的区段。

<!-- destination-s2s-edit.xml -->

添加或编辑[!DNL S2S]目标的区段映射：

1. 转到&#x200B;**[!UICONTROL Audience Data > Destinations]**。 选择&#x200B;**集成平台>基于设备**，然后找到要使用的[!DNL S2S]目标。
2. 在[!UICONTROL Action]列中，单击铅笔图标以编辑目标。
   * 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;框中，开始键入区段的名称，或单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;浏览可用区段的列表。
   * 找到要使用的区段后，单击&#x200B;**[!UICONTROL Add Selected Segments]**。 添加区段会打开[!UICONTROL Edit Mapping]窗口。
   * 在[!UICONTROL Edit Mapping]内：
      * **[!UICONTROL Mappings]**：为此目标使用的[键值对](../../features/destinations/key-value-pairs.md)设置值。
      * **[!UICONTROL Start Date]**&#x200B;和&#x200B;**[!UICONTROL End Date]**：选择目标的开始日期和结束日期。 如果结束日期为空，则目标永不过期。
3. 单击&#x200B;**[!UICONTROL Save]**，然后单击&#x200B;**[!UICONTROL Done]**。
