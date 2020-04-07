---
description: 基于人员的目标根据客户数据的结构优惠了多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。
seo-description: '基于人员的目标根据客户数据的结构优惠了多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。  '
seo-title: 基于人员的目的地实施指南
solution: Audience Manager
title: 实施指南
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# 实施指南 {#implementation-guidance}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations] 优惠多种实施战略，具体取决于客户数据的结构。 本文概述了您需要遵循的实施步骤，具体取决 [!DNL People-Based Destinations]于您的方案。

## 概述 {#overview}

配置将带 [!DNL People-Based Destinations] 您浏览受众管理器的多个部分，并需要不同的设置和数据载入方法，具体取决于您在受众管理器中已有的客户数据类型以及要执行的受众定位类型。

>[!IMPORTANT]
> 配置之 [!DNL People-Based Destinations]前，请务必仔细阅读本文。 阅读本指南后，您应清楚了解将启用的方案 [!DNL People-Based Destinations]。

在使用之前，您需要先阐明六个实施方面 [!DNL People-Based Destinations]。 本文将帮助您了解当前的配置内容，以便您能够正确执行方案的实施步骤。

![pbd实现](assets/pbd-implementation.png)

## 1.定义用例 {#defining-your-use-case}

在开始实施之 [!DNL People-Based Destinations]前，您需要明确定义将要为此功能使用的用例。 您可以根 [!DNL People-Based Destinations] 据目标受众，通过两种方式使用受众:

**A)基于线上和线下用户组合活动的受众定位**。 在此方案中，您希望将来自受众管理器的现有受众数据与来自内部系统的数据相 [!DNL CRM] 结合，并将生成的受众区段发送到 [!DNL People-Based Destinations]。 下面是一个说明此方案的示例：

您的公司是一家航空公司，它有不同的客户层（铜牌、银牌和金牌），您希望通过社交平台为每层提供个性化的优惠。 您可以使用受众经理分析网站上的客户活动。 但是，并非所有客户都使用该航空公司的移动应用程序，其中一些客户尚未登录该公司的网站。 您的客户数据主要限于会员ID和电子邮件地址。

要在社交媒体和类似的基于人员的目标中进行渠道 [](people-based-destinations-prerequisites.md) ，您可以将哈希化的电子邮件地址导入受众管理器中，并将它们与现有的在线活动特征结合，从而构建新的受众细分。 接下来，您可以使用这些细分来目标受众 [!DNL People-Based Destinations]。

**B)受众定位仅基于您的脱机用户活动**。 在这种情况下，您的系 [!DNL CRM] 统包含您的客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您在受众经理中没有任何客户活动。 下面是一个说明此方案的示例：

您的公司是电信服务提供商，它将客户数据（如电子邮件地址和购买的电信计划）保存在内部 [!DNL CRM]。 您希望目标社交平台中的现有客户，以根据现有订阅优惠他们的升级包。 为此，您可以将哈希化的客户电子邮件地址收录到受众管理器中，并根据现有客户订阅创建细分。 然后，您可以发送这些细分，以 [!DNL People-Based Destinations] 便通过个性化优惠目标客户。

## 2.定义目标电子邮件地址的类型 {#define-target-email}

定义实施战略的第二步是确定要目标的客户电子邮件地址类型。

**A)根据经过身份验证的电子邮件地址进行受众定位**。 在此方案中，您的用户有多个帐户与多个电子邮件地址关联，并且您希望仅根据他们在您的网站上实时验证的电子邮件地址，将他们与个性化的优惠目标。

**B)根据您的所有关联电子邮件地址进行受众定位**。 在此方案中，您的用户有多个帐户与多个电子邮件地址关联，并且您希望将这些帐户目标到其所有关联的电子邮件地址中，而不管通过身份验证的活动。

## 3.识别您拥有的客户ID(CRM ID)类型 {#identify-customer-id}

定位中的受众 [!DNL People-Based Destinations] 需要您发送 [SHA256哈希版本的客户电子邮件地址](people-based-destinations-prerequisites.md) 。 根据您现有的受众管理器配置，您可能会发现处于以下两种情况之一：

