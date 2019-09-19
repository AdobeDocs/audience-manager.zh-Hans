---
description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-title: 适用于 IAB TCF 的 Audience Manager 插件
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 适用于 IAB TCF 的 Audience Manager 插件 {#aam-iab-plugin}

## 概述

在您对用户的隐私义务中，其中一个重要方面是获取和传达用户对其个人数据使用方式（即“目的”）和使用者（即“公司”）的选择。

Adobe 通过[选择加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)和 [IAB 透明度及同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。Audience Manager在IAB TCF中注册，供应商ID为565。

用于IAB TCF的Audience Manager插件利用 [Opt-in功能](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)，而 [Opt-in功能又是Adobe](https://marketing.adobe.com/resources/help/en_US/mcvid/) Experience Cloud ID服务(ECID)库的一部分。

## 范围和限制 {#scope-and-limitations}

作为与Audience manager协作的发布者或广告商，您能够根据IAB TCF将用户选择传达给Audience Manager。 这样，您就可以轻松、一致地向与您合作的所有合作伙伴传达用户选择，Audience Manager可以帮助您尊重用户的隐私选择。

本文中描述的IAB TCF支持是Audience manager计划对IAB框架的支持的第一阶段。 目前，Audience manager不支持：

* 移动设备工作流程；
* 跨设备同意管理；
* 将同意书附加到发送到 [URL目标的URL](/help/using/features/destinations/create-url-destination.md);
* 将同意书附加到区段。

## 先决条件 {#prerequisites}

要将IAB TCF与Audience Manager一起使用，您必须满足以下先决条件：

1. 您必须使用Experience Cloud ID服务(ECID)4.1版或更高版本。 [下载](https://github.com/Adobe-Marketing-Cloud/id-service/releases) ECID的最新版本。
2. 
   1. 您必须使用Audience Manager数据集成库(DIL)9.0版或更高版本，可从此处下 [载](https://github.com/Adobe-Marketing-Cloud/dil/releases)。 阅读Audience manager文 [档中的DIL信息](/help/using/dil/dil-overview.md)。
   2. 或者，如果使用服务器端转发(SSF)将数据导入Audience Manager，则必须升级到最新版AppMeasurement。 使用Analytics代码管理器 [下载AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。
3. 您必须使用支持IAB的商业类或您自己的同意管理平台(CMP)，并在IAB TCF中注册。 请参见在IAB框架 [内注册的CMP的列表](https://advertisingconsent.eu/cmp-list/)。

## 建议及如何实施 {#recommendations}

要在Audience manager中启用IAB TCF支持，请阅读我们有关如 [何通过选择加入设置IAB的文档](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。

使用 [Adobe Launch在您的属性上使用ECID](https://docs.adobelaunch.com/) Opt-in，可以最轻松地完成此操作。 Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## 使用IAB框架时的用户选择工作流 {#user-choice-workflow}

在访问Web属性时，用户可以提供有关发布者以及发布者与之合作的第三方供应商如何使用其数据的选择。 用户以标准用途和权限的形 *式向在全局供应商列* 表中注册的第三方供应商 ** 提供其选择。 下图代表CMP对话框的示例，该对话框显示给网站的首次访客。 请记住，根据客户实施情况，此对话可能看起来非常不同。

![CMP对话框](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB框架中的标准用途是：

* 信息存储和访问
* 个性化
* 广告选择、投放和报告
* 内容选择、交付和报告
* 测量

有关五 [个标准用途的说明](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) ，请参阅IAB框架规范页。

用户可以出于标准目的和供应商的考虑授予他们同意。 例如，用户可以授予其对存储、个性化和衡量的同意，并授予其对由《议定书》/《公约》缔约方会议展示的所有第三方供应商的同意。 或者，在另一个例子中，他们可以就所有五项标准目的同意，但只准许《议定书》/《公约》缔约方会议所显示的几个供应商同意。

当用户选择其隐私选择后，用户选择被记录在IAB TCF同意字符串中。 IAB TCF同意字符串存储已批准用途和供应商的组合以及其他元数据信息(请参阅 [IAB页面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) ，了解更多信息)。 在IAB TCF中注册的每个供应商评估IAB TCF同意字符串并根据用户的隐私选择做出决策。 请记住，用户的隐私选择在所有经过批准的供应商中均有效。

## Audience manager需要的标准用途 {#aam-standard-purposes}

Audience manager评估存储在IAB TFC同意字符串中的用户选择，其目的是：

* 信息存储和访问(全局供应商列表中的目 [的ID 1](https://vendorlist.consensu.org/vendorlist.json))
* 个性化（目的ID 2）
* 测量（用途ID 5）
* Audience manager供应商同意为发布者存储、处理或激活数据。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience manager的行为取决于用户是否同意 {#aam-behavior-consent}

Audience manager的工作方式不同，具体取决于Audience manager是否在IAB TCF同意字符串中检测到用户已为三个用途（存储、个性化、衡量）提供同意。

| 当用户同 *意后*,Audience Manager: | 当用户拒绝 *同意* ,Audience Manager: |
|---|---|
| <ul><li>执行您请求的所有Audience manager使用案例。</li><li>向ID同步中的第三方传达同意（通过在ID同步调用中通过gdpr = 1和同意字符串作为gdpr_connence）。</li><li>评估并接受从广告服务器像素传递的同意。</li><li>支持合作伙伴发起的ID同步。</li></ul> | <ul><li>不在实例中存储任何新用户数据。 这包括合作伙伴ID、信号、特征或像素数据。</li><li>不启动第三方ID同步。</li><li>不支持由合作伙伴发起的ID同步。</li></ul> |



## 发布者用例 {#publisher-use-case}

通过实施IAB TCF，您无需通过Adobe或其他第三方供应商的其他机制在您的Web属性上维护用于同意管理的自定义代码。 图像和以下步骤介绍了用例。 从图像左侧开始：

1. 用户访问您的某个Web属性。 只要您使用最新版本的ECID和DIL库(请参阅 [先决条件](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites))，就会触发选择加入流程。
2. Audience manager检查IAB流是否适用(`isIabContext=true`)。 请参 [阅建议和如何实施](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)。
3. Audience manager检查GDPR是否适用(`gdpr = 1`)，以及您的Web资产上是否存在向IAB注册的CMP。 例如，这将适用于从欧盟地区访问的用户。 请注意，作为发布者，您有责任设置GDPR标志。
4. 如果GDPR适用，Audience manager将检查在参数中传递的IAB TCF同意字符串，以 `gdpr_consent`获得所需的权限。 Audience manager需要存储、个性化、评估权限以及Audience manager供应商的同意权限，才能存储、处理或激活数据。
5. 如果IAB TCF同意字符串存在并且包含所需的权限，则Audience manager会将IAB TCF同意字符串传递到我们的 [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) (DCS)。
6. Audience manager通过在浏览器上设置 [Demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) 来做出响应。 Audience manager还启动并支持第三方ID同步。
7. 或者，如果在步骤5中通过的IAB TCF同意字符串不包含所有所需的权限，则Audience manager不会收集、处理或激活数据，也不会执行或启动ID同步。

![发布者用例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

Audience manager根据IAB TCF评估并接受在像素调 [用中通过](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)的同意。

像素通常由Audience manager客户放在其合作伙伴页面上，或者放在广告服务器中以包含在广告响应中。 在第一种情况下，您的合作伙伴必须以编程方式检索同意参数并将其添加到像素，然后才能触发。 在第二种情况中，广告服务器将从供应端平台(SSP)或发布者广告服务器收到的同意参数附加到所有像素，这种情况更为常见，具体如下所述。

Audience manager使用两个参数在像素调用中通过用户同意：

* `gdpr` 可以是0（GDPR不适用）或1（GDPR适用）;
* `gdpr_consent` 是URL安全的base64编码的GDPR同意字符串(请参 [阅规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications))。 对印象像素的示例调用，其中两个参数可能如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

图像和以下步骤介绍了用例。 从图像左侧开始：

1. 广告服务器会给用户留下印象。 这将转化为对我们的数据收集服务器(DCS)的像素调用。
1. Audience manager检查GDPR标志是否适用。 否则，Audience manager会在像素调用中存储宏变量中传递的数据。
1. 如果同意字符串存在并且包含所需的权限，则Audience manager会将传入宏变量的数据存储在像素调用中。
1. 如果同意字符串缺失或缺少所需的权限，则Audience manager会删除像素调用中宏变量中传递的数据。

![广告商用例](assets/advertiser-use-case.png)

## 支持IAB TCF的激活合作伙伴 {#aam-activation-partners}

适用于IAB TCF的Audience Manager插件允许您将IAB TCF同意字符串转发给激活合作伙伴，同时尊重用户的隐私选择。 有关哪些激活合作伙伴支持IAB TCF（截至2019年7月7日准确）的信息，请参阅我们的 **[Partner excel表](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**。

## 测试IAB实施 {#test-iab-implementation}

要测试您是否正确实施了IAB TCF的Audience Manager插件，请阅读 [Validation Methods for Opt-in和IAB实施中的使用案例4](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)。

## IAB和Audience Manager中的选择退出。 优先顺序。 {#iab-and-optout}

用户还可以选择退出所有数据收集，这是另一个隐私权选项。 Adobe为用户提供了在“您的隐私选择”页面 [中执行此操作](https://www.adobe.com/privacy/opt-out.html#customeruse) 的方法。

Audience manager在我们文档中的另一篇文章中解 [决了退出管理问题](/help/using/overview/data-security-and-privacy/opt-out-management.md)。

>[!NOTE]
>
>**优先顺序** -如果用户使用全局退出工具退出数据收集（如上面链接所述），则此优先级高于选择加入和IAB验证。

## 其他资源 {#additional-resources}

* [Experience Cloud ID服务选择加入](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB欧洲GDPR透明度和同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB欧洲GDPR透明度和同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin —— 视频演示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)