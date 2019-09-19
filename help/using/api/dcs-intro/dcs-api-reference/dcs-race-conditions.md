---
description: 介绍如何防止竞争情况和DCS错误处理。
seo-description: 介绍如何防止竞争情况和DCS错误处理。
seo-title: 竞争条件和错误处理
solution: Audience Manager
title: 竞争条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 竞争条件和错误处理 {#race-conditions-and-error-handling}

介绍如何防止竞争条件和错 [!UICONTROL DCS] 误处理。

## 防止种族情况 {#prevent-race-conditions}

如果您在完成响应初始查询并将数据写入用户的Cookie之前同时（或快速连续）向 [!UICONTROL DCS] Cookie发送多个调用，则可能会出现竞争条件。 不需要竞争条件，因为它可能损坏或不正确地覆盖cookie数据。 作为最佳实践，请考虑以下方法以帮助避免此问题：

* 不要同时向同一用户发出呼叫或快速连 [!UICONTROL DCS] 续发出呼叫。
* 在发出后续呼叫之前，请等待每个响应返回。

## 错误处理 {#error-handling}

对于无效或格式不良的查询，错误处理受限。 无效请求会返回响 `HTTP 200 OK` 应，但不会返回数据。 此外，当用 [!UICONTROL DCS]`HTTP 200 OK` 户：

* 在Audience manager或合作伙伴级别选择不跟踪。
* 来自无效／未选择的地理区域。
* 禁用浏览器Cookie（全部或第三方）。

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).