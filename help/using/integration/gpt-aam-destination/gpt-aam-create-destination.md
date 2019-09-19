---
description: 您可以通过客户端（浏览器端）集成或服务器端集成将合格的区段发送到DFP。 如果选择客户端集成，则必须在Audience manager中为Google Publisher标记创建基于Cookie的目标。
seo-description: 您可以通过客户端（浏览器端）集成或服务器端集成将合格的区段发送到DFP。 如果选择客户端集成，则必须在Audience manager中为Google Publisher标记创建基于Cookie的目标。
seo-title: 创建GPT目标
solution: Audience Manager
title: 创建GPT目标
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# 创建GPT目标 {#create-a-gpt-destination}

您可以通过客户端(浏 [!DNL DFP] 览器端)集成或服务器端集成向其发送合格的区段。 如果选择客户端集成，则必须在Audience manager中为其创建基于Cookie的 [!DNL Google Publisher Tags] 目标。

## 目标

在Audience manager中，是任 *`destination`* 何其他系统(广告服务器、 [!DNL DSP]广告网络等)要与之共享数据。 [!UICONTROL Destination Builder] 提供了用于创建和管理这些数据交付流程的工具。 Audience manager目标功能位于 *[!UICONTROL Audience Data]&gt;中[!UICONTROL Destinations]*。 要开始，请单击 **[!UICONTROL Add New Destination]** 并按照以下步骤操作。

## 基本信息

要完成此部 [!UICONTROL Basic Information] 分，请执行以下操作：

1. 命名目标。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 单 **[!UICONTROL Next]** 击并转到和部 [!UICONTROL Configuration] 分 [!UICONTROL Segment Mappings] 。

## Cookie配置

请提供以下内容以完成该 [!UICONTROL Configuration] 部分（其他字段为可选字段）:

1. **** Cookie名称：为您的cookie提供一个简短的描述性名称。
1. **** 数据格式：选择选 **[!UICONTROL "Single Key"]** 项。
1. **** 关键：提供密钥名称。
1. **** 序列化：选中此复 **[!UICONTROL Enable]** 选框。
1. **** 序列分隔符：仅使用逗号。

## 区段映射

要向Cookie目标添加区段，请执行以下操作：

1. 查找区段：该部 [!UICONTROL Segment Mappings] 分提供了两种搜索工具，可帮助查找区段。 要查找区段，请执行以下操作：

   * 选项1:开始在搜索字段中键入区段名称。 字段会根据输入的文本自动更新。 找到 **[!UICONTROL Add]** 要使用的区段后，单击。
   * 选项2:单击 **[!UICONTROL Browse All Segments]** 以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 Click **[!UICONTROL Add Selected Segments]** when done.

1. **** 添加映射：在映射弹出窗口中，在映射字段中输入区段ID，然后单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL Done]**.