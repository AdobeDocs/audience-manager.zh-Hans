---
description: 您可以通过客户端（浏览器端）集成或服务器端集成将合格的细分发送到Google Ad Manager。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。
seo-description: 您可以通过客户端（浏览器端）集成或服务器端集成将合格的细分发送到Google Ad Manager。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。
seo-title: 创建 GPT 目标
solution: Audience Manager
title: 创建 GPT 目标
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# 创建 GPT 目标 {#create-a-gpt-destination}

您可以通过客户端（浏览器端）集成或服务器端集成向[!DNL Google Ad Manager]发送符合条件的区段。 如果选择客户端集成，则必须为Audience Manager中的[!DNL Google Publisher Tags]创建基于cookie的目标。

## 目标

在Audience Manager中，*`destination`*&#x200B;是任何其他系统（广告服务器、[!DNL DSP]和广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供了用于创建和管理这些数据投放流程的工具。Audience Manager目标功能位于&#x200B;*[!UICONTROL Audience Data]>[!UICONTROL Destinations]*&#x200B;中。 要开始，请单击&#x200B;**[!UICONTROL Add New Destination]**&#x200B;并按照以下步骤操作。

## 基本信息

完成[!UICONTROL Basic Information]部分：

1. 命名目标。
1. 从[!UICONTROL Type]下拉列表中选择&#x200B;**[!UICONTROL "Cookie"]**。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并转到[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

## Cookie配置

请提供以下内容以完成[!UICONTROL Configuration]部分（其他字段为可选字段）:

1. **Cookie名称：** 为Cookie提供一个简短的描述性名称。
1. **数据格式：** 选择 **[!UICONTROL "Single Key"]** 选项。
1. **键：** 提供键名。
1. **序列化：** 选中复 **[!UICONTROL Enable]** 选框。
1. **序列分隔符：** 仅使用逗号。

## 区段映射

要向Cookie目标添加区段，请执行以下操作：

1. 查找区段：[!UICONTROL Segment Mappings]部分提供两种搜索工具来帮助查找区段。 要查找区段，请执行以下操作：

   * 选项1:开始在搜索字段中键入区段名称。 字段会根据输入的文本自动更新。 找到要使用的区段后，单击&#x200B;**[!UICONTROL Add]**。
   * 选项2:单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 完成后，单击&#x200B;**[!UICONTROL Add Selected Segments]**。

1. **添加映** 射：在映射弹出窗口中，在映射字段中输入段ID并单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL Done]**.