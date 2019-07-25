---
description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-title: REST API入门
solution: Audience Manager
title: REST API入门
uuid: af0e527e-6eec-449c-9709-f90 e57 d188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **请求参数：** 除非另有指定，否则所有请求参数都是必需的。
* **[!DNL JSON]内容类型：** 指定 `content-type: application/json`*并*`accept: application/json` 在代码中。

* **请求和答复：** 将请求发送为格式正确的 [!DNL JSON] 对象。[!DNL Audience Manager] 响应 [!DNL JSON] 格式数据。服务器响应可以包含请求的数据、状态代码或两者。

* **访问：**[!DNL Audience Manager] 您的顾问将为您提供一个客户ID和允许您 [!DNL API] 提出请求的密钥。

* **文档和代码示例：***斜体文本* 表示您在制作或接收 [!DNL API] 数据时提供或传入的变量。Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. 未绑定到特定员工的通用帐户可帮助您避免此问题。

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>将访问和刷新令牌存储在数据库中。

### 步骤1：请求API访问

联系您的合作伙伴解决方案经理。They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### 步骤2：请求令牌

Pass in a token request with your preferred [!DNL JSON] client. 在您构建请求时：

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 将客户端ID和机密转换为base-64编码的字符串。在转换过程中用冒号分隔ID和机密。For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求主体：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### 步骤3：接收令牌

[!DNL JSON] 响应包含访问令牌。响应应当如下：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` 该键表示访问令牌过期之前的秒数。作为最佳实践，在令牌暴露时使用短截止时间限制曝光。

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. 如果未收到刷新令牌，请通过密码身份验证过程新建一个令牌。

您还可以使用刷新令牌在现有访问令牌过期之前生成新令牌。

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### 步骤1：请求新令牌

Pass in a refresh token request with your preferred [!DNL JSON] client. 在您构建请求时：

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 将客户端ID和机密转换为base-64编码的字符串。在转换过程中用冒号分隔ID和机密。For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### 步骤2：接收新令牌

[!DNL JSON] 响应包含您的新访问令牌。响应应当如下：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ This]
>
>* [OAuth2.0](https://oauth.net/2/)
>* [OAuth简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ This]
>
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

将可选参数设置为返回对象所有属性的方法。

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| 参数 | 描述 |
|--- |--- |
| page | 按页码返回结果。编号从开始开始。 |
| pageSize | 设置请求返回的响应结果数(默认为10)。 |
| SortBy | Sorts and returns results according to the specified [!DNL JSON] property. |
| 降序 | 按降序排序并返回结果。默认为升序。 |
| search | 返回基于要用作搜索参数的指定字符串的结果。例如，假设您要查找在该项目的任何值字段中具有“测试”字样的所有模型的结果。Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  您可以搜索由“get all”方法返回的任何值。 |
| folderID | 返回指定文件夹内特征的所有ID。不适用于所有方法。 |
| 权限 | 根据指定的权限返回区段列表。Read is default.权限包括：<ul><li>`READ` ：返回并查看有关区段的信息。</li><li>`WRITE` ：用于 `PUT` 更新区段。</li><li>`CREATE` ：用于 `POST` 创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征(如果有)。例如，如果要删除区段，您将需要删除属于某个区段的特征。</li></ul><br>指定具有单独键值对的多个权限。For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| 包括权限 | (Boolean)设置为true可返回区段的权限。默认为 false。 |

### 关于页面选项的注释

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. 使用页面选项的示例请求可能类似于：

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 用于请求、暂存和生产环境以及版本。

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| 算法建模 | `https://api.demdex.com/v1/models/` |
| 数据源 | `https://api.demdex.com/v1/datasources/` |
| 派生信号 | `https://api.demdex.com/v1/signals/derived/` |
| 目标 | `https://api.demdex.com/v1/destinations/` |
| 域名 | `https://api.demdex.com/v1/partner-sites/` |
| 文件夹 | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| 架构 | `https://api.demdex.com/v1/schemas/` |
| 区段 | `https://api.demdex.com/v1/segments/` |
| 特征 | `https://api.demdex.com/v1/traits/` |
| 特征类型 | `https://api.demdex.com/v1/customer-trait-types` |
| 分类分类 | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. 这些环境可帮助您针对不同数据库测试代码，而不会影响实时制作数据。The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| 环境 | 主机名 |
|---|---|
| **生产** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Audience Manager beta环境是一个规模较小、独立版本的生产环境。必须在此环境中输入和收集要测试的所有数据。

## 版本 {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` 状态代码和Audience Manager返回的响应文本 [!UICONTROL REST API]。

<!-- r_api_http_response_codes.xml -->

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| 200 | OK | 请求已成功处理。如果需要，将返回预期内容或数据。 |
| 201 | 已创建 | 资源已创建。Returns for `PUT` and `POST` requests. |
| 204 | 无内容 | 资源已被删除。响应正文将为空。 |
| 400 | 错误请求 | 服务器不了解请求。通常是由于语法错误。请检查您的请求，然后重试。 |
| 403 | 禁止访问 | 您无权访问资源。 |
| 404 | 未找到” | 找不到指定路径的资源。 |
| 409 | Conflict | 由于与资源状态发生冲突，此请求无法完成。 |
| 500 | 服务器错误 | 服务器遇到一个意外错误，阻止其完成请求。 |