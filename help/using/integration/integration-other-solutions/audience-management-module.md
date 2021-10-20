---
description: 将受众管理模块添加到Adobe Analytics AppMeasurement，以将Analytics数据转发到Audience Manager，而不是让Audience ManagerData Integration Library(DIL)代码从页面发送像素。
keywords: 受众分析；analytics;ssf;服务器端转发
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 实施受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 如何从 [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

请按照本教程中的步骤进行转发 [!DNL Analytics] 数据到 [!DNL Audience Manager] 而不是 [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])代码从页面发送像素。

>[!TIP]
>
>我们建议您使用 [!DNL Adobe Experience Platform Tags] 转发 [!UICONTROL Analytics] 数据输入 [!DNL Audience Manager]. 使用 [!UICONTROL Tags]，则无需将代码手动复制到 [!DNL AppMeasurement]，如此页面所示。

## 先决条件 {#prereqs}

除了启用扩展或实施本文档中描述的代码之外，您还必须：

* 实施 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* 启用 [服务器端转发](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) (对于 [!UICONTROL Adobe Analytics Admin Console].

## 实施 {#implementation}

有两种方法可从中实施数据转发 [!DNL Adobe Analytics] to [!DNL Audience Manager]，具体取决于您使用的标签管理解决方案。

### 使用实施 [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] 建议您使用 [标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 仪器的扩展 [!DNL Adobe Analytics] 和 [!DNL Audience Manager] 在您的资产上。 在这种情况下，您无需手动复制任何代码。 您而是必须在 [!DNL Analytics] 扩展，如下图所示。 另请参阅 [Adobe Analytics扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) 文档。

>[!TIP]
>
>如果安装 [!DNL Adobe Analytics] 扩展， *不* 另请安装 [!DNL Audience Manager] 扩展。 将数据从 [!DNL Analytics] 扩展取代了 [!DNL Audience Manager] 扩展功能。

![如何启用从Adobe Analytics扩展到Audience Manager的数据共享](/help/using/integration/assets/analytics-to-aam.png)

## 定义的代码元素 {#code-elements-defined}

下表在代码示例中定义了重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是分配给您的合作伙伴名称 [!DNL Adobe]. 它有时称为您的 [!UICONTROL partner ID] 或合作伙伴子域。  联系您的 [!DNL Adobe] 顾问或 [客户关怀](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html) 如果你不知道你的搭档名。 |
| `containerNSID` | 必需。大多数客户只需设置  `"containerNSID":0` . 但是，如果您的公司需要自定义与其他容器的ID同步，您可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您设置 [!DNL Adobe] 第一方域中的Cookie。 此 [!DNL cookie] 包含 [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 必需。的 `namespace` 参数是必需的 [!DNL AudienceManagement] 与 [!UICONTROL AppMeasurement] 版本2.10或更高版本。 此 [!UICONTROL AudienceManagement] 模块要求您使用 [!UICONTROL Adobe Experience Platform Identity Service] 3.3或更高版本。 <br><br>的 [!UICONTROL Experience Cloud Organization ID] 是公司在注册时获得的ID [!UICONTROL Experience Cloud]. 在 [组织和帐户关联](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## 结果：数据转发到 [!DNL Audience Manager] {#results-data-forwarding}

您的 [!DNL Analytics] 实施将数据发送到 [!DNL Audience Manager] 在以下情况下：

* 已启用 [!UICONTROL Server-Side Forwarding] （就此功能与您的顾问沟通）；
* 实施了 [!DNL Adobe Experience Platform Identity Service];
* 按照本教程中的实施步骤操作。

此过程会将数据发送到 [!DNL Audience Manager]:

* 在页面查看调用中；
* 从跟踪的链接；
* 从视频里程碑和心率视频查看。

>[!NOTE]
>
>发送到的变量 [!DNL Audience Manager] 从 [!DNL Analytics] 使用特殊前缀。 在创建 [!DNL Audience Manager] 特征。 有关这些前缀的更多信息，请参阅 [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md).
