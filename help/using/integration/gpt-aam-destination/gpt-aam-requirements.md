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


# 使用Google Publisher标记(GPT){#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}将区段发送到Google Ad Manager的要求和方法

您可以通过客户端或通过服务器端集成将限定的区段发送到[!DNL Google Ad Manager]（以前称为DFP）。 下面列出了两种方法的要求和相关信息。

## 客户端集成{#client-side-integration}

对于客户端集成，您需要以Audience Manager设置[!DNL GPT]目标。 如果要将[!DNL GPT]设置为Audience Manager目标，请考虑以下几点：

* **添 [!UICONTROL DIL]加：** 在 [!UICONTROL Data Integration Library (DIL)] 要目标的所有页面上部署代码。[!UICONTROL DIL] 将Audience Manager区段数据和用户ID写入cookie，以供 [!DNL GPT] 定位使用。

* **在Audience Manager [!UICONTROL Cookie Destination]中** [!DNL GPT] 创建：必须设置为基于cookie的目标。

* **实施Cookie检查代码：** 将API [!DNL GPT] `.setTargeting` 方法包含在我们推荐 [的Cookie检查代码中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。此代码在调用`.setTargeting`方法之前查找有效的AAM cookie，有助于防止出现错误。

* **添加函 `AamGpt` 数：** 代 `AamGpt` 码从Audience ManagerCookie中捕获数据并发送到 [!DNL GPT]。将[Google Publisher标记](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)(`AamGpt`)的Audience Manager代码放在页面顶部或`<head>`代码块中。

   >[!NOTE]
   >
   >如果您使用自己的代码读取Audience Managercookie数据，则不需要`AamGpt`函数。

* **将投放日志发送给Audience Manager** ：如果您想要区段投放报告（可选），请为Audience Manager提供包含印象级投放数据的每日日志。数据可以采用原始格式，但每个记录必须包含Audience Manager`UUID`。 Audience Manager可以通过[!DNL FTP]接收或接收这些文件。

### 只有合格的区段才会发送到GPT

传入[!DNL GPT]的数据量取决于特定用户符合的区段数。 例如，假设您设置100个Audience Manager段。 如果一个站点访客有资格获得其中五个，则只有这五个区段会被发送到[!DNL GPT]（不是全部100）。

>[!NOTE]
>
>您可以发送的键值数没有限制，但[!DNL Google]请求[!DNL URL]对它可以接受的字符数有限制。 请参阅[使用GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)设置定位和大小。

## 服务器端集成{#server-side-integration}

如果要使用[!DNL GPT]设置与[!DNL Google Ad Manager]的服务器端集成，请与Audience Manager顾问或客户服务部联系。 您需要提供[!DNL Google Ad Manager]帐户网络ID和受众链接ID。

>[!IMPORTANT]
>
>如果您的网页正在运行[加速媒体页](https://www.ampproject.org/)([!DNL AMP])库，则必须将服务器端集成与Audience Manager结合使用。 如果您位于[!DNL AMP]上，并且与[!DNL AMP]有客户端集成，则必须迁移到服务器端集成。 请联系您的Audience Manager顾问或客户关怀来讨论迁移。

>[!MORELIKETHIS]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

