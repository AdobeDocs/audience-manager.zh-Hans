---
description: 通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth 2.0进行身份验证。 这表示能够向您的端点发出经过Audience Manager的已验证请求。
seo-description: 通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth 2.0进行身份验证。 这表示能够向您的端点发出经过Audience Manager的已验证请求。
seo-title: 用于实时出站传输的 OAuth 2.0 集成
solution: Audience Manager
title: 用于实时出站传输的 OAuth 2.0 集成
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: 出站数据传输
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# [!DNL OAuth 2.0] 实时出站传输集成{#oauth-integration-for-real-time-outbound-transfers}

通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用[!DNL OAuth 2.0]进行身份验证。 这表示能够向您的端点发出经过Audience Manager的已验证请求。

## 身份验证流程{#auth-flow}

[!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4)身份验证实施基于客户端凭据授予流程，并遵循以下步骤：

1. 您必须向我们提供：
   * 生成身份验证令牌的[!DNL OAuth 2.0]端点。
   * 用于生成令牌的凭据。
1. [!DNL Audience Manager]顾问使用您提供的信息设置[目标](../../../features/destinations/destinations.md)。
1. 在区段映射到此目标后，我们的实时数据传输系统[IRIS](../../../reference/system-components/components-data-action.md#iris)向令牌端点发出`POST`请求以交换承载令牌的凭据。
1. 对于每个区段向合作伙伴端点发布请求，[!UICONTROL IRIS]使用载体令牌进行身份验证。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作为[!DNL Audience Manager]合作伙伴，需要以下端点才能接收经过身份验证的请求：

### IRIS用于获取承载令牌的端点1

此端点将接受步骤1中提供的凭据，并生成将在后续请求中使用的承载令牌。

* 端点必须接受`HTTP POST`请求。
* 端点必须接受并查看[!DNL Authorization]标头。 此标题的值将为：`Basic <credentials_provided_by_partner>`。
* 端点必须查看[!DNL Content-type]标头，并验证其值是否为`application/x-www-form-urlencoded ; charset=UTF-8`。
* 请求正文将为`grant_type=client_credentials`。

### 由Audience Manager向合作伙伴端点发出的示例请求，以获取载体令牌

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

### 来自合作伙伴端点的示例响应

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS使用载体令牌发布区段的端点2

[!DNL Audience Manager] 在用户符合区段资格时，会近乎实时地向此端点发送数据。此外，此方法可每24小时发送一批脱机或已载入的数据。

端点1生成的载体令牌用于向此端点发出请求。 [!DNL Audience Manager]实时数据传输系统[IRIS](../../../reference/system-components/components-data-action.md#iris)构建正常的HTTPS请求并包含授权标头。 此标题的值将为：载体`<bearer token from step 1>`。

### 来自合作伙伴端点的示例响应

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
>此请求包含标准有效负载（请求内容）。

## 重要注意事项 {#considerations}

### 令牌是密码

合作伙伴提供的凭据以及使用[!DNL OAuth 2.0]流进行身份验证时由[!DNL Audience Manager]获取的令牌是敏感信息，不得与第三方共享。

### [!DNL SSL] 必需

[!DNL SSL] 必须使用才能维护安全身份验证过程。所有请求（包括用于获取和使用令牌的请求）都必须使用`HTTPS`端点。
