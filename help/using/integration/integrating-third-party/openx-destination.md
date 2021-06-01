---
description: 将OpenX设置为目标，并将Audience Manager区段数据发送到该平台。
seo-description: 将OpenX设置为目标，并将Audience Manager区段数据发送到该平台。
seo-title: OpenX 作为 Audience Manager 目标
solution: Audience Manager
title: OpenX 作为 Audience Manager 目标
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: 第三方集成
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 3%

---

# OpenX 作为 Audience Manager 目标{#openx-as-an-audience-manager-destination}

将[!DNL OpenX]设置为目标，并将Audience Manager区段数据发送到该平台。

>[!NOTE]
>
>仅用于现场广告服务器定位。

## OpenX目标要求{#openx-requirements}

代码放置标准、支持的键值格式、报表以及发送到[!DNL OpenX]的区段数据类型。

<!-- aam-openx-requirements.xml -->

在将[!DNL OpenX]设置为Audience Manager目标之前，请查看以下内容：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 代码应部署在您的网站上。[!UICONTROL DIL] 有助于消除为数据收集、集成、读取Cookie值和恢复页面数据编写特殊代码的需求。
* **`get_aamCookie`函数：** 用于捕获Audience Manager用户ID和Cookie数据的代码。将[此代码](../../features/destinations/get-aam-cookie-code.md)置于页面顶部或`<head>`代码块内。
* **将投放日志发送到Audience Manager:** 如果您想要区段投放报告（可选），请为Audience Manager提供包含展示级别投放数据的每日日志。数据可以采用原始格式，但每个记录必须包含Audience Manager`UUID`。 Audience Manager可以通过[!DNL FTP]接收这些文件。

### 键值数据：格式要求

Audience Manager以键值对的形式发送数据。 根据以下规范创建键值对：

* 使用`c.`（例如`c.color`或`c.price`）进行前言。
* 用逗号分隔附加到单个键的序列化值（例如`c.color = red, green, blue`）。
* 使用与号分隔多个键值对（例如，`c.color=red & c.price = 100 & c.condition = new`）。
* 键名称不应包含特殊字符，如重音符号、标点符号或其他符号。

### 仅将符合条件的区段发送到OpenX

传递到[!DNL OpenX]的数据量取决于特定用户符合的区段数量。 例如，假设您设置了100个Audience Manager区段。 如果网站访客符合其中5个区段的条件，则只有这5个区段会发送到[!DNL OpenX]（不是全部100个）。

## 创建OpenX目标{#openx-destination}

在Audience Manager中为[!DNL OpenX]创建Cookie目标。

<!-- aam-openx-destination.xml -->

在Audience Manager中，*目标*&#x200B;是任何其他系统（广告服务器、[!DNL DSP]、广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供了用于创建和管理这些数据提交流程的工具。Audience Manager目标功能位于&#x200B;*受众数据>目标*&#x200B;中。 要开始配置，请单击&#x200B;**[!UICONTROL Add New Destination]**&#x200B;并按照以下步骤操作。

### 步骤1:基本信息

要完成[!UICONTROL Basic Information]部分，请执行以下操作：

1. 命名目标。
1. 从[!UICONTROL Type]下拉列表中选择&#x200B;**[!UICONTROL "Cookie"]**。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并转到[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

### 步骤2:配置信息

要完成[!UICONTROL Configuration]部分，请执行以下操作：

1. **Cookie名称：** 为您的Cookie提供一个简短的描述性名称。
1. **Cookie域：** 留空可在用户当前页面的域中设置Cookie。如果要指定域，请在名称前加上类似`.mydomain.com`的句点。
1. 在[!UICONTROL Data Format]部分选择键选项。
1. 如果您的键使用具有序列化值的数据，请选择&#x200B;**[!UICONTROL Serialize]**&#x200B;控件并指定序列分隔符（用于分隔序列化值的字符）。
1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;并展开[!UICONTROL Segment Mappings]部分。

### 步骤3:区段映射

要向Cookie目标添加区段，请执行以下操作：

1. **查找区段：** 部分提 [!UICONTROL Segment Mappings] 供了两个搜索工具来帮助查找区段。要查找区段，请执行以下操作：
   * 选项1:开始在搜索字段中键入区段名称。 字段会根据文本自动更新。 找到要使用的区段后，单击&#x200B;**[!UICONTROL Add]**。
   * 选项2:单击&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以打开一个窗口，通过该窗口可按名称或存储位置浏览区段。 完成后，单击&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **添加映射：** 在映射弹出窗口中，在映射字段中输入区段ID，然后单击 **[!UICONTROL Save]**。
1. 单击 **[!UICONTROL Done]**.

## OpenX安装程序{#openx-code-setup}

修改[!DNL OpenX]设置以处理Audience Manager区段数据。

<!-- aam-openx-code.xml -->

要设置[!DNL OpenX]，请执行以下操作：

* 在您的网站上安装[!UICONTROL DIL]代码。
* 在Audience Manager中创建[!DNL OpenX]作为Cookie目标。
* 将`get_aamCookie`函数放置在页面顶部，最好放在`<head>`代码块中。 `get_aamCookie`代码在[此处](../../features/destinations/get-aam-cookie-code.md)提供。
* 修改广告标记以调用`get_aamCookie`函数，并包含您在设置[!DNL OpenX]目标时提供的Cookie名称。 例如，如果您将Cookie命名为`test_cookie`，则广告标记应调用`get_aamCookie`并引用Cookie名称。
* 您的广告标记可能与以下示例类似。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

请记住包含`xid=` 。 它包含在广告调用期间传入的实际唯一用户ID([!UICONTROL UUID])。

格式完整的广告调用可能类似于以下内容：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
