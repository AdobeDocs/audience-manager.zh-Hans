---
description: 基于人员的目标优惠了多种实施策略，具体取决于客户数据的结构。 本文概述了在基于人员的目标中需要遵循的实施步骤，具体取决于您的方案。
seo-description: '基于人员的目标优惠了多种实施策略，具体取决于客户数据的结构。 本文概述了在基于人员的目标中需要遵循的实施步骤，具体取决于您的方案。  '
seo-title: 基于人的目的地实施指南
solution: Audience Manager
title: 实施指南
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# 实施指南{#implementation-guidance}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都是法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 优惠多种实施战略，具体取决于客户数据的结构。本文概述了[!DNL People-Based Destinations]需要遵循的实施步骤，具体取决于您的方案。

## 概述 {#overview}

[!DNL People-Based Destinations]的配置将带您浏览Audience Manager的多个部分，并需要不同的设置和数据载入方法，具体取决于您在Audience Manager中已拥有的受众类型以及要执行的客户定位类型。

>[!IMPORTANT]
> 在配置[!DNL People-Based Destinations]之前，请务必仔细阅读本文。 阅读本指南后，您应清楚了解将通过[!DNL People-Based Destinations]启用的方案。

在使用[!DNL People-Based Destinations]之前，您需要阐明六个实现方面。 本文将帮助您了解当前的配置，以便您能够正确遵循方案的实施步骤。

![PBD实现](assets/pbd-implementation.png)

## 1.定义用例{#defining-your-use-case}

在开始实施[!DNL People-Based Destinations]之前，您需要明确定义将使用此功能的用例。 可以根据受众活动，通过两种方式使用[!DNL People-Based Destinations]来目标受众:

**答：受众定位基于线上和线下用户的组合活动**。在此方案中，您希望将来自Audience Manager的现有受众数据与来自内部[!DNL CRM]系统的数据合并，并将生成的受众段发送到[!DNL People-Based Destinations]。 以下是一个说明此方案的示例：

您的公司（一家航空公司）拥有不同的客户层（铜牌、银牌和金牌），您希望通过社交平台为每个层提供个性化的优惠。 您可以使用Audience Manager分析网站上的客户活动。 然而，并非所有客户都使用航空公司的移动应用程序，其中一些客户尚未登录公司网站。 您的客户数据主要限于会员ID和电子邮件地址。

要在社交媒体和类似的基于人的渠道中目标它们，您可以将您的[哈希电子邮件地址](people-based-destinations-prerequisites.md)引入Audience Manager，并将它们与您现有的在线活动特征相结合，以构建新的受众细分。 接下来，您可以使用这些区段通过[!DNL People-Based Destinations]目标受众。

**B)受众定位只基于您的脱机用户活动**。在此方案中，您的[!DNL CRM]系统包含您的客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您在Audience Manager中没有任何客户活动。 以下是一个说明此方案的示例：

您的公司是电信服务提供商，将客户数据（如电子邮件地址和购买的电信计划）保存在内部[!DNL CRM]中。 您希望目标社交平台中的现有客户，以基于现有订阅优惠他们的升级包。 为此，您可以将哈希化的客户电子邮件地址录入Audience Manager，并基于现有客户订阅创建细分。 然后，您可以将这些细分发送到[!DNL People-Based Destinations]，以通过个性化的优惠目标客户。

## 2.定义目标电子邮件地址的类型{#define-target-email}

定义实施策略的第二步是确定要目标的客户电子邮件地址类型。

**答：受众定位基于您经过身份验证的电子邮件地址**。在此方案中，您的用户有多个帐户与多个电子邮件地址关联，您希望仅根据用户在您网站上进行身份验证的电子邮件地址实时目标这些帐户，并使用个性化的优惠。

**B)基于所有关联电子邮件地址进行受众定位**。在此方案中，您的用户有多个帐户与多个电子邮件地址关联，而且您希望将这些帐户目标到其所有关联的电子邮件地址，而不管身份验证活动。

