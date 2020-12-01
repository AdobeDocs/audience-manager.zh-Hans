---
description: 将受众管理模块添加到Adobe AnalyticsAppMeasurement，将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: 将受众管理模块添加到Adobe AnalyticsAppMeasurement，将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
seo-title: 实现受众管理模块
solution: Audience Manager
title: 实现受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# 如何将数据从[!DNL Adobe Analytics]转发到[!DNL Audience Manager] {#implement-the-audience-management-module}

按照本教程中的步骤将[!DNL Analytics]数据转发到[!DNL Audience Manager]，而不是让[!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL])代码从页面发送像素。

>[!TIP]
>
>我们建议您使用[!DNL Adobe Experience Platform Launch]将数据转发到[!DNL Audience Manager]中。 [!UICONTROL Analytics]使用[!UICONTROL Launch]，您不必手动将代码复制到[!DNL AppMeasurement]中，如本页所示。

## 先决条件 {#prereqs}

除了启用本文档所述的扩展或实现代码之外，您还必须：

* 实施[Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。
* 为[!UICONTROL Adobe Analytics Admin Console]中的报表包启用[服务器端转发](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)。

## 实施 {#implementation}

根据您使用的标签管理解决方案，有两种方法可实现从[!DNL Adobe Analytics]到[!DNL Audience Manager]的数据转发。

### 使用[!DNL Adobe Experience Platform Launch]实现

[!DNL Adobe] 建议您使用 [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension对属 [!DNL Adobe Analytics] 性进 [!DNL Audience Manager] 行仪表和操作。在这种情况下，无需手动复制任何代码。 相反，您必须在[!DNL Analytics Launch]扩展中启用数据共享，如下图所示。 另请参阅[Adobe Analytics扩展](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)文档。

>[!TIP]
>
>如果安装[!DNL Adobe Analytics]扩展，*不要*&#x200B;也安装[!DNL Audience Manager]扩展。 从[!DNL Analytics]扩展转发数据将替换[!DNL Audience Manager]扩展功能。

![如何实现从Adobe Analytics扩展到Audience Manager的数据共享](/help/using/integration/assets/analytics-to-aam.png)

### 使用[!DNL Adobe Digital Tag Management (DTM)]或任何其他标签管理解决方案实现

>[!WARNING]
>
>[!DNL Adobe] 已于2020年底发 [!DNL DTM] 布日落计划。有关详细信息和日程安排，请参阅[Adobe社区论坛](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)中的[!DNL DTM]日落计划。

要使用[AdobeDTM](https://docs.adobe.com/content/help/zh-Hans/dtm/using/dtm-home.html)或其他标签管理解决方案实现[!UICONTROL Audience Management Module]:

1. 使用[分析代码管理器](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/code-manager-admin.html)下载[!UICONTROL AppMeasurement]（需要版本1.5或更高版本）。
1. 将您的[!UICONTROL AppMeasurement]代码更新为下载的zip文件中包含的版本。
1. 从zip文件复制`AppMeasurement_Module_AudienceManagement.js`中的所有代码。 将其粘贴到文本`appMeasurement.js`上方的`"DO NOT ALTER ANYTHING BELOW THIS LINE."`文件中
1. 添加代码`s.loadModule("AudienceManagement");`，就在您刚才在上一步中添加的`AppMeasurement_Module_AudienceManagement.js`代码的上方。
1. 更新并复制下面的代码，将其添加到`AppMeasurement.js`文件中的`doPlugins`函数。

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
>`audienceManagement.setup`函数与[!DNL Audience Manager] `DIL.create`函数共享参数，您可以在此代码中配置这些参数。 有关这些参数的详细信息，请参阅[DILcreate](../../dil/dil-class-overview/dil-create.md#dil-create)。

## 定义的代码元素{#code-elements-defined}

下表定义代码示例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是[!DNL Adobe]分配给您的合作伙伴名称。 它有时称为[!UICONTROL partner ID]或合作伙伴子域。  如果您不知道您的合作伙伴姓名，请与您的[!DNL Adobe]顾问或[客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html)联系。 |
| `containerNSID` | 必需。大多数客户只需设置`"containerNSID":0`。 但是，如果公司需要使用其他容器自定义ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置[!DNL Adobe] cookie。 此[!DNL cookie]包含[UUID](../../reference/ids-in-aam.md)。 |
| `visitorService` - `namespace` | 必需。如果使用与[!UICONTROL AppMeasurement]版本2.10或更高版本绑定的[!DNL AudienceManagement]模块，则需要`namespace`参数。 此[!UICONTROL AudienceManagement]模块要求您使用[!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>是 [!UICONTROL Experience Cloud Organization ID] 公司在注册时获得的ID  [!UICONTROL Experience Cloud]。在[组织和帐户链接](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)中查找公司的组织ID。 |

## 结果：向[!DNL Audience Manager] {#results-data-forwarding}传输数据

在[!DNL Analytics]实现后，将数据发送到[!DNL Audience Manager]:

* 已启用[!UICONTROL Server-Side Forwarding]（请咨询顾问了解此功能）;
* 已实现[!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的实施步骤操作。

此进程将数据发送到[!DNL Audience Manager]:

* 页面视图调用；
* 从跟踪的链接；
* 从视频里程碑和心跳视频视图。

>[!NOTE]
>
>从[!DNL Analytics]发送到[!DNL Audience Manager]的变量使用特殊前缀。 创建[!DNL Audience Manager]特征时，您需要了解并考虑这些前缀。 有关这些前缀的详细信息，请参阅[关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)。
