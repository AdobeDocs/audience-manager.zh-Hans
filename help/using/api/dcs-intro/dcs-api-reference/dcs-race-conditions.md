---
description: 介绍如何防止竞态情况和DCS错误处理。
seo-description: 介绍如何防止竞态情况和DCS错误处理。
seo-title: 争用条件和错误处理
solution: Audience Manager
title: 争用条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# 争用条件和错误处理 {#race-conditions-and-error-handling}

介绍如何防止竞争情况和[!DNL DCS]错误处理。

## 防止竞争条件{#prevent-race-conditions}

如果您在[!DNL DCS]完成响应初始查询并将数据写入用户的cookie之前同时（或快速连续）向其发送多个呼叫，则可能会出现竞争情况。 不需要竞争条件，因为它可能损坏或不正确覆盖cookie数据。 作为最佳实践，请考虑以下方法来帮助避免此问题：

* 不要向同一用户的[!DNL DCS]快速连续发出同时呼叫或呼叫。
* 请等待每个响应返回，然后再进行后续呼叫。

## 错误处理{#error-handling}

错误处理仅限于无效或格式不良的查询。 无效请求返回`HTTP 200 OK`响应，无数据。 此外，当用户：[!DNL DCS]`HTTP 200 OK`

* 在Audience Manager或合作伙伴级别退出跟踪。
* 来自无效／未选定的地理区域。
* 禁用浏览器cookie（全部或第三方）。

另请参阅[DCS错误代码、消息和示例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。