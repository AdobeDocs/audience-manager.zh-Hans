---
description: 有关一般要求、身份验证、可选查询参数、请求 URL 和其他引用的信息。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: 开始使用 REST API
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 1%

---

# 开始使用[!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有关一般要求、身份验证、可选查询参数、请求[!DNL URLs]和其他引用的信息。

## API要求和建议 {#api-requirements-recommendations}

使用[Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/)代码时，请注意以下事项：

* **请求参数：**&#x200B;除非另有指定，否则所有请求参数都是必需的。
* **请求标头**：使用[Adobe Developer](https://www.adobe.io/)令牌时，必须提供`x-api-key`标头。 您可以按照[!DNL API]服务帐户集成[页面中的说明获取](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)密钥。
* **[!DNL JSON]内容类型：**&#x200B;在您的代码中指定`content-type: application/json` *和* `accept: application/json`。
* **请求和响应：**&#x200B;将请求作为正确格式化的[!DNL JSON]对象发送。 [!DNL Audience Manager]使用[!DNL JSON]格式的数据进行响应。 服务器响应可以包含请求的数据、状态代码或同时包含这两者。
* **访问：**&#x200B;您的[!DNL Audience Manager]顾问将为您提供客户端ID和密钥，以便您发出[!DNL API]请求。
* **文档和代码示例：**&#x200B;斜体&#x200B;*中的文本*&#x200B;表示在生成或接收[!DNL API]数据时提供或传入的变量。 将&#x200B;*斜体*&#x200B;文本替换为您自己的代码、参数或其他必需的信息。

## 身份验证 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支持三种身份验证方法。

* [!BADGE 推荐]{type=positive} [OAuth服务器到服务器身份验证](#oauth-adobe-developer)，使用[Adobe开发人员控制台](https://www.adobe.io/)。 [!DNL Adobe Developer]是Adobe的开发人员生态系统和社区。 它包含所有Adobe产品的[API](https://developer.adobe.com/apis/)。 这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方法。 有关[OAuth服务器到服务器身份验证](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)的更多信息，请参阅Adobe开发人员文档。
* 使用[!BADGE Adobe开发人员控制台]{type=negative}的[已弃用](#jwt) [JWT（服务帐户）身份验证](https://www.adobe.io/)。 [!DNL Adobe Developer]是Adobe的开发人员生态系统和社区。 它包含所有Adobe产品的[API](https://developer.adobe.com/apis/)。
* [!BADGE 已弃用]{type=negative} [旧版OAuth身份验证](#oauth-deprecated)。 虽然此方法已弃用，但具有现有[!DNL OAuth]集成的客户可以继续使用此方法。

>[!IMPORTANT]
>
>根据您的身份验证方法，您需要相应地调整请求[!DNL URLs]。 有关应使用的主机名的详细信息，请参阅[环境](#environments)部分。

## 使用Adobe Developer的OAuth服务器到服务器身份验证 {#oauth-adobe-developer}

本节介绍如何收集所需的凭据来验证Audience Manager API调用，如下面的流程图中所述。 您可以在初始一次性设置中收集大多数所需的凭据。 但是，必须每24小时刷新一次访问令牌。

![Audience Manager身份验证流程图。](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer概述 {#developer-overview}

[!DNL Adobe Developer]是Adobe的开发人员生态系统和社区。 它包含所有Adobe产品的[API](https://developer.adobe.com/apis)。

这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方法。

### 先决条件 {#prerequisites-server-to-server}

在配置[!DNL OAuth Server-to-Server]身份验证之前，请确保您有权访问[Adobe Developer](https://developer.adobe.com/console/home)中的[Adobe Developer Console](https://developer.adobe.com/)。 有关访问请求，请联系您的组织管理员。

### 身份验证 {#oauth}

请按照以下步骤使用[!DNL OAuth Server-to-Server]配置[!DNL Adobe Developer]身份验证：

1. 登录到[Adobe Developer Console](https://developer.adobe.com/console/home)。
1. 按照[OAuth服务器到服务器凭据实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)中的步骤操作。
   * 在[步骤2：使用服务帐户身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)将API添加到您的项目中，选择[!DNL Audience Manager] [!DNL API]选项。
1. 根据[!DNL API]步骤3[中的说明进行第一个](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)调用以尝试连接。

>[!NOTE]
>
>要自动配置和使用[!DNL Audience Manager] [!DNL REST APIs]，您可以以编程方式轮换客户端密钥。 有关详细说明，请参阅[开发人员文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically)。

### 将Audience Manager API添加到项目 {#add-aam-api-to-project}

转到[Adobe Developer Console](https://www.adobe.com/go/devs_console_ui)并使用您的Adobe ID登录。 接下来，按照Adobe Developer Console文档中有关[创建空项目](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/)的教程中概述的步骤进行操作。

创建新项目后，在&#x200B;**[!UICONTROL Add API]**&#x200B;屏幕上选择&#x200B;**[!UICONTROL Project Overview]**。

>[!TIP]
>
>如果您配置了多个组织，请使用界面右上角的组织选择器，以确保您在所需的组织中。

突出显示了“添加API”选项的![Developer Console屏幕。](/help/using/api/rest-api-main/assets/add-api.png)

出现&#x200B;**[!UICONTROL Add an API]**&#x200B;屏幕。 选择Adobe Experience Cloud的产品图标，然后选择&#x200B;**[!UICONTROL Audience Manager API]**&#x200B;再选择&#x200B;**[!UICONTROL Next]**。

![选择Audience Manager API。](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>选择&#x200B;**[!UICONTROL View docs]**&#x200B;选项可在单独的浏览器窗口中导航到完整的[Audience Manager API参考文档](https://bank.demdex.com/portal/swagger/index.html#)。

### 选择OAuth服务器到服务器身份验证类型 {#select-oauth-server-to-server}

接下来，选择身份验证类型以生成访问令牌并访问Audience Manager API。

>[!IMPORTANT]
>
>选择&#x200B;**[!UICONTROL OAuth Server-to-Server]**&#x200B;方法，因为这将是今后唯一支持的方法。 **[!UICONTROL Service Account (JWT)]**&#x200B;方法已弃用。 虽然使用JWT身份验证方法的集成将继续工作到2025年1月1日，但Adobe强烈建议您在该日期之前将现有集成迁移到新的OAuth服务器到服务器方法。

![选择OAuth身份验证方法。](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### 为您的集成选择产品配置文件 {#select-product-profiles}

在&#x200B;**[!UICONTROL Configure API]**&#x200B;屏幕中，选择所需的产品配置文件。 通过此处所选的产品配置文件，您的集成服务帐户将获得对精细功能的访问权限。

![为您的集成选择产品配置文件。](/help/using/api/rest-api-main/assets/select-product-profiles.png)

准备就绪后选择&#x200B;**[!UICONTROL Save configured API]**。

### 收集凭据 {#gather-credentials}

将API添加到项目后，项目的&#x200B;**[!UICONTROL Audience Manager API]**&#x200B;页面将显示所有调用Audience Manager API时所需的以下凭据：

在Developer Console中添加API后的![集成信息。](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## 生成访问令牌 {#generate-access-token}

下一步是生成用于Audience Manager API调用的`{ACCESS_TOKEN}`凭据。 与`{API_KEY}`和`{ORG_ID}`的值不同，必须每24小时生成一个新令牌才能继续使用Audience Manager API。 选择&#x200B;**[!UICONTROL Generate access token]**，如下所示。

![显示如何生成访问令牌](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## 测试API调用 {#test-api-call}

获取身份验证持有者令牌后，执行API调用以测试您现在是否可以访问Audience Manager API。

1. 导航到[API参考文档](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_)。
2. 选择&#x200B;**[!UICONTROL Authorize]**&#x200B;并粘贴您在[生成访问令牌](#generate-access-token)步骤中获得的访问令牌。

   ![授权API调用](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. 执行GET对`/datasources` API端点的调用，以检索所有全局可用数据源的列表，如[API参考文档](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_)中所述。 依次选择&#x200B;**[!UICONTROL Try it out]**&#x200B;和&#x200B;**[!UICONTROL Execute]**，如下所示。

   ![执行API调用](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API请求]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>如果使用正确的持有者令牌，[!TAB API响应]


使用有效的访问令牌时，API端点会返回200响应以及包含您的组织有权访问的所有全局数据源的响应正文。

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE 已弃用]{type=negative} [!DNL JWT] ([!DNL Service Account])使用Adobe Developer的身份验证 {#jwt}

+++ 查看有关已弃用的[!DNL JWT] ([!DNL Service Account])获取身份验证令牌方法的信息。

### Adobe Developer概述 {#adobeio}

[!DNL Adobe Developer]是Adobe的开发人员生态系统和社区。 它包含所有Adobe产品的[API](https://www.adobe.io/apis.html)。

这是设置和使用[!DNL Adobe] [!DNL APIs]的推荐方法。

### 先决条件 {#prerequisites}

在配置[!DNL JWT]身份验证之前，请确保您有权访问[Adobe Developer](https://console.adobe.io/)中的[Adobe Developer Console](https://www.adobe.io/)。 有关访问请求，请联系您的组织管理员。

### 身份验证 {#auth}

请按照以下步骤使用[!DNL JWT (Service Account)]配置[!DNL Adobe Developer]身份验证：

1. 登录到[Adobe Developer Console](https://console.adobe.io/)。
1. 按照[服务帐户连接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步骤操作。
   * 在[步骤2：使用服务帐户身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)将API添加到您的项目中，选择[!DNL Audience Manager] [!DNL API]选项。
1. 根据[!DNL API]步骤3[中的说明进行第一个](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)调用以尝试连接。

>[!NOTE]
>
>要自动配置和使用[!DNL Audience Manager] [!DNL REST APIs]，您可以通过编程方式生成[!DNL JWT]。 有关详细说明，请参阅[JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

### 技术帐户RBAC权限

如果您的Audience Manager帐户使用[基于角色的访问控制](../../features/administration/administration-overview.md)，则必须创建一个Audience Manager技术用户帐户，并将其添加到将进行API调用的Audience Manager RBAC组。

按照以下步骤创建技术用户帐户并将其添加到RBAC组中：

1. 对`GET`进行`https://aam.adobe.io/v1/users/self`调用。 此调用将创建一个技术用户帐户，您可以在[!UICONTROL Admin Console]的[!UICONTROL Users]页面中看到该帐户。

   ![技术帐户](assets/technical-account.png)

1. 登录到您的Audience Manager帐户，然后[将技术用户帐户](../../features/administration/administration-overview.md#create-group)添加到将进行API调用的用户组。

+++

## [!BADGE 已弃用]{type=negative} [!DNL OAuth]身份验证（已弃用） {#oauth-deprecated}

+++ 查看有关已弃用的获取身份验证令牌的旧版[!DNL OAuth]身份验证方法的信息。

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API]令牌身份验证和通过[!DNL OAuth 2.0]续订现在已被弃用。
>
> 请改用[JWT（服务帐户）身份验证](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循令牌身份验证和续订的[!DNL OAuth 2.0]标准。 以下各节介绍如何验证并开始使用[!DNL API]。

### 创建通用[!DNL API]用户 {#requirements}

我们建议您创建一个单独的技术用户帐户来使用[!DNL Audience Manager] [!DNL API]。这是一个通用帐户，它与组织中的特定用户无关，也与特定用户关联。 此类型的[!DNL API]用户帐户可帮助您完成2件事：

* 识别正在调用[!DNL API]的服务（例如，来自使用我们[!DNL API]的应用或来自发出[!DNL API]请求的其他工具的调用）。
* 提供对[!DNL API]的无中断访问。与特定人员关联的帐户可能会在他们离开您的公司时删除。 这将阻止您使用可用的[!DNL API]代码。 不绑定到特定员工的通用帐户有助于避免此问题。

作为此类帐户的示例或用例，假设您希望使用[批量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次更改多个区段。 为此，您的用户帐户需要[!DNL API]访问权限。 不要向特定用户添加权限，而是创建一个非特定的[!DNL API]用户帐户，该帐户具有进行[!DNL API]调用所需的相应凭据、密钥和密钥。 如果您开发自己的使用[!DNL Audience Manager] [!DNL API]的应用程序，这也很有用。

与您的[!DNL Audience Manager]顾问合作，设置一个通用、仅限[!DNL API]的用户帐户。

### 密码身份验证工作流 {#password-authentication-workflow}

密码身份验证安全访问我们的[!DNL REST API]。 以下步骤概述了从浏览器中的[!DNL JSON]客户端进行密码身份验证的工作流。

>[!TIP]
>
>如果您将令牌存储在数据库中，则加密访问和刷新令牌。

#### 步骤1：请求[!DNL API]访问权限

请联系您的合作伙伴解决方案经理。 他们将为您提供[!DNL API]客户端ID和密码。 ID和密码通过[!DNL API]验证您的身份。

注意：如果您希望接收刷新令牌，请在请求[!DNL API]访问权限时指定。

#### 步骤2：请求令牌

向首选[!DNL JSON]客户端传递令牌请求。 构建请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和密码转换为base-64编码字符串。 在转换过程中使用冒号分隔ID和密码。 例如，凭据`testId : testSecret`转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded` 。 例如，您的标题可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式设置请求正文：
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步骤3：接收令牌

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

`expires_in`键表示访问令牌过期前的秒数。 作为最佳实践，如果令牌被公开，请使用较短的过期时间以限制泄露。

### 刷新令牌 {#refresh-token}

刷新令牌在原始令牌过期后续订[!DNL API]访问权限。 如果请求，密码工作流中的响应[!DNL JSON]将包含刷新令牌。 如果您没有收到刷新令牌，请通过密码身份验证过程创建一个新令牌。

您还可以使用刷新令牌在现有访问令牌过期之前生成新的令牌。

如果您的访问令牌已过期，则会在响应中接收`401 Status Code`和以下标头：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步骤概述了使用刷新令牌从浏览器中的[!DNL JSON]客户端创建新的访问令牌的工作流。

#### 步骤1：请求新令牌

向首选[!DNL JSON]客户端传入刷新令牌请求。 构建请求时：

* 使用`POST`方法调用`https://api.demdex.com/oauth/token`。
* 将您的客户端ID和密码转换为base-64编码字符串。 在转换过程中使用冒号分隔ID和密码。 例如，凭据`testId : testSecret`转换为`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 传入HTTP标头`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的标题可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在请求正文中，指定`grant_type:refresh_token`并传入您在上一个访问请求中收到的刷新令牌。 请求应如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步骤2：接收新令牌

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

### 授权代码和隐式身份验证 {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支持授权代码和隐式身份验证。 若要使用这些访问方法，您的用户需要登录到`https://api.demdex.com/oauth/authorize`以获取访问权杖并刷新令牌。

+++

## 提出经过身份验证的[!DNL API]请求 {#authenticated-api-requests}

收到身份验证令牌后调用[!DNL API]方法的要求。

要针对可用的[!DNL API]方法进行调用，请执行以下操作：

* 在`HTTP`标头中，设置`Authorization: Bearer <token>`。
* 使用[JWT（服务帐户）身份验证](#jwt)时，需要提供`x-api-key`标头，该标头将与您的`client_id`相同。 您可以从`client_id`Adobe Developer集成[页面获取](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。
* 调用所需的[!DNL API]方法。

## 可选的[!DNL API]查询参数 {#optional-api-query-parameters}

设置可用于返回对象所有属性的方法的可选参数。

您可以将这些可选参数与[!DNL API]方法一起使用，这些方法返回对象的&#x200B;*所有*&#x200B;属性。 将查询传递到[!DNL API]时，在请求字符串中设置这些选项。

| 参数 | 描述 |
|--- |--- |
| `page` | 按页码返回结果。 编号从0开始。 |
| `pageSize` | 设置请求返回的响应结果数（默认为10）。 |
| `sortBy` | 根据指定的[!DNL JSON]属性排序并返回结果。 |
| `descending` | 按降序排序并返回结果。 `ascending`是默认的。 |
| `search` | 根据要用作搜索参数的指定字符串返回结果。 例如，假设您要查找在该项目的任何值字段中包含“Test”一词的所有模型的结果。 您的示例请求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜索“[!DNL get all]”方法返回的任何值。 |
| `folderId` | 返回指定文件夹内[!UICONTROL traits]的所有ID。 并非对所有方法都可用。 |
| `permissions` | 根据指定的权限返回区段列表。 `READ`是默认的。 权限包括：<ul><li>`READ` ：返回并查看有关区段的信息。</li><li>`WRITE` ：使用`PUT`更新区段。</li><li>`CREATE` ：使用`POST`创建区段。</li><li>`DELETE` ：删除区段。 需要访问基础特征（如果有）。 例如，如果要删除属于某个区段的特征，您需要拥有删除该区段的权限。</li></ul><br>使用单独的键值对指定多个权限。 例如，要返回仅具有`READ`和`WRITE`权限的区段列表，请传入`"permissions":"READ"`、`"permissions":"WRITE"`。 |
| `includePermissions` | ([!DNL Boolean])设置为`true`以返回您对该区段的权限。 默认值为`false`。 |

{style="table-layout:auto"}

### 有关页面选项的注释

未指定页面信息&#x200B;*时，请求返回数组中的纯*&#x200B;结果。 [!DNL JSON]如果指定了页面信息&#x200B;**，则返回的列表将封装在包含有关总结果和当前页面信息的[!DNL JSON]对象中。 使用页面选项的示例请求可能如下所示：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

请求、暂存和生产环境及版本的[!DNL URLs]。

## 请求[!DNL URLs] {#request-urls}

下表按方法列出了用于传入[!DNL URLs]请求的请求[!DNL API]。

根据您使用的身份验证方法，您需要根据下表调整请求[!DNL URLs]。

### 请求[!DNL URLs]通过Adobe Developer进行[!BADGE Recommended]{type=positive} OAuth Server-to-Server和[!BADGE Deprecated]{type=negative} [!DNL JWT]身份验证 {#request-urls-jwt}

| [!DNL API]方法 | 请求[!DNL URL] |
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

{style="table-layout:auto"}

### 针对[!DNL URLs]已弃用[!BADGE 旧版]{type=negative}身份验证的请求[!DNL OAuth] {#request-urls-oauth}

| [!DNL API]方法 | 请求[!DNL URL] |
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

{style="table-layout:auto"}

## 环境 {#environments}

[!DNL Audience Manager] [!DNL API]提供对不同工作环境的访问权限。 这些环境可帮助您针对单独的数据库测试代码，而不影响实时的生产数据。 下表列出了可用的[!DNL API]环境和相应的资源主机名。

根据您使用的身份验证方法，您需要根据下表调整环境[!DNL URLs]。

| 环境 | [!DNL JWT]身份验证的主机名 | [!DNL OAuth]身份验证的主机名 |
|---|---|---|
| **生产** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager]测试版环境是生产环境的较小规模的独立版本。 必须在此环境中输入和收集您要测试的所有数据。

## 版本 {#versions}

这些[!DNL API]的新版本将定期发布。 新版本将增加[!DNL API]版本号。 请求[!DNL URL]中以`v<version number>`的形式引用了版本号，如以下示例所示：

`https://<host>/v1/...`

## 定义的响应代码 {#response-codes-defined}

`HTTP` [!DNL Audience Manager]返回的[!UICONTROL REST API]状态代码和响应文本。

| 响应代码ID | 响应文本 | 定义 |
|---|---|---|
| `200` | `OK` | 已成功处理请求。 如果需要，将返回预期的内容或数据。 |
| `201` | `Created` | 已创建资源。 返回`PUT`和`POST`请求。 |
| `204` | `No Content` | 已删除资源。 响应正文将为空白。 |
| `400` | `Bad Request` | 服务器不理解该请求。 通常由于语法格式错误所致。 请检查您的请求，然后重试。 |
| `403` | `Forbidden` | 您无权访问该资源。 |
| `404` | `Not Found` | 找不到指定路径的资源。 |
| `409` | `Conflict` | 由于与资源的状态冲突，无法完成请求。 |
| `500` | `Server Error` | 服务器遇到意外错误，无法完成请求。 |

>[!MORELIKETHIS]
>
>* [JWT（服务帐户）身份验证](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份验证](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [简化的OAuth 2](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
