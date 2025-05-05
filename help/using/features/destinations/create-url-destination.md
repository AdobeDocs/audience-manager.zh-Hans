---
description: URL目标会从页面向目标进行像素调用。 按照以下说明使用Destination Builder创建URL目标。
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: 配置URL目标
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# 配置[!DNL URL Destination] {#configure-url-destination}

[!DNL URL destination]从页面向[!DNL destination]进行像素调用。 按照这些说明使用[!UICONTROL Destination Builder]创建[!DNL URL] [!DNL destination]。

<!-- create-url-destination.xml -->

要创建新[!DNL URL] [!DNL destination]，请转到&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;并完成以下所述部分。

## 基本信息 {#basic-info}

此部分包含启动[!DNL URL destination]创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Basic Information]**&#x200B;显示控件。
2. 为[!DNL destination]命名。 避免使用缩写和特殊字符。
3. *（可选）*&#x200B;描述[!DNL destination]。 简洁的描述是定义或提供更多有关[!DNL destination]的信息的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;列表中，选择要触发[!DNL URL destination]的环境。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;列表中，单击&#x200B;**[!UICONTROL URL]**。
7. *（可选）*&#x200B;选择&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**。 选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送至[!DNL destination]。
   * **[!UICONTROL Integration Code Value]**：自动添加段集成代码并将其发送到目标映射。 集成代码是由客户创建和使用的唯一标识符。 最多为255个字符。
8. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以转到[!UICONTROL Configuration]设置，或单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以将导出控件应用到[!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

此部分包含将[数据导出控件](../../features/data-export-controls.md)应用于[!DNL URL]目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;显示控件。
2. 选择与应用于目标的数据导出控制对应的标签（有关详细信息，请参阅[将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md)）。
3. 单击 **[!UICONTROL Save]**。

## 配置 {#configure-base-data}

此部分包含允许您设置基[!DNL URL]和由[!DNL URL]字符串传入的数据分隔符的选项。 此部分为可选部分。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Configuration]**&#x200B;显示控件。
1. *（可选）*&#x200B;选中&#x200B;**[!UICONTROL Serialize]**&#x200B;复选框。
这样，您就可以按顺序将区段发送到[!DNL destination]，而不是为每个区段分别发出调用。 序列化有助于高效传输数据。 选中此复选框会显示URL和分隔符字段。 有关详细信息，请参阅[标准和序列键值对](../../features/destinations/key-value-pairs.md)。
1. 如果选择&#x200B;**[!UICONTROL Serialize]**，则还必须配置如下所述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| [!UICONTROL Base URL] | 不会更改的标准`HTTP` [!DNL URL]的基部分。 此外，您需要在基本URL中放置`%ALIAS%` [占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined)。 示例： `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 不会更改的安全`HTTPS` [!DNL URL]的基部分。 此外，您需要放置`%ALIAS%`   基础URL中的[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined)。 示例： `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 用于分隔[!DNL URL]字符串中的区段变量的符号。 这通常是逗号或分号。 从目标合作伙伴处获取此信息。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此部分允许您搜索区段并将其添加到您的[!UICONTROL destination]。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;显示控件。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;框中，开始键入区段的名称，或单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;浏览可用区段的列表。
1. 找到要使用的区段后，单击&#x200B;**[!UICONTROL Add Selected Segments]**。 添加区段会打开[!UICONTROL Edit Mapping]窗口。
1. 在[!UICONTROL Edit Mapping]内：
   * **[!UICONTROL Mappings]**：提供区段使用的键值对。
   * **[!UICONTROL Start Date]**&#x200B;和&#x200B;**[!UICONTROL End Date]**：选择[!DNL destination]的开始和结束日期。 如果结束日期为空，[!DNL destination]将永不过期。
1. 单击 **[!UICONTROL Done]**。
