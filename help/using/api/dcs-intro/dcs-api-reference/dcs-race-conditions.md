---
description: 介绍如何防止竞争条件和DCS错误处理。
seo-description: 介绍如何防止竞争条件和DCS错误处理。
seo-title: 竞争条件和错误处理
solution: Audience Manager
title: 竞争条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. 竞争条件不需要，因为它可能损坏或不适当覆盖cookie数据。作为最佳实践，请考虑以下方法以帮助避免此问题：

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* 等待每个响应在发出后续调用之前返回。

## Error Handling {#error-handling}

对于无效或构成错误的查询，错误处理受到限制。An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* 选择退出Audience Manager或合作伙伴级别跟踪。
* 来自无效/未选定的地理区域。
* 禁用浏览器cookie(全部或第三方)。

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).