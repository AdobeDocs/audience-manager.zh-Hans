---
description: 允许您以编程方式使用目标功能的方法。
seo-description: 允许您以编程方式使用目标功能的方法。
seo-title: 目标API方法
solution: Audience Manager
title: 目标API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 目标API方法 {#destination-api-methods}

允许您以编程方式使用目标功能的方法。

<!-- c_destinations_api.xml -->

在Audience manager中，目标是任何其他系统(广告服务器、广 [!DNL DSP]告网络、交换、您自己的第一方Cookie等)要与之共享数据。

## 目标类型：URL和Cookie {#destination-types}

列出参数使用的 `destinationType` 变量。 指 `push` 定或 `ADS` 使用或 [!UICONTROL URL] 。 [!UICONTROL cookie destination]不能使用可 [!UICONTROL server-to-server destinations] 用的目标方法进行 [!DNL API] 创建。

<!-- r_destination_types.xml -->

| API目标类型 | UI目标类型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_LIKE_THIS]
>
>* [如何选择目标类型](../../../features/destinations/destinations.md)

