---
description: 此材料包含我们的客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见的问题，以及Adobe Audience Manager如何满足各种GDPR要求。
seo-description: 此材料包含我们的客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见的问题，以及Adobe Audience Manager如何满足各种GDPR要求。
seo-title: GDPR 常见问题解答
solution: Audience Manager
title: GDPR 常见问题解答
uuid: e52design27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# GDPR 常见问题解答{#gdpr-faq}

此材料包含我们的客户和合作伙伴提出的与欧洲一般数据保护规定(GDPR)相关的一些最常见的问题，以及Adobe Audience Manager如何满足各种GDPR要求。

在本文中，我们解决了Audience Manager中的GDPR准备问题。Make sure you also read the [Experience Cloud GDPR FAQ.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR于2018年月25日生效，主要目标是为欧盟的个人(数据主体)提供更多控制，同时通过欧盟统一法规简化国际业务的法规环境，同时简化国际业务的监管环境。作为Adobe GDPR的一部分，Adobe Audience Manager团队根据需要增强服务和流程，以支持访问和删除来自数据主体、消费者的请求。

## GDPR Glossary {#gdpr-glossay}

熟悉与GDPR相关的关键术语。我们重点介绍了下面最常用的术语。

<br> 

**数据管理者：** GDPR将“控制器”定义为“…法律人员…单独或与其他人一起决定处理个人数据的目的和手段。”Audience Manager客户是数据管理者。客户控制在Audience Manager中管理数据的方式。

<br> 

**数据处理者：** “处理者”是“…法务人员…代表控制器处理个人数据”。在Audience Manager(Adobe的数据管理平台或DMP)环境中，Adobe充当通过DMP处理和存储和服务的任何个人数据的“数据处理者”。Adobe仅按照数据管理者的许可和说明处理个人数据(例如，我们与客户达成协议中的规定)。

<br> 

**数据主体：** 个人数据与其相关的个人。在Audience Manager的情境下，数据主体是Audience Manager客户的消费者或最终用户。如果Audience Manager直接从数据主体接收请求，则这些请求将转发给各个Adobe客户。

<br> 

**同意：** 同意意味着“任何免费提供、具体、知情和明确地指明数据主体的愿望，通过声明或明确确认行动，表明同意处理与其相关的个人数据的处理”。同意由数据管理者而非Adobe通过Audience Manager负责。

<br> 

**访问：** 数据主体有权要求数据管理者确认控制器是否处理其个人数据。如果数据管理者确实处理数据主体的个人数据，则必须提供对个人数据的访问和副本。数据管理者可能会要求Adobe协助访问来自数据主体的请求。

<br> 

**删除：** GDPR描绘了“被遗忘的权利”或“权利的右侧”。”数据主体有权要求数据管理者擦除其个人数据。数据管理者与其处理器(包括Adobe)一起支持删除来自数据主体的请求。

<br> 

**更正：** 数据主体有权要求数据管理者重新认证不准确的个人数据。数据控制器与处理器(包括Adobe)一起支持来自数据主体的校正请求。

<br> 

**Audience Manager标识符(ID)：** Adobe Audience Manager存储各种类型的ID。The [GDPR in Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) page provides a summary of these IDs, their corresponding data sources, and brief descriptions. 向Adobe提供请求时，引用这些ID以删除或访问数据主体的请求。

<br> 

**个人数据：** GDPR扩展了个人数据的定义。在GDPR下，Audience Manager中的任何数据均可根据客户使用案例分类为个人数据。

<br> 

**禁止的数据：** Audience Manager禁止客户获取直接识别信息，例如名字和姓氏、电子邮件ID、CRM ID(可用于直接识别个人)。Adobe Experience Cloud解决方案还禁止敏感信息。有关这些要求的详细信息，请参阅与Adobe的合同。如果需要引入Audience Manager中的这些类型的数据点，请咨询Adobe咨询团队，了解有关在摄取之前散列这些ID的建议。

<br> 

## Managing Individual GDPR Rights {#manage-ind-gdpr-rights}

**管理参与/获取同意**

在数据管理者需要同意时，GDPR没有改变，它改变了如何获得同意。对于某些市场营销活动需要征得同意的情况，消费者同意必须处于活动状态(例如，没有预先选中的方框或沉默)、捆绑和提供服务，不能根据同意的数据主体提供条件。甚至有时也可能需要刷新某些同意才能继续使用未来数据。

作为您的数据处理者，Adobe无法提供获得同意的法律建议。请咨询您的法律团队寻求指导。We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe已与这些提供商合作，以协助通过Adobe Launch进行此类集成。

Audience Manager客户可以在Audience Manager中存储用户对各种用例(如广告或个性化)的同意。构建具有这些特征的细分之后，将仅包括每个使用案例提供各自同意的用户。请注意，使用此方法不会停止数据收集，但只会在您发送区段进行激活时影响数据使用。When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

<br> 

**管理退出/撤销同意**

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. 单击功能可让最终用户控制和退出Adobe Experience Cloud广告解决方案(包括Audience Manager)的数据收集。Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br> 

**提交Audience Manager GDPR访问和删除Adobe请求**

You can submit Individual GDPR requests for Access and Delete either through the [GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) or by calling the [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). Any [Audience Manager identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids), can be submitted in the requests along with their respective namespace IDs (data source IDs). 如果提交跨设备标识符(如CRM ID)，Audience Manager将对经过身份验证的配置文件以及与之链接的设备ID进行操作。建议客户尽可能使用Audience Manager唯一用户ID(AAM UUID)。

<br> 

**管理访问请求**

2018年月25日之前，Audience Manager支持在Audience Manager中手动访问与唯一ID关联的特征、客户ID和细分。自2018年月25日起，我们以上述各种产品和服务增强方式支持这些请求。除了特征、客户ID、对访问请求的响应之外，访问请求还包括特征和区段总数、特征类型、特征和区段描述以及各自的数据源名称。访问响应还包括由数据管理者访问的第二方和第三方数据以及第一方数据。See more in [Data Access Requests](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**管理删除请求**

2018年月25日之前，Audience Manager支持手动删除Audience Manager中与唯一ID相关联的特征、客户ID和细分。在GDPR生效后，我们将以上述各种产品和服务增强的方式支持这些请求。除删除操作之外，数据主体的相应Audience Manager标识符将被选择退出进一步的数据收集，并将删除相应的ID映射。See more in [Data Deletion Requests](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**第二方数据提供商和管理同意**

第二方数据提供商通常也是数据管理者，拥有从数据主体获得任何必要同意的过程，以便与其第二方数据合作伙伴共享数据。Audience Manager客户有责任确定第二方数据提供商是否已获得您使用案例的必要同意。有关获得同意的详细信息，请参阅上述内容。

<br> 

**第三方数据提供商和管理同意**

数据提供商也是数据管理者，他们拥有获得同意和管理访问/删除/更正请求的流程。Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. 信息将由数据提供商提供，其目标是让该工具在2012年第季度更新。但是，每个Audience Manager客户都应确定第三方数据提供商已获得该客户使用案例的必要同意。Adobe不对第三方数据提供商为特定用例获得或报告的同意范围或有效性表示声明。

<br> 

**删除受众激活请求的影响**

Audience Manager通过向数据主体发送请求删除特定数据的数据主体取消细分信息，通知激活合作伙伴有关删除请求。但是，一些激活合作伙伴：1)不能支持来自Adobe和/或的取消区段(或删除区段)请求2)无法接收我们的更新频率，频率低于30天。在这些情况下，Audience Manager客户无法通过Audience Manager以自动化方式向激活合作伙伴发送删除请求。[GDPR合作伙伴取消细分文档](../../overview/aam-gdpr/aam-gdpr-partners.md) 提供了有关所有激活合作伙伴的取消细分功能和数据交换频率的信息。

<br> 

**Audience Manager中的数据保留**

对数据应用适当、安全和及时的数据保留策略是符合GDPR的重要组成部分。Audience Manager客户能够通过定义所需的TTL(生存时间)来设置特征和细分上的自定义保留期。We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. 我们还将为非活动CRM配置文件和ID映射应用保留期限。Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br> 

**管理数据更正请求**

鉴于Audience Manager不是数据的来源，Audience Manager中的数据校正作用有限。该更正可能意味着数据主体请求从错误的特征/区段中取消资格或符合所需特征/区段资格。Audience Manager客户可以选择根据用户配置文件捕获相关信号/特征/细分，并通过离线数据获取到Audience Manager。请注意，如果用户重复行为，则用户将继续获得原始特征和区段。

<br> 

**跨边框数据传输**

GDPR不禁止在欧洲以外传输数据。它要求在传输数据的任何地方都保留欧洲数据的隐私保护。Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br> 

## GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

我们建议在数据治理和组织就绪方面积极主动。这可以确保将您的消费者数据组织到与访问或删除请求相关的流程中，您的团队将被启用并支持这些请求，并且您的消费者(数据主体)将具有与您的品牌的积极、差异化体验。

请注意，作为您的数据处理者，Adobe无法提供有关GDPR要求的法律建议以及获取您的数据主体同意的流程。有关您的组织符合GDPR规范的指导，请咨询法律顾问。

<br> 

**数据治理：开始考虑如何在Audience Manager实例中管理您的消费者数据**

* 查看营销团队用于识别Audience Manager中用户的各种客户ID以及存储它们的数据源。这将简化请求(如删除或访问)的过程，因为在Audience Manager中进行摄取之前，某些数据类型将被您的团队散列化。
* IDFA/GID移动设备ID用于Audience Manager中的多个用例。如果您使用的是Adobe Mobile SDK，请确保提交Experience Cloud ID(MID)和IDFA/GID，以确保GDPR答复已完成。
* 随着个人数据的定义变得更加广泛，IP地址可能被视为您所在地区的个人数据。主动与Adobe Consulting互动以模糊化最后一位字节。
* 确定验证/身份验证策略和流程，以确认数据主体在GDPR请求时的身份。
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. 例如，具有第三方数据的区段不应与电子邮件服务提供商同步。Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data.
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data.
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data.
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

<br> 

**组织就绪：建立业务流程**

* 确定接收/响应数据主体请求的流程。考虑构建一个自动工具以提交到Audience Manager的请求。
* 在您的DMP卓越中心内指定隐私权联系人。连接您组织的隐私权联系人与Audience Manager产品使用团队，以了解如何管理输入ID要求。
* 在与数据主体共享之前进行数据审查。记录您落实的步骤，帮助您建立责任。

