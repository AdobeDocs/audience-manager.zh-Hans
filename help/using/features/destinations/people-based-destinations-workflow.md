---
description: 基于人员的目标提供多个实施战略，具体取决于客户数据的构造方式。本文概述了根据您的方案需要遵循的面向基于人员的目标的实施步骤。
seo-description: '基于人员的目标提供多个实施战略，具体取决于客户数据的构造方式。本文概述了根据您的方案需要遵循的面向基于人员的目标的实施步骤。  '
seo-title: 基于人员的目标实施指南
solution: Audience Manager
title: 实施指南
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 实施指南 {#implementation-guidance}

[!DNL People-Based Destinations] 提供多个实施战略，具体取决于客户数据的构造方式。本文概述了根据您的方案需要遵循的 [!DNL People-Based Destinations]实施步骤。

## 概述 {#overview}

配置 [!DNL People-Based Destinations] 将带您遍历Audience Manager的多个部分，并要求不同的设置和数据入门方式，具体取决于您在Audience Manager中已经拥有何种客户数据，以及要执行的受众定位类型。

>[!IMPORTANT]
> 在配置 [!DNL People-Based Destinations]之前，请确保仔细、完全阅读本文。阅读本指南后，您应清晰了解要启用的方案 [!DNL People-Based Destinations]。

您需要在使用 [!DNL People-Based Destinations]前阐明六个实施方面。本文将帮助您了解当前配置，以便正确遵循方案的实施步骤。

![pdd-implementation](assets/pbd-implementation.png)

## 1. 定义使用案例 {#defining-your-use-case}

在开始实施 [!DNL People-Based Destinations]之前，您需要明确定义使用此功能的用例。您可以根据 [!DNL People-Based Destinations] 受众活动通过两种方式定位受众：

**A) 根据综合线上线下用户活动定位受众**。在此方案中，您需要将Audience Manager中的现有受众数据与内部 [!DNL CRM] 系统中的数据相结合，并将生成的受众细分发送到 [!DNL People-Based Destinations]。下面是一个说明此场景的示例：

您的公司是一家航空公司，拥有不同的客户层(铜牌、银牌和黄金)，您希望通过社交平台为每个层提供个性化的推广信息。您可以使用Audience Manager分析网站上的客户活动。然而，并非所有客户都使用该航空公司的移动应用程序，而且他们甚至从未登录到公司的网站。您的客户数据主要限于成员ID和电子邮件地址。

要在社交媒体和类似的基于人群的渠道中定位这些渠道，您可以将 [散列电子邮件地址](people-based-destinations-prerequisites.md) 引入Audience Manager并将其与现有的在线活动特征相结合，从而构建新的受众细分。接下来，您可以使用这些细分定位受众 [!DNL People-Based Destinations]。

**B) 仅基于离线用户活动的受众定位**。在此方案中， [!DNL CRM] 您的系统包含客户电子邮件地址和其他客户属性，但客户尚未与您的网站交互，因此您在Audience Manager中没有任何客户活动。下面是一个说明此场景的示例：

您的公司是电信服务提供商，它将电子邮件地址和购买的电信计划等客户数据保留在一个内部 [!DNL CRM]。您希望针对社交平台中的现有客户，根据现有订阅为其提供升级包。为此，您可以将散列客户电子邮件地址收录到Audience Manager中，并根据现有客户订阅创建细分。然后，您可以将这些细分 [!DNL People-Based Destinations] 发送到客户以提供个性化优惠。

## 2. 定义目标电子邮件地址的类型 {#define-target-email}

定义实施战略的第二步是确定要定位的客户电子邮件地址类型。

**A) 基于身份验证的电子邮件地址定位受众**。在这种情况下，您的用户有多个与多个电子邮件地址关联的帐户，您希望根据个性化的推广信息，仅基于他们在网站上进行身份验证的电子邮件地址来定位这些帐户。

**B) 根据所有相关电子邮件地址定位受众**。在此方案中，您的用户有多个与多个电子邮件地址关联的帐户，并且您希望在所有关联的电子邮件地址中定位这些帐户，而不管身份验证活动如何。

## 3. 识别您拥有的客户ID(CRM ID)类型 {#identify-customer-id}

