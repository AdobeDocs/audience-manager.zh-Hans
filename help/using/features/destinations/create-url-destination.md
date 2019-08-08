---
description: URL目标可向目标页面发出像素调用。按照这些说明，使用目标生成器创建URL目标。
seo-description: URL目标可向目标页面发出像素调用。按照这些说明，使用目标生成器创建URL目标。
seo-title: 配置URL目标
solution: Audience Manager
title: 配置URL目标
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# 配置URL目标 {#configure-url-destination}

[!DNL URL] 目标会向目标页面发出像素调用。按照这些说明创建 [!DNL URL][!UICONTROL Destination Builder]目标。

<!-- create-url-destination.xml -->

要创建 [!DNL URL] 新目标，请转至 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 并完成如下所述的章节。

## 基本信息 {#basic-info}

此部分包含启动URL目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名目标。避免缩写和特殊字符。
3. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
4. 在 **[!UICONTROL Category]** 列表中，选择 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 列表中，选择触发URL目标的环境。
6. 在 **[!UICONTROL Type]** 列表中，单击 **[!UICONTROL URL]**。
7. *(可选)* 选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。长度限制为255个字符，最大。
8. 单击 **[!UICONTROL Next]** 以转到 [!UICONTROL Configuration] 设置，或单击 **[!UICONTROL Data Export Labels]** 以将导出控件应用于目标。

## 数据导出标签 {#data-export-labels-dest}

此部分包含将 [数据导出控件](../../features/data-export-controls.md) 应用 [!DNL URL] 到目标的选项。如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签(请参阅 [将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) 以了解详细信息)。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configure-base-data}

此部分包含允许您设置由字符串传入的基础 [!DNL URL] 和数据分隔符的 [!DNL URL] 选项。此部分为可选部分。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Configuration]** 以显示控件。
1. *(可选)* 选中复选 **[!UICONTROL Serialize]** 框。
这允许您按顺序将区段发送到目标，而不是为每个区段单独发送调用。序列化有助于提高数据传输效率。选中此复选框可显示URL和分隔符字段。有关详细信息，请参阅 [标准和串行密钥对。](../../features/destinations/key-value-pairs.md)
1. 如果您选择 **[!UICONTROL Serialize]**&#x200B;此选项，则还必须配置下面描述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| 基本 URL | 标准 `HTTP`[!DNL URL] 的基本部分不变。此外，您还需要将 `%ALIAS%`[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 放置到基本URL中。示例: `https://www.myCompany.com/%alias%...` |
| 安全URL | 安全的基本部分 `HTTPS`[!DNL URL] 不会改变。此外，您还需要将 `%ALIAS%`[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 放置到基本URL中。示例: `https://www.myCompany.com/%alias%...` |
| Delimiter（分隔符） | 分隔 [!DNL URL] 字符串变量的符号。这通常是逗号或分号。从目标合作伙伴处获取此信息。 |

## 细分映射 {#segment-mappings}

此部分允许您搜索区段并将其添加到目标位置。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段列表。
1. 在 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时单击。添加区段将打开 [!UICONTROL Edit Mapping] 窗口。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供区段使用的键值对。
   * **[!UICONTROL Start Date]** 以及 **[!UICONTROL End Date]**：选择目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Done]**.