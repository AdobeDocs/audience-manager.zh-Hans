---
description: 允许您以编程方式使用目标功能的方法。
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 目标API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: 'https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: 7dee9651-deb5-5d4d-acfd-fbc10040467f
    internal-label: API
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 0%
---
# 目标API方法 {#destination-api-methods}

允许您以编程方式使用目标功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目标是任何其他系统（广告服务器、[!DNL DSP]、广告网络、exchange、您自己的第一方Cookie等） 任何其他系统(广告服务器、DSP、

## 目标类型：URL和Cookie {#destination-types}

列出`destinationType`参数使用的变量。 指定要与[!UICONTROL URL]或[!UICONTROL cookie destination]一起使用的`push`或`ADS`。 无法使用可用的目标[!DNL API]方法创建[!UICONTROL server-to-server destinations]。

<!-- r_destination_types.xml -->

| API目标类型 | UI目标类型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [如何选择目标类型](../../../features/destinations/destinations.md)
