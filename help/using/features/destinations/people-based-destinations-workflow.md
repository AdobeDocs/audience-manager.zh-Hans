---
description: 基于人员的目标根据客户数据的结构方式提供了多种实施策略。 本文概述了基于人员的目标需要遵循的实施步骤，具体取决于您的方案。
seo-description: '基于人员的目标根据客户数据的结构方式提供了多种实施策略。 本文概述了基于人员的目标需要遵循的实施步骤，具体取决于您的方案。  '
seo-title: 基于人员的目标实施指南
solution: Audience Manager
title: 实施指南
feature: 基于人员的目标
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# 实施指南{#implementation-guidance}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 根据客户数据的结构方式，可提供多种实施策略。本文概述了[!DNL People-Based Destinations]需要遵循的实施步骤，具体取决于您的方案。

## 概述 {#overview}

[!DNL People-Based Destinations]的配置将引导您完成多个Audience Manager部分，并且需要不同的设置和数据载入方法，具体取决于您在Audience Manager中已拥有的客户数据类型以及要执行的受众定位类型。

>[!IMPORTANT]
> 在配置[!DNL People-Based Destinations]之前，请务必仔细、完整地阅读本文。 阅读本指南后，您应该清楚地了解将通过[!DNL People-Based Destinations]启用的情景。

在使用[!DNL People-Based Destinations]之前，您需要阐明六个实施方面。 本文将帮助您了解当前配置的内容，以便您能够正确执行方案的实施步骤。

![pbd实施](assets/pbd-implementation.png)

## 1.定义用例{#defining-your-use-case}

在开始实施[!DNL People-Based Destinations]之前，您需要明确定义要将此功能用于的用例。 您可以使用[!DNL People-Based Destinations]根据受众活动通过两种方式定位受众：

**A)基于线上和线下用户组合活动的受众定位**。在此方案中，您要将来自Audience Manager的现有受众数据与来自内部[!DNL CRM]系统的数据合并，并将生成的受众区段发送到[!DNL People-Based Destinations]。 以下示例说明了此情况：

您的公司（一家航空公司）具有不同的客户层（铜牌、银牌和金牌），您希望通过社交平台为每个层提供个性化优惠。 您可以使用Audience Manager分析网站上的客户活动。 但是，并非所有客户都使用航空公司的移动设备应用程序，其中一些客户尚未登录到公司网站。 您的客户数据主要限于会员ID和电子邮件地址。

要在社交媒体和类似的基于人员的渠道中定位受众，您可以将[经过哈希处理的电子邮件地址](people-based-destinations-prerequisites.md)Audience Manager，并将它们与现有在线活动特征相结合，以构建新的受众区段。 接下来，您可以使用这些区段通过[!DNL People-Based Destinations]定位受众。

**B)仅基于离线用户活动的受众定位**。在此方案中，您的[!DNL CRM]系统包含您的客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您没有Audience Manager中的任何客户活动。 以下示例说明了此情况：

您的公司是电信服务提供商，将客户数据（如电子邮件地址）和购买的电信计划保留在内部[!DNL CRM]中。 您希望定位社交平台中的现有客户，以根据现有订阅为他们提供升级包。 为此，您可以将经过哈希处理的客户电子邮件地址摄取到Audience Manager中，并根据现有客户订阅创建区段。 然后，您可以将这些区段发送到[!DNL People-Based Destinations]，以使用个性化选件来定位客户。

## 2.定义目标电子邮件地址的类型{#define-target-email}

定义实施策略的第二步是确定要定向的客户电子邮件地址类型。

**A)基于您经过身份验证的电子邮件地址进行受众定位**。在此方案中，您的用户有多个帐户，这些帐户与多个电子邮件地址关联，您希望根据他们在您的网站上进行实时身份验证的电子邮件地址，通过个性化选件来定位他们。

**B)基于所有关联电子邮件地址的受众定位**。在此方案中，您的用户有多个帐户，这些帐户与多个电子邮件地址关联，无论是经过身份验证的活动，您都希望在所有关联的电子邮件地址中定位这些帐户。

## 3.识别您拥有{#identify-customer-id}的客户ID(CRM ID)类型

