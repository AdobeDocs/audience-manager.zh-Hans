---
description: 将受众管理模块添加到Adobe Analytics AppMeasurement以将Analytics数据转发给Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
keywords: 受众分析；分析；sf；服务器端转发
seo-description: 将受众管理模块添加到Adobe Analytics AppMeasurement以将Analytics数据转发给Audience Manager，而不是让Audience Manager数据集成库(DIL)代码从页面发送像素。
seo-title: 实施受众管理模块
solution: Audience Manager
title: 实施受众管理模块
uuid: 08846427-def3-4a15-88e5-08882d8 d57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## 先决条件 {#prereqs}

除了实施本文档所述的代码之外，您还必须：

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## 实施 {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

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
>`audienceManagement.setup` 函数与Audience Manager `DIL.create` 函数共享参数，您可以在此代码中配置该函数。For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

下表定义了代码范例中的重要变量。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。这是Adobe为您分配的合作伙伴名称。有时称为“合作伙伴ID”或“合作伙伴子域”。Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | 必需。Most customers can just set  `"containerNSID":0` . 但是，如果您的公司需要与其他容器同步ID，则可以在此处指定该容器ID。 |
| `uuidCookie` | 可选。此配置允许您在第一方域中设置Adobe cookie。This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 必需。`namespace` 如果使用与 [!UICONTROL AppMeasurement] 2.10或更新版本绑定的AudienceManager ement，则此参数是必需的。[!UICONTROL AudienceManagement] 本单元要求您使用 [!UICONTROL Experience Cloud ID Service] 3.3或更新版本。<br>[!UICONTROL Experience Cloud Organization ID] 这是在注册后提供的公司ID [!UICONTROL Experience Cloud]。Find out your company&#39;s Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

[!DNL Analytics] 在您有以下情况后，实施将向Audience Manager发送数据：

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* 实施了ID服务；
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* 在页面查看调用中；
* 从跟踪链接；
* 视频里程碑和心跳视频观看。

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. 您需要了解并在创建Audience Manager特征时考虑这些前缀。For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).