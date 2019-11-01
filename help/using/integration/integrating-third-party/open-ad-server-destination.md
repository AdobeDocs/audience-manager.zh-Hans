---
description: 将Open Ad server设置为目标，然后将Audience manager数据发送到该平台。
seo-description: 将Open Ad server设置为目标，然后将Audience manager数据发送到该平台。
seo-title: OAS作为Audience Manager目标
solution: Audience Manager
title: OAS作为Audience Manager目标
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# OAS作为Audience Manager目标 {#oas-as-an-audience-manager-destination}

将Audience manager设 [!DNL Open Ad Server] 置为目标，并将Audience manager数据发送到该平台。

## OAS目标要求 {#oas-requirements}

代码放置标准、支持的键值格式、报告以及发送到的区段数据类型 [!DNL OAS]。

<!-- aam-oas-requirements.xml -->

此目标类型需要：

* **[!UICONTROL DIL]** :应在 [!UICONTROL Data Integration Library] 您的库存中部署代码。 [!UICONTROL DIL] 有助于消除为数据收集、集成、读取Cookie值和恢复页面数据而编写特殊代码的需求。
* **`get_aamCookie`** 函数：捕获Audience Manager用户ID和Cookie数据的代码。 将 [此代码放在页面顶部](../../features/destinations/get-aam-cookie-code.md) ，或放在代码块 `<head>` 中。
* **** 将交付日志发送到Audience Manager:如果您需要区段交付报告（可选），请向Audience Manager提供包含印象级交付数据的每日日志。 数据可以采用原始格式，但每个记录必须包含Audience Manager [!UICONTROL UUID]。 Audience manager可以通过获取或接收这些 [!DNL FTP]。

### Cookie格式和键值数据

Audience manager可以按如下方式将区段数据发送到浏览器Cookie:

* 单键(`x=1&x=2`);
* 多键(`x=1&x=2&y=3&y=4`);
* 序列化值(`x=1,2,3`);
* 用于分隔各键值对的标准值分隔符。

### 只有符合条件的区段才会发送到OAS

传入的数据量取决于 [!DNL OAS] 特定用户符合的区段数。 例如，假设您设置了100个Audience manager区段。 如果一个网站访问者有资格获得其中五个，那么只有这五个区段被发送到OAS（不是全部100个）。

>[!MORELIKETHIS]
>
>* [get_aamCookie代码](../../features/destinations/get-aam-cookie-code.md)
>* [说明的键值对](../../reference/key-value-pairs-explained.md)


## 创建OAS目标 {#oas-dest-setup}

在Audience manager中创建基于Cookie [!DNL OAS] 的目标。

<!-- aam-oas-destination-setup.xml -->

在Audience manager中，目 *标是* 任何其他系统(广告服务器 [!DNL DSP]、广告网络等)要与之共享数据。 [!UICONTROL Destination Builder] 提供了用于创建和管理这些数据交付流程的工具。 Audience manager目标功能位于“受众数据”&gt;“ *目标”中*。 要开始，请单击 **[!UICONTROL Add New Destination]** 并按照以下步骤操作。

### 第1步： 基本信息

要完成此部 [!UICONTROL Basic Information] 分，请执行以下操作：

1. 命名目标。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 单 **[!UICONTROL Save]** 击并转到和部 [!UICONTROL Configuration] 分 [!UICONTROL Segment Mappings] 。

### 第2步：配置信息

要完成此部 [!UICONTROL Configuration] 分，请执行以下操作：

1. **** Cookie名称：为您的cookie提供一个简短的描述性名称。
1. **** Cookie域：留空可在用户当前页面的域中设置Cookie。 如果要指定域，请在名称前加上类似句号 `.mydomain.com`。
1. 在部分中选择一个键选 [!UICONTROL Data Format] 项。
1. 如果您的密钥使用具有序列化值的数据，请选 **[!UICONTROL Serialize]** 择控件并指定序列分隔符（分隔序列化值的字符）。
1. 单击 **[!UICONTROL Save]** 并展开该 [!UICONTROL Segment Mappings] 部分。

### 第3步：区段映射

要向Cookie目标添加区段，请执行以下操作：

1. **** 查找区段：该部 [!UICONTROL Segment Mappings] 分提供了两种搜索工具，可帮助查找区段。 要查找区段，请执行以下操作：
   * 选项1:开始在搜索字段中键入区段名称。 字段会根据文本自动更新。 找到 **[!UICONTROL Add]** 要使用的区段后，单击。
   * 选项2:单击 **[!UICONTROL Browse All Segments]** 以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 Click **[!UICONTROL Add Selected Segments]** when done.
1. **** 添加映射：在映射弹出窗口中，在映射字段中输入区段ID，然后单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**.

## OAS设置 {#oas-code-setup}

修改 [!DNL OAS] 设置以使用Audience manager细分数据。

<!-- aam-oas-code.xml -->

设置 [!DNL OAS]

* 在您 [!UICONTROL DIL] 的站点中安装代码。
* 在Audience manager中将OAS创建为Cookie目标。
* 将函 `get_aamCookie` 数放在页面顶部，最好放在代码块 `<head>` 中。 此 `get_aamCookie` 处提供该 [代码](../../features/destinations/get-aam-cookie-code.md)。
* 修改广告标记以调用函 `get_aamCookie` 数并包含您在设置目标时提供的Cookie名 [!DNL OAS] 称。 例如，如果您命名了cookie，则 `test_cookie`广告标记应调用并引 `get_aamCookie` 用cookie名称。
* 您的广告标记可能与以下示例类似。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

请记住包含该 `u=` 变量。 它包含在广告呼叫过程中传[!UICONTROL UUID]入的实际唯一用户ID()。
