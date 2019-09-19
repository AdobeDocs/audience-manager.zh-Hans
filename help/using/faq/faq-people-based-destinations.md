---
description: '关于基于人员的目标的常见问题解答。  '
seo-description: '关于基于人员的目标的常见问题解答。  '
seo-title: 基于人员的目标常见问题解答
solution: Audience Manager
title: 基于人员的目标常见问题解答
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 基于人员的目标常见问题解答 {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**我无法在[!DNL People-Based Destinations]Audience manager帐户中查看。 我需要了解哪些可用性？**

[!DNL People-Based Destinations] 是购买时可用的高级Audience Manager功能。 有关价格和上市时间的详细信息，请与Adobe销售代表联系。

## 数据入门 {#data-onboarding}

**我如何将客户电子邮件地址载入Audience Manager中，以便在中使用[!DNL People-Based Destinations]?**

有两种方法可将离线数据导入Audience Manager [!DNL People-Based Destinations]。

* **使用基于文件的ID同步**。 有关 [ID同步文件的外观的详细信息](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，请参阅ID同步文件的名称和内容要求。 使用此方法时，您可以瞄准数据库中的所有哈希电子邮件地址 [!DNL CRM] 。
* **在传入经过身份验证的客户ID时** ，使用Declared ID声明具有哈希值的电子邮件地址。 使用此方法时，Audience manager仅激活已通过联机身份验证的用户的哈希电子邮件地址。 通过Facebook激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时激活。

**我是否可以通过Web表单或移动应用程序收集经过散列处理的电子邮件地址，或者它们必须通过批处理文件进行收集？**

您可以使用Declared ID通过Web身份验证收集散列 [!DNL ECID] 化的 [电子邮件地址](../features/declared-ids.md)。 批处理文件还允许您收集通过身份验证无法发送的散列电子邮件地址(例如，您的([!DNL CRM])中的休眠用户)，并在基于人员的目标中激活这些地址。

**通过Web表单摄取哈希电子邮件地址与通过批处理文件上传哈希电子邮件地址有何不同？**

脱机数据摄取设计为支持无身份验证的用例，并且新的配置文件合并规则([!UICONTROL All Cross-Device Profiles])可作为的一部分提供，该规则在所有脱机配置文件上运行，而与身份验证无关 [!DNL CRM][!DNL People-Based Destinations]。 此方法旨在补充从在线来源获取经身份验证的受众。

**我可以发送／更新散列化电子邮件地址的最大频率是多少？**

* 使用Declared ID时，Audience manager会将散列化的电子邮件地址实时发送到目标。
* 通过ID同步文件摄取数据时，Audience Manager每天都会处理这些数据。

**如何知道电子邮件地址哈希是否正确？**

Audience manager未摄取原始电子邮件地址，我们无法验证哈希是否正确。 有关 [如何散列已载入数据的详细信息](../features/destinations/people-based-destinations-prerequisites.md) ，请参阅先决条件和注意事项。

## 个人资料合并规则 {#profile-merge-rules}

**我是否可以使用新的配置文件合并规则[!DNL People-Based Destinations]?**

能。购买的客户 [!DNL People-Based Destinations] 还可以访问新的配置文件合并规则，以便进行脱机细分。 该规则被调 [!DNL All Cross-Device Profiles] 用，用于仅脱机分段。 注册时，除了三 [!DNL People-Based Destinations]个现有的基于身份验证的规则外，这是您可以创建的第四个配置文件合并规则。

**是否必须复制现有受众细分才能在中激活[!DNL People-Based Destinations]?**

这取决于你的用例。 如果您计划在基于人员的渠道中激活现有的第一方细分，则无需创建新细分。 您只需将区段映射到基于人员的目标。

如果您计划在基于人员的渠道中激活新的线下受众，则需要使用合并规则创建新的第 [!DNL All Cross-Device Profiles] 一方细分。
>[!NOTE]
>
> 您只能将具有第一方数据的区段映射到 [!DNL People-Based Destinations]。 我们的目标平台不接受具有第二方和第三方数据的细分。

## 匹配率 {#match-rates}

**是否[!DNL People-Based Destinations]可以了解匹配率或可寻址的受众？**

不会。将受众细分发送到 [!DNL People-Based Destinations]时，受众匹配会在合作伙伴端发生。 Adobe无权访问这些指标。 Audience manager为您显示每个目标的最大可共享受众数以及属于某个区段的人员的实时计数。 此信息可以帮助您进行营销活动规划和预测。

**与将受众发送到目标平台[!DNL People-Based Destinations]的其他方法相比，理论上如何使用匹配率？**

只要电子邮件地址经过哈希处理并正确摄取，其匹配率就不会与其他方法 [!DNL People-Based Destinations] 有任何差异。 匹配率低于100%的唯一原因是，如果引入Audience manager的电子邮件地址与目标平台用户群中的电子邮件地址不匹配。

**我收集来自客户的工作电子邮件地址，这些地址与社交网络中使用的个人电子邮件地址不同。 如何在多个电子邮件地址之间匹配身份？**

Audience manager可以收集最多10封电子邮件并发送到目标平台，但需要通过同步文件捕获电子邮件地址。 在Audience manager将电子邮件地址发送到目标平台后，需要由平台根据自己的用户群来匹配电子邮件地址。 某些平台可能具有其他电子邮件地址图表，以匹配从Audience manager发送到用户配置文件的地址。

## 数据导出控制 {#data-export-controls}

**如何[!DNL Data Export Controls]使用[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] 将阻止包含用户尝试发送到的第二方和第三方数据的任何区段 [!DNL People-Based Destinations]。 [!DNL People-Based Destinations] 仅允许第一方数据用于定位。 [!DNL Data Export Controls] 还可使用设备图 [!DNL Profile Merge Rules] 形块段。 [!DNL People-Based Destinations] 创建时会选中相应的数据导出标签，并且您无法覆盖导出设置。

## 合作伙伴特定问题 {#partner-specific-questions}

### [!DNL Facebook]

**在将受众细分发送到之前，我需要做什么[!DNL Facebook]?**

在使用将受 [!DNL People-Based Destinations] 众区段发送到之前 [!DNL Facebook]，您需要执行以下配置任务：

1. 将Adobe Experience cloud商业帐户添加为您的广告合作伙伴 [!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`. 有关详细信息，请参阅将合作伙伴添加到您的业务经理。

   >[!IMPORTANT]
   >
   > 配置Adobe Experience cloud的权限时，必须启用“管理营销活动”权限。 这是集成所必需的 [!DNL People-Based Destinations] 选项。

1. 阅读并签署 [!DNL Facebook Custom Audiences Terms of Service]。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

**是否[!DNL People-Based Destinations]支持其他应用程序([!DNL Facebook]如)中的受众定位[!DNL Instagram]?**

您可以跨 [!DNL People-Based Destinations] 包括、 [!DNL Facebook]和在内的受支持 [!DNL Custom Audiences]的应用程序系 [!DNL Facebook]列 [!DNL Instagram]使用 [!DNL Audience Network][!DNL Messenger]。 在中的放置级别指示要针对其运行营销活动的应用程序的选择 [!DNL Facebook Ads Manager]。

**和之间有何区[!DNL People-Based Destinations]别[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] 利用与 [!DNL Custom Audiences (CA)] 的集成 [!DNL Facebook]。 集成和集 [!DNL WCA] 成之 [!DNL CA] 间的区别是客户在将受众发送到时使用的关键 [!DNL Facebook]。 [!DNL WCA] 使用像 [!DNL Facebook] 素（即网站用户ID），同时使用散列 [!DNL People-Based Destinations] 电子邮件地址与集成 [!DNL CA]。

您可以通过该功能使用Audience Manager [!DNL Facebook] 的集 [!DNL WCA] 成，而 [!DNL URL Destinations] 无需支付额外费用。

这两种整合是相辅相成的，您可以使用两者来确保更好的受众覆盖。 例如，当公司 [!DNL WCA] 寻求定位未注册帐户的网站访客时，可以用于寻找潜在客户，但是 [!DNL People-Based Destinations] ，可以帮助您定位已提供其电子邮件地址但可能未访问网站的现有客户。