定位受众 [!DNL People-Based Destinations] 要求您发送 [客户电子邮件地址的SHA256散列](people-based-destinations-prerequisites.md) 版本。根据现有Audience Manager配置，您可以在以下两种情况下找到自己：

**A) Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已小写化为小写电子邮件地址**。在此方案中，您可以使用这些现有的ID来定位受众 [!DNL People-Based Destinations]。

**B) Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写电子邮件地址**。在此方案中，无法将现有客户ID发送到 [!DNL People-Based Destinations]。要使用 [!DNL People-Based Destinations]，您需要在现有客户ID与客户电子邮件地址的小写版本之间执行ID同步。您可以通过 [基于文件的ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 或 [使用声明的ID](../declared-ids.md)来执行此操作。

## 4. 特征资格资格 {#trait-qualification}

为了准确定位受众， [!DNL People-Based Destinations]您的用户需要符合基于规则的或载入的特征，具体取决于要执行的受众定位类型。

**A) 实时确定基于规则的特征的客户ID和设备ID**。此选项适用于使用案例A从 [1。定义使用案例](people-based-destinations-workflow.md#defining-your-use-case)。如果您的计划是根据线上和线下活动定位受众，那么您很可能已经符合基于 [规则特征的受众](../traits/trait-qualification-reference.md)资格。

**B) 通过入站数据文件**&#x200B;针对客户ID进行定位。此选项适用于将用例B从 [1开始。定义使用案例](people-based-destinations-workflow.md#defining-your-use-case)。根据纯粹离线活动定位受众时，您需要通过 [入站数据文件确定载入特征的客户ID](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5. 创建或标签数据源和绘图板散列电子邮件地址 {#create-label-data-sources}

根据您在Audience Manager中的客户ID类型(请参阅 [3)。识别您拥有的客户ID(CRM ID)类型](people-based-destinations-workflow.md#identify-customer-id)，您将在下列情况之一中找到自己：

**A) 标记现有数据源**。此选项适用于Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已经是小写、散列电子邮件地址的情况。在这种情况下，您需要做的是标签作为 [!DNL PII] 数据源存储的ID的数据源。有关数据源设置的详细信息，请参阅 [数据源设置](../datasources-list-and-settings.md) 。您需要做的是确保未选中“无法与个人识别信息绑定”选项。

**B) 创建新数据源**。此选项适用于Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是散列电子邮件地址的情况。在这种情况下，您需要创建新的跨设备数据源并将散列电子邮件地址载入其中。您可以通过以下两种方式执行此操作：

* 使用基于文件的ID同步。有关 [ID同步文件的详细信息，请参阅ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 的名称和内容要求。使用此方法时，您可以从 [!DNL CRM] 数据库中定位所有散列电子邮件地址。
* 使用 [声明的ID](../declared-ids.md) 在通过身份验证的客户ID时声明散列电子邮件地址。使用此方法时，Audience Manager仅针对已通过联机身份验证的用户提供散列电子邮件地址。通过Facebook定位的电子邮件地址只是声明ID事件调用中的一个。与客户ID关联的其他电子邮件地址不会实时激活。

## 6. 对分段使用配置文件合并规则 {#use-profile-merge-rules}

根据您的用例(请参阅 [1)。定义您的使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有两种用于细分 [!DNL Profile Merge Rules] 的方式。

**A) 使用现有[!DNL Profile Merge Rules]**。此选项适用于第一个用例(基于综合线上线下用户活动的受众定位)。在此方案中，您在Audience Manager中拥有现有客户活动，并且已经定义了至少一个已在细分中使用的配置文件合并规则。在这种情况下，您无需创建任何新 [!DNL Profile Merge Rules]内容。

**B) 创建[!DNL All Cross-Device Profiles]新的合并规则**。此选项适用于第二个用例(仅基于脱机用户活动的受众定位)。在此情景下，您将离线客户数据从您 [!DNL CRM] 的Audience Manager导入，并希望从该数据创建细分。为此 [!DNL People-Based Destinations] ，请引入一个新的、第四个配置文件合并规则 **[!DNL All Cross-Device Profiles]**。这是在分段数据时需要使用的规则。
