---
description: 将受众管理模块添加到Adobe Analytics AppMeasurement，将Analytics数据转发到受众管理器，而不是让受众管理器数据集成库(DIL)代码从页面发送像素。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: 将受众管理模块添加到Adobe Analytics AppMeasurement，将Analytics数据转发到受众管理器，而不是让受众管理器数据集成库(DIL)代码从页面发送像素。
seo-title: 实现受众管理模块
solution: Audience Manager
title: 实现受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 如何将数据从Adobe Analytics转发到受众管理器 {#implement-the-audience-management-module}

请按照本教程中的步骤将数 [!DNL Analytics] 据转发到受众管理器，而 [!UICONTROL Data Integration Library] 不是让受众[!UICONTROL DIL]管理器()代码从页面发送像素。

>[!TIP]
>
>我们建议您使 [!DNL Adobe Experience Platform Launch] 用将数 [!UICONTROL Analytics] 据转发到受众管理器。 使用 [!UICONTROL Launch]后，您不必手动将代码复 [!UICONTROL AppMeasurement]制到中，如本页所示。

## 先决条件 {#prereqs}

除了启用本文档所述的扩展或实现代码之外，您还必须：

* 实施 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)。
* 在 [中为报表包](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) “启用服务器端转发” [!UICONTROL Adobe Analytics Admin Console]。

## 实施 {#implementation}

根据您使用的标签管理解决方案，有两种方法可以实施从Adobe Analytics到受众管理器的数据转发。

### 使用Adobe Experience Platform Launch实施

Adobe建议您使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) 扩展来在您的属性中演示Adobe Analytics和受众管理器。 在这种情况下，无需手动复制任何代码。 您必须在Analytics Launch扩展中启用数据共享，如下图所示。 另请参阅 [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 文档。

>[!TIP]
>
>如果您安装Adobe Analytics扩展， *请勿* 同时安装受众管理器扩展。 从Analytics扩展转发受众取代了Analytics Manager扩展功能。

![如何启用从Adobe Analytics扩展到受众管理器的数据共享](/help/using/integration/assets/analytics-to-aam.png)

### 使用Adobe数字标签管理(DTM)或任何其他标签管理解决方案实施


>[!WARNING]
>
>Adobe已发布计划，在2020年底之前将日落DTM。 有关详细信息和日程安排，请参阅Adobe社区论坛中的DTM [日落计划](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)。

要使用Adobe DTM [!UICONTROL Audience Management Module] 或其 [他标签管理解决方](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) 案来实施，请执行以下操作：

1. 使用 [!UICONTROL AppMeasurement] Analytics Code Manager [下载](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) （需要版本1.5或更高版本）。
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
>该函 `audienceManagement.setup` 数与受众管理器函数共 `DIL.create` 享参数，您可以在此代码中配置该函数。 For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## 定义的代码元素 {#code-elements-defined}

下表定义代码示例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是Adobe分配给您的合作伙伴名称。 它有时称为“合作伙伴ID”或“合作伙伴子域”。  如果您不知道 [您的合作伙伴](https://helpx.adobe.com/marketing-cloud/contact-support.html) ，请与Adobe顾问或客户关怀联系。 |
| `containerNSID` | 必需。大多数客户只需设置 `"containerNSID":0` 。 但是，如果公司需要使用其他容器自定义ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置Adobe cookie。 此Cookie包含 [UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必需。如果 `namespace` 您使用与版本2.10或更高版本绑定的AudienceManagement模 [!UICONTROL AppMeasurement] 块，则此参数是必需的。 本 [!UICONTROL AudienceManagement] 模块要求您使用 [!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br> 是 [!UICONTROL Experience Cloud Organization ID] 公司在注册时获得的ID [!UICONTROL Experience Cloud]。 在“组织和帐户链接”中查 [找公司的组织ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)。 |

## 结果： 数据转发到受众管理器 {#results-data-forwarding}

在您 [!DNL Analytics] 拥有以下各项后，您的实施会将数据发送到受众管理器：

* 启用 [!UICONTROL Server-Side Forwarding] （与咨询顾问讨论此功能）;
* 实施Adobe Experience Platform Identity Service;
* 按照本教程中的实施步骤操作。

此进程将数据发送到 [!DNL Audience Manager]:

* 页面视图调用；
* 从跟踪的链接；
* 从视频里程碑和心跳视频视图。

>[!NOTE]
>
>从发送到受众管理器的变量 [!DNL Analytics] 使用特殊前缀。 在创建受众管理器特征时，您需要了解并考虑这些前缀。 有关这些前缀的详细信息，请参 [阅关键变量前缀要求](../../features/traits/trait-variable-prefixes.md)。