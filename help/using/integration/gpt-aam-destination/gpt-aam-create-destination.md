---
description: 您可以通过客户端(浏览器端)集成或服务器端集成将合格的区段发送到DFP。如果选择客户端集成，则必须在Audience Manager中为Google Publisher标记创建基于cookie的目标。
seo-description: 您可以通过客户端(浏览器端)集成或服务器端集成将合格的区段发送到DFP。如果选择客户端集成，则必须在Audience Manager中为Google Publisher标记创建基于cookie的目标。
seo-title: 创建GPT目标
solution: Audience Manager
title: 创建GPT目标
uuid: e3bbf327-a7 e0-48da-bc84-8f531 b7 f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## 目标

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) 您希望与之共享数据的数据。[!UICONTROL Destination Builder] 提供允许您创建和管理这些数据交付流程的工具。Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## 基本信息

To complete the [!UICONTROL Basic Information] section:

1. 命名目标。
1. **[!UICONTROL "Cookie"]** 从 [!UICONTROL Type] 下拉列表中进行选择。
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Cookie配置

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Cookie名称：** 为您的cookie提供简短的描述性名称。
1. **数据格式：** 选择 **[!UICONTROL "Single Key"]** 选项。
1. **密钥：** 提供密钥名。
1. **序列化：** 选中复选 **[!UICONTROL Enable]** 框。
1. **串行分隔符：** 仅使用逗号。

## 细分映射

要将区段添加到cookie目标，请执行以下操作：

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. 要查找区段，请执行以下操作：

   * 选项1：开始在搜索字段中键入区段名称。字段会根据输入的文本自动更新。Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **添加映射：** 在映射弹出窗口中，在映射字段中输入区段ID，然后单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL Done]**.