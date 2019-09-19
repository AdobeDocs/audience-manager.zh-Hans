---
description: Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供其他可访问页面的平台读取的数据。 按照以下说明使用[!UICONTROL Destination Builder]创建Cookie目标。
seo-description: Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供其他可访问页面的平台读取的数据。 按照以下说明使用[!UICONTROL Destination Builder]创建Cookie目标。
seo-title: 配置Cookie目标
solution: Audience Manager
title: 配置Cookie目标
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 配置Cookie目标 {#create-cookie-destination}

Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供其他可访问页面的平台读取的数据。 按照以下说明创建Cookie目标 [!UICONTROL Destination Builder]。

<!-- create-cookie-destination.xml -->

要创建新的Cookie目标，请转到并 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 完成以下部分，如下所述。

## 基本信息 {#basic-information}

此部分包含用于启动Cookie目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* ，描述目标。 简洁的描述是定义或提供有关目标的更多信息的有效方法。
4. 在列表 **[!UICONTROL Category]** 中，选择 **[!UICONTROL Custom]**。
5. 在列表 **[!UICONTROL Environment]** 中，选择 **[!UICONTROL Browser]**。 您无法为Android或iOS应用程序等本机移动环境配置Cookie目标。
6. 在列表 **[!UICONTROL Type]** 中，单击 **[!UICONTROL Cookie]**。
7. *（可选）* ，选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。 选项包括：
   * **[!UICONTROL Segment ID]**:自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**:自动添加区段集成代码并将其发送到目标映射。 集成代码是客户创建和使用的唯一标识符。 最多限制为255个字符。
8. 单 **[!UICONTROL Next]** 击可转到设置或 [!UICONTROL Configuration] 单击 **[!UICONTROL Data Export Labels]** 可将导出控件应用到目标。

## 数据导出标签 {#data-export-labels-cookies}

此部分包含将数据导出控 [件应用到](../../features/data-export-controls.md) Cookie目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件相对应的标签(有关详细信 [息，请参阅将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) )。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configuration}

此部分包含字段和选项，可让您为目标设置Cookie。

>[!NOTE]
>
>[!DNL Audience Manager] 对写入到目标cookie的数据进行编码。 例如，空格将编码为空格， `%20` 分号将编码为 `%3B`。

要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Configuration]** 以显示控件
1. 命名Cookie。 避免缩写和特殊字符。
1. 选择数据格式选项。 这些选项允许您为将段数据发送到目标的键值对选择分隔符和分隔符。 格式选项包括：
   * **** 单键：允许您在键值对中设置键。 在以下部分中选择区段后，您将设置该 [!UICONTROL Segment Mappings] 值。
   * **** 多键：用于设置键值对的键和值。 在下面的“区段映射”部分选择区段后，您将创建键值对。
有关 [这些数据元素的详细信息，请参阅标准键值对和序列键值对](../../features/destinations/key-value-pairs.md) 。
1. 单击 **[!UICONTROL Save]**.

所有其他设置都是可选的。 有关这些设置和设置的更 **[!UICONTROL Cookie Domain]** 多信 **[!UICONTROL Publish data to]** 息，请参阅 [Cookie目标的可选设置](/help/using/features/destinations/cookie-destination-options.md)。

## 区段映射 {#segments-mapping}

通过此部分，您可以搜索区段并将其添加到目标。 要完成此部分，请执行以下操作：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. 在框 **[!UICONTROL Search and Add Segments]** 中，开始键入区段的名称，或单击以浏览 **[!UICONTROL Browse All Segments]** 可用区段的列表。
1. 当您 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时，单击。 添加区段会打开窗 [!UICONTROL Edit Mapping] 口。
1. 在对话 [!UICONTROL Edit Mapping] 框中：
   * **[!UICONTROL Mapping]** 允许您为上述“配置”部分中指定的键设置值。
   * **[!UICONTROL Publish from]** 允许您设置目标的开始和结束日期。 如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.