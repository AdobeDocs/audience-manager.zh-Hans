---
description: Audience Manager要求对HTTP(S)服务器到服务器请求进行数字签名以使其生效。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: 经过数字签名的HTTP请求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# 对`HTTP(S)`请求进行数字签名 {#digitally-signed-http-requests}

Audience Manager要求对`HTTP(S)`服务器到服务器请求进行数字签名以使其生效。 本文档介绍如何使用私钥对`HTTP(S)`请求进行签名。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用您提供的并与[!DNL Audience Manager]共享的私钥，我们可以对`HTTP(S)`IRIS[和您的HTTP(S)服务器之间发送的](../../../reference/system-components/components-data-action.md#iris)请求进行数字签名。 这样可以确保：

* **真实性**：只有拥有私钥([!UICONTROL IRIS])的发件人才能向合作伙伴发送有效的`HTTP(S)`邮件。
* **消息完整性**：使用此方法，即使在`HTTP`上，您也会受到保护，不会受到中间人攻击造成消息失真的攻击。

[!UICONTROL IRIS]已内置支持在零停机时间的情况下旋转密钥，如下面的[旋转私钥](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key)部分所示。

## 您需要提供的信息 {#info-to-provide}

对于`HTTP(S)`实时服务器到服务器目标，请联系您的[!DNL Audience Manager]顾问并指定：

* 用于签署请求的密钥。
* 将保存生成的签名（下面示例标头中的X-Signature）的`HTTP(S)`标头的名称。
* 可选：用于签名的哈希类型(md5、sha1、sha256)。

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## 工作原理 {#how-it-works}

1. [!UICONTROL IRIS]创建要发送给合作伙伴的`HTTP(S)`消息。
1. [!UICONTROL IRIS]根据`HTTP(S)`消息和合作伙伴传达的私钥创建签名。
1. [!UICONTROL IRIS]将`HTTP(S)`请求发送给合作伙伴。 此消息包含签名和实际消息，如上面的示例所示。
1. 伙伴服务器接收`HTTP(S)`请求。 它读取从[!UICONTROL IRIS]收到的邮件正文和签名。
1. 合作伙伴服务器根据收到的消息正文和私钥重新计算签名。 请参阅下面的[如何计算签名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)部分，了解如何实现此目标。
1. 比较在合作伙伴服务器（接收方）上创建的签名与从[!UICONTROL IRIS]（发送方）接收的签名。
1. 如果签名匹配，则验证&#x200B;**真实性**&#x200B;和&#x200B;**消息完整性**。 只有拥有私钥的发件人才能发送有效的签名（真实性）。 此外，中间人无法修改消息并生成新的有效签名，因为他们没有私钥（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何计算签名 {#calculate-signature}

[!DNL HMAC] （基于哈希的消息身份验证代码）是[!UICONTROL IRIS]用于消息签名的方法。 实施和库基本上以每种编程语言提供。 [!DNL HMAC]没有已知的扩展攻击。 查看以下[!DNL Java]中的示例：

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

[!DNL HMAC]哈希实现的RFC为[https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 测试站点： [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac)（请注意，您必须[将](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)十六进制编码转换为base64）。

## 旋转私钥 {#rotate-private-key}

要轮换私钥，合作伙伴必须将新的私钥传达给其[!DNL Adobe Audience Manager]顾问。 旧密钥已从[!DNL Audience Manager]中删除，[!UICONTROL IRIS]仅发送新签名标头。 这些钥匙已旋转。

## 用于签名的数据 {#data-signing}

对于`GET`类型目标，用于签名的消息将为&#x200B;*REQUEST_PATH +查询字符串* （例如&#x200B;*/from-aam-s2s？sids=1,2，3*）。 IRIS不考虑主机名或`HTTP(S)`标头 — 这些标头可能沿路径修改/配置错误或报告不正确。

对于`POST`类型目标，用于签名的消息是&#x200B;*请求正文*。 同样，标头或其他请求参数将被忽略。
