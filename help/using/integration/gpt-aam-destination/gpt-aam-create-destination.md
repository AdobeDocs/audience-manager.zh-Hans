---
description: 您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到DFP。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。
seo-description: 您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到DFP。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。
seo-title: 创建 GPT 目标
solution: Audience Manager
title: 创建 GPT 目标
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 7%

---


# 创建 GPT 目标 {#create-a-gpt-destination}

您可以通过客户端( [!DNL DFP] 浏览器端)集成或服务器端集成向客户端发送符合条件的区段。 如果选择客户端集成，则必须创建Audience Manager中基于cookie的 [!DNL Google Publisher Tags] 目标。

## 目标

在Audience Manager中， *`destination`* 是任何其他系统(广告服 [!DNL DSP]务器、广告网络等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供了用于创建和管理这些数据投放流程的工具。 Audience Manager目标功能位于 *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*。 要开始，请单&#x200B;**[!UICONTROL Add New Destination]**击并按照以下步骤操作。

## 基本信息

要完成该部 [!UICONTROL Basic Information] 分：

1. 命名目标。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 单 **[!UICONTROL Next]** 击并转到和 [!UICONTROL Configuration] 部 [!UICONTROL Segment Mappings] 分。

## Cookie配置

请提供以下内容以完 [!UICONTROL Configuration] 成部分（其他字段为可选字段）:

1. **Cookie名称：** 为您的cookie提供一个简短的描述性名称。
1. **数据格式：** 选择选 **[!UICONTROL "Single Key"]** 项。
1. **密钥：** 提供密钥名称。
1. **序列化：** 选中复 **[!UICONTROL Enable]** 选框。
1. **序列分隔符：** 只使用逗号。

## 区段映射

要向Cookie目标添加区段，请执行以下操作：

1. 查找区段： 此部 [!UICONTROL Segment Mappings] 分提供两种搜索工具，帮助查找区段。 要查找区段，请执行以下操作：

   * 选项1: 开始在搜索字段中键入区段名称。 字段会根据输入的文本自动更新。 找到 **[!UICONTROL Add]** 要使用的区段后，单击。
   * 选项2: 单击 **[!UICONTROL Browse All Segments]** 以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 完成 **[!UICONTROL Add Selected Segments]** 后单击。

1. **添加映射：** 在映射弹出窗口中，在映射字段中输入段ID并单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL Done]**.