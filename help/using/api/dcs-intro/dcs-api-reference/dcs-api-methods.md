---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: 使用GET或POST方法将数据发送到DCS API。
seo-title: DCS API方法
solution: Audience Manager
title: DCS API方法
uuid: e407458-11d4-4342-a84 a-512afa5 fc5 fc183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS API Methods {#dcs-api-methods}

Send data to the [!UICONTROL DCS] [!DNL API] using `GET` or `POST` methods.

You can send data to the [!UICONTROL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Send Data via GET {#send-data-via-get}

Note that the maximum allowed size for `GET` calls is 8K.

<pre><code>curl -i“<i>yourcompany.demdex.net/event</i>？
d_uuid=<i>12345678901234567890123456789012345678</i>&amp;d_rtbd=json&amp;<i>c_likes=famous%20popstar</i>&amp;<i>c_loves=famous%20actress</i>"
</code></pre>

## Send Data via POST {#send-data-via-post}

Note the requirements for sending data using the `POST` method:

* 允许的最大大小为32K。
* Set the content type to `application/x-www-form-urlencoded`.

### 示例调用

<pre><code>curl -X POST\
https://yourcompany.demdex.net/event<i></i>\
-H“content-type：application/x-www-form-urlencoded'\
-d'<i>c_ limes=著名的%20popstar</i>&amp;<i>c_ los= lighted%20actreset</i>&amp;<i>d_ uuid=1234567780123456787040367787803778</i>'</code>
</pre>

<pre><code>curl -X POST\
https://yourcompany.demdex.net/event<i></i>\
-H“content-type：application/x-www-form-urlencoded'\
-d'<i>c_ limes=著名的%20popstar</i>&amp; <i>c_ los= lighted%20actreset</i>&amp;<i>d_ uuid=1234567780123456787040367787803778</i>'</code>
</pre>
