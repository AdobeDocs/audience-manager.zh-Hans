---
description: 当通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth 2.0进行身份验证。 这表明能够从Audience Manager向端点发出经过身份验证的请求。
seo-description: 当通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth 2.0进行身份验证。 这表明能够从Audience Manager向端点发出经过身份验证的请求。
seo-title: 用于实时出站传输的 OAuth 2.0 集成
solution: Audience Manager
title: 用于实时出站传输的 OAuth 2.0 集成
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] 实时出站传输集成{#oauth-integration-for-real-time-outbound-transfers}

当通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时 [!DNL OAuth 2.0] 使用身份验证。 这表明能够从Audience Manager向端点发出经过身份验证的请求。

## 身份验证流 {#auth-flow}

OAuth [!DNL Adobe Audience Manager] 2.0 [身份验证实现基于客户端凭据授权流](https://tools.ietf.org/html/rfc6749#section-4.4) ，并遵循以下步骤：

1. 您必须向我们提供：
   * 生成 [!DNL OAuth 2.0] 身份验证令牌的端点。
   * 用于生成令牌的凭据。
1. 顾 [!DNL Audience Manager] 问使用您提 [供的](../../../features/destinations/destinations.md) 信息设置目标。
1. 一旦将一个区段映射到此目标，我们的实时数据传输系 [统](../../../reference/system-components/components-data-action.md#iris)IRIS就向令牌端点发出请求 `POST` ，以交换用于承载令牌的凭据。
1. 对于每个段发布请求到伙伴端点， [!UICONTROL IRIS] 使用承载令牌进行身份验证。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作为合 [!DNL Audience Manager] 作伙伴，需要以下端点来接收经过身份验证的请求：

### IRIS用于获取承载令牌的端点1

此端点将接受在步骤1提供的凭据并生成用于后续请求的承载令牌。

* 端点必须接受 `HTTP POST` 请求。
* 端点必须接受并查看标 [!DNL Authorization] 头。 此标题的值将为： `Basic <credentials_provided_by_partner>`.
* 端点必须查看头 [!DNL Content-type] 并验证其值是否为 `application/x-www-form-urlencoded ; charset=UTF-8`。
* 请求的正文将是 `grant_type=client_credentials`。

### 由Audience Manager向伙伴端点发出的示例请求，以便获得承载令牌

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### 来自伙伴端点的示例响应

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS使用的端点2使用承载令牌发布段

[!DNL Audience Manager] 当用户符合区段资格时，会近乎实时地向此端点发送数据。 此外，此方法可每24小时发送一批脱机或载入的数据。

端点1生成的承载令牌用于向此端点发出请求。 实 [!DNL Audience Manager] 时数据传输系统IRIS [构造](../../../reference/system-components/components-data-action.md#iris)正常的HTTPS请求并包括授权头。 此标题的值将为： 持 `<bearer token from step 1>`人。

### 来自伙伴端点的示例响应

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>此请求包含标准有效负荷（请求内容）。

## 重要注意事项 {#considerations}

### 令牌是口令

合作伙伴提供的凭据和使用流进行 [!DNL Audience Manager] 身份验证时获 [!DNL OAuth 2.0] 得的令牌是敏感信息，不得与第三方共享。

### [!DNL SSL] 必填

[!DNL SSL] 必须用于维护安全身份验证过程。 所有请求（包括用于获取和使用令牌的请求）都必须使用 `HTTPS` 端点。