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

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。Audience Manager在IAB TCF中注册为供应商ID565。

IAB TCF的Audience Manager插件采用 [选择加入功能](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)，该功能是Adobe [Experience Cloud ID服务(ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) 库的一部分。

## 范围和限制 {#scope-and-limitations}

作为使用Audience Manager的Publisher或Advertiser，您可以根据IAB TCF传达对Audience Manager的用户选择。这为您提供了一种轻松、一致的方式来向您使用的所有合作伙伴交流用户选择，Audience Manager可以帮助您尊重用户的隐私选择。

本文所述的IAB TCF支持表示AAB Manager计划支持IAB框架的第一阶段。目前，Audience Manager不支持：

* 移动设备工作流程；
* 跨设备同意管理；
* 附加同意发送到 [URL目标](/help/using/features/destinations/create-url-destination.md)的URL；
* 附加同意区段。

## 先决条件 {#prerequisites}

您必须满足以下前提条件才能将IAB TCF与Audience Manager结合使用：

1. 您必须使用Experience Cloud ID Service(EID)版本4.1或更新版本。[下载](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 我们最新的ECID版本。
2. 
   1. 您必须使用Audience Manager数据集成库(DIL)9.0或更新版本， [可从此处下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)。在Audience [Manager文档](/help/using/dil/dil-overview.md)中了解DIL。
   2. 或者，如果您使用服务器端转发(SSSF)将数据导入Audience Manager，则必须升级到AppMeasurement的最新版本。使用 [Analytics代码管理器下载AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。
3. 您必须使用支持IAB的同意管理平台(CMP)，它支持IAB，并且已注册IAB TCF。查看IAB框架中注册 [的CMS的列表](https://advertisingconsent.eu/cmp-list/)。

## 推荐和如何实施 {#recommendations}

要在Audience Manager中启用IAB TCF支持，请阅读我们关于 [如何通过选择加入IAB设置IAB的文档](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)。

这是使用 [Adobe Launch](https://docs.adobelaunch.com/) 在您的属性上选择EID选择加入的最简单方法。Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## 使用IAB框架时的用户选择工作流程 {#user-choice-workflow}

访问Web资产时，您的用户可以提供有关publisher和publisher使用的第三方供应商如何使用其数据的选项。用户以 *标准目的* 和权限向在全球供应商列表中注册的 *第三方供应商* 提供他们的选择。下图显示了一个CMP对话框示例，该对话框显示给网站的首次访客。请记住，这一对话可能会根据客户实施而有所不同。

![CMP对话框](/help/using/overview/aam-gdpr/assets/cmp.png)

IAB框架中的标准用途有：

* 信息存储和访问
* 个性化
* 广告选择、交付和报告
* 内容选择、交付和报告
* 测量

有关五个标准用途的说明，请参阅 [IAB框架规范页面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) 。

用户可以同意标准用途和供应商的组合。例如，用户可以同意存储、个性化和测量，并同意对由“CMP”显示的所有第三方供应商进行同意。或者，在另一个示例中，他们可以为所有五个标准目的授予同意，但仅向部分由“CMP”显示的供应商授予同意。

用户选择其隐私权选择后，用户选择将记录在IAB TCF同意字符串中。IAB TCF同意字符串存储经过批准的目的和供应商以及其他元数据信息(请参阅 [IAB页面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) 以了解更多信息)。在IAB TCF中注册的每个供应商都会评估IAB TCF同意字符串，并根据用户的隐私选择作出决策。请记住，用户的隐私选择在所有认可的供应商中都有效。

## Audience Manager需要的标准用途 {#aam-standard-purposes}

Audience Manager对存储在IAB TFC同意字符串中的用户选择进行评估：

* 信息存储和访问(全局供应商列表 [中的目的ID1](https://vendorlist.consensu.org/vendorlist.json))
* 个性化(目的ID2)
* 测量(目的ID5)
* Audience Manager供应商同意为publisher存储、处理或激活数据。

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager行为取决于用户是否授予同意 {#aam-behavior-consent}

Audience Manager的工作方式不同，具体取决于AAB Manager是否检测到用户已为三个用途(存储、个性化、测量)提供同意的IAB TCF同意字符串。

| 当您的用户 *同意时*，Audience Manager： | 用户 *拒绝* 同意时，Audience Manager： |
|---|---|
| <ul><li>执行您请求的所有Audience Manager使用案例。</li><li>在ID同步中传达给第三方(通过将gdpr=和同意字符串传递为gdpr_同意，以标识ID同步调用)。</li><li>评估并遵守从广告服务器像素传递的同意。</li><li>授予合作伙伴发起的ID同步。</li></ul> | <ul><li>不会存储实例中的任何新用户数据。这包括合作伙伴ID、信号、特征或像素数据。</li><li>不启动第三方ID同步。</li><li>不接受合作伙伴发起的ID同步。</li></ul> |



## Publisher使用案例 {#publisher-use-case}

通过实施IAB TCF，您无需通过与Adobe或其他第三方供应商的不同机制维护自定义代码，以实现网络资产的同意管理。图像中以及以下步骤中介绍了使用案例。从图像左侧开始：

1. 用户访问您的某个Web属性。只要您使用最新版本的ECID和DIL库(请参阅 [入门项目](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites))，就会触发选择流。
2. Audience Manager会检查IAB流程是否应用(`isIabContext=true`)。请参阅 [推荐和如何实施](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations)。
3. Audience Manager会检查GDPR是否应用(`gdpr = 1`)以及在您的Web资产上是否有CMP注册(见IAB)。例如，这适用于从欧盟地区访问的用户。请注意，您应作为publisher负责设置GDPR标志。
4. 如果GDPR适用，Audience Manager会根据需要检查该参数 `gdpr_consent`中传递的IAB TCF同意字符串。Audience Manager需要使用存储、个性化、测量和Audience Manager供应商同意权限，以存储、处理或激活数据。
5. 如果IAB TCF同意字符串存在并且它包含所需的权限，Audience Manager会将IAB TCF同意字符串传递到我们 [的数据收集服务器](/help/using/reference/system-components/components-data-collection.md) (DCS)。
6. Audience Manager通过在浏览器上设置 [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) 做出响应。Audience Manager还启动和遵守第三方ID同步。
7. 或者，如果在步骤中传递的IAB TCF同意字符串不包含所有所需的权限，Audience Manager不会收集、处理或激活数据，并且不会授予或启动ID同步。

![Publisher使用案例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

Audience Manager根据IAB TCF评估并遵守 [以像素调用](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)形式传递的同意。

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

## 支持IAB TCF的激活合作伙伴 {#aam-activation-partners}

IAB TCF的Audience Manager插件使您能够将IAB TCF同意字符串转发给激活合作伙伴，同时拒绝用户的隐私选择。有关哪些激活合作伙伴支持IAB TCF(自2019年月日起)的信息，请参阅我们 **[的合作伙伴Excel表](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**。

## 测试IAB实施 {#test-iab-implementation}

要测试您是否正确实施了IAB TCF的Audience Manager插件，请阅读 [用于选择加入和IAB实施的验证方法中的使用案例4](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)。

## AAB和Opt-out in Audience Manager。优先级。 {#iab-and-optout}

用户使用的另一个隐私选项是选择退出所有数据收集。Adobe为用户提供了在“您的隐私选择 [](https://www.adobe.com/privacy/opt-out.html#customeruse) ”页面中进行此操作的方法。

Audience Manager通过我们文档中 [的单独文章解决选择退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)。

>[!NOTE]
>
>**优先级** -如果用户使用全局选择退出工具退出数据收集，如上面链接中所述，这优先于选择加入和IAB验证。

## 其他资源 {#additional-resources}

* [Experience Cloud ID服务选择加入](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR透明度和同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR透明度和同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF插件-视频演示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)