---
description: 介绍如何防止出现争用情况和DCS错误处理。
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: 争用条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# 争用条件、速率限制和错误处理 {#race-conditions-and-error-handling}

描述如何防止出现争用情况和[!DNL DCS]错误处理。

## 防止竞争情况 {#prevent-race-conditions}

如果您在[!DNL DCS]完成响应初始查询并将数据写入用户Cookie之前，同时或快速连续地向其发送多个调用，则会发生争用情况。 争用条件是不希望出现的，因为它可能会损坏或不正确地覆盖Cookie数据。 作为最佳实践，请考虑以下方法以帮助避免此问题：

* 不要同时调用或快速连续调用同一用户的[!DNL DCS]。
* 等待每个响应返回，然后再进行后续调用。

## 限速 {#rate-limiting}

如果Adobe检测到过多的DCS API调用可能对服务可用性产生负面影响，则可能会引入速率限制。

如果启用了速率限制，您可能会在DCS调用中收到`429 Too Many Requests`个HTTP响应状态代码。 收到此HTTP响应时，请稍后重试API调用。

## 错误处理 {#error-handling}

无效或格式错误的查询的错误处理受到限制。 无效请求返回`HTTP 200 OK`响应且没有数据。 此外，当用户出现以下情况时，[!DNL DCS]停止处理请求，丢弃特征数据并返回`HTTP 200 OK`响应：

* 在Audience Manager或合作伙伴级别选择退出跟踪。
* 来自无效/未选择的地理区域。
* 禁用浏览器Cookie（所有或第三方）。

另请参阅[DCS错误代码、消息和示例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。
