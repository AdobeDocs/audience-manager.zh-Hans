---
description: Cookie目标会返回数据，并将其写入用户浏览器中的Cookie中。 该Cookie包含的数据可由具有页面访问权限的其他平台读取。 按照以下说明创建具有[!UICONTROL Destination Builder]的Cookie目标。
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: 配置Cookie目标
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# 配置Cookie目标 {#create-cookie-destination}

Cookie目标会返回数据，并将其写入用户浏览器中的Cookie中。 该Cookie包含的数据可由具有页面访问权限的其他平台读取。 按照以下说明创建具有[!UICONTROL Destination Builder]的Cookie目标。

<!-- create-cookie-destination.xml -->

要创建新的Cookie目标，请转到&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;并完成以下所述部分。

## 基本信息 {#basic-information}

此部分包含启动Cookie目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Basic Information]**&#x200B;显示控件。
2. 命名目标。 避免使用缩写和特殊字符。
3. *（可选）*&#x200B;描述目标。 简洁的描述是定义或提供更多有关目标的信息的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Browser]**。 无法为本机移动设备环境(如Android或iOS应用程序)配置Cookie目标。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Cookie]**。
7. *（可选）*&#x200B;选择&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**。 选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加段集成代码并将其发送到目标映射。 集成代码是由客户创建和使用的唯一标识符。 最多为255个字符。
8. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以转到[!UICONTROL Configuration]设置，或单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以将导出控件应用到目标。

## 数据导出标签 {#data-export-labels-cookies}

此部分包含将[数据导出控件](../../features/data-export-controls.md)应用于Cookie目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;显示控件。
2. 选择与应用于目标的数据导出控制对应的标签（有关详细信息，请参阅[将导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md)）。
3. 单击 **[!UICONTROL Save]**。

## 配置 {#configuration}

此部分包含允许您为目标设置Cookie的字段和选项。

>[!NOTE]
>
>[!DNL Audience Manager]对写入目标Cookie的数据进行编码。 例如，空格编码为`%20`，分号编码为`%3B`。

要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Configuration]**&#x200B;以公开控件
1. 为Cookie命名。 避免使用缩写和特殊字符。
1. 选择数据格式选项。 这些选项允许您为将区段数据发送到目标的键值对选择分隔符和分隔符。 格式选项包括：
   * **单键：**&#x200B;允许您在键值对中设置键。 在以下[!UICONTROL Segment Mappings]部分中选择区段后，您将设置该值。
   * **多键：**允许您设置键值对的键和值。 在下面的“区段映射”部分中选择区段后，您将创建键值对。
有关这些数据元素的详细信息，请参阅[标准和序列键值对](../../features/destinations/key-value-pairs.md)。
1. 单击 **[!UICONTROL Save]**。

所有其他设置都是可选的。 有关&#x200B;**[!UICONTROL Cookie Domain]**&#x200B;和&#x200B;**[!UICONTROL Publish data to]**&#x200B;设置的详细信息，请参阅[Cookie目标的可选设置](/help/using/features/destinations/cookie-destination-options.md)。

## 区段映射 {#segments-mapping}

在此部分中，您可以搜索区段并将区段添加到目标。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;显示控件。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;框中，开始键入区段的名称，或单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;浏览可用区段的列表。
1. 找到要使用的区段后，单击&#x200B;**[!UICONTROL Add Selected Segments]**。 添加区段会打开[!UICONTROL Edit Mapping]窗口。
1. 在[!UICONTROL Edit Mapping]对话框中：
   * **[!UICONTROL Mapping]**&#x200B;允许您为上面“配置”部分中指定的键设置值。
   * **[!UICONTROL Publish from]**&#x200B;允许您设置目标的开始日期和结束日期。 如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**。
