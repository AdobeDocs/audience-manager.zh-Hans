---
description: URL目标会从页面向目标进行像素调用。 按照以下说明，使用Destination Builder创建URL目标。
seo-description: URL目标会从页面向目标进行像素调用。 按照以下说明，使用Destination Builder创建URL目标。
seo-title: 配置 URL 目标
solution: Audience Manager
title: 配置 URL 目标
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# 配置[!DNL URL Destination] {#configure-url-destination}

[!DNL URL destination]从页面向[!DNL destination]发出像素调用。 按照以下说明创建[!DNL URL] [!DNL destination]和[!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

要创建新的[!DNL URL] [!DNL destination]，请转到&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;并完成以下部分。

## 基本信息 {#basic-info}

此部分包含开始[!DNL URL destination]创建过程的字段和选项。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Basic Information]**&#x200B;以显示控件。
2. 命名[!DNL destination]。 避免缩写和特殊字符。
3. *（可选）* 描述 [!DNL destination]。简洁的描述是定义或提供有关[!DNL destination]的更多信息的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;列表中，选择触发[!DNL URL destination]的环境。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;列表中，单击&#x200B;**[!UICONTROL URL]**。
7. *（可选）* 选择 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**:自动添加区段ID并将其发送到 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**:自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。 最多限制为255个字符。
8. 单击&#x200B;**[!UICONTROL Next]**&#x200B;可转到[!UICONTROL Configuration]设置，或单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;可将导出控件应用于[!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本节包含将[数据导出控件](../../features/data-export-controls.md)应用到[!DNL URL]目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签（有关详细信息，请参阅[将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md)）。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configure-base-data}

此部分包含用于设置基[!DNL URL]和由[!DNL URL]字符串传入的数据分隔符的选项。 此部分是可选的。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Configuration]**&#x200B;以显示控件。
1. *（可选）选* 中该 **[!UICONTROL Serialize]** 复选框。这样，您就可以按顺序将区段发送到[!DNL destination]，而不是对每个区段单独调用。 序列化有助于提高数据传输效率。 选中此复选框将显示URL和分隔符字段。 有关详细信息，请参阅[标准和串行键值对](../../features/destinations/key-value-pairs.md)。
1. 如果选择&#x200B;**[!UICONTROL Serialize]**，则还必须配置下面描述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| [!UICONTROL Base URL] | 未更改的标准`HTTP` [!DNL URL]的基部。 此外，您还需要将`%ALIAS%` [占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined)放在基本URL中。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 安全`HTTPS` [!DNL URL]的基本部分没有变化。 此外，您需要将`%ALIAS%`   基本URL中的[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined)。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 在[!DNL URL]字符串中分隔段变量的符号。 这通常是逗号或分号。 从目标合作伙伴处获取此信息。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此部分允许您搜索区段并将其添加到[!UICONTROL destination]。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以显示控件。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;框中，开始键入区段名称或单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;浏览可用区段的列表。
1. 当您找到要使用的区段时，单击&#x200B;**[!UICONTROL Add Selected Segments]**。 添加区段会打开[!UICONTROL Edit Mapping]窗口。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:提供段使用的键值对。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:选择开始和结束日期 [!DNL destination]。如果结束日期为空，则[!DNL destination]永不过期。
1. 单击 **[!UICONTROL Done]**.