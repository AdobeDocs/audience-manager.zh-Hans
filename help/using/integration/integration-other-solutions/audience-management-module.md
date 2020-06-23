---
description: 将受众管理模块添加到AdobeAnalyticsAppMeasurement以将Analytics数据转发到Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: 将受众管理模块添加到AdobeAnalyticsAppMeasurement以将Analytics数据转发到Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
seo-title: 实现受众管理模块
solution: Audience Manager
title: 实现受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# How to forward data from [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

请按照本教程中的步骤转 [!DNL Analytics] 发数 [!DNL Audience Manager] 据，而不 [!DNL Audience Manager] 是让 [!UICONTROL Data Integration Library] ()[!DNL DIL]代码从页面发送像素。

>[!TIP]
>
>我们建议您使 [!DNL Adobe Experience Platform Launch] 用将数 [!UICONTROL Analytics] 据转发到 [!DNL Audience Manager]。 使用 [!UICONTROL Launch]后，您不必手动将代码复 [!DNL AppMeasurement]制到中，如本页所示。

## 先决条件 {#prereqs}

除了启用本文档所述的扩展或实现代码之外，您还必须：

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html).
* 在 [中为报表包](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) “启用服务器端转发” [!UICONTROL Adobe Analytics Admin Console]。

## 实施 {#implementation}

根据您使用的标签管理解决方 [!DNL Adobe Analytics] 案， [!DNL Audience Manager]有两种方法实现从到的数据转发。

### 实施(使用 [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] 建议您使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) 扩展来对 [!DNL Adobe Analytics] 属性进 [!DNL Audience Manager] 行测试和测试。 在这种情况下，无需手动复制任何代码。 您必须在扩展中启用数 [!DNL Analytics Launch] 据共享，如下图所示。 另请参阅Adobe [Analytics扩展](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 文档。

>[!TIP]
>
>如果安装扩 [!DNL Adobe Analytics] 展， *请勿* 也安装 [!DNL Audience Manager] 扩展。 从扩展转发数 [!DNL Analytics] 据将替换扩 [!DNL Audience Manager] 展功能。

![如何启用从AdobeAnalytics扩展到Audience Manager的数据共享](/help/using/integration/assets/analytics-to-aam.png)

### 使用或任 [!DNL Adobe Digital Tag Management (DTM)] 何其他标签管理解决方案实施

>[!WARNING]
>
>[!DNL Adobe] 已于2020年底发 [!DNL DTM] 布日落计划。 有关详细信息和日程安排，请参 [!DNL DTM] 阅Adobe社区论坛中 [的日落计划](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)。

要使用Adobe DTM [!UICONTROL Audience Management Module] 或其 [他标签管理解决方](https://docs.adobe.com/content/help/zh-Hans/dtm/using/dtm-home.html) 案来实施，请执行以下操作：

1. 使用 [!UICONTROL AppMeasurement] Analytics [代码管理器](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/code-manager-admin.html) （需要版本1.5或更高版本）下载。
1. 将您的 [!UICONTROL AppMeasurement] 代码更新至下载的zip文件中包含的版本。
1. 从zip文件复制所 `AppMeasurement_Module_AudienceManagement.js` 有代码。 将其粘贴到 `appMeasurement.js` 文本正上方的文件中， `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 添加代码， `s.loadModule("AudienceManagement");`就在您刚在上 `AppMeasurement_Module_AudienceManagement.js` 一步中添加的代码的上方。
1. 更新并复制下面的代码，并将其添加到 `doPlugins` 文件中的 `AppMeasurement.js` 函数。

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>函 `audienceManagement.setup` 数与函数共享参数 [!DNL Audience Manager] ，您可以在 `DIL.create` 此代码中配置这些参数。 For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## 定义的代码元素 {#code-elements-defined}

下表定义代码示例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是分配给您的合作伙伴名称 [!DNL Adobe]。 它有时称为您或合 [!UICONTROL partner ID] 作伙伴子域。  如果您 [!DNL Adobe] 不知道 [您的合作伙伴](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html) ，请与您的顾问或客户关怀联系。 |
| `containerNSID` | 必需。大多数客户只需设置 `"containerNSID":0` 。 但是，如果公司需要使用其他容器自定义ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在 [!DNL Adobe] 第一方域中设置Cookie。 它 [!DNL cookie] 包含 [UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必需。如果 `namespace` 您使用与版本2.10或更 [!DNL AudienceManagement] 高版本绑 [!UICONTROL AppMeasurement] 定的模块，则此参数是必需的。 本 [!UICONTROL AudienceManagement] 模块要求您使用 [!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>是 [!UICONTROL Experience Cloud Organization ID] 公司在注册时获得的ID [!UICONTROL Experience Cloud]。 在“组织和帐户链接”中查 [找公司的组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)。 |

## 结果： 数据转发到 [!DNL Audience Manager] {#results-data-forwarding}

实施 [!DNL Analytics] 会在您拥有以 [!DNL Audience Manager] 下各项后向发送数据：

* 启用 [!UICONTROL Server-Side Forwarding] （与咨询顾问讨论此功能）;
* 执行 [!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的实施步骤操作。

此进程将数据发送到 [!DNL Audience Manager]:

* 页面视图调用；
* 从跟踪的链接；
* 从视频里程碑和心跳视频视图。

>[!NOTE]
>
>从发送到的变 [!DNL Audience Manager] 量使 [!DNL Analytics] 用特殊前缀。 创建特征时需要了解并考虑这些前 [!DNL Audience Manager] 缀。 有关这些前缀的详细信息，请参 [阅关键变量前缀要求](../../features/traits/trait-variable-prefixes.md)。
