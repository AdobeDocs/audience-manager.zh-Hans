---
description: Audience Manager需要对HTTP服务器到服务器请求进行数字签名以进行有效性签名。本文档描述了如何使用私钥对HTTP请求进行签名。
seo-description: Audience Manager需要对HTTP服务器到服务器请求进行数字签名以进行有效性签名。本文档描述了如何使用私钥对HTTP请求进行签名。
seo-title: 数字签名的HTTP请求
solution: Audience Manager
title: 数字签名的HTTP请求
uuid: 1183a70f-0c96-42cf-a4 f5-37a83 ffa1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. 这可确保：

* **真实性**：只有具有私钥([!UICONTROL IRIS])的发送者才能向合作伙伴发送有效 `HTTP(S)` 消息。
* **消息完整性**：通过这种方法，即使是在中， `HTTP`您也受到了邮件扭曲的中间人攻击。

[!UICONTROL IRIS] 具有内建支持，可在零停机时旋转键， [如旋转私钥](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 部分中所示。

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* 用于签署请求的密钥。
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] 创建 `HTTP` 要发送给合作伙伴的消息。
1. [!UICONTROL IRIS] 根据 `HTTP` 消息和合作伙伴传递的私钥创建签名。
1. [!UICONTROL IRIS] 将 `HTTP(S)` 请求发送给合作伙伴。此消息包含签名和实际消息，如上面的示例所示。
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. 根据收到的消息正文和私钥，合作伙伴服务器重新计算签名。See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. 只有具有私钥的发送者才能发送有效的签名(真实性)。此外，中间的人无法修改消息并生成新的有效签名，因为他们没有私钥(消息完整性)。

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (基于散列的消息身份验证代码)是用于消息 [!UICONTROL IRIS] 签名的方法。实现和库基本上都在每种编程语言中可用。[!DNL HMAC] 没有已知扩展名攻击。See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
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

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

由于安全原因，建议定期旋转私钥。由您决定私钥和旋转周期。In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. 一个标题将包含使用旧键生成的签名，另一个标题将包含使用新私钥生成的签名。请参阅详细步骤：

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] 将开始发送两个签名标题(一个使用旧密钥，另一个使用新密钥)。
1. 在开始接收两个标题后，您可以选择放弃旧密钥，只查看新签名。
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. 键已旋转。

## Data used for signing {#data-signing}

`GET` 对于类型目标，用于签名的消息将是 *REQUEST_ PATH+ QUERY StrING* (例如 */from-aam-s2s？sids=1,2,3*)。IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

`POST` 对于类型目标，用于签名的消息是 *请求正文*。再次忽略标题或其他请求参数。
