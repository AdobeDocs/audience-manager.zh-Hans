---
description: 基于人员的目标根据客户数据的结构提供多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。
seo-description: '基于人员的目标根据客户数据的结构提供多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。  '
seo-title: 基于人员的目的地实施指南
solution: Audience Manager
title: 实施指南
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 实施指南 {#implementation-guidance}

[!DNL People-Based Destinations] 根据客户数据的结构，提供多种实施战略。 本文概述了您需要遵循的实施步骤，具体取决 [!DNL People-Based Destinations]于您的方案。

## 概述 {#overview}

配置可 [!DNL People-Based Destinations] 以引导您浏览Audience manager的多个部分，并且需要不同的设置和数据载入方法，具体取决于您在Audience manager中已有的客户数据类型以及要执行的受众定位类型。

>[!IMPORTANT]
> 配置之 [!DNL People-Based Destinations]前，请务必仔细阅读本文。 阅读本指南后，您应清楚了解将启用的方案 [!DNL People-Based Destinations]。

在使用之前，您需要先阐明六个实施方面 [!DNL People-Based Destinations]。 本文将帮助您了解当前的配置内容，以便您能够正确执行方案的实施步骤。

![pbd实现](assets/pbd-implementation.png)

## 1.定义用例 {#defining-your-use-case}

在开始实施之 [!DNL People-Based Destinations]前，您需要明确定义将要为此功能使用的用例。 您可以根 [!DNL People-Based Destinations] 据受众活动，通过两种方式定位受众：

**A)基于线上和线下用户活动组合的受众定位**。 在此方案中，您希望将Audience manager的现有受众数据与内部系统的数据相结合， [!DNL CRM] 并将生成的受众细分发送到 [!DNL People-Based Destinations]。 下面是一个说明此方案的示例：

您的公司（一家航空公司）有不同的客户层（铜牌、银牌和金牌），您希望通过社交平台为每层提供个性化的推广信息。 您可以使用Audience manager分析网站上的客户活动。 然而，并非所有客户都使用该航空公司的移动应用程序，其中一些客户甚至从未登录该公司的网站。 您的客户数据主要限于会员ID和电子邮件地址。

要跨社交媒体和类似的基于人员的渠道定位受众，您可以将散列化的电子邮件地址导入 [Audience Manager](people-based-destinations-prerequisites.md) ，并将它们与现有的在线活动特征相结合，以构建新的受众细分。 接下来，您可以使用这些细分来定位受众 [!DNL People-Based Destinations]。

**B)仅基于脱机用户活动的受众定位**。 在此方案中，您的系 [!DNL CRM] 统包含客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您在Audience manager中没有任何客户活动。 下面是一个说明此方案的示例：

您的公司（电信服务提供商）将电子邮件地址和购买的电信计划等客户数据保存在内部 [!DNL CRM]。 您希望针对社交平台中的现有客户基于其现有订阅提供升级包。 为此，您可以将散列化的客户电子邮件地址收录到Audience Manager中，并根据现有客户订阅创建细分。 然后，您可以发送这些细分，以 [!DNL People-Based Destinations] 便通过个性化的推广信息定位客户。

## 2.定义目标电子邮件地址的类型 {#define-target-email}

定义实施战略的第二步是确定要定位的客户电子邮件地址类型。

**A)基于实名电子邮件地址的受众定位**。 在此方案中，您的用户有多个帐户，这些帐户与多个电子邮件地址相关联，并且您希望根据他们在您的网站上实时验证的电子邮件地址，通过个性化的优惠来定位这些帐户。

**B)基于所有关联电子邮件地址的受众定位**。 在此方案中，您的用户有多个帐户与多个电子邮件地址关联，并且无论通过身份验证的活动如何，您都希望在其所有关联电子邮件地址中定位这些帐户。

## 3.识别您拥有的客户ID(CRM ID)类型 {#identify-customer-id}

定位中的受 [!DNL People-Based Destinations] 众需要您发送 [SHA256哈希版本的客户电子邮件地址](people-based-destinations-prerequisites.md) 。 根据您现有的Audience manager配置，您可能会发现处于以下两种情况之一：

