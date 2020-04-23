---
description: 受众管理器要求对HTTP(S)服务器到服务器请求进行数字签名以确保有效性。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-description: 受众管理器要求对HTTP(S)服务器到服务器请求进行数字签名以确保有效性。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-title: 数字签名的HTTP请求
solution: Audience Manager
title: 数字签名的HTTP请求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
translation-type: tm+mt
source-git-commit: 5dddaaae3a5cb2ce4c4649e2a153edf1992fa964

---


# 数字签名的 `HTTP(S)` 请求 {#digitally-signed-http-requests}

受众管理器 `HTTP(S)` 要求对服务器到服务器的请求进行数字签名以验证有效性。 本文档介绍如何使用私钥 `HTTP(S)` 对请求进行签名。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用由您提供并与之共享的私钥 [!DNL Audience Manager]，我们可以对 `HTTP(S)` IRIS [](../../../reference/system-components/components-data-action.md#iris) 和您的HTTP(S)服务器之间发送的请求进行数字签名。 这可确保：

* **真实性**:只有具有私钥([!UICONTROL IRIS])的发送方才能向合作伙伴发 `HTTP(S)` 送有效消息。
* **消息完整性**:使用这种方法，即便如此， `HTTP`您也能免受中间攻击中的人的攻击，因为消息会被扭曲。

[!UICONTROL IRIS] 内置了在零停机情况下旋转密钥的支持，如下 [面的旋转私钥部分](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 。

## 您需要提供的信息 {#info-to-provide}

对于实 `HTTP(S)` 时服务器到服务器目标，请与顾问联系并 [!DNL Audience Manager] 指定：

* 用于签署请求的键。
* 将包含生成 `HTTP(S)` 的签名的标题的名称（下面示例标题中的X-Signature）。
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

1. [!UICONTROL IRIS] 创建要 `HTTP(S)` 发送给合作伙伴的消息。
1. [!UICONTROL IRIS] 根据该消息和由合作伙伴 `HTTP(S)` 传递的私钥创建签名。
1. [!UICONTROL IRIS] 向合作 `HTTP(S)` 伙伴发送请求。 此消息包含签名和实际消息，如上例所示。
1. 合作伙伴服务器接收该 `HTTP(S)` 请求。 它读取消息正文和从收到的签名 [!UICONTROL IRIS]。
1. 合作伙伴服务器基于接收到的消息正文和私钥重新计算签名。 有关如何 [实现此目的](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) ，请参阅下面的“如何计算签名”一节。
1. 将在合作伙伴服务器（接收方）上创建的签名与从（发送方）接收的签 [!UICONTROL IRIS] 名进行比较。
1. 如果签名匹配，则验证 **真实性****和消息完** 整性。 只有拥有私钥的发送者才能发送有效的签名（真实性）。 此外，中间人无法修改消息并生成新的有效签名，因为他们没有私钥（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何计算签名 {#calculate-signature}

[!DNL HMAC] （基于哈希的消息身份验证代码）是用于消息签名 [!UICONTROL IRIS] 的方法。 基本上每个编程语言都提供了实施和库。 [!DNL HMAC] 没有已知的扩展攻击。 请参阅以下示例 [!DNL Java] :

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

散列实现的RFC [!DNL HMAC] 是https://www.ietf.org/rfc/rfc2104.txt [的](https://www.ietf.org/rfc/rfc2104.txt)。 测试站点：https://asecuritysite.com/encryption/hmac [(请注意，您必须将](https://asecuritysite.com/encryption/hmac) 十六进制编码转 [换](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) 为base64)。

## 旋转私钥 {#rotate-private-key}

出于安全原因，建议定期旋转私钥。 由您决定私钥和旋转周期。 为了在零停机时实现密钥轮替，支持 [!UICONTROL IRIS] 添加多个签名头。 一个头将包含使用旧密钥生成的签名，另一个头将包含使用新私钥生成的签名。 请详细参阅以下步骤：

1. Partner将新的私钥与进行通信 [!DNL Adobe Audience Manager]。
1. 旧密钥从中删除， [!DNL Audience Manager] 并仅 [!UICONTROL IRIS] 发送新签名头。 键已旋转。

## 用于签名的数据 {#data-signing}

对 `GET` 于类型目标，用于签名的消息将是 *REQUEST_PATH +查询字符串* (例如， */from-aam-s2s?sids=1,2,3*)。 IRIS不考虑主机名或标头- `HTTP(S)` 这些主机名或标头可能会沿路径修改／配置错误或报告错误。

对于 `POST` 类型目标，用于签名的消息是 *REQUEST BODY*。 同样，忽略标题或其他请求参数。
