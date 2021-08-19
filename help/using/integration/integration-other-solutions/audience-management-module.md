---
description: 将受众管理模块添加到Adobe Analytics AppMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
keywords: 受众分析；analytics;ssf;服务器端转发
seo-description: 将受众管理模块添加到Adobe Analytics AppMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
seo-title: 实施受众管理模块
solution: Audience Manager
title: 实施受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics 集成
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 2%

---

# 如何将数据从[!DNL Adobe Analytics]转发到[!DNL Audience Manager] {#implement-the-audience-management-module}

按照本教程中的步骤，将[!DNL Analytics]数据转发到[!DNL Audience Manager]，而不是让[!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL])代码从页面发送像素。

>[!TIP]
>
>我们建议您使用[!DNL Adobe Experience Platform Launch]将[!UICONTROL Analytics]数据转发到[!DNL Audience Manager]中。 通过使用[!UICONTROL Launch]，您不必手动将代码复制到[!DNL AppMeasurement]中，如此页面所示。

## 先决条件 {#prereqs}

除了启用扩展或实施本文档中描述的代码之外，您还必须：

* 实施[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
* 为[!UICONTROL Adobe Analytics Admin Console]中的报表包启用[服务器端转发](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)。

## 实施 {#implementation}

根据您使用的标签管理解决方案，有两种方法可实施从[!DNL Adobe Analytics]到[!DNL Audience Manager]的数据转发。

### 使用[!DNL Adobe Experience Platform Launch]实施

[!DNL Adobe] 建议您使用 [](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) Launch扩展来 [!DNL Adobe Analytics] 对资 [!DNL Audience Manager] 产设置和。在这种情况下，您无需手动复制任何代码。 您而是必须在[!DNL Analytics Launch]扩展中启用数据共享，如下图所示。 另请参阅[Adobe Analytics扩展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)文档。

>[!TIP]
>
>如果安装[!DNL Adobe Analytics]扩展，则&#x200B;*不要*&#x200B;也安装[!DNL Audience Manager]扩展。 转发[!DNL Analytics]扩展的数据取代了[!DNL Audience Manager]扩展功能。

![如何启用从Adobe Analytics扩展到Audience Manager的数据共享](/help/using/integration/assets/analytics-to-aam.png)

## 定义的代码元素 {#code-elements-defined}

下表在代码示例中定义了重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是[!DNL Adobe]分配给您的合作伙伴名称。 它有时称为[!UICONTROL partner ID]或合作伙伴子域。  如果您不知道自己的合作伙伴名称，请联系您的[!DNL Adobe]顾问或[客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html)。 |
| `containerNSID` | 必需。大多数客户只能设置`"containerNSID":0` 。 但是，如果您的公司需要自定义与其他容器的ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置[!DNL Adobe] Cookie。 此[!DNL cookie]包含[UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必需。如果您使用与[!UICONTROL AppMeasurement]版本2.10或更高版本捆绑在一起的[!DNL AudienceManagement]模块，则需要`namespace`参数。 此[!UICONTROL AudienceManagement]模块要求您使用[!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>是 [!UICONTROL Experience Cloud Organization ID] 公司在注册时获得的ID  [!UICONTROL Experience Cloud]。在[组织和帐户关联](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)中查找您公司的组织ID。 |

## 结果：数据转发到[!DNL Audience Manager] {#results-data-forwarding}

在以下情况下，您的[!DNL Analytics]实施会向[!DNL Audience Manager]发送数据：

* 已启用[!UICONTROL Server-Side Forwarding]（请咨询您的顾问，了解此功能）；
* 实施了[!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的实施步骤操作。

此过程会向[!DNL Audience Manager]发送数据：

* 在页面查看调用中；
* 从跟踪的链接；
* 从视频里程碑和心率视频查看。

>[!NOTE]
>
>从[!DNL Analytics]发送到[!DNL Audience Manager]的变量使用特殊前缀。 创建[!DNL Audience Manager]特征时，您需要了解并考虑这些前缀。 有关这些前缀的更多信息，请参阅[关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)。