**A)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已是小写的哈希电子邮件地址**。 在此方案中，您可以使用这些现有ID定位中的受众 [!DNL People-Based Destinations]。

**B)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写的哈希电子邮件地址**。 在此方案中，您的现有客户ID无法发送到 [!DNL People-Based Destinations]。 要使用 [!DNL People-Based Destinations]，您需要在现有客户ID和客户电子邮件地址的小写哈希版本之间执行ID同步。 您可以通过基于文 [件的ID同步或使用声明的ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 来 [执行此操作](../declared-ids.md)。

## 4.特质资格 {#trait-qualification}

要准确定位受众，您的用 [!DNL People-Based Destinations]户需要根据要执行的受众定位类型，有资格获得基于规则或已载入的特征。

**A)实时确定客户ID和设备ID，以获得基于规则的特征**。 此选项适用于用例A(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是根据线上和线下活动定位受众，那么您很可能已经对受众进行基于规 [则的特征资格认定](../traits/trait-qualification-reference.md)。

**B)通过入站数据文件针对客户ID的板载特征**。 此选项适用于用例B(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 根据纯线下活动定位受众时，您需要通过入站数据文件确定客户ID是否符合已载入 [的特征](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5.创建或标记数据源和板载哈希电子邮件地址 {#create-label-data-sources}

根据您在Audience manager中拥有的客户ID的类型(请参 [阅3)。 识别您拥有的客户ID(CRM ID)的类型](people-based-destinations-workflow.md#identify-customer-id)，您会发现自己处于以下任一情况中：

**A)标记现有数据源**。 此选项适用于Audience Manager客户ID(DPUUID[)已小写、哈希化电子邮件地址的情](../../reference/ids-in-aam.md)况。 在这种情况下，您需要做的是将ID存储在的数据源标记为数 [!DNL PII] 据源。 有关 [数据源设置的详细信息](../datasources-list-and-settings.md) ，请参阅数据源设置。 您需要做的是确保未选中“无法绑定到个人识别信息”选项。

**B)创建新数据源**。 此选项适用于Audience Manager客户ID(DPUUID[)没有哈希电子邮件地址的情](../../reference/ids-in-aam.md)况。 在这种情况下，您需要创建一个新的跨设备数据源，并将散列化的电子邮件地址加入其中。 您可以通过两种方式执行此操作：

* 使用基于文件的ID同步。 有关 [ID同步文件的外观的详细信息](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，请参阅ID同步文件的名称和内容要求。 使用此方法时，您可以瞄准数据库中的所有哈希电子邮件地址 [!DNL CRM] 。
* 在传 [入经过身份验证的客户ID时](../declared-ids.md) ，使用声明的ID声明具有哈希值的电子邮件地址。 使用此方法时，Audience manager仅针对已通过在线身份验证的用户的哈希电子邮件地址。 通过Facebook定位的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时激活。

## 6.使用配置文件合并规则进行分段 {#use-profile-merge-rules}

根据您的用例(请参 [阅1。 定义用例](people-based-destinations-workflow.md#defining-your-use-case))，可通过两种方式进行细 [!DNL Profile Merge Rules] 分。

**A)使用现有[!DNL Profile Merge Rules]**。 此选项适用于第一个用例（基于联机和脱机用户活动的组合的受众定位）。 在此方案中，您在Audience manager中有现有的客户活动，并且已至少定义了您在细分中使用的一个配置文件合并规则。 在这种情况下，您无需创建任何新内容 [!DNL Profile Merge Rules]。

**B)创建新的合[!DNL All Cross-Device Profiles]并规则**。 此选项适用于第二个用例（仅基于脱机用户活动的受众定位）。 在此方案中，您将离线客户数据从您的 [!DNL CRM] 数据导入Audience Manager，并希望根据该数据创建细分。 为此，引入 [!DNL People-Based Destinations] 了新的第四个配置文件合并规则，称为 **[!DNL All Cross-Device Profiles]**。 这是您在细分纯脱机数据时需要使用的规则。
