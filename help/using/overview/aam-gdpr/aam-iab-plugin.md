---
description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-title: 适用于 IAB TCF 的 Audience Manager 插件
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
translation-type: tm+mt
source-git-commit: 16c0dd83c18e720045995ac1851b4c91f3346183

---


# 适用于 IAB TCF 的 Audience Manager 插件 {#aam-iab-plugin}

## 概述

在您对用户的隐私义务中，其中一个重要方面是获取和传达用户对其个人数据使用方式（即“目的”）和使用者（即“公司”）的选择。

Adobe 通过[选择加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)和 [IAB 透明度及同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。Audience Manager在IAB TCF中注册为供应商ID565。

The Audience Manager Plug-in for IAB TCF utilizes the [Opt-in functionality](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), which is, in turn, part of the Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) library.

## Scope and Limitations {#scope-and-limitations}

作为使用Audience Manager的Publisher或Advertiser，您可以根据IAB TCF传达对Audience Manager的用户选择。这为您提供了一种轻松、一致的方式来向您使用的所有合作伙伴交流用户选择，Audience Manager可以帮助您尊重用户的隐私选择。

本文所述的IAB TCF支持表示AAB Manager计划支持IAB框架的第一阶段。目前，Audience Manager不支持：

* 移动设备工作流程；
* 跨设备同意管理；
* Appending consent to URLs sent to [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination);
* 附加同意区段。

## 先决条件 {#prerequisites}

您必须满足以下前提条件才能将IAB TCF与Audience Manager结合使用：

