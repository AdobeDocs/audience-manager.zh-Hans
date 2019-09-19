---
description: 您可以通过客户端或服务器端集成将合格的区段发送到DFP。 下面列出了两种方法的要求和相关信息。
seo-description: 您可以通过客户端或服务器端集成将合格的区段发送到DFP。 下面列出了两种方法的要求和相关信息。
seo-title: 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法
solution: Audience Manager
title: 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e67790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以通过客户端或 [!DNL DFP] 服务器端集成将符合条件的区段发送到。 下面列出了两种方法的要求和相关信息。

## 客户端集成 {#client-side-integration}

要实现客户端集成，您需要在Audience manager中设 [!DNL GPT] 置目标。 当您要设置为Audience Manager目标时，请考 [!DNL GPT] 虑以下几点：

* **[!UICONTROL DIL]添加**:在所 [!UICONTROL Data Integration Library (DIL)] 有要定位的页面上部署代码。 [!UICONTROL DIL] 将Audience manager细分数据和用户ID写入Cookie中，供定位使 [!DNL GPT] 用。

* **[!UICONTROL Cookie Destination]创建**:必须 [!DNL GPT] 在Audience manager中设置为基于cookie的目标。

* **** 实施Cookie检查代码：将 [!DNL GPT] API方法包含在我们推荐 `.setTargeting` 的cookie检查代码中 [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。 此代码通过在调用方法之前查找有效的AAM cookies，帮助 `.setTargeting` 防止错误。

* **`AamGpt`添加函** 数：该代 `AamGpt` 码从Audience Manager Cookies捕获数据并将其发送到 [!DNL GPT]。 将Google [Publisher标记的Audience Manager代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)放在页面顶部或代码 `<head>` 块中。

   >[!NOTE]
   >
   >如果 `AamGpt` 您使用自己的代码读取Audience Manager cookie数据，则该函数不是必需的。

* **** 将交付日志发送到Audience Manager:如果您需要区段交付报告（可选），请向Audience Manager提供包含印象级交付数据的每日日志。 数据可以采用原始格式，但每个记录必须包含Audience Manager `UUID`。 Audience manager可以通过获取或接收这些 [!DNL FTP]。

### 只有合格的区段会发送到GPT

传入的数据量取决于特 [!DNL GPT] 定用户符合的区段数。 例如，假设您设置了100个Audience manager区段。 如果某个网站访客有资格获得其中5个，则只有这5个区段会被发送 [!DNL GPT] 到（而非全部100个）。

>[!NOTE]
>
>您可以发送的键值数量没有限制，但请 [!DNL Google] 求 [!DNL URL] 对可接受的字符数有限制。 请参 [阅使用GPT设置定位和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712)。

## 服务器端集成 {#server-side-integration}

如果您希望使用设置服务器端集成，请咨询Audience manager顾问或客户关怀 [!DNL DFP]团队 [!DNL GPT]。 您需要提供帐户网 [!DNL DFP] 络ID和受众链接ID。

>[!IMPORTANT]
>
>如果您的网页正在运行 [加速媒体页面](https://www.ampproject.org/) ([!DNL AMP])库，则必须使用与Audience manager的服务器端集成。 如果您使用并 [!DNL AMP] 且与客户端集成，则必 [!DNL AMP]须迁移到服务器端集成。 请联系您的Audience manager顾问或客户关怀来讨论迁移问题。

>[!MORE_LIKE_THIS]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