## 3.确定您具有{#identify-customer-id}的客户ID(CRM ID)的类型

[!DNL People-Based Destinations]中的定位受众要求您发送[SHA256哈希](people-based-destinations-prerequisites.md)版本的客户电子邮件地址。 根据您现有的Audience Manager配置，您可能会发现自己处于以下两种情况之一：

**A)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已经是小写的散列电子邮件地址**。在此方案中，您可以使用这些现有ID在[!DNL People-Based Destinations]中目标受众。

**B)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写的散列电子邮件地址**。在此方案中，无法将您的现有客户ID发送到[!DNL People-Based Destinations]。 要使用[!DNL People-Based Destinations]，您需要在现有客户ID和小写的客户电子邮件地址哈希版本之间执行ID同步。 您可以通过[基于文件的ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)或使用[声明的ID](../declared-ids.md)执行此操作。

## 4.特质资格{#trait-qualification}

要在[!DNL People-Based Destinations]中准确目标受众，用户需要根据要执行的受众定位类型确定基于规则或已载入的特征。

**A)实时确定您的客户ID和设备ID，以获得基于规则的特征**。此选项适用于[1中的用例A。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是基于线上和线下活动目标受众，则您很可能已经对受众的[基于规则的特征](../traits/trait-and-segment-qualification-reference.md)进行了资格鉴定。

**B)通过入站数据文件根据您的客户ID确定板载特征**。此选项适用于[1中的用例B。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case)。 在基于纯离线活动定位受众时，您需要通过[入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)来确定已载入特征的客户ID。

## 5.创建或标记数据源和板载散列电子邮件地址{#create-label-data-sources}

根据您在Audience Manager中的客户ID类型（请参阅[3）。 确定您](people-based-destinations-workflow.md#identify-customer-id)拥有的客户ID(CRM ID)的类型，您会发现自己处于以下任一情形中：

**A)为现有数据源添加标签**。此选项适用于Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已小写的散列电子邮件地址的情况。 在这种情况下，您需要将存储ID的数据源标记为[!DNL PII]数据源。 有关数据源设置的详细信息，请参阅[数据源设置](../datasources-list-and-settings.md)。 您需要做的是确保未选中“无法绑定到个人可识别信息”选项。

**B)创建新数据源**。此选项适用于Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))没有散列电子邮件地址的情况。 在这种情况下，您需要创建一个新的跨设备数据源，并将哈希电子邮件地址加入其中。 您可以通过两种方式执行此操作：

* 使用基于文件的 ID 同步。有关 ID 同步文件外观的详细信息，请参阅 [ID 同步文件的名称和内容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法时，您可以从[!DNL CRM]数据库目标所有哈希化电子邮件地址。
* 使用[声明的ID](../declared-ids.md)在传递经过身份验证的客户ID时声明您的哈希电子邮件地址。 使用此方法时，Audience Manager仅代表您目标已联机验证的用户的哈希电子邮件地址。 在基于人员的渠道中定位的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户 ID 关联的其他电子邮件地址不会实时激活。

## 6.使用用户档案合并规则进行分段{#use-profile-merge-rules}

根据您的用例(请参阅[1。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case))，有两种方法可使用[!DNL Profile Merge Rules]进行分段。

**A)使用现有[!DNL Profile Merge Rules]**。此选项适用于第一个用例(基于联机和脱机用户组合活动的受众定位)。 在此方案中，您已有Audience Manager活动，并且您至少已定义了一个在分段中使用的用户档案合并规则。 在这种情况下，您无需创建任何新[!DNL Profile Merge Rules]。

**B)创建新的合 [!DNL All Cross-Device Profiles] 并规则**。此选项适用于第二个用例(仅基于脱机用户活动的受众定位)。 在此方案中，您将您的[!DNL CRM]离线客户数据引入Audience Manager，并希望从该数据创建区段。 为此，[!DNL People-Based Destinations]引入了新的第四个用户档案合并规则，称为&#x200B;**[!DNL All Cross-Device Profiles]**。 这是您在细分纯脱机数据时需要使用的规则。
