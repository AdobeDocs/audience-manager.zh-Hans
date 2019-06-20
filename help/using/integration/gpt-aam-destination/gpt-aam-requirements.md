---
description: 您可以通过客户端或通过服务器端集成将合格的区段发送到DFP。以下列出了有关两种方法的要求及相关信息。
seo-description: 您可以通过客户端或通过服务器端集成将合格的区段发送到DFP。以下列出了有关两种方法的要求及相关信息。
seo-title: 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法
solution: Audience Manager
title: 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-3d8e677790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. 以下列出了有关两种方法的要求及相关信息。

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **添加[!UICONTROL DIL]：** 在要定位的所有页面上部署 [!UICONTROL Data Integration Library (DIL)] 代码。[!UICONTROL DIL] 将Audience Manager细分数据和用户ID写入用于定位的 [!DNL GPT] cookies。

* **创建[!UICONTROL Cookie Destination]一个：**[!DNL GPT] 必须在Audience Manager中设置为基于cookie的目标。

* **实施Cookie检查代码：** 将 [!DNL GPT]`.setTargeting` API方法封装在我们建议 [的cookie检查代码](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)中。This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **添加`AamGpt`函数：**`AamGpt` 代码捕获Audience Manager cookies中的数据并将其发送到 [!DNL GPT]。Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **将交付日志发送到Audience Manager：** 如果您需要区段交付报告(可选)，请向Audience Manager提供包含印象级交付数据的每日日志。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### 只有合格的区段才被发送到GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. 例如，假设您设置100个Audience Manager细分。If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You&#39;ll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. 请与Audience Manager顾问或客户关怀部门联系，讨论迁移。

>[!MORE_ LIKE_ This]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

