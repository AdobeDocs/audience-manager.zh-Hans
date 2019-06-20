---
description: 在通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth2.0进行身份验证。这显示了从Audience Manager向端点发出身份验证请求的功能。
seo-description: 在通过实时服务器到服务器集成将区段发布到合作伙伴目标时，可以设置Audience Manager以在发出请求时使用OAuth2.0进行身份验证。这显示了从Audience Manager向端点发出身份验证请求的功能。
seo-title: OAuth2.0实时出站传输集成
solution: Audience Manager
title: OAuth2.0实时出站传输集成
uuid: a39e370c-b3 bd-4b06-a1 AF-60a024 ee7 ee
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] 实时出站传输集成{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. 这显示了从Audience Manager向端点发出身份验证请求的功能。

## Authentication Flow {#auth-flow}

[!DNL Adobe Audience Manager][OAuth2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 身份验证实施基于客户端凭据，并遵循以下步骤：

1. 您必须为我们提供：
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * 用于生成令牌的凭据。
1. [!DNL Audience Manager] 顾问使用您提供的信息设置 [目标](../../../features/destinations/destinations.md) 。
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

[!DNL Audience Manager] 作为合作伙伴，需要以下端点才能接收经过身份验证的请求：

### IIS使用的端点用于获取看字令牌

此端点将接受第步提供的凭据，并生成将在后续请求上使用的看门人令牌。

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Audience Manager向合作伙伴端点发出的示例请求，以获取一个承担者令牌

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

### 合作伙伴端点的示例响应

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IIS使用的端点2，用于使用标记令牌发布区段

[!DNL Audience Manager] 可在用户有资格获得区段时，实时将数据发送到此端点。此外，此方法可以像每24小时一样发送脱机或已载入的数据批次。

端点生成的承担者令牌用于发出对此端点的请求。[!DNL Audience Manager] 实时数据传输系统 [IIS](../../../reference/system-components/components-data-action.md#iris)构建普通HTTPS请求并包含授权标题。The value for this header will be: Bearer `<bearer token from step 1>`.

### 合作伙伴端点的示例响应

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
>此请求包含标准有效负荷(请求内容)。

## Important Considerations {#considerations}

### 令牌是密码

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] is required

[!DNL SSL] 必须用于维护安全身份验证过程。All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.