---
description: 将Open Ad Server设置为目标，并将Audience Manager数据发送到该平台。
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS作为Audience Manager目标
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# OAS作为Audience Manager目标 {#oas-as-an-audience-manager-destination}

将[!DNL Open Ad Server]设置为目标并将Audience Manager数据发送到该平台。

## OAS目标要求 {#oas-requirements}

代码放置标准、支持的键值格式、报表以及发送到[!DNL OAS]的区段数据类型。

<!-- aam-oas-requirements.xml -->

此目标类型需要满足以下条件：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library]代码应部署在您的清单上。 [!UICONTROL DIL]有助于消除为数据收集、集成、读取Cookie值和恢复页面数据编写特殊代码的需要。
* **`get_aamCookie`函数：**&#x200B;捕获Audience Manager用户ID和Cookie数据的代码。 将[此代码](../../features/destinations/get-aam-cookie-code.md)放在页面顶部或`<head>`代码块内。
* **将投放日志发送到Audience Manager：**&#x200B;如果您需要区段投放报告（可选），请为Audience Manager提供包含展示级别投放数据的每日日志。 数据可以是原始格式，但每个记录都必须包含Audience Manager[!UICONTROL UUID]。 Audience Manager可以通过[!DNL FTP]收取或接收这些邮件。

### Cookie格式和键值数据

Audience Manager可以将区段数据发送到浏览器Cookie，如下所示：

* 单个键(`x=1&x=2`)；
* 多个键(`x=1&x=2&y=3&y=4`)；
* 序列化值(`x=1,2,3`)；
* 用于分隔各个键值对的标准值分隔符。

### 只有符合条件的区段才会发送到OAS

传递到[!DNL OAS]的数据量取决于特定用户符合条件的区段数。 例如，假设您设置了100个Audience Manager区段。 如果网站访客符合其中五个区段的条件，则只有这五个区段会发送到OAS（并非所有100个区段）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 代码](../../features/destinations/get-aam-cookie-code.md)
>* [键值对说明](../../reference/key-value-pairs-explained.md)

## 创建OAS目标 {#oas-dest-setup}

在Audience Manager中为[!DNL OAS]创建基于Cookie的目标。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中，*目标*&#x200B;是任何其他系统（广告服务器、[!DNL DSP]、广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder]提供了用于创建和管理这些数据传输流程的工具。 Audience Manager目标功能位于&#x200B;*受众数据>目标*&#x200B;中。 要开始操作，请单击&#x200B;**[!UICONTROL Add New Destination]**&#x200B;并按照以下步骤操作。

### 步骤1：基本信息

要完成[!UICONTROL Basic Information]部分，请执行以下操作：

1. 命名目标。
1. 从[!UICONTROL Type]下拉列表中选择&#x200B;**[!UICONTROL "Cookie"]**。
1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;并转到[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

### 步骤2：配置信息

要完成[!UICONTROL Configuration]部分，请执行以下操作：

1. **Cookie名称：**&#x200B;为您的Cookie提供一个简短的、描述性的名称。
1. **Cookie域：**&#x200B;留空可在用户当前页面的域中设置Cookie。 如果要指定域，请为名称添加句点，如`.mydomain.com`。
1. 在[!UICONTROL Data Format]部分中选择一个键选项。
1. 如果您的键使用具有序列化值的数据，请选择&#x200B;**[!UICONTROL Serialize]**&#x200B;控件并指定序列分隔符（用于分隔序列化值的字符）。
1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;并展开[!UICONTROL Segment Mappings]部分。

### 步骤3：区段映射

要将区段添加到Cookie目标，请执行以下操作：

1. **查找区段：** [!UICONTROL Segment Mappings]部分提供两种搜索工具来帮助查找区段。 要查找段，请执行以下操作：
   * 选项1：开始在搜索字段中键入区段名称。 字段会根据文本自动更新。 找到要使用的区段后，请单击&#x200B;**[!UICONTROL Add]**。
   * 选项2：单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;打开一个窗口，允许您按名称或存储位置浏览区段。 完成后单击&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **添加映射：**&#x200B;在映射弹出窗口中，在映射字段中输入区段ID并单击&#x200B;**[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**。

## OAS设置 {#oas-code-setup}

修改[!DNL OAS]设置以使用Audience Manager区段数据。

<!-- aam-oas-code.xml -->

设置[!DNL OAS]

* 在网站上安装[!UICONTROL DIL]代码。
* 在Audience Manager中创建OAS作为Cookie目标。
* 将`get_aamCookie`函数放在页面顶部，最好放在`<head>`代码块中。 `get_aamCookie`代码在[此处](../../features/destinations/get-aam-cookie-code.md)可用。
* 修改广告标记以调用`get_aamCookie`函数，并包含您在设置[!DNL OAS]目标时提供的Cookie名称。 例如，如果您为Cookie `test_cookie`命名，则广告标记应调用`get_aamCookie`并引用Cookie名称。
* 您的广告标记可能与以下示例类似。

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

切记要包括`u=`变量。 它包含广告调用期间传入的实际唯一用户ID ([!UICONTROL UUID])。
