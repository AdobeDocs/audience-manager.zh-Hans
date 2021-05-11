---
description: 将受众管理模块添加到Adobe Analytics AppMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
keywords: 受众分析；分析；社保基金；服务器端转发
seo-description: 将受众管理模块添加到Adobe Analytics AppMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
seo-title: 实现受众管理模块
solution: Audience Manager
title: 实现受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics 集成
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# 如何将数据从[!DNL Adobe Analytics]转发到[!DNL Audience Manager] {#implement-the-audience-management-module}

按照本教程中的步骤，将[!DNL Analytics]数据转发到[!DNL Audience Manager]，而不是让[!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL])代码从页面发送像素。

>[!TIP]
>
>我们建议您使用[!DNL Adobe Experience Platform Launch]将数据转发到[!DNL Audience Manager]中。 [!UICONTROL Analytics]通过使用[!UICONTROL Launch]，您不必手动将代码复制到[!DNL AppMeasurement]中，如本页所示。

## 先决条件 {#prereqs}

除了启用此文档中描述的扩展或实现代码之外，您还必须：

* 实施[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。
* 为[!UICONTROL Adobe Analytics Admin Console]中的报表包启用[服务器端转发](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)。

## 实施 {#implementation}

有两种方法可实现从[!DNL Adobe Analytics]到[!DNL Audience Manager]的数据转发，具体取决于您使用的标签管理解决方案。

### 使用[!DNL Adobe Experience Platform Launch]实现

[!DNL Adobe] 建议您使用 [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension来对属 [!DNL Adobe Analytics] 性 [!DNL Audience Manager] 进行测量。在这种情况下，无需手动复制任何代码。 相反，您必须启用[!DNL Analytics Launch]扩展中的数据共享，如下图所示。 另请参阅[Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)文档。

>[!TIP]
>
>如果安装[!DNL Adobe Analytics]扩展，*不要*&#x200B;也安装[!DNL Audience Manager]扩展。 从[!DNL Analytics]扩展转发数据将替换[!DNL Audience Manager]扩展功能。

![如何启用从Adobe Analytics扩展到Audience Manager的数据共享](/help/using/integration/assets/analytics-to-aam.png)

## 定义的代码元素{#code-elements-defined}

下表定义了代码示例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是[!DNL Adobe]分配给您的合作伙伴名称。 它有时称为[!UICONTROL partner ID]或合作伙伴子域。  如果您不知道您的合作伙伴姓名，请与您的[!DNL Adobe]顾问或[客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html)联系。 |
| `containerNSID` | 必需。大多数客户只需设置`"containerNSID":0`。 但是，如果您的公司需要使用其他容器自定义ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置[!DNL Adobe] Cookie。 此[!DNL cookie]包含[UUID](../../reference/ids-in-aam.md)。 |
| `visitorService` - `namespace` | 必需。如果使用与[!UICONTROL AppMeasurement]版本2.10或更高版本捆绑的[!DNL AudienceManagement]模块，则需要`namespace`参数。 此[!UICONTROL AudienceManagement]模块要求您使用[!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>是 [!UICONTROL Experience Cloud Organization ID] 公司注册时向其提供的ID  [!UICONTROL Experience Cloud]。在[组织和帐户链接](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)中查找公司的组织ID。 |

## 结果：数据转发到[!DNL Audience Manager] {#results-data-forwarding}

[!DNL Analytics]实现会在您拥有：[!DNL Audience Manager]

* 已启用[!UICONTROL Server-Side Forwarding]（请咨询顾问了解此功能）；
* 已实施[!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的实施步骤操作。

此进程向[!DNL Audience Manager]发送数据：

* 页面视图调用；
* 从跟踪的链接；
* 从视频里程碑和心率视频视图。

>[!NOTE]
>
>从[!DNL Analytics]发送到[!DNL Audience Manager]的变量使用特殊前缀。 创建[!DNL Audience Manager]特征时，您需要了解并考虑这些前缀。 有关这些前缀的详细信息，请参阅[关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)。
