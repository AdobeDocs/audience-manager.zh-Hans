---
description: URL目标会从页面向目标进行像素调用。 按照以下说明，使用Destination Builder创建URL目标。
seo-description: URL目标会从页面向目标进行像素调用。 按照以下说明，使用Destination Builder创建URL目标。
seo-title: 配置 URL 目标
solution: Audience Manager
title: 配置 URL 目标
translation-type: tm+mt
source-git-commit: d83b07a542dd337773d287f4eba0960c6e258504
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# 配置 [!DNL URL Destination] {#configure-url-destination}

从页 [!DNL URL destination] 面到您的页面进行像素调 [!DNL destination]用。 按照以下说明创建 [!DNL URL][!DNL destination] 对象 [!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

要创建新内容， [!DNL URL] 请转 [!DNL destination]到并 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 按照如下所述完成各个部分。

## 基本信息 {#basic-info}

此部分包含开始创建过程的字 [!DNL URL destination] 段和选项。 要完成此部分：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名 [!DNL destination]。 避免缩写和特殊字符。
3. *(可选* )描述 [!DNL destination]。 简洁的描述是定义或提供更多相关信息的有效方式 [!DNL destination]。
4. 在列表 **[!UICONTROL Category]** 中，选择 **[!UICONTROL Custom]**。
5. 在列表 **[!UICONTROL Environment]** 中，选择要在其中触发的环境 [!DNL URL destination]。
6. 在列表 **[!UICONTROL Type]** 中，单击 **[!UICONTROL URL]**。
7. *（可选）* 选择 **[!UICONTROL Auto-fill Destination Mapping]**。 选项包括：
   * **[!UICONTROL Segment ID]**: 自动添加区段ID并将其发送到 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**: 自动添加区段集成代码并将其发送到目标映射。 集成代码是客户创建和使用的唯一标识符。 最多限制为255个字符。
8. 单 **[!UICONTROL Next]** 击以转到设 [!UICONTROL Configuration] 置，或单 **[!UICONTROL Data Export Labels]** 击以将导出控件应用到 [!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本节包含将数据导 [出控件应用](../../features/data-export-controls.md) 到目标 [!DNL URL] 的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签(有关详细信 [息，请参阅将导出标签添加](/help/using/features/destinations/add-data-export-labels.md) 到目标)。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configure-base-data}

此部分包含用于设置由字符串传 [!DNL URL] 入的基本和数据分隔符的 [!DNL URL] 选项。 此部分是可选的。 要完成此部分：

1. 单击 **[!UICONTROL Configuration]** 以显示控件。
1. *（可选）选* 中该 **[!UICONTROL Serialize]** 复选框。
这样，您就可以按顺序发送区 [!DNL destination] 段，而不是对每个区段单独发出调用。 序列化有助于提高数据传输效率。 选中此复选框将显示URL和分隔符字段。 有关详细信息，请 [参阅标准和序列键值对](../../features/destinations/key-value-pairs.md)。
1. 如果您选 **[!UICONTROL Serialize]**&#x200B;择，则还必须配置下面描述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| [!UICONTROL Base URL] | 不变的标准的 `HTTP` 基 [!DNL URL] 部分。 此外，您需要将占 `%ALIAS%` 位 [符宏放](../../features/destinations/destination-macros.md#destination-macros-defined) 置在基URL中。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 安全保护的基 `HTTPS` 本部 [!DNL URL] 分不变。 此外，您需要将占 `%ALIAS%` 位 [符宏放](../../features/destinations/destination-macros.md#destination-macros-defined) 置在基URL中。 示例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 分隔字符串中段变量的符 [!DNL URL] 号。 这通常是逗号或分号。 从目标合作伙伴处获取此信息。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

通过此部分，您可以搜索区段并将其添加到您 [!UICONTROL destination]的。 要完成此部分：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. 在框 **[!UICONTROL Search and Add Segments]** 中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段的列表。
1. 当您 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时，单击。 添加区段会打开 [!UICONTROL Edit Mapping] 窗口。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: 提供段使用的键值对。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**: 选择开始和结束日期 [!DNL destination]。 如果结束日期为空，则永 [!DNL destination] 不过期。
1. 单击 **[!UICONTROL Done]**.