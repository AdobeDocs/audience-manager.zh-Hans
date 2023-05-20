---
description: Audience Manager需要對HTTP(S)伺服器對伺服器請求進行數位簽署以確認有效性。 本檔案說明如何使用私密金鑰簽署HTTP請求。
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: 数字签名 HTTP （S）请求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# 数字签名 `HTTP(S)` 请求 {#digitally-signed-http-requests}

Audience Manager 要求 `HTTP(S)` 对服务器到服务器的请求进行数字签名，以使其有效性。 此文档描述如何通过私钥对请求进行签名 `HTTP(S)` 。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

通过使用您提供的私有密钥并与 [!DNL Audience Manager] 共享，我们可以对 IRIS ](../../../reference/system-components/components-data-action.md#iris) 和您的 HTTP （S）服务器之间 [ 发送的 `HTTP(S)` 请求进行数字签名。这可确保：

* **真实性** ：只有具有私钥的发件人（ [!UICONTROL IRIS] ）可以向合作伙伴发送有效 `HTTP(S)` 消息。
* **訊息完整性**：使用此方法，即使在 `HTTP`，您不會受到中間人攻擊的威脅，因為訊息會遭到扭曲。

[!UICONTROL IRIS] 具有內建支援，可在零停機情況下輪換金鑰，如 [旋轉私密金鑰](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 區段底下。

## 您需要提供的資訊 {#info-to-provide}

對於 `HTTP(S)` 即時伺服器對伺服器目的地，請聯絡您的 [!DNL Audience Manager] 顧問，並指定：

* 用于签署请求的键。
* 将包含生成的签名（在下面的示例标题中使用 X 签名）的标头的名称 `HTTP(S)` 。
* 可选：用于签名的哈希类型（md5、sha1、sha256）。

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

1. [!UICONTROL IRIS]`HTTP(S)`创建要发送到合作伙伴的消息。
1. [!UICONTROL IRIS] 根据合作伙伴所传达的消息和私钥创建签名 `HTTP(S)` 。
1. [!UICONTROL IRIS] 傳送 `HTTP(S)` 向合作夥伴提出要求。 此訊息包含簽名和實際訊息，如上面的範例所示。
1. 合作夥伴伺服器會接收 `HTTP(S)` 要求。 它會讀取訊息內文和收到的簽名 [!UICONTROL IRIS].
1. 合作夥伴伺服器會根據收到的訊息內文和私密金鑰重新計算簽章。 請參閱 [如何計算簽名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) 區段以瞭解如何達成此目標。
1. 比較在合作夥伴伺服器（接收者）上建立的簽章與從收到的簽章 [!UICONTROL IRIS] （寄件者）。
1. 如果签名匹配，则验证真实性 **和** 消息的 **完整性** 。只有拥有私钥的发件人可以发送有效的签名（真实性）。 此外，中间的中间人无法修改消息并生成新的有效签名，因为它们没有私钥（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何计算签名 {#calculate-signature}

[!DNL HMAC] （基于哈希的消息身份验证代码）是用于 [!UICONTROL IRIS] 消息签名的方法。 实施和 Libraries 主要在每种编程语言中提供。 [!DNL HMAC] 没有已知的扩展攻击。 请参阅下面的示例 [!DNL Java] ：

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

RFC for [!DNL HMAC] 雜湊實作是 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). 測試網站： [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (請注意，您必須 [轉換](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) 十六進位編碼為base64)。

## 旋轉私密金鑰 {#rotate-private-key}

若要輪換私密金鑰，合作夥伴必須將新的私密金鑰通訊給其 [!DNL Adobe Audience Manager] 顧問。 舊金鑰已從中移除 [!DNL Audience Manager] 和 [!UICONTROL IRIS] 僅傳送新簽章標頭。 鍵已旋轉。

## 用於簽署的資料 {#data-signing}

对于 `GET` 类型目标，用于签名的消息将是 *REQUEST_PATH + 查询字符串* （例如 */from-aam-s2s？ sid = 1、2、3* ）。 IRIS 不会执行帐户主机名或 `HTTP(S)` 标头，可以通过路径对其进行修改/配置错误，或报告错误。

对于 `POST` 类型目标，用于签名的消息是 *请求正文* 。 同样，将忽略标头或其他请求参数。
