---
description: 您可以通过客户端（浏览器端）集成或服务器端集成，将符合条件的区段发送到Google Ad Manager。 如果选择客户端集成，则必须在Audience Manager中为Google发布者标记创建基于Cookie的目标。
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: 创建GPT目标
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---

# 创建GPT目标 {#create-a-gpt-destination}

您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]。 如果选择客户端集成，则必须在Audience Manager中为[!DNL Google Publisher Tags]创建基于Cookie的目标。

## 目标

在Audience Manager中，*`destination`*&#x200B;是任何其他系统（广告服务器、[!DNL DSP]、广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder]提供了用于创建和管理这些数据传输流程的工具。 Audience Manager目标功能位于&#x200B;*[!UICONTROL Audience Data]>[!UICONTROL Destinations]*&#x200B;中。 要开始操作，请单击&#x200B;**[!UICONTROL Add New Destination]**&#x200B;并按照以下步骤操作。

## 基本信息

要完成[!UICONTROL Basic Information]部分，请执行以下操作：

1. 命名目标。
1. 从[!UICONTROL Type]下拉列表中选择&#x200B;**[!UICONTROL "Cookie"]**。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并转到[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

## Cookie配置

提供以下内容以完成[!UICONTROL Configuration]部分（其他字段是可选的）：

1. **Cookie名称：**&#x200B;为您的Cookie提供一个简短的、描述性的名称。
1. **数据格式：**&#x200B;选择&#x200B;**[!UICONTROL "Single Key"]**&#x200B;选项。
1. **键：**&#x200B;提供键名。
1. **序列化：**&#x200B;选中&#x200B;**[!UICONTROL Enable]**&#x200B;复选框。
1. **串行分隔符：**&#x200B;仅使用逗号。

## 区段映射

要将区段添加到Cookie目标，请执行以下操作：

1. 查找区段： [!UICONTROL Segment Mappings]部分提供两种搜索工具来帮助查找区段。 要查找段，请执行以下操作：

   * 选项1：开始在搜索字段中键入区段名称。 字段会根据输入的文本自动更新。 找到要使用的区段后，请单击&#x200B;**[!UICONTROL Add]**。
   * 选项2：单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;打开一个窗口，允许您按名称或存储位置浏览区段。 完成后单击&#x200B;**[!UICONTROL Add Selected Segments]**。

1. **添加映射：**&#x200B;在映射弹出窗口中，在映射字段中输入区段ID并单击&#x200B;**[!UICONTROL Save]**。

1. 单击 **[!UICONTROL Done]**。
