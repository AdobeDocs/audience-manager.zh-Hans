---
description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-title: REST API入门
solution: Audience Manager
title: REST API入门
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: e51a4302808958093342170d513701ac1547c275
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 3%

---


# REST API入门 {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API 要求和建议 {#api-requirements-recommendations}

与受众经理合作时，您必须且应做的 [!DNL API]事情。

<!-- aam-api-requirements.xml -->

使用受众管理器API代 [码时请注意](https://bank.demdex.com/portal/swagger/index.html#/) :

* **请求参数：** 除非另有指定，否则所有请求参数都是必需的。
* **请求标题**: 使用 [Adobe I/O令牌](https://www.adobe.io/) ，必须提供标 `x-api-key` 头。 您可以按照“服务帐户集成”页中的说明 [获取API密钥](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* **[!DNL JSON]内容类型：**在`content-type: application/json`代&#x200B;*码*`accept: application/json`中指定。

* **请求和答复：** 将请求作为格式正确的对象 [!DNL JSON] 发送。 [!DNL Audience Manager] 用格式化的 [!DNL JSON] 数据做出响应。 服务器响应可以包含请求的数据、状态代码或两者。

* **访问：** 您 [!DNL Audience Manager] 的顾问将为您提供客户端ID和密钥，以便您进行 [!DNL API] 请求。

* **文档和代码示例：** 斜体 *文本* 表示您在创建或接收数据时提供或传递的 [!DNL API] 变量。 将斜 *体文本* 替换为您自己的代码、参数或其他必需信息。

## 身份验证 {#authentication}

受众管理器REST API支持两种身份验证方法。

* [JWT（服务帐户）身份验证](#jwt)。 这是推荐的身份验证方法。
* [OAuth身份验证（已弃用）](#oauth)。 虽然此方法已弃用，但具有现有OAuth集成的客户可以继续使用此方法。

>[!IMPORTANT]
>
>根据身份验证方法，您需要相应地调整请求URL。 有关应 [使用的](#environments) 主机名的详细信息，请参阅环境部分。

## JWT（服务帐户）身份验证 {#jwt}

### 先决条件 {#prerequisites}

在配置JWT身份验证之前，请确保您有权访问Adobe [开发人员控制台](https://console.adobe.io/)。 有关访问请求，请与您的组织管理员联系。

### 身份验证

请按照以下步骤配置JWT（服务帐户）身份验证：

1. 登录Adobe开 [发人员控制台](https://console.adobe.io/)。
1. 按照服务帐户连 [接中的步骤操作](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。
   * 在第 [2步中： 使用服务帐户身份验证将API添加到项目](https://www.adobe.io/authentication/auth-methods.html#step-2-add-an-api-to-your-project-using-service-account-authentication)，选择受众管理器API选项。
1. 根据步骤3中的说明进行第一个API调用，以尝试 [连接](https://www.adobe.io/authentication/auth-methods.html#step-3-try-it.)。

>[!NOTE]
>
>要以自动方式配置和使用受众管理器REST API，可以编程生成JWT。 有关 [详细说明，请参阅JWT(服务帐户](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) )身份验证。

## OAuth身份验证（已弃用） {#oauth}

>[!WARNING]
> 受众管 [!UICONTROL REST API] 理器令牌身份验证和续订 [!DNL OAuth 2.0] 方式现已弃用。
>
> 请改 [用JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt) 。

受众管理 [!UICONTROL REST API] 器遵 [!DNL OAuth 2.0] 循令牌身份验证和续订标准。 以下各节介绍如何验证和使用的 [!DNL API]开始。

### 创建通用API用户 {#requirements}

我们建议您创建单独的技术用户帐户以与受众管理器 [!DNL API]配合。 这是一个通用帐户，它未绑定到您组织中的特定用户或与其关联。 此类型的用 [!DNL API] 户帐户可帮助您完成以下两项任务：

* 确定呼叫哪项服务( [!DNL API] 例如，来自您使用我们的应用程序的呼叫 [!DNL API]或来自发出请求的其他工 [!DNL API] 具的呼叫)。
* 不间断地访问 [!DNL API]s。 与特定人员关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的代 [!DNL API] 码。 未绑定到特定员工的通用帐户可帮助您避免此问题。

作为此类帐户的示例或用例，假设您希望使用批量管理工具一次更改大 [量段](../../reference/bulk-management-tools/bulk-management-intro.md)。 为此，您的用户帐户需要访 [!DNL API] 问权。 不要向特定用户添加权限，而是创建一个非特定的 [!DNL API] 用户帐户，该帐户具有相应的凭据、密钥和密码进行 [!DNL API] 呼叫。 如果您开发自己的使用受众管理器的应用程序，这也很 [!DNL API]有用。

请与受众经理顾问合作，以设置仅限通用 [!DNL API]用户帐户。

### 密码身份验证工作流 {#password-authentication-workflow}

<!-- oath-authentication.xml -->

密码身份验证安全访问我 [!DNL REST API]们。 以下步骤概述了在浏览器中从客户端进 [!DNL JSON] 行口令身份验证的工作流。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，请加密它们。

#### 第1步： 请求API访问

联系您的合作伙伴解决方案经理。 他们会向您提供客 [!DNL API] 户ID和机密。 ID和密码将您验证到 [!DNL API]。

注意： 如果要接收刷新令牌，请在请求访问时指定该 [!DNL API] 令牌。

#### 第2步： 请求令牌

将令牌请求传递给您的首选客 [!DNL JSON] 户机。 生成请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`。
* 将客户端ID和机密转换为基64编码字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据将 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入标 [!DNL HTTP] 题 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` 。 例如，您的标题可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
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
* 传入HTTP头 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下所示： <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* 在请求主体中，指 `grant_type:refresh_token` 定您在上一个访问请求中收到的刷新令牌并传递。 请求应当如下： <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

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

受众管理器支 [!UICONTROL REST API] 持授权代码和隐式身份验证。 要使用这些访问方法，用户需要登录才能 `https://api.demdex.com/oauth/authorize` 获取访问和刷新令牌。

## 发出经过身份验证的API请求 {#authenticated-api-requests}

在收到身份验证 [!DNL API] 令牌后调用方法的要求。

<!-- c_oauth_call_methods.xml -->

要调用可用的方 [!DNL API] 法：

* 在标题 `HTTP` 中，设置 `Authorization: Bearer <token>`。
* 使用 [JWT（服务帐户）身份验证](#jwt)，您需要提供 `x-api-key` 与您的头相同的头 `client_id`。 您可以从Adobe `client_id` I/ [O集成页面获取](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* 调用所需的 [!DNL API] 方法。

## 可选API查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

<!-- c_rest_api_optional.xml -->

可以将这些可选参数与返 [!DNL API] 回对象所 *有属性* 的方法结合使用。 将查询传递到请求字符串时，在中设置这些选项 [!DNL API]。

| 参数 | 描述 |
|--- |--- |
| page | 按页码返回结果。 开始编号为0。 |
| pageSize | 设置请求返回的响应结果数（默认为10）。 |
| 排序依据 | 根据指定的属性对结果进行排序并返回 [!DNL JSON] 结果。 |
| 降序 | 按降序排序和返回结果。 升序为默认值。 |
| 搜索 | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您要在该项目的任何值字段中查找带有“Test”字样的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`.  您可以搜索“get all”方法返回的任何值。 |
| folderId | 返回指定文件夹内特征的所有ID。 并非所有方法都可用。 |
| 权限 | 返回基于指定权限的区段列表。  READ是默认值。 权限包括：<ul><li>`READ` : 有关区段的返回和视图信息。</li><li>`WRITE` : 用 `PUT` 于更新区段。</li><li>`CREATE` : 用 `POST` 于创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，您将需要有权删除该特征。</li></ul><br>使用不同的键值对指定多个权限。 例如，要返回仅具有和权限的列表 `READ` 段， `WRITE` 请传入 `"permissions":"READ"`, `"permissions":"WRITE"` 。 |
| includePermissions | （布尔值）设置为true可返回您对区段的权限。 默认为 false。 |

### 关于页面选项的注意事项

当未指定页 *面信息* 时，请求返回 [!DNL JSON] 数组中的纯结果。 如果指定 *了页面信* 息 [!DNL JSON] ，则返回的列表将打包在一个对象中，该对象包含有关总结果和当前页面的信息。 使用页面选项的示例请求可能与以下内容类似：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 用于请求、暂存和生产环境以及版本。

<!-- r_rest_urls.xml -->

## 请求URL {#request-urls}

下表按方法列表用于传递请 [!DNL API] 求的请求URL。

根据您使用的身份验证方法，您需要根据下表调整请求URL。

### 请求JWT身份验证的URL {#request-urls-jwt}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| 算法建模 | `https://aam.adobe.io/v1/models/` |
| 数据源 | `https://aam.adobe.io/v1/datasources/` |
| 派生信号 | `https://aam.adobe.io/v1/signals/derived/` |
| 目标 | `https://aam.adobe.io/v1/destinations/` |
| 域名 | `https://aam.adobe.io/v1/partner-sites/` |
| 文件夹 | 特征：  `https://aam.adobe.io/v1/folders/traits /`<br>细分：  `https://aam.adobe.io/v1/folders/segments /` |
| 模式 | `https://aam.adobe.io/v1/schemas/` |
| 区段 | `https://aam.adobe.io/v1/segments/` |
| 特征 | `https://aam.adobe.io/v1/traits/` |
| 特征类型 | `https://aam.adobe.io/v1/customer-trait-types` |
| 分类学 | `https://aam.adobe.io/v1/taxonomies/0/` |

### 请求OAuth身份验证的URL（已弃用） {#request-urls-oauth}

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| 算法建模 | `https://api.demdex.com/v1/models/` |
| 数据源 | `https://api.demdex.com/v1/datasources/` |
| 派生信号 | `https://api.demdex.com/v1/signals/derived/` |
| 目标 | `https://api.demdex.com/v1/destinations/` |
| 域名 | `https://api.demdex.com/v1/partner-sites/` |
| 文件夹 | 特征：  `https://api.demdex.com/v1/folders/traits /`<br>细分：  `https://api.demdex.com/v1/folders/segments /` |
| 模式 | `https://api.demdex.com/v1/schemas/` |
| 区段 | `https://api.demdex.com/v1/segments/` |
| 特征 | `https://api.demdex.com/v1/traits/` |
| 特征类型 | `https://api.demdex.com/v1/customer-trait-types` |
| 分类学 | `https://api.demdex.com/v1/taxonomies/0/` |

## 环境 {#environments}

s提 [!DNL Audience Manager][!DNL API]供对不同工作环境的访问。 这些环境可以帮助您针对不同的数据库测试代码，而不影响实时生产数据。 下表列表了可用的 [!DNL API] 环境和相应的资源主机名。

根据您使用的身份验证方法，您需要根据下表调整环境URL。

| 环境 | JWT身份验证的主机名 | OAuth身份验证的主机名 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **测试版** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |


>[!NOTE]
>
>受众管理器测试版环境是生产环境的小型独立版本。 必须在此环境中输入和收集要测试的所有数据。

## 版本 {#versions}

这些新版本 [!DNL API]将定期发布计划。 新版本会增加版 [!DNL API] 本号。 版本号在请求URL中引用， `v<version number>` 如以下示例所示：

`https://<host>/v1/...`

## 已定义响应代码 {#response-codes-defined}

`HTTP` 状态代码和受众管理器返回的响应文本 [!UICONTROL REST API]。

<!-- r_api_http_response_codes.xml -->

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| 200 | OK | 请求已成功处理。 将根据需要返回预期内容或数据。 |
| 201 | 已创建 | 已创建资源。 返回 `PUT` 和 `POST` 请求。 |
| 204 | 无内容 | 已删除资源。 响应主体将为空。 |
| 400 | 错误请求 | 服务器不理解请求。 通常是由于语法格式不正确。 请检查您的请求，然后重试。 |
| 403 | 禁止访问 | 您无权访问资源。 |
| 404 | 未找到” | 找不到指定路径的资源。 |
| 409 | 冲突 | 由于与资源状态发生冲突，无法完成请求。 |
| 500 | 服务器错误 | 服务器遇到意外错误，导致其无法完成请求。 |

>[!MORELIKETHIS]
>
>* [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2已简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

