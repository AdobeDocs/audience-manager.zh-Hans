---
description: Audience Manager要求对HTTP(S)服务器到服务器请求进行数字签名，以确保有效性。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-description: Audience Manager要求对HTTP(S)服务器到服务器请求进行数字签名，以确保有效性。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-title: 数字签名的HTTP请求
solution: Audience Manager
title: 数字签名的HTTP请求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---


# Digitally Signed `HTTP(S)` Requests {#digitally-signed-http-requests}

Audience Manager要求 `HTTP(S)` 对服务器到服务器的请求进行数字签名以验证其有效性。 本文档介绍如何使用私钥 `HTTP(S)` 对请求进行签名。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用您提供并与之共享的私 [!DNL Audience Manager]钥，我们可以对IRIS `HTTP(S)` 和您的HTTP(S)服 [务器](../../../reference/system-components/components-data-action.md#iris) 之间发送的请求进行数字签名。 这确保：

* **真实性**: 只有具有私钥()的发送[!UICONTROL IRIS]者才能向合作伙伴 `HTTP(S)` 发送有效消息。
* **消息完整性**: 这种方法，即使是 `HTTP`在中间攻击中，信息也会被扭曲。

[!UICONTROL IRIS] 内置了在零停机时间内旋转密钥的支持，如下 [面的“旋转私钥](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) ”部分所示。

## 您需要提供的信息 {#info-to-provide}

对于实 `HTTP(S)` 时服务器到服务器目标，请与顾问联系并 [!DNL Audience Manager] 指定：

* 用于签署请求的密钥。
* 将包含生 `HTTP(S)` 成签名的标题的名称（下面示例标题中的X-Signature）。
* 可选： 用于签名的哈希类型(md5、sha1、sha256)。

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

1. [!UICONTROL IRIS] 创建要 `HTTP(S)` 发送给合作伙伴的消息。
1. [!UICONTROL IRIS] 创建基于该消息 `HTTP(S)` 和由合作伙伴传递的私钥的签名。
1. [!UICONTROL IRIS] 将请求 `HTTP(S)` 发送给合作伙伴。 此消息包含签名和实际消息，如上例所示。
1. 合作伙伴服务器接收 `HTTP(S)` 请求。 它读取邮件正文和收到的签名 [!UICONTROL IRIS]。
1. 合作伙伴服务器根据收到的消息正文和私钥重新计算签名。 请参见 [如何计算签名部分](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) ，了解如何实现此功能。
1. 将在合作伙伴服务器（接收方）上创建的签名与从（发送方）收 [!UICONTROL IRIS] 到的签名进行比较。
1. 如果签名匹配，则验证 **真实性****和消息** 完整性。 只有拥有私钥的发送者才能发送有效签名（真实性）。 此外，中间人无法修改消息并生成新的有效签名，因为他们没有私钥（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何计算签名 {#calculate-signature}

[!DNL HMAC] （基于哈希的消息身份验证代码）是消息签名 [!UICONTROL IRIS] 所使用的方法。 实现和库基本上在每种编程语言中都可用。 [!DNL HMAC] 没有已知的扩展攻击。 请参阅以下示例 [!DNL Java] :

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

哈希实现的 [!DNL HMAC] RFC为 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 测试站点： [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (请注意，您必须将 [十六进制](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) 编码转换为base64)。

## 旋转私钥 {#rotate-private-key}

出于安全原因，建议定期旋转私钥。 由您决定私钥和轮换周期。 为了在零停机时间下实现密钥轮替， [!UICONTROL IRIS] 支持添加多个签名头。 一个头将包含用旧密钥生成的签名，另一个头将包含使用新私钥生成的签名。 请详细参阅以下步骤：

1. 合作伙伴可与其通信新的私钥 [!DNL Adobe Audience Manager]。
1. 旧密钥从中删除， [!DNL Audience Manager] 并 [!UICONTROL IRIS] 仅发送新签名头。 钥匙已旋转。

## 用于签名的数据 {#data-signing}

对 `GET` 于类型目标，用于签名的消 *息将是REQUEST_PATH +查询字符串* (例如， */from-aam-s2s?sids=1,2,3*)。 IRIS未考虑主机名或标头 `HTTP(S)` -这些主机名或头可能沿路径修改／配置错误或报告错误。

对 `POST` 于类型目标，用于签名的消息是 *REQUEST BODY*。 同样，标题或其他请求参数也会被忽略。