定位[!DNL People-Based Destinations]中的受众需要您发送客户电子邮件地址的[SHA256哈希](people-based-destinations-prerequisites.md)版本。 根据您现有的Audience Manager配置，您可能会发现出现以下两种情况之一：

**A)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已经小写，且经过哈希处理的电子邮件地址**。在此方案中，您可以使用这些现有ID来定位[!DNL People-Based Destinations]中的受众。

**B)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写的、经过哈希处理的电子邮件地址**。在此方案中，无法将您的现有客户ID发送到[!DNL People-Based Destinations]。 要使用[!DNL People-Based Destinations]，您需要在现有客户ID与客户电子邮件地址的小写、哈希版本之间执行ID同步。 要执行此操作，请通过[基于文件的ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)或使用[声明的ID](../declared-ids.md)。

## 4.特征资格{#trait-qualification}

要在[!DNL People-Based Destinations]中准确定位受众，用户需要符合基于规则的特征或已载入的特征，具体取决于您要执行的受众定位类型。

**A)实时确定客户ID和设备ID是否符合基于规则的特征**。此选项适用于[1中的用例A。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是根据在线和离线活动定位受众，那么您很可能已经符合受众的[基于规则的特征](../traits/trait-and-segment-qualification-reference.md)资格。

**B)通过入站数据文件载入针对客户ID的特征**。此选项适用于[1中的用例B。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 基于纯离线活动定位受众时，您需要通过[入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)，确定客户ID是否符合已载入特征。

## 5.创建或标记数据源和板载哈希电子邮件地址{#create-label-data-sources}

根据您在Audience Manager中拥有的客户ID类型（请参阅[3）。 识别您拥有的](people-based-destinations-workflow.md#identify-customer-id)客户ID类型(CRM ID)，您将在以下任一情况中找到自己：

**A)为现有数据源设置标签**。此选项适用于您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已经小写且经过哈希处理的电子邮件地址的情况。 在这种情况下，您需要为存储ID的数据源设置标签，以将其作为[!DNL PII]数据源。 有关数据源设置的详细信息，请参阅[数据源设置](../datasources-list-and-settings.md)。 您需要执行的操作是确保取消选中不能绑定到个人身份信息选项。

**B)创建新数据源**。此选项适用于您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))未经过哈希处理的电子邮件地址的情况。 在这种情况下，您需要创建一个新的跨设备数据源，并载入您经过哈希处理的电子邮件地址以针对该数据源。 您可以通过两种方式执行此操作：

* 使用基于文件的 ID 同步。有关 ID 同步文件外观的详细信息，请参阅 [ID 同步文件的名称和内容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法时，您可以定位[!DNL CRM]数据库中所有经过哈希处理的电子邮件地址。
* 在传入经过身份验证的客户ID时，使用[声明的ID](../declared-ids.md)声明您经过哈希处理的电子邮件地址。 使用此方法时，请代表您Audience Manager仅定向已在线进行身份验证的用户的经过哈希处理的电子邮件地址。 基于人员的渠道中定向的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户 ID 关联的其他电子邮件地址不会实时激活。

## 6.使用配置文件合并规则进行分段{#use-profile-merge-rules}

根据您的用例(请参阅[1。 定义用例](people-based-destinations-workflow.md#defining-your-use-case))中，有两种方法可使用[!DNL Profile Merge Rules]进行分段。

**A)使用现有[!DNL Profile Merge Rules]**。此选项适用于第一个用例（基于在线和离线用户活动组合的受众定位）。 在此方案中，您的Audience Manager中包含现有客户活动，并且您已经至少定义了一个用于分段的配置文件合并规则。 在这种情况下，您无需创建任何新的[!DNL Profile Merge Rules]。

**B)创建新的合 [!DNL All Cross-Device Profiles] 并规则**。此选项适用于第二个用例（仅限离线用户活动的受众定位）。 在此方案中，您要将[!DNL CRM]中的离线客户数据Audience Manager，并希望根据该数据创建区段。 为此，[!DNL People-Based Destinations]引入了名为&#x200B;**[!DNL All Cross-Device Profiles]**&#x200B;的新的第四个配置文件合并规则。 这是您在对纯离线数据进行分段时需要使用的规则。
