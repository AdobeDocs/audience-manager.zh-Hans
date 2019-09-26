---
description: 基于人员的目标根据客户数据的结构提供多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。
seo-description: '基于人员的目标根据客户数据的结构提供多种实施战略。 本文概述了根据您的方案，您需要为基于人员的目标执行的实施步骤。  '
seo-title: 基于人员的目的地实施指南
solution: Audience Manager
title: 实施指南
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 实施指南 {#implementation-guidance}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

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

您的公司（一家航空公司）有不同的客户层（铜牌、银牌和金牌），您希望通过社交平台为每层提供个性化的推广信息。 您可以使用Audience manager分析网站上的客户活动。 但是，并非所有客户都使用该航空公司的移动应用程序，其中一些客户尚未登录该公司的网站。 您的客户数据主要限于会员ID和电子邮件地址。

要跨社交媒体和类似的基于人员的渠道定位受众，您可以将散列化的电子邮件地址导入Audience Manager [](people-based-destinations-prerequisites.md) ，并将它们与现有在线活动特征相结合，以构建新的受众细分。 接下来，您可以使用这些细分来定位受众 [!DNL People-Based Destinations]。

**B) Audience targeting based exclusively on your offline user activity.** In this scenario, your  system contains your customer email addresses and other customer attributes, but customers have not interacted with your website at all, so you don't have any customer activity in Audience Manager. [!DNL CRM]Here's an example that illustrates this scenario:

Your company, a telecom services provider, keeps customer data like email addresses and purchased telecom plans in an internal [!DNL CRM]. You want to target existing customers in social platforms to offer them upgrade packages based on their existing subscriptions. To do this, you can ingest your hashed customer email addresses into Audience Manager, and create segments based on the existing customer subscriptions. Then, you can send these segments to [!DNL People-Based Destinations] to target your customers with personalized offers.

## 2. Define the Type of Targeted Email Addresses {#define-target-email}

The second step in defining your implementation strategy is deciding what type of customer email addresses you want to target.

**A) Audience targeting based on your authenticated email addresses.** In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them with personalized offers, based only on the email address that they authenticate on your website, in real time.

**B) Audience targeting based on all of your associated email addresses.**&#x200B;在此方案中，您的用户有多个帐户与多个电子邮件地址关联，并且无论通过身份验证的活动如何，您都希望在其所有关联电子邮件地址中定位这些帐户。

## 3. Identify the Type of Customer IDs (CRM IDs) That You Have {#identify-customer-id}

Targeting audiences in  requires you to send SHA256 hashed versions of your customer email addresses. [!DNL People-Based Destinations][](people-based-destinations-prerequisites.md)Depending on your existing Audience Manager configuration, you may find yourself in one of the following two scenarios:

**A)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))已是小写的哈希电子邮件地址**。 在此方案中，您可以使用这些现有ID定位中的受众 [!DNL People-Based Destinations]。

**B)您的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))不是小写的哈希电子邮件地址**。 在此方案中，您的现有客户ID无法发送到 [!DNL People-Based Destinations]。 要使用 [!DNL People-Based Destinations]，您需要在现有客户ID和客户电子邮件地址的小写哈希版本之间执行ID同步。 您可以通过基于文 [件的ID同步或使用声明的ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 来 [执行此操作](../declared-ids.md)。

## 4.特质资格 {#trait-qualification}

要准确定位受众，您的用 [!DNL People-Based Destinations]户需要根据要执行的受众定位类型，有资格获得基于规则或已载入的特征。

**A)实时确定客户ID和设备ID，以获得基于规则的特征**。 此选项适用于用例A(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是根据线上和线下活动定位受众，那么您很可能已经对受众进行基于规 [则的特征资格认定](../traits/trait-qualification-reference.md)。

**B)通过入站数据文件根据您的客户ID提供板载特征**。 此选项适用于用例B(从 [1开始)。 定义用例](people-based-destinations-workflow.md#defining-your-use-case)。 根据纯线下活动定位受众时，您需要通过入站数据文件确定客户ID是否符合已载入 [的特征](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5.创建或标记数据源和板载哈希电子邮件地址 {#create-label-data-sources}

根据您在Audience manager中拥有的客户ID的类型(请参 [阅3)。 识别您拥有的客户ID(CRM ID)的类型](people-based-destinations-workflow.md#identify-customer-id)，您会发现自己处于以下任一情况中：

**A)标记现有数据源**。 此选项适用于Audience Manager客户ID(DPUUID[)已小写、哈希化电子邮件地址的情](../../reference/ids-in-aam.md)况。 在这种情况下，您需要做的是将ID存储为数据源的数据源 [!DNL PII] 标签。 有关 [数据源设置的详细信息](../datasources-list-and-settings.md) ，请参阅数据源设置。 您需要做的是确保未选中“无法绑定到个人识别信息”选项。

**B)创建新数据源**。 此选项适用于Audience Manager客户ID(DPUUID[)没有哈希电子邮件地址的情](../../reference/ids-in-aam.md)况。 在这种情况下，您需要创建一个新的跨设备数据源并在其上嵌入哈希电子邮件地址。 您可以通过两种方式执行此操作：

* 使用基于文件的ID同步。 See Name and Content Requirements for ID Synchronization Files for details on what ID synchronization files should look like. [](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)使用此方法时，您可以瞄准数据库中的所有哈希电子邮件地址 [!DNL CRM] 。
* Use declared IDs to declare your hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md)When using this method, Audience Manager, on your behalf, only targets your hashed email addresses from users who have authenticated online. The email addresses targeted in people-based channels are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not activated in real-time.

## 6. Use a Profile Merge Rule for Segmentation {#use-profile-merge-rules}

Depending on your use case (see 1. [Defining Your Use Case), there are two ways to use  for segmentation.](people-based-destinations-workflow.md#defining-your-use-case)[!DNL Profile Merge Rules]

**A) Use existing .[!DNL Profile Merge Rules]** This option applies to the first use case (audience targeting based on combined online and offline user activity). In this scenario, you have existing customer activity in Audience Manager and you have already defined at least one Profile Merge Rule that you have used in segmentation. In this case, you don't need to create any new .[!DNL Profile Merge Rules]

**B) Create a new,  Merge Rule.[!DNL All Cross-Device Profiles]** This option applies to the second use case (audience targeting based exclusively on offline user activity). 在此方案中，您将线下客户数据从您的 [!DNL CRM] Audience manager中导入，并希望根据这些数据创建细分。 To do this,  introduces a new, fourth Profile Merge Rule, called . [!DNL People-Based Destinations]**[!DNL All Cross-Device Profiles]**&#x200B;这是您在细分纯脱机数据时需要使用的规则。
