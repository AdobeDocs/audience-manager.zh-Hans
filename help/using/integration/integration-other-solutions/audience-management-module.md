---
description: 将Audience Management模块添加到Adobe Analytics appMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: 将Audience Management模块添加到Adobe Analytics appMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
seo-title: 实施受众管理模块
solution: Audience Manager
title: 实施受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: d6bfffa97813eeafd7e478f0520b2a62eb63cb94

---


# 实施受众管理模块 {#implement-the-audience-management-module}

添加 [!UICONTROL Audience Management Module] 到，以将 [!DNL Adobe Analytics] 数据转发到Audience Manager，而不是让Audience Manager [!UICONTROL AppMeasurement] ( [!DNL Analytics][!UICONTROL Data Integration Library][!UICONTROL DIL])代码从页面发送像素。

>[!NOTE]
>
>本页中的说明涉及使用 [Adobe Digital Tag Manager(DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) 或任何其他标签管理解决方案( *Adobe Launch除外)的* 实 [施](https://docs.adobe.com/content/help/en/launch/using/overview.html)。 我们建议您使用Adobe Launch。 使用启动项，您不必手动复制代码，如本页所示。

## 先决条件 {#prereqs}

除了实施本文档所述的代码外，您还必须：

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* 为 [!UICONTROL Server-Side Forwarding] 中的报表包启用 [!UICONTROL Adobe Analytics Admin Console]。

## 实施 {#implementation}

要实施以下各项，请执行以 [!UICONTROL Audience Management Module]下操作：

1. 使用 [!UICONTROL AppMeasurement] Analytics Code Manager [下载](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) （需要版本1.5或更高版本）。
1. 将您的 [!UICONTROL AppMeasurement] 代码更新到下载的zip文件中包含的版本。
1. 从zip文件复制所 `AppMeasurement_Module_AudienceManagement.js` 有代码。 将其粘贴到文 `appMeasurement.js` 本正上方的文件中， `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 添加代码， `s.loadModule("AudienceManagement");`就在您刚在上一 `AppMeasurement_Module_AudienceManagement.js` 步中添加的代码的上方。
1. 更新并复制下面的代码，并将其添加到文 `doPlugins` 件中的函 `AppMeasurement.js` 数中。

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>该函 `audienceManagement.setup` 数与Audience Manager函数共享参数，您 `DIL.create` 可以在此代码中配置该函数。 For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## 定义的代码元素 {#code-elements-defined}

下表定义了代码示例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是Adobe分配给您的合作伙伴名称。 它有时称为“合作伙伴ID”或“合作伙伴子域”。  如果您不知道您的 [合作伙伴名称](https://helpx.adobe.com/marketing-cloud/contact-support.html) ，请与Adobe顾问或客户关怀联系。 |
| `containerNSID` | 必需。大多数客户只需设置 `"containerNSID":0` 。 但是，如果您的公司需要自定义ID与其他容器同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置Adobe cookie。 此Cookie包含 [UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必需。如果 `namespace` 您使用与版本2.10或更高版本捆绑的AudienceManagement [!UICONTROL AppMeasurement] 模块，则此参数是必需的。 本 [!UICONTROL AudienceManagement] 模块要求您使用 [!UICONTROL Experience Cloud ID Service] 3.3或更高版本。 <br> 该 [!UICONTROL Experience Cloud Organization ID] ID是公司在注册时获得的ID [!UICONTROL Experience Cloud]。 在“组织”和“帐户关联”中查 [找您公司的组织ID](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)。 |

## 结果：向Audience Manager转发数据 {#results-data-forwarding}

在您 [!DNL Analytics] 拥有以下各项后，您的实施会将数据发送到Audience Manager:

* 启 [!UICONTROL Server-Side Forwarding] 用（与顾问讨论此功能）;
* 实施了ID服务；
* 已安装 [!UICONTROL Audience Management Module]。

此过程将数据发送到 [!DNL Audience Manager]:

* 页面查看调用；
* 从跟踪的链接；
* 从视频里程碑和心跳视频查看。

>[!NOTE]
>
>从发送到Audience manager的变量使用 [!DNL Analytics] 特殊前缀。 在创建Audience manager特征时，您需要了解并考虑这些前缀。 有关这些前缀的详细信息，请参 [阅关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)。