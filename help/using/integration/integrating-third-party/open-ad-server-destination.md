---
description: 将Open Ad Server设置为目标，并将Audience Manager数据发送到该平台。
seo-description: 将Open Ad Server设置为目标，并将Audience Manager数据发送到该平台。
seo-title: OAS 作为 Audience Manager 目标
solution: Audience Manager
title: OAS 作为 Audience Manager 目标
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# OAS 作为 Audience Manager 目标 {#oas-as-an-audience-manager-destination}

设置 [!DNL Open Ad Server] 为目标并将Audience Manager数据发送到该平台。

## OAS目标要求 {#oas-requirements}

代码放置标准、支持的键值格式、报告以及发送到的段数据类型 [!DNL OAS]。

<!-- aam-oas-requirements.xml -->

此目标类型需要：

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]应在您的库存中部署代码。[!UICONTROL DIL]有助于消除为数据收集、集成、读取cookie值和恢复页面数据编写特殊代码的需求。
* **`get_aamCookie`函数：**捕获Audience Manager用户ID和Cookie数据的代码。 将[此代码放](../../features/destinations/get-aam-cookie-code.md)在页面顶部或代码块`<head>`中。
* **将投放日志发送给Audience Manager:** 如果您需要区段投放报告（可选），请为Audience Manager提供包含印象级投放数据的每日日志。 数据可以采用原始格式，但每个记录必须包含Audience Manager [!UICONTROL UUID]。 Audience Manager可以通过获取或接收这些 [!DNL FTP]。

### Cookie格式和密钥值数据

Audience Manager可以按如下方式将区段数据发送到浏览器cookie:

* 单键(`x=1&x=2`);
* 多键(`x=1&x=2&y=3&y=4`);
* 序列化值(`x=1,2,3`);
* 用于分隔各个键值对的标准值分隔符。

### 只有合格的区段会发送到OAS

传入的数据量取决于 [!DNL OAS] 特定用户符合的区段数量。 例如，假设您设置100个Audience Manager段。 如果一个网站访客有资格获得其中五个，那么只有这五个区段被发送到OAS（不是全部100个）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 代码](../../features/destinations/get-aam-cookie-code.md)
>* [键值对说明](../../reference/key-value-pairs-explained.md)


## 创建OAS目标 {#oas-dest-setup}

为Audience Manager创建基于cookie的 [!DNL OAS] 目标。

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供了用于创建和管理这些数据投放流程的工具。 Audience Manager目标功能位于“受众 *数据”>“目标”中*。 要开始，请单 **[!UICONTROL Add New Destination]** 击并按照以下步骤操作。

### 第1步： 基本信息

要完成该部 [!UICONTROL Basic Information] 分：

1. 命名目标。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 单 **[!UICONTROL Save]** 击并转到和 [!UICONTROL Configuration] 部 [!UICONTROL Segment Mappings] 分。

### 第2步： 配置信息

要完成该部 [!UICONTROL Configuration] 分：

1. **Cookie名称：** 为您的cookie提供一个简短的描述性名称。
1. **Cookie域：** 留空可在用户当前页面的域中设置Cookie。 如果要指定域，请在名称前加上类似句点 `.mydomain.com`。
1. 在部分中选择一个键 [!UICONTROL Data Format] 选项。
1. 如果您的密钥使用具有序列化值的数据，请选 **[!UICONTROL Serialize]** 择控件并指定序列分隔符（用于分隔序列化值的字符）。
1. 单击 **[!UICONTROL Save]** 并展开 [!UICONTROL Segment Mappings] 部分。

### 第3步： 区段映射

要向Cookie目标添加区段，请执行以下操作：

1. **查找区段：** 此部 [!UICONTROL Segment Mappings] 分提供两种搜索工具，帮助查找区段。 要查找区段，请执行以下操作：
   * 选项1: 开始在搜索字段中键入区段名称。 字段会根据文本自动更新。 找到 **[!UICONTROL Add]** 要使用的区段后，单击。
   * 选项2: 单击 **[!UICONTROL Browse All Segments]** 以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 完成 **[!UICONTROL Add Selected Segments]** 后单击。
1. **添加映射：** 在映射弹出窗口中，在映射字段中输入段ID并单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**.

## OAS设置 {#oas-code-setup}

修改 [!DNL OAS] 设置以处理Audience Manager段数据。

<!-- aam-oas-code.xml -->

设置 [!DNL OAS]

* 在您 [!UICONTROL DIL] 的网站上安装代码。
* 在Audience Manager中创建OAS作为Cookie目标。
* 将函 `get_aamCookie` 数放在页面顶部，最好放在代码块 `<head>` 中。 此 `get_aamCookie` 处提供 [代码](../../features/destinations/get-aam-cookie-code.md)。
* 修改广告标记以调用 `get_aamCookie` 函数并包含您在设置目标时提供的Cookie名 [!DNL OAS] 称。 例如，如果您命名了cookie, `test_cookie`则广告标记应调用并引 `get_aamCookie` 用cookie名称。
* 您的广告标签可能与以下示例类似。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

请记住要包含 `u=` 变量。 它包含广告呼叫期间[!UICONTROL UUID]传入的实际唯一用户ID。
