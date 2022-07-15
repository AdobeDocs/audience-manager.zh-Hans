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

# 入门 [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求的信息 [!DNL URLs]、和其他引用。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

使用时必须且应该执行的操作 [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

使用时请注意以下事项 [Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/) 代码：

* **请求参数：** 除非另有指定，否则所有请求参数都是必需的。
* **请求头**:使用 [Adobe Developer](https://www.adobe.io/) 令牌，您必须提供 `x-api-key` 标题。 您可以 [!DNL API] 键 [服务帐户集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 页面。
* **[!DNL JSON]内容类型：** 指定 `content-type: application/json`  *和*  `accept: application/json` 代码中。
* **请求和响应：** 以格式正确的方式发送请求 [!DNL JSON] 对象。 [!DNL Audience Manager] 回复 [!DNL JSON] 格式化的数据。 服务器响应可以包含请求的数据、状态代码或两者。
* **访问：** 您的 [!DNL Audience Manager] 顾问将为您提供客户ID和密钥，以便您能够 [!DNL API] 请求。
* **文档和代码示例：** 中的文本 *斜体* 表示您在制作或接收时提供或传递的变量 [!DNL API] 数据。 替换 *斜体* 文本，其中包含您自己的代码、参数或其他必需信息。

## 身份验证 {#authentication}

的 [!DNL Audience Manager] [!DNL REST APIs] 支持两种身份验证方法。

* [JWT（服务帐户）身份验证](#jwt) 使用 [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] 是Adobe的开发人员生态系统和社区。 包括 [适用于所有Adobe产品的API](https://www.adobe.io/apis.html). 这是设置和使用的推荐方法 [!DNL Adobe] [!DNL APIs].
* [OAuth身份验证（已弃用）](#oauth). 虽然此方法已弃用，但客户现有 [!DNL OAuth] 集成可以继续使用此方法。

>[!IMPORTANT]
>
>根据您的身份验证方法，您需要调整请求 [!DNL URLs] 因此。 请参阅 [环境](#environments) 部分以了解有关您应使用的主机名的详细信息。

## [!DNL JWT] ([!DNL Service Account])使用Adobe Developer进行身份验证 {#jwt}

### Adobe Developer概述 {#adobeio}

[!DNL Adobe Developer] 是Adobe的开发人员生态系统和社区。 包括 [适用于所有Adobe产品的API](https://www.adobe.io/apis.html).

这是设置和使用的推荐方法 [!DNL Adobe] [!DNL APIs].

### 先决条件 {#prerequisites}

在配置之前 [!DNL JWT] 身份验证，确保您有权访问 [Adobe Developer控制台](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). 有关访问请求，请联系您的组织管理员。

### 身份验证 {#auth}

请按照以下步骤配置 [!DNL JWT (Service Account)] 使用验证 [!DNL Adobe Developer]:

1. 登录到 [Adobe Developer控制台](https://console.adobe.io/).
1. 按照 [服务帐户连接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * 期间 [步骤2:使用服务帐户身份验证将API添加到您的项目](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)，选择 [!DNL Audience Manager] [!DNL API] 选项。
1. 通过创建第一个 [!DNL API] 根据 [步骤3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>要配置并使用 [!DNL Audience Manager] [!DNL REST APIs] 以自动方式，您可以生成 [!DNL JWT] 编程。 请参阅 [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 以了解详细说明。

### 技术帐户RBAC权限

如果您的Audience Manager帐户使用 [基于角色的访问控制](../../features/administration/administration-overview.md)，则必须创建一个Audience Manager技术用户帐户，并将其添加到将进行API调用的Audience ManagerRBAC组中。

请按照以下步骤创建技术用户帐户并将其添加到RBAC组：

1. 制作 `GET` 调用 `https://aam.adobe.io/v1/users/self`. 该调用将创建一个技术用户帐户，您可以在 [!UICONTROL Admin Console]，在 [!UICONTROL Users] 页面。

   ![技术帐户](assets/technical-account.png)

1. 登录到您的Audience Manager帐户并 [添加技术用户帐户](../../features/administration/administration-overview.md#create-group) 到要进行API调用的用户组。

## [!DNL OAuth] 身份验证（已弃用） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 通过进行令牌身份验证和续订 [!DNL OAuth 2.0] 现已弃用。
>
> 请使用 [JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt) 中。

的 [!DNL Audience Manager] [!UICONTROL REST API] 如下所示 [!DNL OAuth 2.0] 令牌身份验证和续订的标准。 以下各节介绍如何验证并开始使用 [!DNL API]s.

### 创建通用 [!DNL API] 用户 {#requirements}

我们建议您创建一个单独的技术用户帐户，以便使用 [!DNL Audience Manager] [!DNL API]s.这是一个通用帐户，它未绑定到组织中的特定用户或与其关联。 此类 [!DNL API] 用户帐户可帮助您完成以下两项：

* 识别调用的服务 [!DNL API] (例如，来自使用 [!DNL API]或来自其他 [!DNL API] 请求)。
* 提供对 [!DNL API]s.与特定人员关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的 [!DNL API] 代码。 未与特定员工绑定的通用帐户有助于您避免此问题。

例如，对于此类型的帐户，假设您想要使用 [批量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md). 为此，您的用户帐户需要 [!DNL API] 访问权限。 创建非特定的、 [!DNL API] 具有相应凭据、密钥和密钥的用户帐户 [!DNL API] 调用。 如果您开发的应用程序使用 [!DNL Audience Manager] [!DNL API]s.

使用 [!DNL Audience Manager] 顾问来设置通用， [!DNL API]-only用户帐户。

### 密码验证工作流 {#password-authentication-workflow}

密码验证安全访问我们的 [!DNL REST API]. 以下步骤概述了通过 [!DNL JSON] 客户端。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，则对其进行加密。

#### 步骤1:请求 [!DNL API] 访问

请联系您的合作伙伴解决方案经理。 他们会为您提供 [!DNL API] 客户端ID和密钥。 ID和密钥可对您进行身份验证 [!DNL API].

注意：如果要接收刷新令牌，请在请求时指定 [!DNL API] 访问权限。

#### 步骤2:请求令牌

使用首选项传递令牌请求 [!DNL JSON] 客户。 构建请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`.
* 将您的客户端ID和密钥转换为基于64的编码字符串。 在转换过程中，使用冒号将ID和密钥分隔开。 例如，凭据 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 传入 [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` . 例如，您的标头可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求正文：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步骤3:接收令牌

的 [!DNL JSON] 响应包含您的访问令牌。 响应应如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

的 `expires_in` 键值表示访问令牌过期前的秒数。 最佳做法是，使用较短的过期时间来限制令牌曝光时的曝光。

### 刷新令牌 {#refresh-token}

刷新令牌续订 [!DNL API] 在原始令牌过期后访问。 如果请求，则响应 [!DNL JSON] 在密码工作流中，包含刷新令牌。 如果未收到刷新令牌，请通过密码身份验证过程创建新令牌。

您还可以在现有访问令牌过期之前使用刷新令牌生成新令牌。

如果您的访问令牌已过期，您将收到 `401 Status Code` 和响应中的以下标头：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从创建新访问令牌的工作流 [!DNL JSON] 客户端。

#### 步骤1:请求新令牌

使用首选项传递刷新令牌请求 [!DNL JSON] 客户。 构建请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`.
* 将您的客户端ID和密钥转换为基于64的编码字符串。 在转换过程中，使用冒号将ID和密钥分隔开。 例如，凭据 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 传入HTTP标头 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`. 例如，您的标头可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在请求正文中，指定 `grant_type:refresh_token` 和会传递您在上一个访问请求中收到的刷新令牌。 请求应如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步骤2:接收新令牌

的 [!DNL JSON] 响应包含您的新访问令牌。 响应应如下所示：

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

的 [!DNL Audience Manager] [!UICONTROL REST API] 支持授权代码和隐式身份验证。 要使用这些访问方法，您的用户需要登录到 `https://api.demdex.com/oauth/authorize` 以获取访问和刷新令牌。

## 进行身份验证 [!DNL API] 请求 {#authenticated-api-requests}

调用要求 [!DNL API] 方法。

对可用的 [!DNL API] 方法：

* 在 `HTTP` 标题，设置 `Authorization: Bearer <token>`.
* 使用 [JWT（服务帐户）身份验证](#jwt)，您需要提供 `x-api-key` 标头，与 `client_id`. 您可以 `client_id` 从 [Adobe Developer集成](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 页面。
* 调用所需的 [!DNL API] 方法。

## 可选 [!DNL API] 查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

您可以将这些可选参数与 [!DNL API] 返回的方法 *全部* 对象的属性。 将查询传递到 [!DNL API].

| 参数 | 描述 |
|--- |--- |
| `page` | 按页码返回结果。 编号从0开始。 |
| `pageSize` | 设置请求返回的响应结果数（默认为10）。 |
| `sortBy` | 根据指定的 [!DNL JSON] 属性。 |
| `descending` | 按降序排序和返回结果。 `ascending` 为默认值。 |
| `search` | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您希望在该项目的任何值字段中查找包含“Test”字样的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`.  您可以搜索“[!DNL get all]方法。 |
| `folderId` | 返回的所有ID [!UICONTROL traits] 在指定的文件夹中。 并非对所有方法都可用。 |
| `permissions` | 根据指定的权限返回区段列表。 `READ` 为默认值。 权限包括：<ul><li>`READ` :返回并查看有关区段的信息。</li><li>`WRITE` :使用  `PUT`  更新区段。</li><li>`CREATE` :使用  `POST`  创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，则需要拥有删除该区段的权限。</li></ul><br>使用单独的键值对指定多个权限。 例如，要返回包含  `READ`  和  `WRITE`  仅限权限，传递  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean])设置为 `true` 返回区段的权限。 默认值为 `false`. |

### 关于页面选项的注释

页面信息时 *不是* 指定，则请求返回纯 [!DNL JSON] 导致出现数组。 如果页面信息 *is* 指定，则返回的列表将封装在 [!DNL JSON] 包含有关总结果和当前页面信息的对象。 使用页面选项的示例请求可能类似于以下内容：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 适用于请求、暂存和生产环境和版本。

## 请求 [!DNL URLs] {#request-urls}

下表列出了请求 [!DNL URLs] 过去常传入 [!DNL API] 请求。

根据您使用的身份验证方法，您需要调整请求 [!DNL URLs] 根据下表。

### 请求 [!DNL URLs] 表示 [!DNL JWT] 身份验证 {#request-urls-jwt}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特征：  `https://aam.adobe.io/v1/folders/traits /`<br>区段：  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 请求 [!DNL URLs] 表示 [!DNL OAuth] 身份验证（已弃用） {#request-urls-oauth}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特征：  `https://api.demdex.com/v1/folders/traits /`<br>区段：  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 环境 {#environments}

的 [!DNL Audience Manager] [!DNL API]提供对不同工作环境的访问权限。 这些环境可帮助您针对单独的数据库测试代码，而不会影响实时生产数据。 下表列出了 [!DNL API] 环境和相应的资源主机名。

根据您使用的身份验证方法，您需要调整环境 [!DNL URLs] 根据下表。

| 环境 | 的主机名 [!DNL JWT] 身份验证 | 的主机名 [!DNL OAuth] 身份验证 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>的 [!DNL Audience Manager] 测试版环境是生产环境的较小规模的独立版本。 必须在此环境中输入和收集您要测试的所有数据。

## 版本 {#versions}

这些版本的 [!DNL API]定期发布。 新发行版增加了 [!DNL API] 版本号。 请求中引用的版本号 [!DNL URL] as `v<version number>` 如以下示例所示：

`https://<host>/v1/...`

## 定义的响应代码 {#response-codes-defined}

`HTTP` 状态代码和由返回的响应文本 [!DNL Audience Manager] [!UICONTROL REST API].

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| `200` | `OK` | 请求已成功处理。 将根据需要返回预期的内容或数据。 |
| `201` | `Created` | 已创建资源。 返回 `PUT` 和 `POST` 请求。 |
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