1. 您必须使用Experience Cloud ID Service(EID)版本4.1或更新版本。[下载](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 我们最新的ECID版本。
2. 
   1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Read about [DIL in the Audience Manager documentation](/help/using/dil/dil-overview.md).
   2. 或者，如果您使用服务器端转发(SSSF)将数据导入Audience Manager，则必须升级到AppMeasurement的最新版本。Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. 您必须使用支持IAB的同意管理平台(CMP)，它支持IAB，并且已注册IAB TCF。See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## Recommendations and how to implement {#recommendations}

To enable the IAB TCF support in Audience Manager, read our documentation on [how to set up IAB with Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## User choice workflow when using the IAB framework {#user-choice-workflow}

访问Web资产时，您的用户可以提供有关publisher和publisher使用的第三方供应商如何使用其数据的选项。Users provide their choices in the form of *standard purposes* and permissions to *third-party vendors* registered in the global vendor list. 下图显示了一个CMP对话框示例，该对话框显示给网站的首次访客。请记住，这一对话可能会根据客户实施而有所不同。

![CMP对话框](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB框架中的标准用途有：

* 信息存储和访问
* 个性化
* 广告选择、交付和报告
* 内容选择、交付和报告
* 测量

Refer to the [IAB framework specification page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) for a description of the five standard purposes.

用户可以同意标准用途和供应商的组合。例如，用户可以同意存储、个性化和测量，并同意对由“CMP”显示的所有第三方供应商进行同意。或者，在另一个示例中，他们可以为所有五个标准目的授予同意，但仅向部分由“CMP”显示的供应商授予同意。

用户选择其隐私权选择后，用户选择将记录在IAB TCF同意字符串中。The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). 在IAB TCF中注册的每个供应商都会评估IAB TCF同意字符串，并根据用户的隐私选择作出决策。请记住，用户的隐私选择在所有认可的供应商中都有效。

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager对存储在IAB TFC同意字符串中的用户选择进行评估：

* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* 个性化(目的ID2)
* 测量(目的ID5)
* Audience Manager供应商同意为publisher存储、处理或激活数据。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager的工作方式不同，具体取决于AAB Manager是否检测到用户已为三个用途(存储、个性化、测量)提供同意的IAB TCF同意字符串。

| When your user *provides consent*, Audience Manager: | When your user *declines* consent, Audience Manager: |
|---|---|
| <ul><li>执行您请求的所有Audience Manager使用案例。</li><li>在ID同步中传达给第三方(通过将gdpr=和同意字符串传递为gdpr_同意，以标识ID同步调用)。</li><li>评估并遵守从广告服务器像素传递的同意。</li><li>授予合作伙伴发起的ID同步。</li></ul> | <ul><li>不会存储实例中的任何新用户数据。这包括合作伙伴ID、信号、特征或像素数据。</li><li>不启动第三方ID同步。</li><li>不接受合作伙伴发起的ID同步。</li></ul> |



## Publisher Use Case {#publisher-use-case}

通过实施IAB TCF，您无需通过与Adobe或其他第三方供应商的不同机制维护自定义代码，以实现网络资产的同意管理。图像中以及以下步骤中介绍了使用案例。从图像左侧开始：

1. 用户访问您的某个Web属性。As long as you are using the latest versions of the ECID and DIL libraries (see [Prerequisites](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), the opt-in flow is triggered.
2. Audience Manager checks whether the IAB flow applies (`isIabContext=true`). See [Recommendations and how to implement](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB, on your web property. 例如，这适用于从欧盟地区访问的用户。请注意，您应作为publisher负责设置GDPR标志。
4. If GDPR applies, Audience Manager checks the IAB TCF consent string, passed in the parameter `gdpr_consent`, for the needed permissions. Audience Manager需要使用存储、个性化、测量和Audience Manager供应商同意权限，以存储、处理或激活数据。
5. If the IAB TCF consent string is present and it contains the required permissions, Audience Manager passes the IAB TCF consent string on to our [data collection servers](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responds by setting a [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) on the browser. Audience Manager还启动和遵守第三方ID同步。
7. 或者，如果在步骤中传递的IAB TCF同意字符串不包含所有所需的权限，Audience Manager不会收集、处理或激活数据，并且不会授予或启动ID同步。

![Publisher使用案例](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in [pixel calls](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in accordance with the IAB TCF.

像素通常由Audience Manager客户在其合作伙伴页面上放置，或者放置在广告服务器中以包含在广告响应中。在第一种情况下，您的合作伙伴必须有计划地检索同意参数并在触发之前将其添加到像素。在第二种情况下，更常见的是，在下面详细描述了广告服务器，广告服务器将从供应端平台(SP)或publisher广告服务器收到的同意参数附加到所有像素。

Audience Manager使用两个参数在像素调用中传递用户同意：

* `gdpr` 可能为0(GDPR不适用)或1(GDPR适用)；
* `gdpr_consent` 是URL安全基础64编码的GDPR同意字符串(请参见 [规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications))。印象像素的样本调用，其中两个参数如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

图像中以及以下步骤中介绍了使用案例。从图像左侧开始：

1. 您的用户通过广告服务器获得印象。这转换为对我们的数据收集服务器(DCS)的像素调用。
1. Audience Manager会检查GDPR标志是否适用。如果没有，Audience Manager将在像素调用中存储宏变量中传递的数据。
1. 如果同意字符串存在并且它包含所需的权限，Audience Manager将在像素调用中存储宏变量中传递的数据。
1. 如果同意字符串缺失或缺少所需的权限，Audience Manager会丢弃像素调用中宏变量中传递的数据。

![广告商用例](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

IAB TCF的Audience Manager插件使您能够将IAB TCF同意字符串转发给激活合作伙伴，同时拒绝用户的隐私选择。For information on which activation partners support IAB TCF (accurate as of March 21st, 2019), refer to our **[Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-March2019.xlsx)**.

## Test your IAB implementation {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## AAB和Opt-out in Audience Manager。Order of precedence. {#iab-and-optout}

用户使用的另一个隐私选项是选择退出所有数据收集。Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out management in a [separate article in our documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**优先级** -如果用户使用全局选择退出工具退出数据收集，如上面链接中所述，这优先于选择加入和IAB验证。

## 其他资源 {#additional-resources}

* [Experience Cloud ID服务选择加入](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR透明度和同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR透明度和同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF插件-视频演示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)