**A)您的受众经理客户ID([DPUUID](../../reference/ids-in-aam.md))已经是小写的、哈希化的电子邮件地址**。 在此方案中，您可以使用这些现有ID在中目标受众 [!DNL People-Based Destinations]。

**B)您的受众经理客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写的哈希电子邮件地址**。 在此方案中，您的现有客户ID无法发送到 [!DNL People-Based Destinations]。 要使用 [!DNL People-Based Destinations]，您需要在现有客户ID和客户电子邮件地址的小写哈希版本之间执行ID同步。 您可以通过基于文 [件的ID同步或使用声明的ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 来 [执行此操作](../declared-ids.md)。

## 4.特质资格 {#trait-qualification}

要准确目标您的受众，您的用户需要符合基于规则或已载入的特征，具体取决于您要执行的受众定位类型。 [!DNL People-Based Destinations]

**A)实时确定客户ID和设备ID，以获得基于规则的特征**。 此选项适用于用例A(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是基于线上和线下活动目标受众，那么您很可能已经对基于规则的特征 [的受众有资格](../traits/trait-and-segment-qualification-reference.md)。

**B)通过入站数据文件根据您的客户ID提供板载特征**。 此选项适用于用例B(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 在基于纯离线活动定位您的受众时，您需要通过入站数据文件确定客户ID是否符合已载入 [的特征](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5.创建或标记数据源和板载哈希电子邮件地址 {#create-label-data-sources}

根据您在受众管理器中拥有的客户ID的类型(请参 [阅3)。 识别您拥有的客户ID(CRM ID)的类型](people-based-destinations-workflow.md#identify-customer-id)，您会发现自己处于以下任一情况中：

**A)标记现有数据源**。 此选项适用于受众经理客户ID(DPUUID[](../../reference/ids-in-aam.md))已小写的哈希电子邮件地址的情况。 在这种情况下，您需要做的是将ID存储为数据源的数据源 [!DNL PII] 标签。 有关 [数据源设置的详细信息](../datasources-list-and-settings.md) ，请参阅数据源设置。 您需要做的是确保未选中“无法绑定到个人识别信息”选项。

**B)创建新数据源**。 此选项适用于受众经理客户ID(DPUUID[](../../reference/ids-in-aam.md))未经过哈希处理的电子邮件地址的情况。 在这种情况下，您需要创建一个新的跨设备数据源并在其上嵌入哈希电子邮件地址。 您可以通过两种方式执行此操作：

* 使用基于文件的ID同步。 有关 [ID同步文件的外观的详细信息](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，请参阅ID同步文件的名称和内容要求。 使用此方法时，您可以目标数据库中所有哈希化的电子邮件 [!DNL CRM] 地址。
* 在传 [入经身份验证的客户ID时](../declared-ids.md) ，使用声明的ID声明您的哈希电子邮件地址。 使用此方法时，受众经理仅代表您从在线通过身份验证的用户那里目标您经过哈希处理的电子邮件地址。 基于人员的渠道中目标的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时激活。

## 6.使用用户档案合并规则进行分段 {#use-profile-merge-rules}

根据您的用例(请参 [阅1。 定义用例](people-based-destinations-workflow.md#defining-your-use-case))，可通过两种方式进行细 [!DNL Profile Merge Rules] 分。

**A)使用现有[!DNL Profile Merge Rules]**。 此选项适用于第一个用例(基于联机和脱机用户受众的组合的活动定位)。 在此方案中，您在受众管理器中拥有现有的客户活动，并且您已经至少定义了一个用于分段的用户档案合并规则。 在这种情况下，您无需创建任何新内容[!DNL Profile Merge Rules]。

**B)创建新的合[!DNL All Cross-Device Profiles]并规则**。 此选项适用于第二个用例(仅基于脱机用户活动的受众定位)。 在这种情况下，您将线下客户数据从您的 [!DNL CRM] 渠道导入受众管理器，并希望根据这些数据创建细分。 为此，引入 [!DNL People-Based Destinations] 了新的第四个用户档案合并规则，称为 **[!DNL All Cross-Device Profiles]**。 这是您在细分纯脱机数据时需要使用的规则。
