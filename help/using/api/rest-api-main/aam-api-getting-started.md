---
description: 有关一般要求、身份验证、可选查询参数、请求 URL 和其他引用的信息。
seo-description: 有关一般要求、身份验证、可选查询参数、请求 URL 和其他引用的信息。
seo-title: 开始使用 REST API
solution: Audience Manager
title: 开始使用 REST API
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---


# [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}入门

有关一般要求、身份验证、可选查询参数、请求[!DNL URLs]和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

使用[!DNL Audience Manager] [!DNL API]时必须且应做的事情。

<!-- aam-api-requirements.xml -->

使用[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/)代码时请注意以下事项：

* **请求参数：除** 非另有指定，否则所有请求参数都是必需的。
* **请求标头**:使用 [Adobe I/](https://www.adobe.io/) Otokens时，必须提 `x-api-key` 供头。您可以按照[服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)页中的说明获取[!DNL API]密钥。
* **[!DNL JSON]内容类型：** 指 `content-type: application/json`  **  `accept: application/json` 定代码和代码。
* **请求和响应：将请** 求作为格式正确的对象 [!DNL JSON] 发送。[!DNL Audience Manager] 以格式化 [!DNL JSON] 的数据作出响应。服务器响应可以包含请求的数据、状态代码或两者。
* **访问：** 顾 [!DNL Audience Manager] 问将为您提供一个客户端ID和用于发出请求的 [!DNL API] 密钥。
* **文档和代码示例：** 斜体 ** 文本表示您在创建或接收数据时提供或传递的 [!DNL API] 变量。将&#x200B;*斜体*&#x200B;文本替换为您自己的代码、参数或其他必需信息。

## 身份验证{#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支持两种身份验证方法。

* [JWT（服务帐户）使](#jwt) 用 [Adobe I/O](https://www.adobe.io/)。[!DNL Adobe I/O] 是Adobe的开发者生态系统和社区。它包含所有Adobe I/O产品](https://www.adobe.io/apis.html)的[Adobe开发工具和API](https://www.adobe.io/apis/experienceplatform.html)和[API。 这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方式。
* [OAuth身份验证（已弃用）](#oauth)。虽然已弃用此方法，但具有现有[!DNL OAuth]集成的客户可以继续使用此方法。

>[!IMPORTANT]
>
>根据身份验证方法，您需要相应地调整请求[!DNL URLs]。 有关您应使用的主机名的详细信息，请参阅[环境](#environments)部分。

## [!DNL JWT] ([!DNL Service Account])使用Adobe I/O  {#jwt}

### Adobe I/O概述{#adobeio}

[!DNL Adobe I/O] 是Adobe的开发者生态系统和社区。它包含所有Adobe I/O产品](https://www.adobe.io/apis.html)的[Adobe开发工具和API](https://www.adobe.io/apis/experienceplatform.html)和[API。

这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方式。

### 先决条件 {#prerequisites}

在配置[!DNL JWT]身份验证之前，请确保您有权访问[Adobe](https://www.adobe.io/)中的[Adobe I/O开发者控制台](https://console.adobe.io/)。 有关访问请求，请与您的组织管理员联系。

### 身份验证{#auth}

请按照以下步骤使用[!DNL Adobe I/O]配置[!DNL JWT (Service Account)]身份验证：

1. 登录到[Adobe开发者控制台](https://console.adobe.io/)。
1. 按照[服务帐户连接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步骤操作。
   * 在[步骤2中：使用服务帐户身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)将API添加到您的项目，选择[!DNL Audience Manager] [!DNL API]选项。
1. 根据[步骤3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的说明进行第一个[!DNL API]调用，以尝试连接。

>[!NOTE]
>
>要以自动方式配置和使用[!DNL Audience Manager] [!DNL REST APIs]，可以编程生成[!DNL JWT]。 有关详细说明，请参见[JWT（服务帐户）Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

## [!DNL OAuth] 身份验证（已弃用）  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 令牌身份验证和通过的 [!DNL OAuth 2.0] 续订现已弃用。
>
> 请改用[JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循令牌身份验证和续订的[!DNL OAuth 2.0]标准。 以下各节介绍如何验证和开始使用[!DNL API]。

### 创建通用[!DNL API]用户{#requirements}

我们建议您创建单独的技术用户帐户，以便与[!DNL Audience Manager] [!DNL API]一起使用。这是一个通用帐户，它不绑定到您组织中的特定用户或与其关联。 此类型的[!DNL API]用户帐户可帮助您完成以下两项任务：

* 确定哪项服务正在调用[!DNL API]（例如，来自您使用我们的[!DNL API]的应用程序或来自发出[!DNL API]请求的其他工具的调用）。
* 提供对[!DNL API]s的不间断访问。与特定人关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的[!DNL API]代码。 未绑定到特定员工的通用帐户可帮助您避免此问题。

作为此类帐户的示例或用例，假设您希望使用[批量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次更改大量区段。 为此，您的用户帐户需要[!DNL API]访问。 请创建一个非特定的[!DNL API]用户帐户，该帐户具有进行[!DNL API]调用所需的凭据、密钥和机密，而不是向特定用户添加权限。 如果您开发自己的使用[!DNL Audience Manager] [!DNL API]的应用程序，这也很有用。

与您的[!DNL Audience Manager]顾问合作，设置通用的[!DNL API]仅用户帐户。

### 密码身份验证工作流{#password-authentication-workflow}

密码身份验证安全访问我们的[!DNL REST API]。 以下步骤概述了在浏览器中从[!DNL JSON]客户端进行密码身份验证的工作流程。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，请加密它们。

#### 第1步：请求[!DNL API]访问

联系您的合作伙伴解决方案经理。 他们将为您提供[!DNL API]客户端ID和机密。 ID和密码将您验证给[!DNL API]。

注意：如果要接收刷新令牌，请在请求[!DNL API]访问时指定此选项。

#### 第2步：请求令牌

将令牌请求传递给首选[!DNL JSON]客户端。 生成请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和机密转换为基64编码字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据`testId : testSecret`将转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下所示：<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求主体：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 第3步：接收令牌

[!DNL JSON]响应包含您的访问令牌。 响应应当如下：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in`键表示访问令牌过期前的秒数。 作为最佳实践，在令牌曝光时使用较短的过期时间限制曝光。

### 刷新令牌{#refresh-token}

在原始令牌过期后刷新令牌续订[!DNL API]访问。 如果请求，密码工作流中的响应[!DNL JSON]包含刷新令牌。 如果您没有收到刷新令牌，请通过密码身份验证过程创建一个新令牌。

您还可以在现有访问令牌过期之前使用刷新令牌生成新令牌。

如果您的访问令牌已过期，您将在响应中收到`401 Status Code`和以下标头：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从浏览器中的[!DNL JSON]客户端创建新访问令牌的工作流。

#### 第1步：请求新令牌

将刷新令牌请求传递给首选[!DNL JSON]客户端。 生成请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和机密转换为基64编码字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据`testId : testSecret`将转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入HTTP头`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下所示：<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在请求主体中，指定`grant_type:refresh_token`并传递您在上一个访问请求中收到的刷新令牌。 请求应当如下：<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 第2步：接收新令牌

[!DNL JSON]响应包含您的新访问令牌。 响应应当如下：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授权码和隐式身份验证{#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支持授权码和隐式身份验证。 要使用这些访问方法，用户需要登录`https://api.demdex.com/oauth/authorize`以获取访问和刷新令牌。

## 进行身份验证[!DNL API]请求{#authenticated-api-requests}

在收到身份验证令牌后调用[!DNL API]方法的要求。

要调用可用的[!DNL API]方法：

* 在`HTTP`标头中，设置`Authorization: Bearer <token>`。
* 使用[JWT（服务帐户）身份验证](#jwt)时，您需要提供`x-api-key`头，该头将与您的`client_id`相同。 您可以从[Adobe I/O集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)页获得`client_id`。
* 调用所需的[!DNL API]方法。

## 可选[!DNL API]查询参数{#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

您可以将这些可选参数与[!DNL API]方法一起使用，这些方法返回对象的&#x200B;*所有*&#x200B;属性。 将查询传递到[!DNL API]时，在请求字符串中设置这些选项。

| 参数 | 描述 |
|--- |--- |
| `page` | 按页码返回结果。 将开始编号为0。 |
| `pageSize` | 设置请求返回的响应结果数（默认为10）。 |
| `sortBy` | 根据指定的[!DNL JSON]属性对结果进行排序和返回。 |
| `descending` | 按降序排序和返回结果。 `ascending` 。 |
| `search` | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您希望在该项目的任何值字段中查找带有“Test”字样的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  可以搜索“[!DNL get all]”方法返回的任何值。 |
| `folderId` | 返回指定文件夹内[!UICONTROL traits]的所有ID。 并非所有方法都可用。 |
| `permissions` | 返回基于指定权限的区段列表。 `READ` 。权限包括：<ul><li>`READ` :返回和视图区段信息。</li><li>`WRITE` :用  `PUT`  于更新区段。</li><li>`CREATE` :用  `POST`  于创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果您要删除属于某个区段的特征，您将需要删除该区段的权限。</li></ul><br>使用不同的键值对指定多个权限。例如，要返回仅具有`READ`和`WRITE`权限的区段列表，请传入`"permissions":"READ"`、`"permissions":"WRITE"`。 |
| `includePermissions` | ([!DNL Boolean])设置为`true`以返回您对区段的权限。 默认值为 `false`. |

### 关于页面选项的注意事项

当页面信息&#x200B;*未指定*&#x200B;时，请求返回纯[!DNL JSON]将生成数组。 如果指定了页面信息&#x200B;**，则返回的列表将包含在[!DNL JSON]对象中，该对象包含有关总结果和当前页面的信息。 您使用页面选项的示例请求可能类似于：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 用于请求、暂存和生产环境以及版本。

## 请求 [!DNL URLs] {#request-urls}

下表按方法列表用于传递[!DNL API]请求的请求[!DNL URLs]。

根据您使用的身份验证方法，您需要根据下表调整请求[!DNL URLs]。

### [!DNL JWT]身份验证{#request-urls-jwt}请求[!DNL URLs]

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

### [!DNL OAuth]身份验证请求[!DNL URLs]（已弃用）{#request-urls-oauth}

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

## 环境{#environments}

[!DNL Audience Manager] [!DNL API]提供对不同工作环境的访问。 这些环境可帮助您针对不同的数据库测试代码，而不影响实时生产数据。 下表列表了可用的[!DNL API]环境和相应的资源主机名。

根据您使用的身份验证方法，您需要根据下表调整环境[!DNL URLs]。

| 环境 | [!DNL JWT]身份验证的主机名 | [!DNL OAuth]身份验证的主机名 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager]测试版环境是生产环境的较小规模的独立版本。 必须在此环境中输入并收集要测试的所有数据。

## 版本 {#versions}

这些[!DNL API]的新版本以常规计划发布。 新版本将增加[!DNL API]版本号。 版本号在请求[!DNL URL]中以`v<version number>`的形式引用，如下例所示：

`https://<host>/v1/...`

## 已定义的响应代码{#response-codes-defined}

`HTTP` 状态代码和由返回的响应文 [!DNL Audience Manager] [!UICONTROL REST API]本

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| `200` | `OK` | 已成功处理请求。 将根据需要返回预期内容或数据。 |
| `201` | `Created` | 已创建资源。 返回`PUT`和`POST`请求。 |
| `204` | `No Content` | 已删除该资源。 响应主体将为空。 |
| `400` | `Bad Request` | 服务器不理解请求。 通常是由于语法格式不正确。 请检查您的请求，然后重试。 |
| `403` | `Forbidden` | 您无权访问该资源。 |
| `404` | `Not Found` | 找不到指定路径的资源。 |
| `409` | `Conflict` | 由于与资源状态发生冲突，无法完成请求。 |
| `500` | `Server Error` | 服务器遇到意外错误，导致它无法完成请求。 |

>[!MORELIKETHIS]
>
>* [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2已简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

