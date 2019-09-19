---
description: 本材料包含客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见问题，以及Adobe Audience manager作为数据处理者如何满足各种GDPR要求。
seo-description: 本材料包含客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见问题，以及Adobe Audience manager作为数据处理者如何满足各种GDPR要求。
seo-title: GDPR 常见问题解答
solution: Audience Manager
title: GDPR 常见问题解答
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# GDPR 常见问题解答{#gdpr-faq}

本材料包含客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见问题，以及Adobe Audience manager作为数据处理者如何满足各种GDPR要求。

在本文中，我们解决了Audience manager中有关GDPR就绪性的问题。 确保您还阅读了 [Experience Cloud GDPR常见问题解答。](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR于2018年5月25日生效，其主要目标是让欧盟的个人（数据主体）能够更多地控制其个人数据，同时通过更好地统一欧盟内部的监管来简化国际企业的监管环境。 作为Adobe GDPR就绪性的一部分，Adobe Audience manager团队已根据需要增强了服务和流程，以支持来自您的消费者数据主体的访问和删除请求。

## GDPR词汇表 {#gdpr-glossay}

熟悉与GDPR相关的关键术语。 我们重点介绍了下面一些最常用的术语。

<br> 

**** 数据控制器：GDPR将“控制人”定义为“...法人……他人单独或与其他人共同决定处理个人数据的目的和手段。”Audience manager客户是数据管理者。 客户可以在Audience manager中控制数据的管理方式。

<br> 

**** 数据处理者：“处理者”是“...法人……”，他代表控制者处理个人数据。 在Audience Manager（Adobe的数据管理平台或DMP）环境中，Adobe将充当“数据处理者”，处理其通过DMP处理、存储和服务的任何个人数据。 Adobe仅根据数据管理者的许可和指示（例如，我们与客户的协议中所述）处理个人数据。

<br> 

**** 数据主体：个人数据相关的个人。 在Audience manager的上下文中，数据主体是Audience manager客户的消费者或最终用户。 如果Audience manager直接从数据主体接收请求，则这些请求将转发给相应的Adobe客户。

<br> 

**** 同意：“同意”是指“他／她通过声明或明确肯定行动，表示同意处理与他／她有关的个人数据，并且自由、具体、知情和明确地表明数据主体的意愿”。 同意由数据管理者负责，而非Adobe通过Audience manager负责。

<br> 

**** 访问：数据主体有权要求数据管理者确认控制者是否处理其个人数据。 如果数据管理者确实处理数据主体的个人数据，则必须提供对个人数据的访问和复制。 数据管理者可能要求Adobe协助处理来自数据主体的访问请求。

<br> 

**** 删除：GDPR概述了“被遗忘权”或“擦除权”。数据主体有权要求数据管理者擦除其个人数据。 数据管理者与其处理者（包括Adobe）一起支持数据主体的删除请求。

<br> 

**** 更正：数据主体有权要求数据管理者纠正不准确的个人数据。 数据管理者与包括Adobe在内的处理者一起支持数据主体的更正请求。

<br> 

**** Audience manager标识符(ID):Adobe Audience manager存储各种类型的ID。 Audience Manager [中的GDPR页面提供了这些ID的摘要](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) 、其相应的数据源和简短描述。 向Adobe提供请求时，请参考这些ID，以对数据主体发出删除或访问请求。

<br> 

**** 个人数据：GDPR扩展了个人数据的定义。 根据GDPR,Audience manager中的任何数据都可以根据客户使用案例分类为个人数据。

<br> 

**** 禁止的数据：Audience manager禁止客户获取直接可识别的信息，如名字和姓氏、电子邮件ID、CRM ID，这些信息可用于直接识别个人身份。 Adobe Experience cloud解决方案也禁止敏感信息。 有关这些要求的详细信息，请参阅您与Adobe的合同。 如果需要将这些类型的数据点引入Audience Manager，请咨询Adobe咨询团队，以获得有关在引入之前散列这些ID的建议。

<br> 

## 管理个人GDPR权利 {#manage-ind-gdpr-rights}

**管理选择加入／获得同意**

GDPR在数据管理者需要同意时不会更改，它会更改获取同意的方式。 在某些营销活动需要同意的情况下，消费者同意必须处于活动状态（例如，没有预先选中的框或默认设置）、取消捆绑并且服务提供不得以数据主体给予同意为条件。 甚至有时某些同意需要刷新才能继续使用数据。

作为您的数据处理者，Adobe无法就获得同意提供法律建议。 请咨询您的法律团队以获得指导。 我们建议您与同意管理解决方案提供商(如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) )合作，就此提供更好的建议。 Adobe已与多家此类提供商合作，通过Adobe Launch协助进行此集成。

