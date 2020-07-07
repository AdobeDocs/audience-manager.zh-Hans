---
description: 您可以通过客户端或服务器端集成将符合条件的区段发送到Google Ad Manager。 下面列出了两种方法的要求和相关信息。
seo-description: 您可以通过客户端或服务器端集成将符合条件的区段发送到Google Ad Manager。 下面列出了两种方法的要求和相关信息。
seo-title: 使用Google Publisher标记(GPT)将区段发送到Google Ad Manager的要求和方法
solution: Audience Manager
title: 使用Google Publisher标记(GPT)将区段发送到Google Ad Manager的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以通过客户端 [!DNL Google Ad Manager] 或服务器端集成将符合条件的区段发送到（以前称为DFP）。 下面列出了两种方法的要求和相关信息。

## 客户端集成 {#client-side-integration}

对于客户端集成，您需要以Audience Manager [!DNL GPT] 设置目标。 要设置为Audience Manager目标时，请考 [!DNL GPT] 虑以下几点：

* **添加[!UICONTROL DIL]:** 在 [!UICONTROL Data Integration Library (DIL)] 要目标的所有页面上部署代码。 [!UICONTROL DIL] 将Audience Manager区段数据和用户ID写入用于定位 [!DNL GPT] 的cookie。

* **创建[!UICONTROL Cookie Destination]:** [!DNL GPT] 必须在Audience Manager中设置为基于cookie的目标。

* **实施Cookie检查代码：** 将API方 [!DNL GPT] 法包含在我 `.setTargeting` 们推荐的Cookie [检查代码中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。 此代码通过在调用方法之前查找有效的AAM cookie，帮助 `.setTargeting` 防止错误。

* **添加函`AamGpt`数：** 该代 `AamGpt` 码从Audience Managercookies中捕获数据并将其发送 [!DNL GPT]到。 将Google [Publisher标记的](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) Audience Manager代码 `AamGpt`( `<head>` )放在页面顶部或代码块中。

   >[!NOTE]
   >
   >如果您 `AamGpt` 使用自己的代码读取Audience Managercookie数据，则不需要该函数。

* **将投放日志发送给Audience Manager:** 如果您需要区段投放报告（可选），请为Audience Manager提供包含印象级投放数据的每日日志。 数据可以采用原始格式，但每个记录必须包含Audience Manager `UUID`。 Audience Manager可以通过获取或接收这些 [!DNL FTP]。

### 只有合格的区段才会发送到GPT

传入的数据量取决于 [!DNL GPT] 特定用户符合的区段数。 例如，假设您设置100个Audience Manager段。 如果网站访客有资格获得其中五个，则只有这五个区段会被发送 [!DNL GPT] 到（不是全部100个）。

>[!NOTE]
>
>您可以发送的键值数没有限制，但请 [!DNL Google] 求 [!DNL URL] 对可接受的字符数有限制。 请参 [阅使用GPT设置定位和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)。

## 服务器端集成 {#server-side-integration}

如果您希望使用设置服务器端集成，请与Audience Manager顾问或客户服务 [!DNL Google Ad Manager]部联系 [!DNL GPT]。 您需要提供您的帐 [!DNL Google Ad Manager] 户网络ID和受众链接ID。

>[!IMPORTANT]
>
>如果您的网页正在运 [行加速媒体页](https://www.ampproject.org/) ([!DNL AMP])库，则必须使用与Audience Manager的服务器端集成。 如果您处于 [!DNL AMP] 并且与客户端集成 [!DNL AMP]，则必须迁移到服务器端集成。 请联系您的Audience Manager顾问或客户关怀来讨论迁移。

>[!MORELIKETHIS]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

