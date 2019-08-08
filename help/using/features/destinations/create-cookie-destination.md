---
description: Cookie目标返回数据并将数据写入用户浏览器中的cookie。cookie包含可由有权访问页面的其他平台读取的数据。按照这些说明，使用[！UICCONTROL目标生成器]。
seo-description: Cookie目标返回数据并将数据写入用户浏览器中的cookie。cookie包含可由有权访问页面的其他平台读取的数据。按照这些说明，使用[！UICCONTROL目标生成器]。
seo-title: 配置Cookie目标
solution: Audience Manager
title: 配置Cookie目标
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 配置Cookie目标 {#create-cookie-destination}

Cookie目标返回数据并将数据写入用户浏览器中的cookie。cookie包含可由有权访问页面的其他平台读取的数据。按照这些说明创建Cookie [!UICONTROL Destination Builder]目标。

<!-- create-cookie-destination.xml -->

要创建新的cookie目标，请转至 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 并完成下面所述的章节。

## 基本信息 {#basic-information}

此部分包含启动cookie目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名目标。避免缩写和特殊字符。
3. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
4. 在 **[!UICONTROL Category]** 列表中，选择 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 列表中，选择 **[!UICONTROL Browser]**。无法为原生移动环境(如Android或iOS应用程序)配置cookie目标。
6. 在 **[!UICONTROL Type]** 列表中，单击 **[!UICONTROL Cookie]**。
7. *(可选)* 选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。长度限制为255个字符，最大。
8. 单击 **[!UICONTROL Next]** 以转到 [!UICONTROL Configuration] 设置，或单击 **[!UICONTROL Data Export Labels]** 以将导出控件应用于目标。

## 数据导出标签 {#data-export-labels-cookies}

此部分包含将 [数据导出控件](../../features/data-export-controls.md) 应用到Cookie目标的选项。如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签(请参阅 [将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) 以了解详细信息)。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configuration}

此部分包含允许您为目标设置Cookie的字段和选项。

>[!NOTE]
>
>[!DNL Audience Manager] 对写入目标cookie的数据进行编码。例如，空格以编码方式 `%20` 编码，分号编码为 `%3B`。

要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Configuration]** 以显示控件
1. 命名cookie。避免缩写和特殊字符。
1. 选择数据格式选项。这些选项允许您为将区段数据发送到目标的键值对选择分隔符和分隔符。格式选项包括：
   * **单键：** 允许您在键值对中设置键。您将在下 [!UICONTROL Segment Mappings] 一节中选择一个区段后设置该值。
   * **多键：** 允许您设置键值对的键和值。在下面的“区段映射”部分选择区段之后，您将创建键值对。
有关这些数据元素的更多信息，请参阅 [标准和序列密钥对。](../../features/destinations/key-value-pairs.md)
1. 单击 **[!UICONTROL Save]**.

所有其他设置均为可选设置。有关和 **[!UICONTROL Cookie Domain]****[!UICONTROL Publish data to]** 设置的更多信息，请参阅 [Cookie目标的可选设置](/help/using/features/destinations/cookie-destination-options.md)。

## 细分映射 {#segments-mapping}

此部分允许您搜索区段并将其添加到目标位置。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 以浏览可用区段列表。
1. 在 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时单击。添加区段将打开 [!UICONTROL Edit Mapping] 窗口。
1. 在 [!UICONTROL Edit Mapping] 对话框中：
   * **[!UICONTROL Mapping]** 允许您为以上“配置”部分中指定的键设置值。
   * **[!UICONTROL Publish from]** 允许您设置目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.