---
description: Audience Manager要求对HTTP(S)服务器到服务器请求进行数字签名，以确保有效性。 本文档介绍如何使用私钥对HTTP请求进行签名。
seo-description: Audience Manager要求对HTTP(S)服务器到服务器请求进行数字签名，以确保有效性。 本文档介绍如何使用私钥对HTTP(S)请求进行签名。
seo-title: 经过数字签名的HTTP请求
solution: Audience Manager
title: 经过数字签名的HTTP请求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: 出站数据传输
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# 已数字签名的`HTTP(S)`请求{#digitally-signed-http-requests}

Audience Manager要求对`HTTP(S)`服务器到服务器请求进行数字签名，以确保有效性。 本文档介绍如何使用私钥对`HTTP(S)`请求进行签名。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用您提供并与[!DNL Audience Manager]共享的私钥，我们可以对在[IRIS](../../../reference/system-components/components-data-action.md#iris)和HTTP(S)服务器之间发送的`HTTP(S)`请求进行数字签名。 这可确保：

* **真实性**:只有具有私钥([!UICONTROL IRIS])的发件人才能向合作伙 `HTTP(S)` 伴发送有效消息。
* **消息完整性**:使用这种方法，即使是 `HTTP`在此情况下，您也会受到保护，免受中间攻击中消息失真的攻击。

[!UICONTROL IRIS] 内置支持在不停机的情况下旋转密钥，如下面的“旋转专用 [密钥”部](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 分所示。

## 需要提供{#info-to-provide}的信息

对于`HTTP(S)`实时服务器到服务器目标，请联系您的[!DNL Audience Manager]顾问并指定：

* 用于对请求进行签名的键。
* 将保存生成的签名的`HTTP(S)`标头的名称（以下示例标头中为X-Signature）。
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

## 工作原理{#how-it-works}

1. [!UICONTROL IRIS] 创建 `HTTP(S)` 要发送给合作伙伴的消息。
1. [!UICONTROL IRIS] 创建基于该消息和 `HTTP(S)` 合作伙伴传送的私钥的签名。
1. [!UICONTROL IRIS] 向合作 `HTTP(S)` 伙伴发送请求。此消息包含签名和实际消息，如上面的示例所示。
1. 合作伙伴服务器接收`HTTP(S)`请求。 它读取从[!UICONTROL IRIS]收到的消息正文和签名。
1. 合作伙伴服务器根据收到的消息正文和私钥重新计算签名。 请参阅下面的[如何计算签名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)部分，了解如何实现此目的。
1. 比较在合作伙伴服务器（接收者）上创建的签名与从[!UICONTROL IRIS]（发送者）收到的签名。
1. 如果签名匹配，则&#x200B;**真实性**&#x200B;和&#x200B;**消息完整性**&#x200B;已得到验证。 只有拥有私钥的发送者才能发送有效签名（真实性）。 此外，中间人无法修改消息并生成新的有效签名，因为他们没有私钥（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何计算签名{#calculate-signature}

[!DNL HMAC] （基于哈希的消息身份验证代码）是用于消息签 [!UICONTROL IRIS] 名的方法。实施和库基本上以每种编程语言提供。 [!DNL HMAC] 没有已知的扩展攻击。请参阅下面的[!DNL Java]示例：

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

用于[!DNL HMAC]哈希实现的RFC是[https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 测试网站：[https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac)（请注意，必须[将](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)十六进制编码转换为base64）。

## 旋转私钥{#rotate-private-key}

要轮换私钥，合作伙伴必须将新私钥传递给其[!DNL Adobe Audience Manager]顾问。 旧密钥从[!DNL Audience Manager]中删除，并且[!UICONTROL IRIS]只发送新的签名标头。 钥匙已旋转。

## 用于签名{#data-signing}的数据

对于`GET`类型目标，用于签名的消息将是&#x200B;*REQUEST_PATH + QUERY STRING*(例如，*/from-aam-s2s?sids=1,2,3*)。 IRIS不考虑主机名或`HTTP(S)`标头 — 这些标头可能会沿路径被修改/配置错误或报告错误。

对于`POST`类型目标，用于签名的消息是&#x200B;*REQUEST BODY*。 同样，标头或其他请求参数也会被忽略。
