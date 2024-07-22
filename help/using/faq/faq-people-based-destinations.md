---
description: 关于基于人员的目标的常见问题解答。
seo-description: Answers to common questions about People-Based Destinations.
seo-title: People-Based Destinations FAQ
solution: Audience Manager
title: 基于人员的目标常见问题解答
feature: People-based Destinations
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 93%

---

# 基于人员的目标常见问题解答 {#people-based-destinations-faq}

关于 [!DNL People-Based Destinations] 的常见问题解答。

## 可用性 {#availability}

**我在 Audience Manager 帐户中看不到 [!DNL People-Based Destinations]。我需要了解关于可用情况的信息？**

[!DNL People-Based Destinations] 是一项高级 Audience Manager 功能，可在购买后使用。有关定价和可用情况的详细信息，请联系 Adobe 销售代表。

## 数据载入 {#data-onboarding}

**如何将客户电子邮件地址载入 Audience Manager，以便在 [!DNL People-Based Destinations] 中使用？**

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!DNL People-Based Destinations]。

* **使用基于文件的 ID 同步**。有关 ID 同步文件外观的详细信息，请参阅 [ID 同步文件的名称和内容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法时，您可以定位来自 [!DNL CRM] 数据库的所有经过哈希处理的电子邮件地址。
* 在传入经过身份验证的客户 ID 时，**使用声明的 ID** 来声明经过哈希处理的电子邮件地址。使用此方法时，Audience Manager 仅会激活已在线进行身份验证的用户的经过哈希处理的电子邮件地址。通过 Facebook 激活的电子邮件地址只是声明的 ID 事件调用中的电子邮件地址。与客户 ID 关联的其他电子邮件地址不会实时激活。

**我是否可以通过 Web 表单或移动设备应用程序收集经过哈希处理的电子邮件地址，还是必须通过批处理文件来获取这些地址？**

您可以使用带有[声明的 ID](../features/declared-ids.md) 的 [!DNL ECID] 通过 Web 身份验证来收集经过哈希处理的电子邮件地址。使用批处理文件，您还可以收集无法通过身份验证发送的经过哈希处理的电子邮件地址（例如 [!DNL CRM] 中的休眠用户），并在基于人员的目标中激活它们。

**通过 Web 表单摄取经过哈希处理的电子邮件地址与通过批处理文件上传经过哈希处理的电子邮件地址有何不同？**

离线数据摄取可支持未经过身份验证的用例，并且在所有离线 [!DNL CRM] 配置文件上运行的新配置文件合并规则 ([!UICONTROL All Cross-Device Profiles]) 可作为 [!DNL People-Based Destinations] 的一部分使用，而不管是否经过身份验证。此方法旨在补充从在线来源摄取的经过身份验证的受众。

**我可以发送/更新经过哈希处理的电子邮件地址的最大频率是多少？**

* 使用声明的 ID 时，Audience Manager 会将经过哈希处理的电子邮件地址实时发送到目标。
* 通过 ID 同步文件摄取数据时，Audience Manager 每天都会处理它们。

**我如何知道电子邮件地址的哈希处理是否正确？**

Audience Manager 不会摄取原始电子邮件地址，因此我们无法验证哈希处理是否正确。有关如何对载入的数据进行哈希处理的详细信息，请参阅[先决条件和注意事项](../features/destinations/people-based-destinations-prerequisites.md)。

## 配置文件合并规则 {#profile-merge-rules}

**是否可以与 [!DNL People-Based Destinations] 结合使用新的配置文件合并规则？**

是。购买 [!DNL People-Based Destinations] 的客户还会被授予用于离线分段的新配置文件合并规则的访问权限。该规则称为 [!DNL All Cross-Device Profiles]，用于仅离线分段。当您注册 [!DNL People-Based Destinations] 时，除了三个现有的基于身份验证的规则之外，这是您可以创建的第四个配置文件合并规则。

**我是否需要复制现有的受众区段才能在 [!DNL People-Based Destinations] 中激活它们？**

这取决于您的用例。如果您计划在基于人员的渠道中激活现有的第一方区段，则无需创建新区段。您只需将区段映射到基于人员的目标即可。

如果您计划在基于人员的渠道中激活新的离线受众，则需要使用 [!DNL All Cross-Device Profiles] 合并规则创建新的第一方区段。
>[!NOTE]
>
> 您只能将具有第一方数据的区段映射到 [!DNL People-Based Destinations]。我们的目标平台不接受具有第二方和第三方数据的区段。

## 匹配率 {#match-rates}

**[!DNL People-Based Destinations] 是否可以查看匹配率或可寻址受众？**

否。将受众区段发送到 [!DNL People-Based Destinations] 时，会在合作伙伴方进行受众匹配。Adobe 无权访问这些量度。Audience Manager 会显示每个目标的最大可共享受众以及属于某个区段的人员的实时计数。此信息可帮助您规划和预测营销活动。

**从理论上讲，使用 [!DNL People-Based Destinations] 的匹配率与使用其他用于将受众发送到目标平台的方法相比如何？**

只要电子邮件地址经过哈希处理并正确摄取，则使用 [!DNL People-Based Destinations] 的匹配率与使用其他方法的匹配率应当没有任何差异。匹配率低于 100% 的唯一原因是，摄取到 Audience Manager 的电子邮件地址无法与目标平台用户群中的电子邮件地址进行匹配。

**我收集客户的工作电子邮件地址，这些地址与社交网络中使用的个人电子邮件地址不同。如何跨多个电子邮件地址进行身份匹配？**

Audience Manager 可以收集每个用户的最多 10 个电子邮件地址并将这些地址发送到目标平台，但需要通过同步文件来获取这些电子邮件地址。在 Audience Manager 将电子邮件地址发送到目标平台后，由平台决定是否将电子邮件地址与其自己的用户群进行匹配。某些平台可能具有其他电子邮件地址图形，用于将 Audience Manager 发送的地址与用户配置文件进行匹配。

**我能否在[!DNL Audience Lab]中使用[!DNL People-Based Destinations]？**

不需要。当前，所有[!DNL People-Based Destinations]目标都从[!DNL Audience Lab]中排除。 鉴于[!DNL People-Based Destinations]和需求端平台使用不同的ID，您无法通过在它们之间平均拆分受众来测试和测量性能。

## 数据导出控制 {#data-export-controls}

**[!DNL Data Export Controls] 如何与 [!DNL People-Based Destinations] 一起使用？**

[!DNL Data Export Controls] 将阻止包含用户尝试发送到 [!DNL People-Based Destinations] 的第二方和第三方数据的任何区段。[!DNL People-Based Destinations] 仅允许将第一方数据用于定位。[!DNL Data Export Controls] 还可以使用带有设备图的 [!DNL Profile Merge Rules] 阻止区段。创建 [!DNL People-Based Destinations] 时选中了相应的数据导出标签，因此您无法覆盖导出设置。

## 针对合作伙伴的问题 {#partner-specific-questions}

### [!DNL Facebook]

**在将受众区段发送到 [!DNL Facebook] 之前，我需要做什么？**

在使用 [!DNL People-Based Destinations] 将受众区段发送到 [!DNL Facebook] 之前，您需要执行以下配置任务：

1. 将 Adobe Experience Cloud 商业帐户作为广告合作伙伴添加到 [!DNL Facebook Ad Account] 中。使用 `business ID=206617933627973`。有关详细信息，请参阅“将合作伙伴添加到业务管理器”。

   >[!IMPORTANT]
   >
   > 配置 Adobe Experience Cloud 的权限时，必须启用“管理营销活动”权限。[!DNL People-Based Destinations] 集成要求具备此权限。

1. 阅读并签署 [!DNL Facebook Custom Audiences Terms of Service]。为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

**[!DNL People-Based Destinations] 在其他 [!DNL Facebook] 应用程序（例如 [!DNL Instagram]）中是否支持受众定位？**

您可以在 [!DNL Custom Audiences] 支持的 [!DNL Facebook] 的一系列应用程序（包括 [!DNL Facebook]、[!DNL Instagram]、[!DNL Audience Network] 和 [!DNL Messenger]）中使用 [!DNL People-Based Destinations]。[!DNL Facebook Ads Manager] 中的版面级别会显示您要针对其运行营销活动的所选应用程序。

**[!DNL People-Based Destinations] 和 [!DNL Website Custom Audiences] 之间有何区别？**

[!DNL People-Based Destinations] 利用 [!DNL Custom Audiences (CA)] 与 [!DNL Facebook] 的集成。[!DNL WCA] 集成和 [!DNL CA] 集成之间的区别在于客户向 [!DNL Facebook] 发送受众时使用的键。[!DNL WCA] 使用 [!DNL Facebook] 像素（这将是网站用户 ID）进行集成，而 [!DNL People-Based Destinations] 则使用经过哈希处理的电子邮件地址与 [!DNL CA] 集成。

您可以通过 [!DNL URL Destinations] 功能使用 Audience Manager 的 [!DNL Facebook] [!DNL WCA] 集成，而无需支付额外费用。

这两种集成是互补的，您可以同时使用这两种集成来确保更好的受众覆盖。例如，[!DNL WCA] 可用于在公司要定位尚未注册帐户的网站访客时帮助寻找潜在客户，而 [!DNL People-Based Destinations] 则可以帮助您定位已提供其电子邮件地址但可能未访问网站的现有客户。

**与[!DNL Facebook]的[!DNL People-Based Destinations]集成是否支持在用户不再符合受众资格时取消其受众资格？**

是，该集成支持在用户不再符合[!DNL Facebook]受众资格时将其从受众中删除。
