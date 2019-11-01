---
description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-description: 有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。
seo-title: REST API快速入门
solution: Audience Manager
title: REST API快速入门
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# REST API快速入门 {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求URL和其他引用的信息。

<!-- c_rest_api_overview.xml -->

## API要求和建议 {#api-requirements-recommendations}

使用Audience Manager时必须且应做的 [!DNL API]事。

<!-- aam-api-requirements.xml -->

使用 [Audience Manager API代码时请注意](https://bank.demdex.com/portal/swagger/index.html#/) :

* **** 请求参数：除非另有指定，否则所有请求参数都是必需的。
* **[!DNL JSON]** 内容类型：在 `content-type: application/json` 代 *码中*`accept: application/json` 指定和指定。

* **** 请求和答复：将请求作为格式正确的对象 [!DNL JSON] 发送。 [!DNL Audience Manager] 对格式化的数 [!DNL JSON] 据做出响应。 服务器响应可以包含请求的数据、状态代码或两者。

* **** 访问：您 [!DNL Audience Manager] 的顾问将为您提供客户端ID和密钥，以便您提出 [!DNL API] 请求。

* **** 文档和代码示例：斜体 *文本* ，表示您在创建或接收数据时提供或传入的变 [!DNL API] 量。 将斜 *体文本替换* ，替换为您自己的代码、参数或其他必需信息。

## 建议：创建通用API用户 {#requirements}

我们建议您创建单独的技术用户帐户以与Audience Manager一起 [!DNL API]使用。这是一个通用帐户，它不绑定到组织中的特定用户或与其关联。 此类型的用 [!DNL API] 户帐户可帮助您完成以下两项任务：

* 确定调用哪项服务( [!DNL API] 例如，来自您使用我们的应用程序的调用或来自发出请 [!DNL API]求的其他工具的调 [!DNL API] 用)。
* 提供对s的不间断 [!DNL API]访问。与特定人员关联的帐户在离开您的公司时可能会被删除。 这将阻止您使用可用的代 [!DNL API] 码。 未绑定到特定员工的通用帐户可以帮助您避免此问题。

例如，作为此类帐户的示例或用例，假设您希望使用批量管理工具同时更改大 [量区段](../../reference/bulk-management-tools/bulk-management-intro.md)。 为此，您的用户帐户需要访问 [!DNL API] 权限。 不要向特定用户添加权限，而是创建一个非特定的用户帐户，该帐户具有相应的凭据、密钥和机密进行 [!DNL API][!DNL API] 调用。 如果您开发自己的使用Audience manager的应用程序，这也很有 [!DNL API]用。

与Audience manager顾问合作，设置一个通用的、仅 [!DNL API]限用户帐户。

## OAuth Authentication {#oauth}

Audience Manager遵循令 [!UICONTROL REST API] 牌身份 [!DNL OAuth 2.0] 验证和续订的标准。 以下各节介绍了如何验证和开始使用 [!DNL API]这些。

## 密码身份验证工作流 {#password-authentication-workflow}

<!-- oath-authentication.xml -->

密码身份验证安全访问我们的 [!DNL REST API]。 以下步骤概述了从浏览器中的客户端进行密 [!DNL JSON] 码身份验证的工作流程。

>[!TIP]
>
>如果将访问和刷新令牌存储在数据库中，请加密这些令牌。

### 第1步：请求API访问

联系您的合作伙伴解决方案经理。 他们将为您提供客户 [!DNL API] 端ID和机密。 ID和机密会向您验证身份 [!DNL API]。

注意：如果要接收刷新令牌，请在请求访问时指定该 [!DNL API] 令牌。

### 第2步：请求令牌

将令牌请求传递给首选客 [!DNL JSON] 户端。 构建请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`。
* 将您的客户端ID和机密转换为基本64编码的字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据将 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入标 [!DNL HTTP] 题 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` 。 例如，您的标题可能如下： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求主体：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### 第3步：接收令牌

响应 [!DNL JSON] 包含您的访问令牌。 响应应当如下：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

该 `expires_in` 键表示访问令牌过期前的秒数。 作为最佳实践，如果令牌暴露，请使用较短的过期时间来限制曝光。

## 刷新令牌 {#refresh-token}

在原始令牌 [!DNL API] 过期后刷新令牌续订访问权限。 如果请求，密码工作 [!DNL JSON] 流中的响应包括刷新令牌。 如果您没有收到刷新令牌，请通过口令身份验证过程创建一个新令牌。

您还可以在现有访问令牌过期之前使用刷新令牌生成新令牌。

如果您的访问令牌已过期，您将在响 `401 Status Code` 应中收到以下标题：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从浏览器中的客户端创建新访问令 [!DNL JSON] 牌的工作流。

### 第1步：请求新令牌

将刷新令牌请求传递给您的首选客 [!DNL JSON] 户端。 构建请求时：

* 使用 `POST` 方法调用 `https://api.demdex.com/oauth/token`。
* 将您的客户端ID和机密转换为基本64编码的字符串。 在转换过程中，用冒号分隔ID和机密。 例如，凭据将 `testId : testSecret` 转换为 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入HTTP头 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下： <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* 在请求主体中，指定您 `grant_type:refresh_token` 在上一个访问请求中收到的刷新令牌并传入。 请求应当如下： <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### 第2步：接收新令牌

响 [!DNL JSON] 应包含您的新访问令牌。 响应应当如下：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## 授权码与隐式认证 {#authentication-code-implicit}

Audience manager支持授 [!UICONTROL REST API] 权代码和隐式身份验证。 要使用这些访问方法，您的用户需要登录才能获 `https://api.demdex.com/oauth/authorize` 取访问和刷新令牌。

## 发出实名API请求 {#authenticated-api-requests}

在收到身份验证 [!DNL API] 令牌后调用方法的要求。

<!-- c_oauth_call_methods.xml -->

要调用可用的方法，请执行以下 [!DNL API] 操作：

* 在标题 `HTTP` 中，设置 `Authorization: Bearer <token>`。
* 调用所需的 [!DNL API] 方法。

## 可选API查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

<!-- c_rest_api_optional.xml -->

可以将这些可选参数与返回 [!DNL API] 对象所有属 *性的方* 法一起使用。 将查询传入请求字符串时，在请求字符串中设置这些选项 [!DNL API]。

| 参数 | 描述 |
|--- |--- |
| page | 按页码返回结果。 编号从0开始。 |
| pageSize | 设置请求返回的响应结果数（默认为10）。 |
| sortBy | 根据指定的属性对结果进行排序和返 [!DNL JSON] 回。 |
| 降序 | 按降序排序和返回结果。 默认为升序。 |
| 搜索 | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您要查找所有模型的结果，这些模型在该项目的任何值字段中都有单词“Test”。 您的示例请求可能如下： `GET https://api.demdex.com/v1/models/?search=Test`.  您可以搜索“get all”方法返回的任何值。 |
| folderId | 返回指定文件夹内特征的所有ID。 并非所有方法都可用。 |
| 权限 | 返回基于指定权限的区段列表。  READ是默认值。 权限包括：<ul><li>`READ` :返回并查看有关区段的信息。</li><li>`WRITE` :使用 `PUT` 更新区段。</li><li>`CREATE` :使用 `POST` 创建区段。</li><li>`DELETE` : 删除区段. 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，您将需要删除该区段的权限。</li></ul><br>使用不同的键值对指定多个权限。 例如，要返回仅具有和权限的区 `READ` 段 `WRITE` 列表，请传递 `"permissions":"READ"`、 `"permissions":"WRITE"` 。 |
| includePermissions | （布尔值）设置为true可返回您对区段的权限。 默认为 false。 |

### 关于页面选项的注意事项

当未指定页 *面信息时* ，请求返回数 [!DNL JSON] 组中的纯结果。 如果指定了页 *面信息*[!DNL JSON] ，则返回的列表将打包在一个对象中，该对象包含有关总结果和当前页面的信息。 您使用页面选项的示例请求可能类似于：

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 用于请求、暂存和生产环境以及版本。

<!-- r_rest_urls.xml -->

## 请求URL {#request-urls}

下表按方法列出了用于传入请 [!DNL API] 求的请求URL。

| [!DNL API] 方法 | 请求 [!DNL URL] |
|--- |--- |
| 算法建模 | `https://api.demdex.com/v1/models/` |
| 数据源 | `https://api.demdex.com/v1/datasources/` |
| 派生信号 | `https://api.demdex.com/v1/signals/derived/` |
| 目标 | `https://api.demdex.com/v1/destinations/` |
| 域名 | `https://api.demdex.com/v1/partner-sites/` |
| 文件夹 | 特征： 区 `https://api.demdex.com/v1/folders/traits /`<br>段：  `https://api.demdex.com/v1/folders/segments /` |
| 架构 | `https://api.demdex.com/v1/schemas/` |
| 区段 | `https://api.demdex.com/v1/segments/` |
| 特征 | `https://api.demdex.com/v1/traits/` |
| 特征类型 | `https://api.demdex.com/v1/customer-trait-types` |
| 分类 | `https://api.demdex.com/v1/taxonomies/0/` |

## 环境 {#environments}

通过 [!DNL Audience Manager] s，可 [!DNL API]以访问不同的工作环境。 这些环境可以帮助您针对不同的数据库测试代码，而不影响实时生产数据。 下表列出了可用环境 [!DNL API] 和相应的资源主机名。

| 环境 | 主机名 |
|---|---|
| **生产** | `https://api.demdex.com/...` |
| **测试版** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Audience Manager测试版环境是生产环境的一个较小规模的独立版本。 必须在此环境中输入并收集要测试的所有数据。

## 版本 {#versions}

这些新版本 [!DNL API]将定期发布。 新版本会增加版 [!DNL API] 本号。 版本号在请求URL中引用， `v<version number>` 如下例所示：

`https://<host>/v1/...`

## 已定义响应代码 {#response-codes-defined}

`HTTP` 状态代码和由Audience manager返回的响应文本 [!UICONTROL REST API]。

<!-- r_api_http_response_codes.xml -->

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| 200 | OK | 请求已成功处理。 将根据需要返回预期内容或数据。 |
| 201 | 已创建 | 已创建资源。 返回和 `PUT` 请 `POST` 求。 |
| 204 | 无内容 | 已删除该资源。 响应主体将为空。 |
| 400 | 错误请求 | 服务器不理解请求。 通常由于语法格式错误。 请检查您的请求，然后重试。 |
| 403 | 禁止访问 | 您无权访问资源。 |
| 404 | 未找到” | 找不到指定路径的资源。 |
| 409 | 冲突 | 由于与资源状态发生冲突，无法完成请求。 |
| 500 | 服务器错误 | 服务器遇到意外错误，导致其无法完成请求。 |

>[!MORELIKETHIS]
>
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2简化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

