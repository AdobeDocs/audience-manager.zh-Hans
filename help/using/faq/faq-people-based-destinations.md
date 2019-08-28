---
description: '关于基于People的目标的常见问题解答。  '
seo-description: '关于基于People的目标的常见问题解答。  '
seo-title: 基于人员的目标常见问题解答
solution: Audience Manager
title: 基于人员的目标常见问题解答
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 基于人员的目标常见问题解答 {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**我无法[!DNL People-Based Destinations]在Audience Manager帐户中看到。我需要了解什么可用性？**

[!DNL People-Based Destinations] 是购买后提供的高级Audience Manager功能。有关定价和上市情况的详细信息，请与Adobe销售代表联系。

## 数据适职 {#data-onboarding}

**如何将客户电子邮件地址置于Audience Manager中，以便我能够使用它们[!DNL People-Based Destinations]？**

有两种方法可将离线数据引入Audience Manager [!DNL People-Based Destinations]。

* **使用基于文件的ID同步**。有关 [ID同步文件的详细信息，请参阅ID同步文件](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 的名称和内容要求。使用此方法时，您可以从 [!DNL CRM] 数据库中定位所有散列电子邮件地址。
* **使用声明的ID** 在通过身份验证的客户ID时声明散列电子邮件地址。使用此方法时，Audience Manager只会激活已通过联机身份验证的用户的哈希电子邮件地址。通过Facebook激活的电子邮件地址只是声明ID事件调用中的一个。与客户ID关联的其他电子邮件地址不会实时激活。

**我是否可以通过Web表单或移动应用程序收集散列电子邮件地址，或者它们必须通过批处理文件才能访问？**

您可以 [!DNL ECID] 使用 [声明ID通过Web身份验证收集散列电子邮件地址](../features/declared-ids.md)。通过批处理文件，您还可以收集无法通过身份验证发送的散列电子邮件地址(如([!DNL CRM])中的domust用户)并在基于人员的目标中激活这些地址。

**如何通过Web表单摄取散列电子邮件地址与通过批量文件上传散列电子邮件地址不同？**

离线数据摄取设计为支持不带身份验证的用例，而在所有脱机配置文件上运行的新配置文件合并规则([!UICONTROL All Cross-Device Profiles][!DNL CRM] )可作为一部分提供，而无需使用身份验证 [!DNL People-Based Destinations]。此方法旨在补充从在线来源摄取身份验证的受众。

**我可以在哪个最大频率发送/更新散列电子邮件地址？**

* 使用Declared ID时，Audience Manager会实时将散列电子邮件地址发送到目标。
* 通过ID同步文件摄取数据时，Audience Manager会每天处理这些数据。

**如何知道电子邮件地址哈希是否正确？**

Audience Manager不会摄取原始电子邮件地址，我们无法验证该散列是否已正确完成。有关如何散列载入的数据的详细信息，请参阅 [入门项目和注意事项](../features/destinations/people-based-destinations-prerequisites.md) 。

## 个人资料合并规则 {#profile-merge-rules}

**是否有新的配置文件合并规则可用于[!DNL People-Based Destinations]？**

能。购买的 [!DNL People-Based Destinations] 客户还可以访问新的配置文件合并规则，以实现脱机细分。该规则被调用 [!DNL All Cross-Device Profiles] ，它用于仅脱机分段。注册 [!DNL People-Based Destinations]后，这是您可以创建的第四个配置文件合并规则，除三个基于身份验证的现有规则之外。

**我是否必须复制现有受众细分才能将其激活[!DNL People-Based Destinations]？**

这取决于您的用例。如果您计划在基于人群的渠道激活现有的第一方细分，则无需创建新细分。您只需将区段映射到基于人群的目标即可。

如果计划在基于人群的渠道激活新的离线受众，则需要使用 [!DNL All Cross-Device Profiles] 合并规则创建新的第一方细分。
>[!NOTE]
>
> 您只能使用第一方数据映射区段 [!DNL People-Based Destinations]。我们的目标平台不接受包含第二方和第三方数据的细分。

## 匹配率 {#match-rates}

**能否[!DNL People-Based Destinations]了解匹配率或可寻址受众？**

不会。发送受众细分时 [!DNL People-Based Destinations]，受众匹配在合作伙伴端发生。Adobe无权访问这些指标。Audience Manager为您显示每个目标的最大可共享受众，以及属于某个细分的人们的实时计数。此信息可帮助您进行营销活动规划和预测。

**从理论上讲，使用[!DNL People-Based Destinations]与将受众发送到目标平台的其他方法相比如何匹配费率？**

只要电子邮件地址的哈希化和摄取正确，与 [!DNL People-Based Destinations] 其他方法之间的匹配率也不存在差异。唯一的原因是，如果引入Audience Manager的电子邮件地址无法与目标平台的用户群中的电子邮件地址匹配，则匹配率将低于100%。

**我从客户收集工作电子邮件地址，这与社交网络中使用的个人电子邮件地址不同。您如何在多个电子邮件地址之间匹配身份？**

Audience Manager可为每位用户收集和发送10封电子邮件至目标平台，但需要通过同步文件获取电子邮件地址。Audience Manager将电子邮件地址发送到目标平台后，平台最多可与其自己的用户群匹配。某些平台可能具有其他电子邮件地址图表，以将Audience Manager发送的地址与用户配置文件相匹配。

## 数据导出控制 {#data-export-controls}

**如何[!DNL Data Export Controls]处理[!DNL People-Based Destinations]？**

[!DNL Data Export Controls] 将阻止包含用户尝试发送到 [!DNL People-Based Destinations]的第二方和第三方数据的任何区段。[!DNL People-Based Destinations] 仅允许用于定位的第一方数据。[!DNL Data Export Controls] 还可以使用设备图表 [!DNL Profile Merge Rules] 阻止区段。[!DNL People-Based Destinations] 使用相应的数据导出标签创建，您无法覆盖导出设置。

## 合作伙伴特定问题 {#partner-specific-questions}

### [!DNL Facebook]

**在发送受众细分之前，我需要做什么[!DNL Facebook]？**

在可使用 [!DNL People-Based Destinations] 将受众细分发送到 [!DNL Facebook]之前，您需要执行以下配置任务：

1. 将Adobe Experience Cloud业务帐户添加为您 [!DNL Facebook Ad Account]的广告合作伙伴。使用 `business ID=206617933627973`. 有关详细信息，请参阅向您的业务经理添加合作伙伴。

   >[!IMPORTANT]
   >
   > 在配置Adobe Experience Cloud的权限时，您必须启用“管理营销活动”权限。这是 [!DNL People-Based Destinations] 集成所必需的。

1. 阅读并签署 [!DNL Facebook Custom Audiences Terms of Service]。要执行此操作，请 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`转到 `accountID`[!DNL Facebook Ad Account ID]您的位置。

**[!DNL People-Based Destinations]是否支持其他[!DNL Facebook]应用程序中的受众定位，[!DNL Instagram]例如？**

您可以 [!DNL People-Based Destinations] 在 [!DNL Facebook]支持的应用程序系列中使用 [!DNL Custom Audiences]，包括 [!DNL Facebook]、 [!DNL Instagram][!DNL Audience Network][!DNL Messenger]和。您希望运行的应用程序的选择在放置级别表示 [!DNL Facebook Ads Manager]。

**之间[!DNL People-Based Destinations]有何差异[!DNL Website Custom Audiences]？**

[!DNL People-Based Destinations][!DNL Custom Audiences (CA)][!DNL Facebook]利用集成。在发送受众时 [!DNL WCA] ，客户与 [!DNL CA] 集成之间的区别是客户使用的关键 [!DNL Facebook]。[!DNL WCA] 使用 [!DNL Facebook] 像素(它是网站用户ID)，同时 [!DNL People-Based Destinations] 使用散列电子邮件地址集成 [!DNL CA]。

您可以通过该功能使用Audience Manager [!DNL Facebook][!DNL WCA] 的集成 [!DNL URL Destinations] ，无需额外费用。

这两种集成是互补的；您可以同时使用二者来确保更好的受众范围。例如， [!DNL WCA] 可用于在公司寻找尚未注册帐户的网站访客时进行预测，但 [!DNL People-Based Destinations] 可以帮助您定位已提供电子邮件地址但可能未访问网站的现有客户。
