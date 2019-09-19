---
description: URL目标会从页面向目标发出像素调用。 按照以下说明，使用Destination builder创建URL目标。
seo-description: URL目标会从页面向目标发出像素调用。 按照以下说明，使用Destination builder创建URL目标。
seo-title: 配置URL目标
solution: Audience Manager
title: 配置URL目标
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# 配置URL目标 {#configure-url-destination}

目标 [!DNL URL] 会从页面向目标发出像素调用。 按照以下说明创建 [!DNL URL] 目标 [!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

要创建新目 [!DNL URL] 标，请转 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 到并完成以下部分。

## 基本信息 {#basic-info}

此部分包含开始URL目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* ，描述目标。 简洁的描述是定义或提供有关目标的更多信息的有效方法。
4. 在列表 **[!UICONTROL Category]** 中，选择 **[!UICONTROL Custom]**。
5. 在列 **[!UICONTROL Environment]** 表中，选择触发URL目标的环境。
6. 在列表 **[!UICONTROL Type]** 中，单击 **[!UICONTROL URL]**。
7. *（可选）* ，选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。 选项包括：
   * **[!UICONTROL Segment ID]**:自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**:自动添加区段集成代码并将其发送到目标映射。 集成代码是客户创建和使用的唯一标识符。 最多限制为255个字符。
8. 单 **[!UICONTROL Next]** 击可转到设置或 [!UICONTROL Configuration] 单击 **[!UICONTROL Data Export Labels]** 可将导出控件应用到目标。

## 数据导出标签 {#data-export-labels-dest}

本节包含将数据导出控 [件应用到目标](../../features/data-export-controls.md) 的选 [!DNL URL] 项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签(有关详细信息，请参 [阅将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) )。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configure-base-data}

此部分包含允许您设置由字符串传 [!DNL URL] 入的基本分隔符和数据分隔符的 [!DNL URL] 选项。 此部分是可选的。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Configuration]** 以显示控件。
1. *（可选）* ，选中 **[!UICONTROL Serialize]** 复选框。
这样，您就可以按顺序将区段发送到目标，而不是对每个区段单独调用。 序列化有助于提高数据传输的效率。 选中此复选框将显示URL和分隔符字段。 有关详细信息，请参 [阅标准和序列键值对](../../features/destinations/key-value-pairs.md)。
1. 如果您选 **[!UICONTROL Serialize]**&#x200B;择，则还必须配置以下描述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| 基本 URL | 不变的标准的 `HTTP` 基 [!DNL URL] 本部分。 此外，您还需要将占 `%ALIAS%` 位 [符宏放在基](../../features/destinations/destination-macros.md#destination-macros-defined) 本URL中。 示例: `https://www.myCompany.com/%alias%...` |
| 安全URL | 安全保护的基本部 `HTTPS` 分，不 [!DNL URL] 会更改。 此外，您还需要将占 `%ALIAS%` 位 [符宏放在基](../../features/destinations/destination-macros.md#destination-macros-defined) 本URL中。 示例: `https://www.myCompany.com/%alias%...` |
| Delimiter（分隔符） | 分隔字符串中段变量的符 [!DNL URL] 号。 这通常是逗号或分号。 从目标合作伙伴处获取此信息。 |

## 区段映射 {#segment-mappings}

通过此部分，您可以搜索区段并将其添加到目标。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. 在框 **[!UICONTROL Search and Add Segments]** 中，开始键入区段名称或单击浏览可 **[!UICONTROL Browse All Segments]** 用区段列表。
1. 当您 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时，单击。 添加区段会打开窗 [!UICONTROL Edit Mapping] 口。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:提供段使用的键值对。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:选择目标的开始和结束日期。 如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Done]**.