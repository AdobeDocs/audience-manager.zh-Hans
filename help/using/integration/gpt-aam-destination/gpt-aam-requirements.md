---
description: 您可以通过客户端或服务器端集成，将符合条件的区段发送到Google Ad Manager。 下面列出了这两种方法的要求和相关信息。
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: 使用Google发布者标记(GPT)将区段发送到Google Ad Manager的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# 使用Google发布者标记(GPT)将区段发送到Google Ad Manager的要求和方法 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以通过客户端或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]（以前称为DFP）。 下面列出了这两种方法的要求和相关信息。

## 客户端集成 {#client-side-integration}

对于客户端集成，您需要在Audience Manager中设置[!DNL GPT]目标。 当您要将[!DNL GPT]设置为Audience Manager目标时，请考虑以下几点：

* **添加[!UICONTROL DIL]：**&#x200B;在要定位的所有页面上部署[!UICONTROL Data Integration Library (DIL)]代码。 [!UICONTROL DIL]将Audience Manager区段数据和用户ID写入[!DNL GPT]用于定位的Cookie。

* **创建[!UICONTROL Cookie Destination]：** [!DNL GPT]必须设置为Audience Manager中基于Cookie的目标。

* **实施Cookie检查代码：**&#x200B;将[!DNL GPT] `.setTargeting` API方法包装在我们推荐的[Cookie检查代码](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)中。 此代码有助于在调用`.setTargeting`方法之前查找有效的AAM Cookie，以防止出现错误。

* **添加`AamGpt`函数：** `AamGpt`代码从Audience ManagerCookie捕获数据并将其发送给[!DNL GPT]。 将Google发布者标记的[Audience Manager代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)放在页面顶部或`<head>`代码块内。

  >[!NOTE]
  >
  >如果您使用自己的代码读取Audience ManagerCookie数据，则不需要使用`AamGpt`函数。

* **将投放日志发送到Audience Manager：**&#x200B;如果您需要区段投放报告（可选），请为Audience Manager提供包含展示级别投放数据的每日日志。 数据可以是原始格式，但每个记录都必须包含Audience Manager`UUID`。 Audience Manager可以通过[!DNL FTP]收取或接收这些邮件。

### 只有符合条件的区段才会发送到GPT

传递到[!DNL GPT]的数据量取决于特定用户符合条件的区段数。 例如，假设您设置了100个Audience Manager区段。 如果网站访客符合其中五个区段的条件，则只有这五个区段会发送到[!DNL GPT]（并非全部100个）。

>[!NOTE]
>
>您可以发送的键值数没有限制，但[!DNL Google]请求[!DNL URL]确实对可以接受的字符数有限制。 请参阅[使用GPT设置定位和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)。

## 服务器端集成 {#server-side-integration}

如果要使用[!DNL GPT]设置与[!DNL Google Ad Manager]的服务器端集成，请联系Audience Manager顾问或客户关怀部门。 您需要提供您的[!DNL Google Ad Manager]帐户网络ID和受众链接ID。

>[!IMPORTANT]
>
>如果您的网页正在运行[Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP])库，则必须使用服务器端集成与Audience Manager。 如果您在[!DNL AMP]上并且与[!DNL AMP]进行了客户端集成，则必须迁移到服务器端集成。 请联系您的Audience Manager顾问或客户关怀部门以讨论迁移事宜。

>[!MORELIKETHIS]
>
>* [GPT API参考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)
