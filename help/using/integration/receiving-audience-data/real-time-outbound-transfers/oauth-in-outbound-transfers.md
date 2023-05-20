---
description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，可設定Audience Manager以在提出請求時使用OAuth 2.0進行驗證。 如此一來，您便能從Audience Manager向端點發出已驗證請求。
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: 用于实时出站传输的 OAuth 2.0 集成
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# [!DNL OAuth 2.0] 即時傳出傳輸的整合{#oauth-integration-for-real-time-outbound-transfers}

透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，可設定Audience Manager以使用進行驗證 [!DNL OAuth 2.0] 進行請求時。 如此一來，您便能從Audience Manager向端點發出已驗證請求。

## 驗證流程 {#auth-flow}

此 [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 驗證實作是以使用者端憑證授權流程為基礎，並遵循下列步驟：

1. 您必須提供我們：
   * 此 [!DNL OAuth 2.0] 產生驗證權杖的端點。
   * 用來產生Token的認證。
1. 一個 [!DNL Audience Manager] 顧問設定 [目的地](../../../features/destinations/destinations.md) 使用您提供的資訊。
1. 將區段對應至此目的地後，我們的即時資料傳輸系統 [IRIS](../../../reference/system-components/components-data-action.md#iris)，建立 `POST` 要求權杖端點交換持有人權杖的認證。
1. 對於每個區段發佈請求至合作夥伴端點， [!UICONTROL IRIS] 使用持有人權杖進行驗證。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作為 [!DNL Audience Manager] 合作夥伴，需要下列端點來接收已驗證的請求：

### IRIS用來取得持有人權杖的端點1

此端點將接受在步驟1提供的認證，並產生將在後續請求中使用的持有人權杖。

* 端點必須接受 `HTTP POST` 要求。
* 端點必須接受並檢視 [!DNL Authorization] 標頭。 此標頭的值將為： `Basic <credentials_provided_by_partner>`.
* 端點必須檢視 [!DNL Content-type] 標頭並驗證其值是否為 `application/x-www-form-urlencoded ; charset=UTF-8`.
* 請求內文將為 `grant_type=client_credentials`.

### Audience Manager為取得持有人權杖而對合作夥伴端點提出的範例要求

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

### 來自合作夥伴端點的範例回應

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS使用端點2來發佈使用持有人權杖的區段

[!DNL Audience Manager] 當使用者符合區段資格時，會近乎即時傳送資料至此端點。 此外，此方法可傳送批次的離線或已上線資料，頻率為每24小時一次。

端點1產生的持有人權杖用於發出對此端點的請求。 此 [!DNL Audience Manager] 即時資料傳輸系統、 [IRIS](../../../reference/system-components/components-data-action.md#iris)，會建構一般HTTPS要求並包含Authorization標頭。 此標頭的值將為：持有者 `<bearer token from step 1>`.

### 來自合作夥伴端點的範例回應

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
>此請求包含標準裝載（請求內容）。

## 重要考量 {#considerations}

### Token為密碼

合作夥伴提供的憑證和取得的Token [!DNL Audience Manager] 使用進行驗證時 [!DNL OAuth 2.0] 流量是敏感資訊，不得與第三方共用。

### [!DNL SSL] 為必填

[!DNL SSL] 必須使用，才能維護安全的驗證程式。 所有請求，包括用來取得及使用權杖的請求，都必須使用 `HTTPS` 端點。
