---
description: 设置OpenX作为目标，并将Audience Manager区段数据发送到该平台。
seo-description: 设置OpenX作为目标，并将Audience Manager区段数据发送到该平台。
seo-title: OpenX作为Audience Manager目标
solution: Audience Manager
title: OpenX作为Audience Manager目标
uuid: 5e86ba73-281c-403b-af06-64a1 d427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>仅用于现场广告服务器定位。

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]：**[!UICONTROL Data Integration Library] 应在您的网站上部署代码。[!UICONTROL DIL] 帮助消除了为数据收集、集成、读取cookie值和恢复页面数据编写特殊代码的需求。
* **`get_aamCookie`函数：** 捕获Audience Manager用户ID和cookie数据的代码。Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **将交付日志发送到Audience Manager：** 如果您需要区段交付报告(可选)，请向Audience Manager提供包含印象级交付数据的每日日志。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### 密钥值数据：格式要求

Audience Manager以关键值对的形式发送数据。根据以下规范创建键值对：

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* 键名称不应包含特殊字符，如重音符号、标点符号或其他符号。

### 只有合格的区段被发送到OpenX

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. 例如，假设设置100个受众管理细分。If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 您希望与之共享数据的数据。[!UICONTROL Destination Builder] 提供允许您创建和管理这些数据交付流程的工具。Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### 步骤1：基本信息

To complete the [!UICONTROL Basic Information] section:

1. 命名目标。
1. **[!UICONTROL "Cookie"]** 从 [!UICONTROL Type] 下拉列表中进行选择。
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### 步骤2：配置信息

To complete the [!UICONTROL Configuration] section:

1. **Cookie名称：** 为您的cookie提供简短的描述性名称。
1. **Cookie域：** 留空可在用户当前页面的域中设置cookie。If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### 步骤3：细分映射

要将区段添加到cookie目标，请执行以下操作：

1. **查找区段：**[!UICONTROL Segment Mappings] 该部分提供了两个搜索工具来帮助查找区段。要查找区段，请执行以下操作：
   * 选项1：开始在搜索字段中键入区段名称。字段会根据文本自动更新。Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **添加映射：** 在映射弹出窗口中，在映射字段中输入区段ID，然后单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**.

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

[!DNL OpenX]设置：

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` 此处提供了代码 [](../../features/destinations/get-aam-cookie-code.md)。
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* 您的广告标签可能类似于下面的示例。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

完全成形的广告调用可能类似于：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
