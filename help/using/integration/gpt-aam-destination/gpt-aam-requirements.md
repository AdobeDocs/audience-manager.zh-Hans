---
description: 您可以通过客户端或服务器端集成将符合条件的区段发送到Google Ad Manager。 下面列出了有关这两种方法的要求和相关信息。
seo-description: 您可以通过客户端或服务器端集成将符合条件的区段发送到Google Ad Manager。 下面列出了有关这两种方法的要求和相关信息。
seo-title: 使用Google Publisher Tags(GPT)将区段发送到Google Ad Manager的要求和方法
solution: Audience Manager
title: 使用Google Publisher Tags(GPT)将区段发送到Google Ad Manager的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: 第三方集成
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 使用Google Publisher Tags(GPT){#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}将区段发送到Google Ad Manager的要求和方法

您可以通过客户端或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]（以前称为DFP）。 下面列出了有关这两种方法的要求和相关信息。

## 客户端集成{#client-side-integration}

对于客户端集成，您需要在Audience Manager中设置[!DNL GPT]目标。 如果要将[!DNL GPT]设置为Audience Manager目标，请考虑以下几点：

* **添 [!UICONTROL DIL]加：** 在 [!UICONTROL Data Integration Library (DIL)] 要定位的所有页面上部署代码。[!UICONTROL DIL] 将Audience Manager区段数据和用户ID写入由用于定位 [!DNL GPT] 的Cookie。

* **创建 [!UICONTROL Cookie Destination]:** [!DNL GPT] 必须设置为Audience Manager中基于Cookie的目标。

* **实施Cookie检查代码：** 将API方法 [!DNL GPT] `.setTargeting` 包含在我们推荐的 [Cookie检查代码中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。此代码可在调用`.setTargeting`方法之前查找有效的AAM Cookie，从而帮助防止出现错误。

* **添加函 `AamGpt` 数：** 代码从 `AamGpt` Audience ManagerCookie中捕获数据并将其发送 [!DNL GPT]到。将Google Publisher Tags的[Audience Manager代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)(`AamGpt`)放在页面顶部或`<head>`代码块内。

   >[!NOTE]
   >
   >如果您使用自己的代码读取Audience ManagerCookie数据，则不需要`AamGpt`函数。

* **将投放日志发送到Audience Manager:** 如果您想要区段投放报告（可选），请为Audience Manager提供包含展示级别投放数据的每日日志。数据可以采用原始格式，但每个记录必须包含Audience Manager`UUID`。 Audience Manager可以通过[!DNL FTP]接收这些文件。

### 仅将符合条件的区段发送到GPT

传递到[!DNL GPT]的数据量取决于特定用户符合的区段数量。 例如，假设您设置了100个Audience Manager区段。 如果网站访客符合其中5个区段的条件，则只有这5个区段会发送到[!DNL GPT]（不是全部100个）。

>[!NOTE]
>
>您可以发送的键值数量没有限制，但[!DNL Google]请求[!DNL URL]对它可以接受的字符数有限制。 请参阅[使用GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)设置定位和大小。

## 服务器端集成{#server-side-integration}

如果要使用[!DNL GPT]设置与[!DNL Google Ad Manager]的服务器端集成，请咨询您的Audience Manager顾问或客户关怀团队。 您需要提供[!DNL Google Ad Manager]帐户网络ID和受众链接ID。

>[!IMPORTANT]
>
>如果您的网页运行的是[Accelerated Media Pages](https://www.ampproject.org/)([!DNL AMP])库，则必须将服务器端集成与Audience Manager结合使用。 如果您位于[!DNL AMP]上，并且与[!DNL AMP]具有客户端集成，则必须迁移到服务器端集成。 请联系您的Audience Manager顾问或客户关怀团队，以讨论迁移问题。

>[!MORELIKETHIS]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

