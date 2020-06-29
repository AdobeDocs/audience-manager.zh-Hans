---
description: 让您以编程方式处理目标功能的方法。
seo-description: 让您以编程方式处理目标功能的方法。
seo-title: 目标 API 方法
solution: Audience Manager
title: 目标 API 方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# 目标 API 方法 {#destination-api-methods}

让您以编程方式处理目标功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目标是任何其他系统(广告服 [!DNL DSP]务器、广告网络、交换、您自己的第一方cookie等) 任何其他系统（广告服务器、DSP、广告网络等）。

## 目标类型： URL和Cookie {#destination-types}

列表参数使用的 `destinationType` 变量。 指 `push` 定 `ADS` 或使用或 [!UICONTROL URL] 。 [!UICONTROL cookie destination]不能使用可 [!UICONTROL server-to-server destinations] 用的目标方法进 [!DNL API] 行创建。

<!-- r_destination_types.xml -->

| API目标类型 | UI目标类型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [如何选择目标类型](../../../features/destinations/destinations.md)

