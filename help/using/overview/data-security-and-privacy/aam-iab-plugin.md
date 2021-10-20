---
description: Adobe 通过选择加入功能和 IAB 透明度与同意框架 (TCF) 支持，为您提供用于管理和传达用户所做的隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '2367'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 概述

在您对用户可能承担的隐私义务中，一个重要方面是获取和传达用户对其个人数据的使用方式（即“目的”）和使用者（即“公司”）所做的选择。

Adobe 通过[选择加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)和 [IAB 透明度与同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户所做的隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。

>[!IMPORTANT]
>
>Audience Manager在 [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) 供应商ID为565。

适用于 IAB TCF 的 Audience Manager 插件利用了[选择加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html)，而该功能又是 [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html) 库的一部分。

## 范围和限制 {#scope-and-limitations}

作为使用 Audience Manager 的出版商或广告商，您可以根据 IAB TCF 向 Audience Manager 传达用户所做的选择。

>[!IMPORTANT]
>
>IAB TCF法规仅适用于位于欧洲经济区的访客。

Audience Manager有助于您尊重用户所做的隐私选择，还为您提供了一种轻松的方式，将这些选择传达给与您合作的所有合作伙伴。

目前，Audience Manager 不支持：

* 移动设备工作流程；
* 将同意附加到区段导出。

## 将 升级至 [!DNL IAB TCF v2.0] {#upgrading}

正在升级其 [!DNL Audience Manager Plug-in for IAB TCF] 实施自 [!DNL IAB TCF] v1.1至 [!DNL IAB TCF] v2.0或启用 [!DNL IAB TCF] v2.0首次在先决条件和实施方面应遵循如下所述的相同准则。

## 先决条件 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager支持IAB TCF v2.0。
>
>IAB TCF v1.1支持将于2020年8月15日终止。
>
> 如果客户希望继续使用适用于IAB TCF的Audience Manager插件进行同意管理，则应升级到的最新版本 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 继续支持。
>
> 升级到最新版本后 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 版本中，将不再支持IAB TCF v1.1同意字符串，因此请确保在升级到最新的ECID版本之前更新您的CMP。

要将适用于IAB TCF的Audience Manager插件与Audience Manager结合使用，您必须满足以下先决条件：

1. 您必须使用 Adobe Experience Platform Identity Service (ECID) 版本 5 或更高版本。[下载](https://github.com/Adobe-Marketing-Cloud/id-service/releases) ECID 的最新版本。
2. 您必须使用Audience Manager [!DNL Data Integration Library] (DIL)9.0或更高版本，可从以下网站下载 [此处](https://github.com/Adobe-Marketing-Cloud/dil/releases). 请阅读 [Audience Manager 中的 DIL 文档](../../dil/dil-overview.md)。我们建议使用 [Adobe Audience Manager标记扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) ，以实现最简单的DILAudience Manager。
3. 或者，如果您使用 [!DNL Server-Side Forwarding] (SSF)要将数据导入Audience Manager，您必须升级到AppMeasurement的最新版本。 使用 [Analytics 代码管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html)下载 AppMeasurement。
4. 您必须使用与IAB TCF v2.0集成并在IAB TCF中注册的商业同意管理平台(CMP)，或者您自己的同意管理平台(CMP)。 请参阅[在 IAB 框架内注册的 CMP](https://iabeurope.eu/cmp-list/)。

>[!WARNING]
>
>如果您使用的同意管理平台(CMP)不支持IAB TCF v.2.0，则Audience Manager将自动发送 `gdpr=0` 参数（即使您的访客位于欧盟）。 要确定您的GDPR验证是否处于活动状态，我们建议您通过同意管理平台(CMP)确认它们支持IAB TCF v2.0。

## 建议和实施方式 {#recommendations}

要在 Audience Manager 中启用 IAB TCF 支持，请阅读我们关于[如何通过选择加入来设置 IAB](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html) 的文档。

最简单的方法是使用 [Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 添加 [!DNL ECID Opt-in] 在您的资产上。 请阅读相关文档 [ECID选择加入扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) 以了解如何设置标记扩展。

## 使用 IAB 框架时的用户选择工作流程 {#user-choice-workflow}

在访问 Web 资产时，用户可以选择出版商以及与之合作的第三方供应商如何使用其数据。

用户以 *同意* 和 *合法利益* 用于IAB目的 *第三方供应商* 已在全球供应商列表中注册。

下图是向首次访问网站的访客显示的 CMP 对话框的一个示例。请记住，根据客户实施情况，此对话框可能会大不相同。

![CMP 对话框](assets/cmp-example.png)

有关IAB TCF v2.0中包含的各种目的和权限的详细信息，请参阅 [IAB欧洲透明度与同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

用户可以出于目的和供应商的组合，授予用户同意或合法利益（如果可用）。 例如，用户可以同意在设备上存储信息、开发和改进产品，并向CMP显示的所有第三方供应商授予同意。

或者，在另一个示例中，他们可以出于所有目的授予同意或合法利益，但只向CMP显示的少数供应商授予同意或合法利益。

用户选择其隐私选择后，用户选择将记录在IAB TC字符串中。 IAB TC字符串会存储已批准目的和供应商的组合以及其他元数据信息(请参阅 [IAB页面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) ，以了解更多信息)。

在IAB TCF中注册的每个供应商都会评估IAB TC字符串，并根据用户所做的隐私选择做出决策。 请记住，用户所做的隐私选择在使用IAB TCF注册的所有供应商中都有效。

## Audience Manager所需目的 {#aam-standard-purposes}

Audience Manager将评估IAB TC字符串中存储的用户选择，以用于以下目的(在 [IAB欧洲透明度与同意框架政策](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **用途1**:在设备上存储和/或访问信息；
* **用途10**:开发和改进产品；
* **特殊用途1**:确保安全性、防止欺诈和调试。

>[!IMPORTANT]
>
>Audience Manager需要获得目的1和目的10的同意以及供应商同意，才能部署Cookie并启动ID同步或使之生效。
>
>每 [IAB法规](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)、特殊目的1（确保安全、防止欺诈和调试）始终获得同意，且用户无法对其提出异议。

## Audience Manager 的行为取决于用户是否授予同意 {#aam-behavior-consent}

Audience Manager的工作方式不同，具体取决于IAB TC字符串是否包含用户同意这两个目的（存储和/或访问设备上的信息，以及开发和改进产品）。

只要这些目标已在IAB TCF中注册，我们还会检查是否同意您在Audience Manager中使用的所有目标。

| 当用户&#x200B;*表示同意*&#x200B;时，Audience Manager： | 当用户&#x200B;*拒绝同意*&#x200B;时，Audience Manager： |
|---|---|
| <ul><li>执行您请求的所有 Audience Manager 用例。</li><li>在ID同步中向第三方传达同意(通过 `gdpr = 1` 同意字符串为 `gdpr_consent` （在ID同步调用中）。</li><li>评估并遵循通过广告服务器像素传递的同意。</li><li>执行合作伙伴启动的 ID 同步。</li></ul> | <ul><li>在您的实例中不存储任何新的用户数据。这包括合作伙伴 ID、信号、特征或像素数据。</li><li>不启动第三方 ID 同步。</li><li>不执行合作伙伴启动的 ID 同步。</li><li>从进一步的数据收集中选择用户。</li></ul> |

## 出版商用例 {#publisher-use-case}

通过实施适用于IAB TCF的Audience Manager插件，您无需通过与Adobe或其他第三方供应商的其他机制来维护用于对Web资产进行同意管理的自定义代码。 下面的图像和步骤中介绍了相关用例。我们将从图像左侧开始介绍：

1. 用户访问您的某个 Web 资产。只要您使用最新版的 ECID 和 DIL 库（请参阅[先决条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)），就会触发选择加入流程。
2. Audience Manager 检查 IAB 流程是否适用 (`isIabContext=true`)。请参阅[建议和实施方式](aam-iab-plugin.md#recommendations)。
3. Audience Manager检查GDPR是否适用(`gdpr = 1`)以及您的Web资产上是否存在在IAB TCF中注册的CMP。 例如，这将适用于从欧盟访问的用户。 请注意，作为发布者，您有责任设置GDPR标记。
4. 如果GDPR适用，则Audience Manager会检查传入的IAB TC字符串 `gdpr_consent` 参数，以获得所需的同意。 Audience Manager需要获得存储和/或访问设备上信息的同意([IAB TCF用途1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))、开发和改进产品([IAB TCF用途10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))，以及Audience Manager供应商同意存储、处理或激活数据。
5. 如果IAB TC字符串存在并且包含所需的同意，则Audience Manager会将IAB TC字符串传递到我们的 [数据收集服务器](../../reference/system-components/components-data-collection.md) (DCS)。
6. Audience Manager通过设置 [demdex cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) ，并启动并执行第三方ID同步。
7. 或者，如果在步骤4中传递的IAB TC字符串不包含所有所需的权限，则Audience Manager不会收集、处理或激活任何用户数据，也不会执行或启动ID同步。 此外，它还会从您处理的目标中选择用户。

>[!IMPORTANT]
>
>如果您与需要IAB TCF参数的Audience Manager目标合作伙伴合作，但您的网站上没有支持IAB TCF的CMP，则Audience Manager会发送 `gdpr=0` 在ID同步中。 这意味着GDPR不适用于这些用户。
>
> 如果不需要，您应当启用Audience Manager中的IAB TCF功能，以将相应的IAB TC字符串发送到目标合作伙伴。



![出版商用例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

Audience Manager 根据 IAB TCF 评估并遵循在[像素调用](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)中传递的同意。

像素可能由Audience Manager客户放置在其合作伙伴页面上，也可能放置在广告服务器中以包含在广告响应中。 对于第一种情况，您的合作伙伴必须以编程方式检索同意参数并将其添加到像素，然后才能触发。对于第二种情况，广告服务器会将从供应方平台 (SSP) 或出版商广告服务器接收的同意参数附加到所有像素，这种情况较为常见，详细描述如下。

Audience Manager 在像素调用中使用两个参数传递用户同意：

* `gdpr` 可以为 0（GDPR 不适用）或 1（GDPR 适用）；
* `gdpr_consent` 是 URL 安全的 base64 编码 GDPR 同意字符串（请参阅[规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)）。对展示像素的示例调用（其中包含这两个参数）如下所示：

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

下面的图像和步骤中介绍了相关用例。我们将从图像左侧开始介绍：

1. 通过广告服务器向您的用户提供一次展示。这将转换为 [像素调用](../../integration/media-data-integration/impression-data-pixels.md) 到我们的数据收集服务器(DCS)。
2. Audience Manager 检查 GDPR 标记是否适用。如果没有，则Audience Manager将存储在 `gdpr` 和 `gdpr_consent` 像素调用中的变量。
3. 如果IAB TC字符串存在并且包含所需的权限，则Audience Manager将存储在 `gdpr` 和 `gdpr_consent` 像素调用中的变量。
4. 如果IAB TC字符串缺失或缺少所需的权限，则Audience Manager会丢弃在 `gdpr` 和 `gdpr_consent` 像素调用中的变量。

![广告商用例](assets/advertiser-use-case.png)

## 支持 IAB TCF 的激活合作伙伴 {#aam-activation-partners}

适用于IAB TCF的Audience Manager插件允许您将IAB TC字符串转发给激活合作伙伴，同时尊重用户所做的隐私选择。 有关哪些激活合作伙伴支持 IAB TCF 的信息，请参阅我们[基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)。

## 将同意附加到发送到URL目标的URL

与IAB TCF v2.0的Audience Manager集成支持将同意附加到发送到的信息 [URL目标](../../features/destinations/create-url-destination.md) 与IAB TCF v2.0集成的URL格式。但是，此过程不会通过Audience Manager自动完成，以避免中断特定的URL格式。

希望将同意附加到发送到 [!DNL URL destinations] 必须手动添加 `${GDPR}` 和 `${GDPR_CONSENT_XXXX}` 宏转换为其URL格式，替换 `XXXX` 具有目标合作伙伴ID。

示例: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

请参阅 [定义的目标宏](../../features/destinations/destination-macros.md) 有关支持的目标宏的更多详细信息。

## 跨设备同意管理

适用于IAB TCF的Audience Manager插件会在网站访客没有提供相应权限时自动选择请求中存在的ID。 如果请求包含 [跨设备ID(CRM ID)](../../reference/ids-in-aam.md)，则Audience Manager会选择该ID以及链接到该ID的最后一个设备 [跨设备ID(CRM ID)](../../reference/ids-in-aam.md).

## 测试 IAB 实施 {#test-iab-implementation}

要测试您是否已正确实施适用于IAB TCF的Audience Manager插件，请阅读 [验证选择加入服务的用例4](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## Audience Manager 中的 IAB 和选择退出。优先级顺序。 {#iab-and-optout}

用户可以选择的另一个隐私选项是选择退出所有数据收集。Adobe 在[隐私选择](https://www.adobe.com/cn/privacy/opt-out.html#customeruse)页面中为用户提供了相应的操作方法。

Audience Manager 在[我们文档中的单独文章](data-privacy-requests.md#opt-out-requests)中介绍了选择退出请求。

>[!IMPORTANT]
>
>拒绝同意后被选择退出所有数据收集的用户，将无法选择重新加入。

>[!NOTE]
>
>**优先级顺序** - 如果用户使用全局选择退出工具选择退出数据收集（如上面的链接所述），则此选项优先于选择加入和 IAB 验证。

## 其他资源 {#additional-resources}

* [Adobe Experience Platform Identity Service 选择加入](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 欧洲 GDPR 透明度与同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 欧洲 GDPR 透明度与同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 插件 - 视频演示](https://helpx.adobe.com/cn/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
