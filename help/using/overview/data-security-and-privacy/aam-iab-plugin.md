---
description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe 通过选择加入功能和 IAB 透明度及同意框架 (TCF) 支持，为您提供用于管理和传达用户隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-title: 适用于 IAB TCF 的 Audience Manager 插件
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
translation-type: tm+mt
source-git-commit: b5c56453a7278573dec2b80be7baa9833a847a4a
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 7%

---


# 适用于 IAB TCF 的 Audience Manager 插件 {#aam-iab-plugin}

## 概述

您可能对用户承担的隐私义务的一个重要方面是获取和传递用户对个人数据的使用方式（即“用途”）和用户(即“公司”)的选择。

Adobe 通过[选择加入功能](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)和 [IAB 透明度及同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。

>[!IMPORTANT]
>
>受众管理器在 [IAB TCF中注册](https://iabeurope.eu/tcf-for-vendors/) ，供应商ID为565。

IAB TCF的受众管理器插 [件利用](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)，即Adobe Experience Platform Identity Service(ECID)库 [的一部分加入功能](https://docs.adobe.com/content/help/en/id-service/using/home.html) 。

## 范围和限制 {#scope-and-limitations}

作为与受众管理器协作的发布者或广告商，您可以根据IAB TCF向受众管理器传达用户选择。

>[!IMPORTANT]
>
>IAB TCF条例仅适用于位于欧洲经济区的访客。

受众管理器可帮助您尊重用户的隐私权选择，并为您提供一种轻松的方式，让您与与您合作的所有合作伙伴交流这些选择。

目前，受众管理器不支持：

* 移动设备工作流;
* 在细分出口后附加同意。

## 先决条件 {#prerequisites}

>[!IMPORTANT]
>
>受众管理器支持IAB TCF v2.0。
>
>IAB TCF v1.1支持将于2020年8月15日终止。
>
> 希望继续使用IAB TCF的受众管理器插件进行同意管理的客户应升级到最新版 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 以继续支持。
>
> 升级到最新 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 版本后，将不再支持IAB TCF v1.1同意字符串，因此请确保在升级到最新ECID版本之前更新您的CMP。

要将IAB TCF的受众管理器插件与受众管理器一起使用，您必须满足以下先决条件：

1. 您必须使用Adobe Experience Platform Identity Service(ECID)版本5或更高版本。 [下载我们](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 最新的ECID版本。
2. 您必须使用受众管理器数据集成库(DIL)9.0版或更高版本，可从此处下 [载](https://github.com/Adobe-Marketing-Cloud/dil/releases)。 阅读受众 [管理器文档中的DIL](../..//dil/dil-overview.md)。 我们建议使 [用Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) ，实现受众管理器最简单的DIL实施。
3. 或者，如果您使用服务器端转发(SSF)将数据导入受众管理器，则必须升级到最新版AppMeasurement。 使用Analytics Code Manager [下载AppMeasurement](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)。
4. 您必须使用与IAB TCF v2.0集成并在IAB TCF中注册的商业类或您自己的同意管理平台(CMP)。 请参见在IAB框 [架中注册的CMP的列表](https://iabeurope.eu/cmp-list/)。

>[!WARNING]
>
>如果您使用的是不支持IAB TCF v.2.0的同意管理平台(CMP),受众管理器将自动以ID同 `gdpr=0` 步发送参数，即使访客在欧洲合并。 要确定您的GDPR验证是否处于活动状态，我们建议您通过同意管理平台(CMP)确认他们支持IAB TCF v2.0。

## 建议和如何实施 {#recommendations}

要在受众管理器中启用IAB TCF支持，请阅读我们的 [文档，了解如何通过选择加入设置IAB](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)。

执行此操作的最简单方法是使 [用Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) ，在您的属性上添加ECID选择加入。 Read the documentation for the [ECID Opt-in extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) to learn how to set up the Launch extension.

## 使用IAB框架时的用户选择工作流 {#user-choice-workflow}

在访问Web属性时，用户可以选择发布者以及发布者与之合作的第三方供应商如何使用其数据。

用户以同意和合法利 *益的形式**为IAB目的* ，向在全 *球供应商列表注册的第* 三方供应商提供他们的选择。

下面的图像代表CMP对话框的示例，显示到网站的首次访客。 请记住，根据客户实施情况，此对话看起来会非常不同。

![CMP对话框](assets/cmp-example.png)

有关IAB TCF v2.0中包括的各种用途和权限的详细信息，请参阅IAB欧洲透明 [度和同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)。

用户可以出于多种目的和供应商的考虑授予他们的同意或合法权益（如果可用）。 例如，用户可以同意在设备上存储信息、开发和改进产品，并同意CMP显示的所有第三方供应商。

或者，在另一个例子中，它们可以出于所有目的同意或合法利益，但只准许《议定书》/《公约》缔约方会议所显示的少数供应商同意或合法利益。

用户选择其隐私选择后，用户选择将记录在IAB TC字符串中。 IAB TC字符串存储已批准用途和供应商的组合以及其他元数据信息(请参 [阅IAB页](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) ，了解更多信息)。

在IAB TCF中注册的每个供应商都评估IAB TC字符串并根据用户的隐私选择做出决策。 请记住，用户的隐私权选择在所有注册IAB TCF的供应商中都有效。

## 受众经理需要的用途 {#aam-standard-purposes}

受众管理器评估存储在IAB TC字符串中的用户选择，以用于以下目的，如IAB欧洲透明度和同 [意框架策略中所定义](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)。 此外，您还可以在全局供应商列表 [中找到用途](https://vendorlist.consensu.org/vendorlist.json)。

* **目的1**: 在设备上存储和／或访问信息；
* **目的十**: 开发和改进产品；
* **特殊目的1**: 确保安全、防止欺诈和调试。

>[!IMPORTANT]
>
>受众经理需要获得用途1和用途10的同意以及供应商的同意，才能部署Cookies并启动或遵守ID同步。
>
>根据 [IAB规定](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)，特殊用途1（确保安全、防止欺诈和调试）始终得到同意，用户不能反对。

## 受众管理者的行为取决于用户是否同意 {#aam-behavior-consent}

受众管理器的工作方式取决于IAB TC字符串是否包含用户同意（在设备上存储和／或访问信息，以及开发和改进产品）。

我们还会检查您在受众管理器中处理的所有目的地是否获得用户同意，只要这些目的地是在IAB TCF中注册的。

| 受众经 *理在用户*&#x200B;同意后： | 当用户拒绝 *同意* ,受众经理： |
|---|---|
| <ul><li>执行您请求的所有受众经理使用案例。</li><li>在ID同步中传达对第三方的同意(在ID同 `gdpr = 1` 步调用中传递同 `gdpr_consent` 意字符串)。</li><li>评估并接受从广告服务器像素传递的同意。</li><li>接受合作伙伴发起的ID同步。</li></ul> | <ul><li>不在实例中存储任何新用户数据。 这包括合作伙伴ID、信号、特征或像素数据。</li><li>不启动第三方ID同步。</li><li>不支持合作伙伴发起的ID同步。</li><li>从进一步的数据收集中选择用户。</li></ul> |

## 发布者用例 {#publisher-use-case}

通过为IAB TCF实施受众管理器插件，您无需通过Adobe或其他第三方供应商的其他机制在您的Web属性上维护用于同意管理的自定义代码。 图像和以下步骤介绍了用例。 开始自图像左侧：

1. 用户访问您的某个Web属性。 只要您使用最新版ECID和DIL库(请参阅 [先决条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites))，就会触发选择加入流。
2. 受众管理器检查IAB流是否适用(`isIabContext=true`)。 请参 [阅建议和如何实施](aam-iab-plugin.md#recommendations)。
3. 受众管理器检查GDPR是`gdpr = 1`否适用()以及您的Web属性上是否存在已向IAB TCF注册的CMP。 例如，这将适用于从欧洲合并访问的用户。 请注意，作为出版商，您有责任设置GDPR标志。
4. 如果GDPR适用，受众经理将检查在参数中传递的IAB TC字 `gdpr_consent` 符串，以获得所需的同意。 受众经理需要同意在设备上存储和／或访问信息([IAB TCF用途1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))、开发和改进产品([IAB TCF用途10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))，以及受众经理供应商同意存储、处理或激活数据。
5. 如果IAB TC字符串存在且包含必需的同意，受众管理器会将IAB TC字符串传递到我们的 [数据收集服务器](../../reference/system-components/components-data-collection.md) (DCS)。
6. 受众管理器通过在浏览器 [上设置demdex](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) cookie来做出响应，并启动并接受第三方ID同步。
7. 或者，如果在步骤4中传递的IAB TC字符串不包含所有所需的权限，受众管理器不会收集、处理或激活任何用户数据，也不会执行或启动ID同步。 此外，它还会从您处理的目标中选择用户。

>[!IMPORTANT]
>
>如果您与需要IAB TCF参数的受众管理器目标合作伙伴合作，但您的网站上没有支持IAB TCF的CMP，则受众管理器以ID同 `gdpr=0` 步方式发送。 这意味着GDPR不适用于这些用户。
>
> 如果不需要，您应启用受众管理器中的IAB TCF功能，以将适当的IAB TC字符串发送给目标合作伙伴。



![发布者用例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

受众经理根据IAB TCF评估 [和接受](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)（在像素调用中）通过的同意。

像素可由受众经理客户放在其合作伙伴页面上，也可置于广告服务器中以包含在广告响应中。 在第一种情况下，您的合作伙伴必须以编程方式检索同意参数并将其添加到像素，然后才能触发。 在第二种情况下，广告服务器将从供应端平台(SSP)或发布者广告服务器接收的同意参数附加到所有像素，这种情况较为常见，详细描述如下。

受众管理器在像素调用中使用两个参数传递用户同意：

* `gdpr` 可为0（GDPR不适用）或1（GDPR适用）;
* `gdpr_consent` 是URL安全的基本64编码的GDPR同意字符串(请参 [阅规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string))。 对印象像素的示例调用，其中两个参数如下所示：

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

图像和以下步骤介绍了用例。 开始自图像左侧：

1. 广告服务器会给用户留下深刻印象。 这转换为对我 [们的数据收集](../../integration/media-data-integration/impression-data-pixels.md) 服务器(DCS)的像素调用。
2. 受众管理器检查GDPR标志是否适用。 否则，受众管理器将在像素调用中存储传入 `gdpr` 的数 `gdpr_consent` 据和变量。
3. 如果IAB TC字符串存在并且包含所需的权限，受众管理器会存储在像素调用中传递 `gdpr` 的数 `gdpr_consent` 据和变量中。
4. 如果IAB TC字符串缺失或缺少所需的权限，受众管理器会删除像素调用中传递 `gdpr` 的 `gdpr_consent` 数据和变量。

![广告商用例](assets/advertiser-use-case.png)

## 支持IAB TCF的激活合作伙伴 {#aam-activation-partners}

IAB TCF的受众管理器插件允许您将IAB TC字符串转发给激活合作伙伴，同时尊重用户的隐私选择。 有关哪些激活合作伙伴支持IAB TCF的信息，请参阅我们 [基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)。

## 将同意附加到发送到URL目标的URL

受众管理器与IAB TCF v2.0的集成支持将同意附加到发送到与 [IAB](../../features/destinations/create-url-destination.md) TCF v2.0集成的URL目标的信息。但是，此过程不是由受众管理器自动完成的，以避免破坏特定的URL格式。

希望同意发送到URL目标的数据的客户必须手动将 `${GDPR}` 和 `${GDPR_CONSENT_XXXX}` 宏添加到其URL格式，并 `XXXX` 替换为目标合作伙伴ID。

示例: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

有关 [支持的目标宏](../../features/destinations/destination-macros.md) ，请参阅定义的目标宏。

## 跨设备同意管理

当您的站点受众不提供适当的权限时，IAB TCF的访客管理器插件会自动选择请求中显示的ID。 如果请求包 [含跨设备ID(CRM ID)](../../reference/ids-in-aam.md),受众管理器将选出该ID，以及链接到该跨设备ID(CRM ID) [的最后一个设备](../../reference/ids-in-aam.md)。

## 测试IAB实施 {#test-iab-implementation}

要测试您是否正确实现了IAB TCF的受众管理器插件，请阅 [读验证加入服务中的用例4](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)。

## IAB和退出受众管理器。 优先顺序。 {#iab-and-optout}

用户可使用的另一个隐私选项是能够收选择退出集所有数据。 Adobe为用户提供在您的隐私选择页面 [中执行此操作](https://www.adobe.com/privacy/opt-out.html#customeruse) 。

受众管理器在我们文档中的另一 [篇文章中解决退出请求](data-privacy-requests.md#opt-out-requests)。

>[!IMPORTANT]
>
>拒绝同意后选择退出所有数据收集的用户无法重新加入。

>[!NOTE]
>
>**优先顺序** -如果用户使用全局退出工具退出数据收集（如上面的链接所述），则此优先于选择加入和IAB验证。

## 其他资源 {#additional-resources}

* [Adobe Experience Platform Identity Service选择加入](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB欧洲GDPR透明度与同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB欧洲GDPR透明度和同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF插件——视频演示](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)