---
description: 介绍如何防止争用情况和DCS错误处理。
seo-description: 介绍如何防止争用情况和DCS错误处理。
seo-title: 争用条件和错误处理
solution: Audience Manager
title: 争用条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# 争用条件和错误处理 {#race-conditions-and-error-handling}

介绍如何防止争用情况和[!DNL DCS]错误处理。

## 防止争用情况{#prevent-race-conditions}

如果您在[!DNL DCS]完成对初始查询的响应并将数据写入用户的Cookie之前同时（或快速连续）向该发送多个调用，则可能会出现争用情况。 争用情况不尽如人意，因为它可能损坏或错误地覆盖Cookie数据。 作为最佳实践，请考虑以下方法来帮助避免出现此问题：

* 请勿同时从同一用户向[!DNL DCS]发起调用或快速连续进行调用。
* 等待每个响应返回后再进行后续调用。

## 处理{#error-handling}时出错

对于无效或格式不正确的查询，错误处理受到限制。 无效请求返回`HTTP 200 OK`响应，且没有数据。 此外，当用户：[!DNL DCS]`HTTP 200 OK`

* 在Audience Manager或合作伙伴级别选择退出跟踪。
* 来自无效/未选择的地理区域。
* 禁用浏览器Cookie（全部或第三方）。

另请参阅[DCS错误代码、消息和示例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。
