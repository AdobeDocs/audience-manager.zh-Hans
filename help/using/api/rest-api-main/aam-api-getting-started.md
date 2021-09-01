---
description: 有关一般要求、身份验证、可选查询参数、请求 URL 和其他引用的信息。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: 开始使用 REST API
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 95182160b37bb15df4867bbacd06d8d75c971fa3
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 3%

---

# [!DNL REST] [!DNL APIs]快速入门 {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求[!DNL URLs]和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

使用[!DNL Audience Manager] [!DNL API]时必须且应该执行的操作。

<!-- aam-api-requirements.xml -->

使用[Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/)代码时，请注意以下事项：

* **请求参数：** 除非另有指定，否则所有请求参数都是必需的。
* **请求标头**:使用 [AdobeI/](https://www.adobe.io/) Otokens时，必须提供 `x-api-key` 标头。您可以按照[服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)页面中的说明获取[!DNL API]密钥。
* **[!DNL JSON]内容类型：** 在代 `content-type: application/json`  **  `accept: application/json` 码中指定和。
* **请求和响应：** 将请求作为格式正确的对象 [!DNL JSON] 发送。[!DNL Audience Manager] 以格式化的数 [!DNL JSON] 据做出响应。服务器响应可以包含请求的数据、状态代码或两者。
* **访问：** 您的 [!DNL Audience Manager] 顾问将为您提供客户端ID和用于发出请求的 [!DNL API] 密钥。
* **文档和代码示例：** 斜体 ** 文本表示您在制作或接收数据时提供或传递的 [!DNL API] 变量。将&#x200B;*斜体*&#x200B;文本替换为您自己的代码、参数或其他必需信息。

## 身份验证 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支持两种身份验证方法。

* [JWT（服务帐户）使用](#jwt) Adobe I/O [进行身份验证](https://www.adobe.io/)。[!DNL Adobe I/O] 是Adobe的开发人员生态系统和社区。它包含所有Adobe产品](https://www.adobe.io/apis.html)的[Adobe I/O开发人员工具和API](https://www.adobe.io/apis/experienceplatform.html)和[ API。 这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方法。
* [OAuth身份验证（已弃用）](#oauth)。虽然此方法已弃用，但具有现有[!DNL OAuth]集成的客户可以继续使用此方法。

>[!IMPORTANT]
>
>根据您的身份验证方法，您需要相应地调整请求[!DNL URLs]。 有关应使用的主机名的详细信息，请参阅[Environments](#environments)部分。

## [!DNL JWT] ([!DNL Service Account])使用Adobe I/O进行身份验证 {#jwt}

### Adobe I/O概述 {#adobeio}

[!DNL Adobe I/O] 是Adobe的开发人员生态系统和社区。它包含所有Adobe产品](https://www.adobe.io/apis.html)的[Adobe I/O开发人员工具和API](https://www.adobe.io/apis/experienceplatform.html)和[ API。

这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方法。

### 先决条件 {#prerequisites}

在配置[!DNL JWT]身份验证之前，请确保您有权访问[Adobe I/O](https://www.adobe.io/)中的[Adobe开发人员控制台](https://console.adobe.io/)。 有关访问请求，请联系您的组织管理员。

### 身份验证 {#auth}

请按照以下步骤使用[!DNL Adobe I/O]配置[!DNL JWT (Service Account)]身份验证：

1. 登录到[Adobe开发人员控制台](https://console.adobe.io/)。
1. 按照[服务帐户连接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步骤操作。
   * 在[步骤2中：使用服务帐户身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)将API添加到项目中，选择[!DNL Audience Manager] [!DNL API]选项。
1. 根据[步骤3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的说明进行第一个[!DNL API]调用以尝试连接。

>[!NOTE]
>
>要以自动方式配置和使用[!DNL Audience Manager] [!DNL REST APIs]，可以编程生成[!DNL JWT]。 有关详细说明，请参阅[JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

### 技术帐户RBAC权限

如果您的Audience Manager帐户使用[基于角色的访问控制](../../features/administration/administration-overview.md)，则必须创建一个Audience Manager技术用户帐户，并将其添加到将进行API调用的Audience ManagerRBAC组中。

请按照以下步骤创建技术用户帐户并将其添加到RBAC组：

1. 对`https://aam.adobe.io/v1/users/self`进行`GET`调用。 该调用将创建一个技术用户帐户，您可以在[!UICONTROL Admin Console]的[!UICONTROL Users]页面中看到该帐户。

   ![技术帐户](assets/technical-account.png)

1. 登录到您的Audience Manager帐户，然后[将技术用户帐户](../../features/administration/administration-overview.md#create-group)添加到要进行API调用的用户组。

## [!DNL OAuth] 身份验证（已弃用） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 令牌身份验证和通过的 [!DNL OAuth 2.0] 续订现已弃用。
>
> 请改用[JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循令牌身份验证和续订的[!DNL OAuth 2.0]标准。 以下各节介绍如何验证和开始使用[!DNL API]s。

### 创建通用[!DNL API]用户 {#requirements}

我们建议您创建一个单独的技术用户帐户，用于使用[!DNL Audience Manager] [!DNL API]。这是一个通用帐户，它未绑定到组织中的特定用户或与其关联。 此类型的[!DNL API]用户帐户可帮助您完成以下两项任务：

* 确定哪项服务正在调用[!DNL API]（例如，来自使用我们的[!DNL API]或来自发出[!DNL API]请求的其他工具的应用程序的调用）。
* 提供对[!DNL API]s的无中断访问。与特定人员关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的[!DNL API]代码。 未与特定员工绑定的通用帐户有助于您避免此问题。

例如，对于此类帐户，假设您希望使用[批量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次更改多个区段。 为此，您的用户帐户需要[!DNL API]访问权限。 创建一个非特定的[!DNL API]用户帐户，该帐户具有适当的凭据、密钥和密钥，以便进行[!DNL API]调用，而不是向特定用户添加权限。 如果您开发自己的使用[!DNL Audience Manager] [!DNL API]的应用程序，则此功能也会很有用。

与您的[!DNL Audience Manager]顾问合作，设置一个通用的[!DNL API]仅用户帐户。

### 密码验证工作流 {#password-authentication-workflow}

密码身份验证安全访问我们的[!DNL REST API]。 以下步骤概述了在浏览器中从[!DNL JSON]客户端进行密码验证的工作流程。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，则对其进行加密。

#### 步骤1:请求[!DNL API]访问

请联系您的合作伙伴解决方案经理。 它们将为您提供[!DNL API]客户端ID和密钥。 ID和密钥可对[!DNL API]进行身份验证。

注意：如果要接收刷新令牌，请在请求[!DNL API]访问时指定。

#### 步骤2:请求令牌

使用首选的[!DNL JSON]客户端传递令牌请求。 构建请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和密钥转换为基于64的编码字符串。 在转换过程中，使用冒号将ID和密钥分隔开。 例如，凭据`testId : testSecret`将转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded` 。 例如，您的标头可能如下所示：<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求正文：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步骤3:接收令牌

[!DNL JSON]响应包含您的访问令牌。 响应应如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in`键表示访问令牌过期的秒数。 最佳做法是，使用较短的过期时间来限制令牌曝光时的曝光。

### 刷新令牌 {#refresh-token}

刷新令牌会在原始令牌过期后续订[!DNL API]访问权限。 如果请求，密码工作流中的响应[!DNL JSON]将包含刷新令牌。 如果未收到刷新令牌，请通过密码身份验证过程创建新令牌。

您还可以在现有访问令牌过期之前使用刷新令牌生成新令牌。

如果您的访问令牌已过期，您将在响应中收到`401 Status Code`和以下标头：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从浏览器中的[!DNL JSON]客户端创建新访问令牌的工作流。

#### 步骤1:请求新令牌

使用首选的[!DNL JSON]客户端传递刷新令牌请求。 构建请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和密钥转换为基于64的编码字符串。 在转换过程中，使用冒号将ID和密钥分隔开。 例如，凭据`testId : testSecret`将转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入HTTP标头`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的标头可能如下所示：<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在请求正文中，指定`grant_type:refresh_token`并传递您在上一个访问请求中收到的刷新令牌。 请求应如下所示：<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步骤2:接收新令牌

[!DNL JSON]响应包含您的新访问令牌。 响应应如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授权码与隐式认证 {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支持授权代码和隐式身份验证。 要使用这些访问方法，您的用户需要登录到`https://api.demdex.com/oauth/authorize`以获取访问和刷新令牌。

## 发出经过身份验证的[!DNL API]请求 {#authenticated-api-requests}

在收到身份验证令牌后调用[!DNL API]方法的要求。

要对可用的[!DNL API]方法进行调用，请执行以下操作：

* 在`HTTP`标头中，设置`Authorization: Bearer <token>`。
* 使用[JWT（服务帐户）Authentication](#jwt)时，您需要提供`x-api-key`标头，该标头将与`client_id`的标头相同。 您可以从[Adobe I/O集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)页面获取`client_id`。
* 调用所需的[!DNL API]方法。

## 可选[!DNL API]查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

您可以将这些可选参数与返回对象&#x200B;*所有*&#x200B;属性的[!DNL API]方法一起使用。 将查询传递到[!DNL API]时，在请求字符串中设置这些选项。

| 参数 | 描述 |
|--- |--- |
| `page` | 按页码返回结果。 编号从0开始。 |
| `pageSize` | 设置请求返回的响应结果数（默认为10）。 |
| `sortBy` | 根据指定的[!DNL JSON]属性对结果进行排序和返回。 |
| `descending` | 按降序排序和返回结果。 `ascending` 为默认值。 |
| `search` | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您希望在该项目的任何值字段中查找包含“Test”字样的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜索“[!DNL get all]”方法返回的任何值。 |
| `folderId` | 返回指定文件夹内[!UICONTROL traits]的所有ID。 并非对所有方法都可用。 |
| `permissions` | 根据指定的权限返回区段列表。 `READ` 为默认值。权限包括：<ul><li>`READ` :返回并查看有关区段的信息。</li><li>`WRITE` :使  `PUT`  用更新区段。</li><li>`CREATE` :使  `POST`  用创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，则需要拥有删除该区段的权限。</li></ul><br>使用单独的键值对指定多个权限。例如，要返回仅具有`READ`和`WRITE`权限的区段列表，请传入`"permissions":"READ"`、`"permissions":"WRITE"` 。 |
| `includePermissions` | ([!DNL Boolean])设置为`true`以返回您对该区段的权限。 默认值为 `false`. |

### 关于页面选项的注释

如果未指定页面信息&#x200B;**，请求将返回纯的[!DNL JSON]，从而导致数组。 如果指定了页面信息&#x200B;**，则返回的列表将封装在[!DNL JSON]对象中，该对象包含有关总结果和当前页面的信息。 使用页面选项的示例请求可能类似于以下内容：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 适用于请求、暂存和生产环境和版本。

## 请求 [!DNL URLs] {#request-urls}

下表按方法列出了用于传入[!DNL API]请求的请求[!DNL URLs]。

根据您使用的身份验证方法，您需要根据下表调整请求[!DNL URLs]。

### 请求[!DNL URLs]进行[!DNL JWT]身份验证 {#request-urls-jwt}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特征： `https://aam.adobe.io/v1/folders/traits /`<br>区段： `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### [!DNL OAuth]身份验证请求[!DNL URLs]（已弃用） {#request-urls-oauth}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特征： `https://api.demdex.com/v1/folders/traits /`<br>区段： `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 环境 {#environments}

[!DNL Audience Manager] [!DNL API]提供对不同工作环境的访问权限。 这些环境可帮助您针对单独的数据库测试代码，而不会影响实时生产数据。 下表列出了可用的[!DNL API]环境和相应的资源主机名。

根据您使用的身份验证方法，您需要根据下表调整环境[!DNL URLs]。

| 环境 | [!DNL JWT]身份验证的主机名 | [!DNL OAuth]身份验证的主机名 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager]测试版环境是生产环境的较小规模的独立版本。 必须在此环境中输入和收集您要测试的所有数据。

## 版本 {#versions}

这些[!DNL API]s的新版本会定期发布。 新版本增加了[!DNL API]版本号。 版本号在请求[!DNL URL]中以`v<version number>`的形式引用，如以下示例所示：

`https://<host>/v1/...`

## 定义的响应代码 {#response-codes-defined}

`HTTP` 状态代码和由返回的响应文 [!DNL Audience Manager] [!UICONTROL REST API]本

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| `200` | `OK` | 请求已成功处理。 将根据需要返回预期的内容或数据。 |
| `201` | `Created` | 已创建资源。 为`PUT`和`POST`请求返回。 |
| `204` | `No Content` | 已删除资源。 响应正文将为空。 |
| `400` | `Bad Request` | 服务器不理解该请求。 通常是由于语法格式错误所致。 请检查您的请求，然后重试。 |
| `403` | `Forbidden` | 您无权访问资源。 |
| `404` | `Not Found` | 找不到指定路径的资源。 |
| `409` | `Conflict` | 由于与资源状态冲突，无法完成请求。 |
| `500` | `Server Error` | 服务器遇到错误，导致其无法执行请求。 |

>[!MORELIKETHIS]
>
>* [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2已简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