Audience Manager客户可以在Audience manager中存储广告或个性化等不同用例的用户同意书。 然后，构建具有这些特征的区段时，将仅包括为每个使用案例提供相应同意的用户。 请注意，使用此方法不会停止数据收集，但只会在发送区段进行激活时影响数据的使用。 当用户撤回其同意时，您可以使用Audience Manager入站批处理或Audience Manager选择退出流程从用 [户档案中删除这些特征](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，具体如下所述。

<br> 

**管理选择退出／撤回同意**

可通过您的隐私选择页面为Adobe Experience Cloud管 [理退出](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 通过一键式功能，您的最终用户可以控制Adobe Experience cloud广告解决方案（包括Audience Manager）的数据收集并选择退出。 具体而言，请参 [阅“隐私选择](https://www.adobe.com/privacy/opt-out.html#customeruse) ”页面的业务客户部分。 对于不支持第三方Cookie的浏览器，请参阅声 [明ID定位](../../features/declared-ids.md#declared-id-targeting)。 对于移动设备，请检索相关的Audience manager标识符并调用Audience Manager退出API，如 [Declared ID退出示例中所述](../../features/declared-ids.md#opt-out-examples)。 随后，您可以使用Mobile SDK中的退出API停止为这些用户收集所有数据——请参阅 [Android设备](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) 和 [iOS设备](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)。 您可以在 [Audience Manager退出文档中查找有关退出的其他详细信息](../../overview/data-security-and-privacy/opt-out-management.md)。

<br> 

**向Adobe提交Audience Manager GDPR访问和删除请求**

您可以通过 [GDPR客户端服务UI或通过调用](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) GDPR API [，提交个人GDPR访问和删除请求](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md)。 任何 [Audience manager标识符](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)，都可以在请求中提交它们以及它们各自的命名空间ID（数据源ID）。 如果您提交跨设备标识符（如CRM ID）,Audience manager将对已验证的配置文件以及与其关联的设备ID执行操作。 建议客户尽可能使用Audience Manager唯一用户ID(AAM UUID)。

<br> 

**管理访问请求**

在2018年5月25日之前，Audience manager手动支持访问特征、客户ID和与Audience manager中的唯一ID关联的区段。 截至2018年5月25日，我们通过各种产品和服务增强按上述方式支持这些请求。 除了特征、客户ID、区段外，对访问请求的响应还包括特征和区段总数、特征类型、特征和区段的描述以及相应的数据源名称的摘要。 访问响应还包括可由数据控制器访问的第二方和第三方数据以及第一方数据。 请参阅数据访 [问请求中的更多信息](../../overview/aam-gdpr/aam-gdpr-details.md#access-data)。

<br> 

**管理删除请求**

在2018年5月25日之前，Audience manager支持手动删除Audience manager中与唯一ID关联的特征、客户ID和区段。 在GDPR生效后，我们通过各种产品和服务增强按上述方式支持这些请求。 除删除操作外，数据主体的相应Audience Manager标识符将被选择退出进一步的数据收集，并且相应的ID映射将被删除。 请参阅数据删 [除请求中的更多内容](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data)。

<br> 

**第二方数据提供商和管理同意**

第二方数据提供者通常也是数据管理者，并拥有从数据主体获得任何必要同意以与其第二方数据合作伙伴共享数据的过程。 Audience manager客户有责任确定第二方数据提供商是否已获得您使用案例的必要同意。 有关获得同意的更多详细信息，请参阅上文。

<br> 

**第三方数据提供商和管理同意**

数据提供者也是数据管理者，他们拥有获得同意和管理访问／删除／更正请求的流程。 Adobe主动要求数据提供商在 [Adobe Audience Finder中更新其公司档案信息，并提供有关用户数据收集的其他信息](https://www.adobe-audience-finder.com/) 。 信息将来自数据提供商，其目标是在2018年第2季度之前更新该工具。 但是，由每位Audience manager客户确定第三方数据提供商已获得该客户使用案例的必要同意。 Adobe不对第三方数据提供商针对特定使用案例获得或报告的同意的范围或有效性做出任何声明。

<br> 

**删除受众激活请求的影响**

Audience manager通过向激活合作伙伴发送请求删除特定数据的数据主体的取消细分信息，来通知他们有关删除请求的信息。 但是，一些激活合作伙伴：1)不能支持从Adobe取消细分（或删除细分）请求，和／或2)无法接收我们以少于30天的频率发出的更新。 在这些情况下，Audience manager客户无法通过Audience manager向激活合作伙伴自动发送删除请求。 GDPR合 [作伙伴取消细分文档提供](../../overview/aam-gdpr/aam-gdpr-partners.md) ，以了解所有激活合作伙伴取消细分功能和数据交换频率的相关信息。

<br> 

**Audience manager中的数据保留**

对数据应用适当、安全和及时的数据保留策略是遵守GDPR的重要部分。 Audience Manager客户可以通过定义所需的TTL（生存时间），为特征和区段设置自定义保留期。 我们已将()和订 [!UICONTROL Customer Data Feeds] 单的 [!UICONTROL CDF]保留期 [!UICONTROL Batch Outbound] 限缩短至8天。 我们还将对不活动的CRM配置文件和ID映射应用保留期。 请在我们的数据保留常见问题解答中查找有关保留期的 [更多详细信息](../../faq/faq-privacy.md)。

<br> 

**管理数据更正请求**

由于Audience manager不是数据源，因此Audience manager中用于数据更正的角色有限。 更正可能意味着数据主体已请求取消不正确的特征／段的资格，或者被限定为符合所需的特征／段。 Audience Manager客户可以根据用户档案选择捕获相关信号／特征／细分，并通过离线数据获取将这些信息发送到Audience Manager。 请注意，如果用户重复其行为，他们将继续获得符合原始特征和区段的资格。

<br> 

**跨边界数据传输**

GDPR不禁止在欧洲以外传输数据。 它要求对欧洲数据的隐私保护在数据传输时始终有效。 请访问 [Adobe隐私中心](https://www.adobe.com/privacy/eudatatransfers.html) ，了解更多信息。

<br> 

## 面向Audience Manager客户（数据管理者）的GDPR就绪性指南 {#gdpr-readiness-guidance}

我们建议在数据管理和组织就绪性方面采取主动行动。 这可以确保您的消费者数据将按照与访问或删除请求相关的流程进行组织，您的团队将能够被启用并被授权管理这些请求，而您的消费者（数据主体）将拥有与您的品牌相关的积极且差异化的体验。

请注意，作为您的数据处理者，Adobe无法就GDPR要求以及获得数据主体同意的过程提供法律建议。 请咨询您的法律顾问，了解贵组织遵守GDPR的相关指导。

<br> 

**数据管理：开始考虑如何在Audience manager实例中管理您的消费者数据**

* 查看您的营销团队用来识别Audience manager中用户的各种客户ID以及存储这些用户的数据源。 这将简化请求流程（如删除或访问），因为某些数据类型在引入Audience manager之前将由您的团队散列化。
* IDFA/GAID移动设备ID用于Audience manager中的多个用例。 如果您使用的是Adobe Mobile SDK，请确保提交Experience Cloud ID(MID)和IDFA/GAID，以确保GDPR答复完成。
* 随着个人数据的定义越来越广泛，IP地址可能会被视为您所在地区的个人数据。 主动与Adobe Consulting联系以模糊化最后八位字节。
* 确定在数据主体发出GDPR请求时确认其身份的验证／身份验证策略和流程。
* 考虑使用 [数据导出控制](../../features/data-export-controls.md) ，阻止受众激活存储个人数据的技术。 例如，具有第三方数据的细分不应整合到电子邮件服务提供商处。 设置一 [!UICONTROL Data Export Control] 个值，以确保组织中的任何人都不会意外激活此数据。
* 开始使用 [基于角色的访问控制](../../features/administration/administration-overview.md) ，以确保正确的团队可以访问预期的数据。
* 请考虑适 [当的数据保](../../faq/faq-privacy.md#data-retention-faq) 留期。
* 查看身份联系和隐私政策以及法律要求，了解何时何地将身份集合绑定在一起；通过Audience Manager的Profile Merge Rules(配置文件合并规 [则)进行适当的使用](../../features/profile-merge-rules/merge-rules-overview.md)。

<br> 

**组织就绪性：建立业务流程**

* 确定接收／响应数据主体请求的流程。 考虑构建一个自动化工具，将请求提交到Audience Manager。
* 在您的DMP卓越中心内指定一个隐私联系人。 将贵组织的隐私联系人与您的Audience manager产品使用团队联系，了解您如何管理输入ID要求。
* 在与数据主体共享之前进行数据审阅。 记录您所执行的步骤，以帮助您建立责任。

