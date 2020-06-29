---
description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-title: 开始使用 REST API
solution: Audience Manager
title: 开始使用 REST API
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1761'
ht-degree: 3%

---


# Getting Started with [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请 [!DNL URLs]求和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

在使用s时，您必须且应该做的 [!DNL Audience Manager] 事 [!DNL API]情。

<!-- aam-api-requirements.xml -->

使用Audience ManagerAPI代码时 [请注意](https://bank.demdex.com/portal/swagger/index.html#/) :

* **请求参数：** 除非另有指定，否则所有请求参数都是必需的。
* **请求标题**: 使用 [Adobe I/O令牌](https://www.adobe.io/) ，必须提供标 `x-api-key` 头。 您可以按照 [!DNL API] 服务帐户集成页中的说 [明获取密钥](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* **[!DNL JSON]内容类型：**在`content-type: application/json`代&#x200B;*码*`accept: application/json`中指定。
* **请求和答复：** 将请求作为格式正确的对象 [!DNL JSON] 发送。 [!DNL Audience Manager] 用格式化的 [!DNL JSON] 数据做出响应。 服务器响应可以包含请求的数据、状态代码或两者。
* **访问：** 您 [!DNL Audience Manager] 的顾问将为您提供客户端ID和密钥，以便您进行 [!DNL API] 请求。
* **文档和代码示例：** 斜体 *文本* 表示您在创建或接收数据时提供或传递的 [!DNL API] 变量。 将斜 *体文本* 替换为您自己的代码、参数或其他必需信息。

## 身份验证 {#authentication}

支持 [!DNL Audience Manager] 两种 [!DNL REST APIs] 身份验证方法。

* [JWT（服务帐户）身份验证](#jwt)。 这是推荐的身份验证方法。
* [OAuth身份验证（已弃用）](#oauth)。 虽然此方法已弃用，但具有现有集成 [!DNL OAuth] 的客户可以继续使用此方法。

>[!IMPORTANT]
>
>根据身份验证方法，您需要相应地调整您的 [!DNL URLs] 请求。 有关应 [使用的](#environments) 主机名的详细信息，请参阅环境部分。

## [!DNL JWT] ([!DNL Service Account])身份验证 {#jwt}

### 先决条件 {#prerequisites}

在配置身份 [!DNL JWT] 验证之前，请确保您有权访 [问Adobe开发人员控制台](https://console.adobe.io/)。 有关访问请求，请与您的组织管理员联系。

### 身份验证

请按照以下步骤配置身 [!DNL JWT (Service Account)] 份验证：

1. 登录Adobe开 [发人员控制台](https://console.adobe.io/)。
1. 按照服务帐户连 [接中的步骤操作](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。
   * 在第 [2步中： 使用服务帐户身份验证将API添加到您的项目](https://www.adobe.io/authentication/auth-methods.html#step-2-add-an-api-to-your-project-using-service-account-authentication)，选择 [!DNL Audience Manager][!DNL API] 选项。
1. 根据步骤3中的说明进行第 [!DNL API] 一次呼叫，尝试 [连接](https://www.adobe.io/authentication/auth-methods.html#step-3-try-it.)。

>[!NOTE]
>
>要以自动方式配置和 [!DNL Audience Manager] 使 [!DNL REST APIs] 用，您可以以编程方式生成 [!DNL JWT] 。 有关 [详细说明，请参阅JWT(服务帐户](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) )身份验证。

## [!DNL OAuth] 身份验证（已弃用） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 令牌身份验证和通过的 [!DNL OAuth 2.0] 续订现已弃用。
>
> 请改 [用JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt) 。

令牌 [!DNL Audience Manager] 身 [!UICONTROL REST API] 份验 [!DNL OAuth 2.0] 证和续订遵循标准。 以下各节介绍如何验证和使用的 [!DNL API]开始。

### 创建通用用 [!DNL API] 户 {#requirements}

我们建议您创建单独的技术用户帐户，以便与 [!DNL Audience Manager][!DNL API]s一起使用。 这是一个通用帐户，它未绑定到您组织中的特定用户或与其关联。 此类型的用 [!DNL API] 户帐户可帮助您完成以下两项任务：

* 确定呼叫哪项服务( [!DNL API] 例如，来自您使用我们的应用程序的呼叫 [!DNL API]或来自发出请求的其他工 [!DNL API] 具的呼叫)。
* 不间断地访问 [!DNL API]s。 与特定人员关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的代 [!DNL API] 码。 未绑定到特定员工的通用帐户可帮助您避免此问题。

作为此类帐户的示例或用例，假设您希望使用批量管理工具一次更改大 [量段](../../reference/bulk-management-tools/bulk-management-intro.md)。 为此，您的用户帐户需要访 [!DNL API] 问权。 不要向特定用户添加权限，而是创建一个非特定的 [!DNL API] 用户帐户，该帐户具有相应的凭据、密钥和密码进行 [!DNL API] 呼叫。 如果您开发自己的使用s的应用程序，这也很 [!DNL Audience Manager] 有 [!DNL API]用。

请与顾问 [!DNL Audience Manager] 合作，以设置仅限通用 [!DNL API]用户帐户。

### 密码身份验证工作流 {#password-authentication-workflow}

密码身份验证安全访问我 [!DNL REST API]们。 以下步骤概述了在浏览器中从客户端进 [!DNL JSON] 行口令身份验证的工作流。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，请加密它们。

#### 第1步： 请求访 [!DNL API] 问

联系您的合作伙伴解决方案经理。 他们会向您提供客 [!DNL API] 户ID和机密。 ID和密码将您验证到 [!DNL API]。

注意： 如果要接收刷新令牌，请在请求访问时指定该 [!DNL API] 令牌。

#### 第2步： 请求令牌

将令牌请求传递给您的首选客 [!DNL JSON] 户机。 生成请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`。
* 将客户端ID和机密转换为基64编码字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据将 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 在和 [!DNL HTTP] 中 [!DNL headers] 传 `Authorization:Basic <base-64 clientID:clientSecret>` 递 `Content-Type: application/x-www-form-urlencoded` 。 例如，您的标题可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求主体：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 第3步： 接收令牌

响应 [!DNL JSON] 包含您的访问令牌。 响应应如下：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

该 `expires_in` 键表示访问令牌过期前的秒数。 作为最佳实践，如果令牌暴露，请使用较短的过期时间来限制暴露。

### 刷新令牌 {#refresh-token}

在原始令牌 [!DNL API] 过期后刷新令牌续订访问。 如果请求，密码工 [!DNL JSON] 作流中的响应包括刷新令牌。 如果您没有收到刷新令牌，请通过口令身份验证过程创建一个新令牌。

您还可以在现有访问令牌过期之前使用刷新令牌生成新令牌。

如果您的访问令牌已过期，您将在 `401 Status Code` 响应中收到以下标题：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从浏览器中的客户端创建新访问令牌 [!DNL JSON] 的工作流。

#### 第1步： 请求新令牌

将刷新令牌请求传递给您的首选客 [!DNL JSON] 户端。 生成请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`。
* 将客户端ID和机密转换为基64编码字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据将 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入HTTP头 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在请求主体中，指 `grant_type:refresh_token` 定您在上一个访问请求中收到的刷新令牌并传递。 请求应当如下： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 第2步： 接收新令牌

响 [!DNL JSON] 应包含新访问令牌。 响应应如下：

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

支持 [!DNL Audience Manager] 授权 [!UICONTROL REST API] 代码和隐式身份验证。 要使用这些访问方法，用户需要登录才能 `https://api.demdex.com/oauth/authorize` 获取访问和刷新令牌。

## 发出经过身份验证 [!DNL API] 的请求 {#authenticated-api-requests}

在收到身份验证 [!DNL API] 令牌后调用方法的要求。

要调用可用的方 [!DNL API] 法：

* 在标题 `HTTP` 中，设置 `Authorization: Bearer <token>`。
* 使用 [JWT（服务帐户）身份验证](#jwt)，您需要提供 `x-api-key` 与您的头相同的头 `client_id`。 您可以从Adobe `client_id` I/ [O集成页面获取](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* 调用所需的 [!DNL API] 方法。

## 可选 [!DNL API] 查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

可以将这些可选参数与返 [!DNL API] 回对象所 *有属性* 的方法结合使用。 将查询传递到请求字符串时，在中设置这些选项 [!DNL API]。

| 参数 | 描述 |
|--- |--- |
| `page` | 按页码返回结果。 开始编号为0。 |
| `pageSize` | 设置请求返回的响应结果数（默认为10）。 |
| `sortBy` | 根据指定的属性对结果进行排序并返回 [!DNL JSON] 结果。 |
| `descending` | 按降序排序和返回结果。 `ascending` 。 |
| `search` | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您要在该项目的任何值字段中查找带有“Test”字样的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`.  您可以搜索“”方法返回的任何[!DNL get all]值。 |
| `folderId` | 返回指定文件夹 [!UICONTROL traits] 内的所有ID。 并非所有方法都可用。 |
| `permissions` | 返回基于指定权限的区段列表。 `READ` 。 权限包括：<ul><li>`READ` : 有关区段的返回和视图信息。</li><li>`WRITE` : 用 `PUT` 于更新区段。</li><li>`CREATE` : 用 `POST` 于创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，您将需要有权删除该特征。</li></ul><br>使用不同的键值对指定多个权限。 例如，要返回仅具有和权限的列表 `READ` 段， `WRITE` 请传入 `"permissions":"READ"`, `"permissions":"WRITE"` 。 |
| `includePermissions` | ([!DNL Boolean])设置为 `true` 返回您对区段的权限。 默认值为 `false`. |

### 关于页面选项的注意事项

当未指定页 *面信息* 时，请求返回 [!DNL JSON] 数组中的纯结果。 如果指定 *了页面信* 息 [!DNL JSON] ，则返回的列表将打包在一个对象中，该对象包含有关总结果和当前页面的信息。 使用页面选项的示例请求可能与以下内容类似：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 用于请求、暂存和生产环境以及版本。

## 请求 [!DNL URLs] {#request-urls}

下表按方法列表 [!DNL URLs] 用于传递请 [!DNL API] 求的请求。

根据您使用的身份验证方法，您需要根据下 [!DNL URLs] 表调整请求。

### 身份 [!DNL URLs] 验证 [!DNL JWT] 请求 {#request-urls-jwt}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特征：  `https://aam.adobe.io/v1/folders/traits /`<br>细分：  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 身份 [!DNL URLs] 验证 [!DNL OAuth] 请求（已弃用） {#request-urls-oauth}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特征：  `https://api.demdex.com/v1/folders/traits /`<br>细分：  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 环境 {#environments}

s提 [!DNL Audience Manager][!DNL API]供对不同工作环境的访问。 这些环境可以帮助您针对不同的数据库测试代码，而不影响实时生产数据。 下表列表了可用的 [!DNL API] 环境和相应的资源主机名。

根据您使用的身份验证方法，您需要根据下表 [!DNL URLs] 调整环境。

| 环境 | 身份验证的主 [!DNL JWT] 机名 | 身份验证的主 [!DNL OAuth] 机名 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **测试版** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>测 [!DNL Audience Manager] 试版环境是生产环境的小型独立版本。 必须在此环境中输入和收集要测试的所有数据。

## 版本 {#versions}

这些新版本 [!DNL API]将定期发布计划。 新版本会增加版 [!DNL API] 本号。 版本号在请求中引用 [!DNL URL] , `v<version number>` 如以下示例所示：

`https://<host>/v1/...`

## 已定义响应代码 {#response-codes-defined}

`HTTP` 状态代码和由返回的响应文 [!DNL Audience Manager][!UICONTROL REST API]本

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| `200` | `OK` | 请求已成功处理。 将根据需要返回预期内容或数据。 |
| `201` | `Created` | 已创建资源。 返回 `PUT` 和 `POST` 请求。 |
| `204` | `No Content` | 已删除资源。 响应主体将为空。 |
| `400` | `Bad Request` | 服务器不理解请求。 通常是由于语法格式不正确。 请检查您的请求，然后重试。 |
| `403` | `Forbidden` | 您无权访问资源。 |
| `404` | `Not Found` | 找不到指定路径的资源。 |
| `409` | `Conflict` | 由于与资源状态发生冲突，无法完成请求。 |
| `500` | `Server Error` | 服务器遇到意外错误，导致其无法完成请求。 |

>[!MORELIKETHIS]
>
>* [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2已简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

