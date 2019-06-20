---
description: 允许您使用目标功能编程工作的方法。
seo-description: 允许您使用目标功能编程工作的方法。
seo-title: 目标API方法
solution: Audience Manager
title: 目标API方法
uuid: 048bcdb9-2b31-46f480b80-4ba06640bb06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination API Methods {#destination-api-methods}

允许您使用目标功能编程工作的方法。

<!-- c_destinations_api.xml -->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) 您希望与之共享数据的数据。

## Destination Types: URL and Cookie {#destination-types}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!DNL API] methods.

<!-- r_destination_types.xml -->

| API目标类型 | UI目标类型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_ LIKE_ This]
>
>* [如何选择目标类型](../../../features/destinations/destinations.md)

