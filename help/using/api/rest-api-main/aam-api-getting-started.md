---
description: 有关一般要求、身份验证、可选查询参数、请求 URL 和其他引用的信息。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: 开始使用 REST API
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 3%

---

# 快速入門 [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

關於一般需求、驗證、選擇性查詢引數、請求的資訊 [!DNL URLs]和其他參考資料。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

您使用時必須完成或應該完成的事項 [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

使用時，請注意下列事項 [AUDIENCE MANAGERAPI](https://bank.demdex.com/portal/swagger/index.html#/) 程式碼：

* **要求引數：** 除非另有指定，否則所有要求引數均為必要。
* **請求標頭**：使用時 [Adobe Developer](https://www.adobe.io/) Token，您必須提供 `x-api-key` 標頭。 您可以取得您的 [!DNL API] 依照 [服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 頁面。
* **[!DNL JSON]內容型別：** 指定 `content-type: application/json`  *和*  `accept: application/json` 在您的程式碼中。
* **要求與回應：** 以正確格式化的形式傳送請求 [!DNL JSON] 物件。 [!DNL Audience Manager] 回應 [!DNL JSON] 格式化資料。 伺服器回應可包含要求的資料、狀態代碼或兩者。
* **存取：** 您的 [!DNL Audience Manager] 顧問將為您提供使用者端ID和金鑰，讓您建立 [!DNL API] 要求。
* **檔案和程式碼範例：** 文字輸入 *斜體* 代表您在進行或接收時提供或傳入的變數 [!DNL API] 資料。 Replace *斜體* 包含您自己的程式碼、引數或其他必要資訊的文字。

## 驗證 {#authentication}

此 [!DNL Audience Manager] [!DNL REST APIs] 支援兩種驗證方法。

* [JWT （服務帳戶）驗證](#jwt) 使用 [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] 是Adobe的開發人員生態系統和社群。 其中包括 [適用於所有Adobe產品的API](https://www.adobe.io/apis.html). 這是設定和使用的建議方式 [!DNL Adobe] [!DNL APIs].
* [OAuth驗證（已棄用）](#oauth). 雖然此方法已過時，但擁有現有 [!DNL OAuth] 整合可繼續使用此方法。

>[!IMPORTANT]
>
>根據您的驗證方法，您需要調整請求 [!DNL URLs] 因此， 請參閱 [環境](#environments) 區段，以瞭解關於您應使用之主機名稱的詳細資訊。

## [!DNL JWT] ([!DNL Service Account])使用Adobe Developer進行驗證 {#jwt}

### Adobe Developer概觀 {#adobeio}

[!DNL Adobe Developer] 是Adobe的開發人員生態系統和社群。 其中包括 [適用於所有Adobe產品的API](https://www.adobe.io/apis.html).

這是設定和使用的建議方式 [!DNL Adobe] [!DNL APIs].

### 先决条件 {#prerequisites}

設定之前 [!DNL JWT] 驗證，確定您有權存取 [Adobe Developer主控台](https://console.adobe.io/) 在 [Adobe Developer](https://www.adobe.io/). 如需存取要求，請聯絡您的組織管理員。

### 驗證 {#auth}

請依照下列步驟進行設定 [!DNL JWT (Service Account)] 驗證使用 [!DNL Adobe Developer]：

1. 登入 [Adobe Developer主控台](https://console.adobe.io/).
1. 請依照中的步驟操作 [服務帳戶連線](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * 期間 [步驟2：使用服務帳戶驗證新增API至您的專案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)，選擇 [!DNL Audience Manager] [!DNL API] 選項。
1. 請先建立連線，然後再試一次 [!DNL API] 根據的指示呼叫 [步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>若要設定與使用 [!DNL Audience Manager] [!DNL REST APIs] 您可以自動產生 [!DNL JWT] 以程式設計方式。 另請參閱 [JWT （服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 以取得詳細指示。

### 技術帳戶RBAC許可權

如果您的Audience Manager帳戶使用 [角色型存取控制](../../features/administration/administration-overview.md)，您必須建立Audience Manager技術使用者帳戶，並將其新增至將進行API呼叫的Audience ManagerRBAC群組。

請依照下列步驟建立技術使用者帳戶，並將其新增至RBAC群組：

1. 建立 `GET` 呼叫目標 `https://aam.adobe.io/v1/users/self`. 通話將會建立您可在中看到的技術使用者帳戶 [!UICONTROL Admin Console]，在 [!UICONTROL Users] 頁面。

   ![技術帳戶](assets/technical-account.png)

1. 登入您的Audience Manager帳戶並 [新增技術使用者帳戶](../../features/administration/administration-overview.md#create-group) 至將進行API呼叫的使用者群組。

## [!DNL OAuth] 驗證（已棄用） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 權杖驗證和續約，透過 [!DNL OAuth 2.0] 現已棄用。
>
> 請使用 [JWT （服務帳戶）驗證](#jwt-service-account-authentication-jwt) 而非。

此 [!DNL Audience Manager] [!UICONTROL REST API] 追蹤 [!DNL OAuth 2.0] 代號驗證和續約的標準。 以下各節說明如何驗證並開始使用 [!DNL API]s.

### 建立一般 [!DNL API] 使用者 {#requirements}

建議您建立個別的技術使用者帳戶，以便使用 [!DNL Audience Manager] [!DNL API]s.這是一般帳戶，與您組織內的特定使用者沒有關係或沒有關聯。 此型別 [!DNL API] 使用者帳戶可協助您完成2件事：

* 識別呼叫的服務 [!DNL API] (例如，從使用我們的應用程式呼叫 [!DNL API]或來自其他工具，這些工具 [!DNL API] 個請求)。
* 提供對的不中斷存取 [!DNL API]s.與特定人員繫結的帳戶可能會在人員離開您的公司時刪除。 這會導致您無法使用可用的 [!DNL API] 程式碼。 未與特定員工繫結的一般帳戶可協助您避免此問題。

作為此類帳戶的範例或使用案例，假設您想使用一次變更許多區段 [大量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md). 若要這麼做，您的使用者帳戶需要 [!DNL API] 存取。 與其將許可權新增至特定使用者，不如建立非特定、 [!DNL API] 具有適當認證、金鑰和密碼的使用者帳戶 [!DNL API] 呼叫。 如果您開發自己的應用程式來使用 [!DNL Audience Manager] [!DNL API]s.

使用您的 [!DNL Audience Manager] 顧問以設定通用、 [!DNL API]-only使用者帳戶。

### 密碼驗證工作流程 {#password-authentication-workflow}

密碼驗證安全存取我們的 [!DNL REST API]. 以下步驟概述密碼驗證的工作流程 [!DNL JSON] 使用者端。

>[!TIP]
>
>如果您將Token儲存在資料庫中，請加密存取並重新整理Token。

#### 步驟1：要求 [!DNL API] 存取

請連絡您的合作夥伴解決方案經理。 他們將為您提供 [!DNL API] 使用者端ID和密碼。 此ID和密碼會驗證您的 [!DNL API].

注意：如果您想要收到重新整理Token，請在您請求時指定 [!DNL API] 存取。

#### 步驟2：要求Token

以您偏好的方式傳遞權杖請求 [!DNL JSON] 使用者端。 建立請求時：

* 使用 `POST` 要呼叫的方法 `https://api.demdex.com/oauth/token`.
* 將您的使用者端ID和密碼轉換為base-64編碼字串。 在轉換過程中使用冒號分隔ID和密碼。 例如，認證 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 傳入 [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` . 例如，您的標題看起來可能像這樣： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 設定要求內文，如下所示：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3：接收Token

此 [!DNL JSON] 回應包含您的存取權杖。 回應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

此 `expires_in` key代表存取Token過期前的秒數。 如果權杖已公開，最佳做法是使用較短的到期時間來限制公開。

### 重新整理Token {#refresh-token}

重新整理Token更新 [!DNL API] 在原始Token過期後存取。 若有要求，回應會顯示 [!DNL JSON] 在密碼工作流程中，包含重新整理權杖。 如果您沒有收到重新整理權杖，請透過密碼驗證程式建立新的權杖。

您也可以使用重新整理權杖，在現有存取權杖過期之前產生新權杖。

如果您的存取Token已過期，則會收到 `401 Status Code` 和回應中的下列標頭：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟概述使用重新整理權杖從建立新存取權杖的工作流程 [!DNL JSON] 使用者端。

#### 步驟1：要求新Token

以您偏好的方式傳遞重新整理權杖請求 [!DNL JSON] 使用者端。 建立請求時：

* 使用 `POST` 要呼叫的方法 `https://api.demdex.com/oauth/token`.
* 將您的使用者端ID和密碼轉換為base-64編碼字串。 在轉換過程中使用冒號分隔ID和密碼。 例如，認證 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 在HTTP標頭中傳遞 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`. 例如，您的標題看起來可能像這樣： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在請求內文中，指定 `grant_type:refresh_token` 並傳入您先前存取請求中收到的重新整理Token。 要求應如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2：接收新Token

此 [!DNL JSON] 回應包含您的新存取權杖。 回應應如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授權代碼和隱含驗證 {#authentication-code-implicit}

此 [!DNL Audience Manager] [!UICONTROL REST API] 支援授權代碼和隱含驗證。 若要使用這些存取方法，您的使用者需要登入 `https://api.demdex.com/oauth/authorize` 以取得存取權並重新整理Token。

## 進行驗證 [!DNL API] 請求 {#authenticated-api-requests}

通話需求 [!DNL API] 方法會在您收到驗證權杖之後。

對可用發出呼叫的方式 [!DNL API] 方法：

* 在 `HTTP` 標題，設定 `Authorization: Bearer <token>`.
* 使用時 [JWT （服務帳戶）驗證](#jwt)，您必須提供 `x-api-key` 標頭，將會與您的 `client_id`. 您可以取得您的 `client_id` 從 [Adobe Developer整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 頁面。
* 呼叫必要的 [!DNL API] 方法。

## 可選 [!DNL API] 查詢引數 {#optional-api-query-parameters}

設定傳回物件所有屬性的方法可用的選用引數。

您可以使用這些選擇性引數搭配 [!DNL API] 傳回的方法 *全部* 物件的屬性。 將查詢傳入時，在請求字串中設定這些選項 [!DNL API].

| 参数 | 描述 |
|--- |--- |
| `page` | 依頁碼傳回結果。 編號從0開始。 |
| `pageSize` | 設定要求傳回的回應結果數目（預設值為10）。 |
| `sortBy` | 根據指定的排序和傳回結果 [!DNL JSON] 屬性。 |
| `descending` | 以遞減順序排序和傳回結果。 `ascending` 為預設值。 |
| `search` | 根據您要用作搜尋引數的指定字串傳回結果。 例如，假設您想要尋找在該專案的任何值欄位中有「Test」字詞的所有模型的結果。 您的範例請求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`.  您可以搜尋「」傳回的任何值[!DNL get all]」方法。 |
| `folderId` | 傳回的所有ID [!UICONTROL traits] 在指定的資料夾內。 並非所有方法都可使用。 |
| `permissions` | 根據指定的許可權傳回區段清單。 `READ` 為預設值。 許可權包括：<ul><li>`READ` ：傳回並檢視區段的相關資訊。</li><li>`WRITE` ：使用  `PUT`  更新區段。</li><li>`CREATE` ：使用  `POST`  以建立區段。</li><li>`DELETE` : 删除区段. 需要存取基礎特徵（如果有）。 例如，如果您想要移除區段，則需要擁有刪除屬於該區段之特徵的許可權。</li></ul><br>使用個別的索引鍵值配對指定多個許可權。 例如，若要傳回含有以下專案的區段清單：  `READ`  和  `WRITE`  僅限許可權，傳入  `"permissions":"READ"`， `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean])設為 `true` 以傳回該區段的許可權。 默认值为 `false`. |

### 關於頁面選項的附註

頁面資訊時間 *不是* 指定，要求會傳回plain [!DNL JSON] 結果為陣列。 如果頁面資訊 *是* 指定，則傳回的清單會包裝在 [!DNL JSON] 包含總計結果和目前頁面相關資訊的物件。 您使用頁面選項的範例請求看起來可能類似這樣：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 請求、中繼和生產環境及版本。

## 请求 [!DNL URLs] {#request-urls}

下表列出請求 [!DNL URLs] 用於傳入 [!DNL API] 請求，依方法。

根據您使用的驗證方法，您需要調整請求 [!DNL URLs] 根據下表。

### 請求 [!DNL URLs] 的 [!DNL JWT] 驗證 {#request-urls-jwt}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://aam.adobe.io/v1/folders/traits /`<br>區段：  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 請求 [!DNL URLs] 的 [!DNL OAuth] 驗證（已棄用） {#request-urls-oauth}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://api.demdex.com/v1/folders/traits /`<br>區段：  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

此 [!DNL Audience Manager] [!DNL API]提供對不同工作環境的存取權。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時生產資料。 下表列出可用的 [!DNL API] 環境和對應的資源主機名稱。

根據您使用的驗證方法，您需要調整環境 [!DNL URLs] 根據下表。

| 环境 | 主機名稱 [!DNL JWT] 驗證 | 主機名稱 [!DNL OAuth] 驗證 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>此 [!DNL Audience Manager] 測試版環境是生產環境的較小規模、獨立版本。 您想要測試的所有資料都必須在此環境中輸入和收集。

## 版本 {#versions}

這些檔案的新版本 [!DNL API]會定期發行。 新發行版本會增加 [!DNL API] 版本號碼。 請求中引用的版本號碼 [!DNL URL] 作為 `v<version number>` 如下列範例所示：

`https://<host>/v1/...`

## 已定義的回應代碼 {#response-codes-defined}

`HTTP` 狀態代碼和傳回的回應文字 [!DNL Audience Manager] [!UICONTROL REST API].

| 回應代碼ID | 回應文字 | 定义 |
|---|---|---|
| `200` | `OK` | 已成功處理要求。 會視需要傳回預期的內容或資料。 |
| `201` | `Created` | 已建立資源。 傳回 `PUT` 和 `POST` 要求。 |
| `204` | `No Content` | 已刪除資源。 回應內文將為空白。 |
| `400` | `Bad Request` | 伺服器不瞭解此要求。 通常是因為語法錯誤。 請檢查您的請求，然後再試一次。 |
| `403` | `Forbidden` | 您無權存取資源。 |
| `404` | `Not Found` | 找不到指定路徑的資源。 |
| `409` | `Conflict` | 無法完成要求，因為與資源的狀態衝突。 |
| `500` | `Server Error` | 伺服器發生未預期的錯誤，無法完成要求。 |

>[!MORELIKETHIS]
>
>* [JWT （服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2簡體](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

