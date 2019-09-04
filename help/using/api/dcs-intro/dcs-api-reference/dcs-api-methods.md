---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: 使用GET或POST方法将数据发送到DCS API。
seo-title: DCS API方法
solution: Audience Manager
title: DCS API方法
uuid: e407458-11d4-4342-a84 a-512afa5 fc5 fc183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# DCS API方法 {#dcs-api-methods}

将数据发送到 [!UICONTROL DCS][!DNL API] 使用 `GET` 或 `POST` 方法。

您可以使用任一 [!UICONTROL DCS]`GET` 或 `POST` 方法将数据发送到。使用 [curl](https://curl.haxx.se/)查看下面的示例调用。在所有三个范例调用中，我们将添加信号 `c_likes = famous popstar` 和 `c_loves = famous actress` 设备配置文件 `12345678901234567890123456789012345678`。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 使用此方法将数据发送到占位 [!UICONTROL DCS] 符时，替换占位符的真实值。

## 通过GET发送数据 {#send-data-via-get}

请注意 `GET` ，调用的最大允许大小为8K。

<pre><code>curl -i“<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>”</code></pre>

## 通过POST发送数据 {#send-data-via-post}

请注意使用该 `POST` 方法发送数据的要求：

* 允许的最大大小为32K。
* 将内容类型设置为 `application/x-www-form-urlencoded`。

### 示例调用

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
