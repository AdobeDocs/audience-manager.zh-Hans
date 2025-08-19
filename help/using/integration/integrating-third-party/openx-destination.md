---
description: 将OpenX设置为目标，并将Audience Manager区段数据发送到该平台。
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX作为Audience Manager目标
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX作为Audience Manager目标{#openx-as-an-audience-manager-destination}

将[!DNL OpenX]设置为目标并将Audience Manager区段数据发送到该平台。

>[!NOTE]
>
>仅用于现场广告服务器定位。

## OpenX目标要求 {#openx-requirements}

代码放置标准、支持的键值格式、报表以及发送到[!DNL OpenX]的区段数据类型。

<!-- aam-openx-requirements.xml -->

在将[!DNL OpenX]设置为Audience Manager目标之前，请查看以下内容：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library]代码应部署在您的网站上。 [!UICONTROL DIL]有助于消除为数据收集、集成、读取Cookie值和恢复页面数据编写特殊代码的需要。
* **`get_aamCookie`函数：**&#x200B;捕获Audience Manager用户ID和Cookie数据的代码。 将[此代码](../../features/destinations/get-aam-cookie-code.md)放在页面顶部或`<head>`代码块内。
* **将投放日志发送到Audience Manager：**&#x200B;如果您需要区段投放报告（可选），请为Audience Manager提供包含展示级别投放数据的每日日志。 数据可以是原始格式，但每个记录都必须包含Audience Manager `UUID`。 Audience Manager可以通过[!DNL FTP]收取或接收这些邮件。

### 键值数据：格式要求

Audience Manager以键值对的形式发送数据。 根据以下规范创建键值对：

* 带有`c.`的前缀键（例如，`c.color`或`c.price`）。
* 用逗号分隔附加到单个键的序列化值（例如，`c.color = red, green, blue`）。
* 使用&amp;符号（例如，`c.color=red & c.price = 100 & c.condition = new`）分隔多个键值对。
* 密钥名称不应包含特殊字符，如重音符号和标点符号或其他符号。

### 只有符合条件的区段才会发送到OpenX

传递到[!DNL OpenX]的数据量取决于特定用户符合条件的区段数。 例如，假设您设置了100个Audience Manager区段。 如果网站访客符合其中五个区段的条件，则只有这五个区段会发送到[!DNL OpenX]（并非全部100个）。

## 创建OpenX目标 {#openx-destination}

在Audience Manager中为[!DNL OpenX]创建Cookie目标。

<!-- aam-openx-destination.xml -->

在Audience Manager中，*目标*&#x200B;是要与其共享数据的任何其他系统（广告服务器、[!DNL DSP]、广告网络等）。 [!UICONTROL Destination Builder]提供了用于创建和管理这些数据传输流程的工具。 Audience Manager目标功能位于&#x200B;*受众数据>目标*&#x200B;中。 要开始操作，请单击&#x200B;**[!UICONTROL Add New Destination]**&#x200B;并按照以下步骤操作。

### 步骤1：基本信息

要完成[!UICONTROL Basic Information]部分，请执行以下操作：

1. 命名目标。
1. 从&#x200B;**[!UICONTROL "Cookie"]**&#x200B;下拉列表中选择[!UICONTROL Type]。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并转到[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

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

## OpenX设置 {#openx-code-setup}

修改[!DNL OpenX]设置以使用Audience Manager区段数据。

<!-- aam-openx-code.xml -->

要设置[!DNL OpenX]：

* 在网站上安装[!UICONTROL DIL]代码。
* 在Audience Manager中创建[!DNL OpenX]作为Cookie目标。
* 将`get_aamCookie`函数放在页面顶部，最好放在`<head>`代码块中。 `get_aamCookie`代码在[此处](../../features/destinations/get-aam-cookie-code.md)可用。
* 修改广告标记以调用`get_aamCookie`函数，并包含您在设置[!DNL OpenX]目标时提供的Cookie名称。 例如，如果您为Cookie `test_cookie`命名，则广告标记应调用`get_aamCookie`并引用Cookie名称。
* 您的广告标记可能与以下示例类似。

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

切记要包括`xid=` 。 它包含广告调用期间传入的实际唯一用户ID ([!UICONTROL UUID])。

完整形式的广告调用可能类似于以下内容：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
