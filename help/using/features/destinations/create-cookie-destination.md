---
description: Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供有权访问页面的其他平台读取的数据。 按照以下说明创建具有[!UICONTROL Destination Builder]的Cookie目标。
seo-description: Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供有权访问页面的其他平台读取的数据。 按照以下说明创建具有[!UICONTROL Destination Builder]的Cookie目标。
seo-title: 配置 Cookie 目标
solution: Audience Manager
title: 配置 Cookie 目标
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# 配置 Cookie 目标 {#create-cookie-destination}

Cookie目标在用户的浏览器中返回数据并将其写入Cookie。 Cookie包含可供有权访问页面的其他平台读取的数据。 按照以下说明创建具有[!UICONTROL Destination Builder]的Cookie目标。

<!-- create-cookie-destination.xml -->

要创建新的cookie目标，请转至&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;并完成以下部分。

## 基本信息 {#basic-information}

此部分包含开始Cookie目标创建过程的字段和选项。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Basic Information]**&#x200B;以显示控件。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* 描述目标。简洁的描述是定义或提供有关目标的更多信息的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Browser]**。 无法为本机移动环境（如Android或iOS应用程序）配置Cookie目标。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Cookie]**。
7. *（可选）* 选择 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**:自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**:自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。 最多限制为255个字符。
8. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以转到[!UICONTROL Configuration]设置，或单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以将导出控件应用到目标。

## 数据导出标签{#data-export-labels-cookies}

本节包含将[数据导出控件](../../features/data-export-controls.md)应用到cookie目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签（有关详细信息，请参阅[将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md)）。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configuration}

此部分包含用于为目标设置Cookie的字段和选项。

>[!NOTE]
>
>[!DNL Audience Manager] 对写入到目标cookie的数据进行编码。例如，空格编码为`%20`，分号编码为`%3B`。

要完成此部分：

1. 单击&#x200B;**[!UICONTROL Configuration]**&#x200B;以显示控件
1. 命名Cookie。 避免缩写和特殊字符。
1. 选择数据格式选项。 这些选项允许您为将段数据发送到目标的键值对选择分隔符和分隔符。 格式选项包括：
   * **单键：** 用于在键值对中设置键。在下面的[!UICONTROL Segment Mappings]部分选择区段后，您将设置该值。
   * **多键：** 用于设置键值对的键和值。在下面的“区段映射”部分选择区段后，您将创建键值对。
有关这些数据元素的详细信息，请参见[标准和串行键值对](../../features/destinations/key-value-pairs.md)。
1. 单击 **[!UICONTROL Save]**.

所有其他设置都是可选的。 有关&#x200B;**[!UICONTROL Cookie Domain]**&#x200B;和&#x200B;**[!UICONTROL Publish data to]**&#x200B;设置的详细信息，请参阅[ Cookie目标的可选设置](/help/using/features/destinations/cookie-destination-options.md)。

## 段映射{#segments-mapping}

此部分允许您搜索区段并将其添加到目标。 要完成此部分：

1. 单击&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以显示控件。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;框中，开始键入区段名称或单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以浏览可用区段的列表。
1. 当您找到要使用的区段时，单击&#x200B;**[!UICONTROL Add Selected Segments]**。 添加区段会打开[!UICONTROL Edit Mapping]窗口。
1. 在[!UICONTROL Edit Mapping]对话框中：
   * **[!UICONTROL Mapping]** 允许您为上述“配置”部分中指定的键设置值。
   * **[!UICONTROL Publish from]** 允许您设置目标的开始和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.