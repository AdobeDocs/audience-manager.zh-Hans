---
description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-title: 适用于 IAB TCF 的 Audience Manager 插件
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
translation-type: tm+mt
source-git-commit: 5fff9315558d3088f68268f32681842bb8d5e7d3

---


# 适用于 IAB TCF 的 Audience Manager 插件 {#aam-iab-plugin}

## 概述

在您对用户的隐私义务中，其中一个重要方面是获取和传达用户对其个人数据使用方式（即“目的”）和使用者（即“公司”）的选择。

Adobe 通过[选择加入功能](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)和 [IAB 透明度及同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。受众管理器在IAB TCF中注册，供应商ID为565。

IAB TCF的受众管理器插 [件利用](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)，即Adobe Experience Platform Identity Service(ECID)库 [的一部分加入功能](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。

## 范围和限制 {#scope-and-limitations}

作为与受众管理器协作的发布者或广告商，您可以根据IAB TCF向受众管理器传达用户选择。 这为您提供了一种轻松、一致的方式，让您能够与您所合作的所有合作伙伴交流用户选择，受众管理器可以帮助您尊重用户的隐私选择。

本文描述的IAB TCF支持是受众经理计划支持IAB框架的第一阶段。 目前，受众管理器不支持：

* 移动设备工作流;
* 跨设备同意管理；
* 将同意书附加到发送到URL目 [标的URL](../../features/destinations/create-url-destination.md);
* 将同意附加到区段。

## 先决条件 {#prerequisites}

要将IAB TCF与受众管理器一起使用，您必须满足以下先决条件：

1. 您必须使用Adobe Experience Platform Identity Service(ECID)4.1版或更高版本。 [下载我们](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 最新的ECID版本。
1. 您必须使用受众管理器数据集成库(DIL)9.0版或更高版本，可从此处下 [载](https://github.com/Adobe-Marketing-Cloud/dil/releases)。 阅读受众 [管理器文档中的DIL](../..//dil/dil-overview.md)。
1. 或者，如果您使用服务器端转发(SSF)将数据导入受众管理器，则必须升级到最新版AppMeasurement。 使用Analytics Code Manager [下载AppMeasurement](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)。
1. 您必须使用支持IAB TCF的商业类或您自己的同意管理平台(CMP)，并且已在IAB TCF中注册。 请参见在IAB框 [架中注册的CMP的列表](https://iabeurope.eu/cmp-list/)。

## 建议和如何实施 {#recommendations}

要在受众管理器中启用IAB TCF支持，请阅读我们的 [文档，了解如何通过选择加入设置IAB](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)。

使用Adobe Experience Platform Launch [在您的属性上](https://docs.adobelaunch.com/) ，通过ECID选择加入来实现这一操作最简单。 Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## 使用IAB框架时的用户选择工作流 {#user-choice-workflow}

在访问Web属性时，用户可以选择发布者以及发布者与之合作的第三方供应商如何使用其数据。 用户以标准用途和权限的形 *式向在* 全球供应商 *列表注册的第* 三方供应商提供自己的选择。 下面的图像代表CMP对话框的示例，显示到网站的首次访客。 请记住，根据客户实施情况，此对话看起来会非常不同。

![CMP对话框](assets/cmp.png)

IAB框架中的标准用途是：

* 信息存储和访问
* 个性化
* 广告选择、投放和报告
* 内容选择、投放和报告
* 测量

有关五 [个标准用途的说明](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) ，请参阅IAB框架规范页。

用户可出于标准目的和供应商的考虑授予其同意。 例如，用户可以授予其对存储、个性化和衡量的同意，并授予其对由CMP展示的所有第三方供应商的同意。 或者，在另一个例子中，他们可以就所有五项标准目的同意书，但只准许《议定书》/《公约》缔约方会议所显示的少数供应商同意。

一旦用户选择其隐私选择，用户选择便记录在IAB TCF同意字符串中。 IAB TCF同意字符串存储已批准用途和供应商的组合以及其他元数据信息(有关详细信 [息，请参阅](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB页面)。 在IAB TCF中注册的每个供应商都评估IAB TCF同意字符串并根据用户的隐私选择做出决策。 请记住，用户的隐私选择在所有经过批准的供应商中都有效。

## 受众经理需要的标准用途 {#aam-standard-purposes}

受众管理器评估存储在IAB TCF同意字符串中的用户选择，其内容包括：

* 信息存储和访问(全局供应商列表中 [的目的ID 1](https://vendorlist.consensu.org/vendorlist.json))
* 个性化（用途ID 2）
* 测量（用途ID 5）
* 受众经理供应商同意存储、处理或激活发布者的数据。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## 受众管理者的行为取决于用户是否同意 {#aam-behavior-consent}

受众管理器的工作方式取决于受众管理器是否在IAB TCF同意字符串中检测到用户为三个目的(存储、个性化、衡量)提供了同意。

| 受众经 *理在用户*&#x200B;同意后： | 当用户拒绝 *同意* ,受众经理： |
|---|---|
| <ul><li>执行您请求的所有受众经理使用案例。</li><li>在ID同步中向第三方传达同意（通过在ID同步调用中通过gdpr = 1和同意字符串gdpr_acconence）。</li><li>评估并接受从广告服务器像素传递的同意。</li><li>接受合作伙伴发起的ID同步。</li></ul> | <ul><li>不在实例中存储任何新用户数据。 这包括合作伙伴ID、信号、特征或像素数据。</li><li>不启动第三方ID同步。</li><li>不支持合作伙伴发起的ID同步。</li></ul> |

## 发布者用例 {#publisher-use-case}

通过实施IAB TCF，您无需通过与Adobe或其他第三方供应商的其他机制在您的Web属性上维护用于同意管理的自定义代码。 图像和以下步骤介绍了用例。 开始自图像左侧：

1. 用户访问您的某个Web属性。 只要您使用最新版ECID和DIL库(请参阅 [先决条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites))，就会触发选择加入流。
2. 受众管理器检查IAB流是否适用(`isIabContext=true`)。 请参 [阅建议和如何实施](aam-iab-plugin.md#recommendations)。
3. 受众管理器检查GDPR是`gdpr = 1`否适用()以及您的Web属性上是否存在向IAB注册的CMP。 例如，这将适用于从欧洲合并区访问的用户。 请注意，您作为发行商有责任设置GDPR标志。
4. 如果GDPR适用，受众经理将检查参数中通过的IAB TCF同意字符串，以 `gdpr_consent`获得所需的权限。 受众经理需要存储、个性化、评估权限以及受众经理供应商的同意权，才能存储、处理或激活数据。
5. 如果IAB TCF同意字符串存在并且包含所需的权限，则受众管理器会将IAB TCF同意字符串传递到我们的 [数据收集服务器](../../reference/system-components/components-data-collection.md) (DCS)。
6. 受众管理器通过在浏览器上 [设置demdex cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) 来做出响应。 受众管理器还启动并接受第三方ID同步。
7. 或者，如果在步骤5中通过的IAB TCF同意字符串不包含所有所需的权限，则受众管理器不会收集、处理或激活数据，也不会执行或启动ID同步。

![发布者用例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

受众经理根据IAB TCF评估 [和接受](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)（在像素调用中）通过的同意。

像素通常由受众经理客户在其合作伙伴页面上放置，或者放置在广告服务器中以包含在广告响应中。 在第一种情况下，您的合作伙伴必须以编程方式检索同意参数并将其添加到像素，然后才能触发。 在第二种情况下，广告服务器将从供应端平台(SSP)或发布者广告服务器接收的同意参数附加到所有像素，这种情况较为常见，详细描述如下。

受众管理器在像素调用中使用两个参数传递用户同意：

* `gdpr` 可为0（GDPR不适用）或1（GDPR适用）;
* `gdpr_consent` 是URL安全的基本64编码的GDPR同意字符串(请参 [阅规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications))。 对印象像素的示例调用，其中两个参数如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

图像和以下步骤介绍了用例。 开始自图像左侧：

1. 广告服务器会给用户留下深刻印象。 这转换为对我们的数据收集服务器(DCS)的像素调用。
2. 受众管理器检查GDPR标志是否适用。 否则，受众管理器会在像素调用中存储宏变量中传递的数据。
3. 如果同意字符串存在并且包含所需的权限，则受众管理器将通过宏变量传递的数据存储在像素调用中。
4. 如果同意字符串缺失或缺少所需的权限，受众管理器会删除像素调用中宏变量中传递的数据。

![广告商用例](assets/advertiser-use-case.png)

## 支持IAB TCF的激活合作伙伴 {#aam-activation-partners}

IAB TCF的受众管理器插件允许您将IAB TCF同意字符串转发给激活合作伙伴，同时尊重用户的隐私选择。 有关哪些激活合作伙伴支持IAB TCF的信息，请参阅我们 [基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)。

## 测试IAB实施 {#test-iab-implementation}

要测试您是否正确实现了IAB TCF的受众管理器插件，请阅 [读Validation Methods for Opt-in和IAB实现中的用例4](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)。

## IAB和退出受众管理器。 优先顺序。 {#iab-and-optout}

用户可使用的另一个隐私选项是能够收选择退出集所有数据。 Adobe为用户提供在您的隐私选择页面 [中执行此操作](https://www.adobe.com/privacy/opt-out.html#customeruse) 。

受众管理器在我们文档中的另一 [篇文章中解决退出请求](data-privacy-requests.md)。

>[!NOTE]
>
>**优先顺序** -如果用户使用全局退出工具退出数据收集（如上面的链接所述），则此优先于选择加入和IAB验证。

## 其他资源 {#additional-resources}

* [Adobe Experience Platform Identity Service选择加入](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB欧洲GDPR透明度与同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB欧洲GDPR透明度和同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF插件——视频演示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)