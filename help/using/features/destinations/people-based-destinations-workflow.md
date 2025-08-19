---
description: 基于人员的目标提供了多种实施策略，具体取决于客户数据的结构方式。 本文概述了基于人员的目标需要遵循的实施步骤，具体取决于您的场景。
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: 实施指南
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# 实施指南 {#implementation-guidance}

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

[!DNL People-Based Destinations]提供了多种实施策略，具体取决于客户数据的结构方式。 本文概述了[!DNL People-Based Destinations]需要遵循的实施步骤，具体取决于您的方案。

## 概述 {#overview}

[!DNL People-Based Destinations]的配置将带您查看Audience Manager的多个部分，并且需要不同的设置和数据载入方法，具体取决于您在Audience Manager中已有的客户数据类型以及要执行的受众定位类型。

>[!IMPORTANT]
> 在配置[!DNL People-Based Destinations]之前，请确保仔细而完整地阅读本文。 阅读本指南后，您应该对将通过[!DNL People-Based Destinations]启用的方案有清楚的了解。

在使用[!DNL People-Based Destinations]之前，需要澄清六个实施方面。 本文将帮助您了解您当前的配置，以便能够正确遵循适用于您的方案的实施步骤。

![pbd-implementation](assets/pbd-implementation.png)

## 1.定义用例 {#defining-your-use-case}

在开始实施[!DNL People-Based Destinations]之前，您需要明确定义要将此功能用于的用例。 您可以通过两种方式（基于受众活动）使用[!DNL People-Based Destinations]来定位受众：

**A)基于您的在线和离线组合用户活动的受众定位**。 在此方案中，您希望将Audience Manager中的现有受众数据与内部[!DNL CRM]系统中的数据相结合，并将生成的受众区段发送到[!DNL People-Based Destinations]。 下面是一个说明此方案的示例：

贵公司是一家航空公司，拥有不同的客户层（青铜、银牌和金牌），您希望通过社交平台为每个层提供个性化优惠。 您可以使用Audience Manager分析网站上的客户活动。 不过，并非所有客户都使用马航的移动应用，其中一些客户尚未登录该公司网站。 您的客户数据大多数受限于成员ID和电子邮件地址。

要在社交媒体和类似的基于人员的渠道中定位这些受众，您可以将[经过哈希处理的电子邮件地址](people-based-destinations-prerequisites.md)引入Audience Manager，并将其与您现有的在线活动特征相结合，以构建新的受众区段。 接下来，您可以使用这些区段通过[!DNL People-Based Destinations]定向受众。

**B)受众定位完全基于您的离线用户活动**。 在此方案中，您的[!DNL CRM]系统包含您的客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您在Audience Manager中没有任何客户活动。 下面是一个说明此方案的示例：

您的公司是一家电信服务提供商，它将客户数据（如电子邮件地址和购买的电信计划）保留在内部[!DNL CRM]中。 您希望定位社交平台中的现有客户，以根据其现有订阅向他们提供升级包。 为此，您可以将经过哈希处理的客户电子邮件地址提取到Audience Manager中，并根据现有客户订阅创建区段。 然后，您可以将这些区段发送到[!DNL People-Based Destinations]，以通过个性化优惠定位您的客户。

## 2.定义定向电子邮件地址的类型 {#define-target-email}

定义实施策略的第二步是确定要定位的客户电子邮件地址类型。

**A)基于经过身份验证的电子邮件地址的受众定位**。 在此方案中，您的用户拥有多个与多个电子邮件地址关联的帐户，您希望根据他们在您的网站上进行身份验证的电子邮件地址，实时为他们提供个性化优惠。

**B)基于所有关联电子邮件地址的受众定位**。 在此方案中，您的用户拥有多个与多个电子邮件地址关联的帐户，并且您希望跨所有关联的电子邮件地址定向这些帐户，而不管经过身份验证的活动。

## 3.识别您拥有的客户ID (CRM ID)类型 {#identify-customer-id}

在[!DNL People-Based Destinations]中定位受众需要您发送客户电子邮件地址的[SHA256 hashed](people-based-destinations-prerequisites.md)版本。 根据您现有的Audience Manager配置，您可能会发现自己处于以下两种情况之一：

**A)您的Audience Manager客户ID ([DPUUID](../../reference/ids-in-aam.md))已采用小写哈希处理电子邮件地址**。 在此方案中，您可以使用这些现有ID在[!DNL People-Based Destinations]中定位受众。

**B)您的Audience Manager客户ID ([DPUUID](../../reference/ids-in-aam.md))不是小写、经过哈希处理的电子邮件地址**。 在此方案中，您现有的客户ID无法发送到[!DNL People-Based Destinations]。 要使用[!DNL People-Based Destinations]，您需要在现有客户ID与小写、散列版本的客户电子邮件地址之间执行ID同步。 你通过[基于文件的ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)或使用[声明的ID](../declared-ids.md)来执行此操作。

## 4.特征资格 {#trait-qualification}

要在[!DNL People-Based Destinations]中准确地定位受众，您的用户需要具备基于规则的特征或已载入的特征，具体取决于您要执行的受众定位类型。

**A)实时让您的客户ID和设备ID符合基于规则的特征**。 此选项适用于[1中的用例A。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的计划是基于在线和离线活动来定位受众，则您很可能已经让受众符合[基于规则的特征](../traits/trait-and-segment-qualification-reference.md)。

**B)通过入站数据文件针对您的客户ID载入特征**。 此选项适用于[1中的用例B。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case)。 基于纯离线活动定位受众时，您需要通过[入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)来限定客户ID的已载入特征。

## 5.创建或标记数据源和载入经过哈希处理的电子邮件地址 {#create-label-data-sources}

根据您在Audience Manager中拥有的客户ID类型（请参阅[3）。 识别您拥有](people-based-destinations-workflow.md#identify-customer-id)的客户ID (CRM ID)类型，您会发现自己处于以下情况之一：

**A)标记现有数据源**。 此选项适用于您的Audience Manager客户ID ([DPUUID](../../reference/ids-in-aam.md))已经是小写散列电子邮件地址的情况。 在这种情况下，您需要做的是将您存储ID的数据源标记为[!DNL PII]数据源。 有关数据源设置的详细信息，请参阅[数据Source设置](../datasources-list-and-settings.md)。 您需要确保取消选中“无法与个人身份信息绑定”选项。

**B)创建新数据源**。 此选项适用于您的Audience Manager客户ID ([DPUUID](../../reference/ids-in-aam.md))未经过哈希处理的电子邮件地址的情况。 在这种情况下，您需要创建一个新的跨设备数据源，并针对该数据源载入经过哈希处理的电子邮件地址。 您可以通过两种方式做到这一点：

* 使用基于文件的ID同步。 有关 ID 同步文件外观的详细信息，请参阅 [ID 同步文件的名称和内容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法时，您可以定位来自[!DNL CRM]数据库的所有经过哈希处理的电子邮件地址。
* 在传入经过身份验证的客户ID时，使用[声明的ID](../declared-ids.md)来声明经过哈希处理的电子邮件地址。 使用此方法时，Audience Manager仅代表您定位已在线进行身份验证的用户的经过哈希处理的电子邮件地址。 基于人员的渠道中定位的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户 ID 关联的其他电子邮件地址不会实时激活。

## 6.使用配置文件合并规则进行分段 {#use-profile-merge-rules}

根据您的用例（请参阅[1）。 定义您的用例](people-based-destinations-workflow.md#defining-your-use-case)，可通过两种方式使用[!DNL Profile Merge Rules]进行分段。

**A)使用现有[!DNL Profile Merge Rules]**。 此选项适用于第一个用例（基于组合在线和离线用户活动的受众定位）。 在此方案中，您在Audience Manager中拥有现有客户活动，并且已定义至少一个在分段中使用的配置文件合并规则。 在这种情况下，您无需创建任何新[!DNL Profile Merge Rules]。

**B)创建新的[!DNL All Cross-Device Profiles]合并规则**。 此选项适用于第二个用例（专门基于离线用户活动的受众定位）。 在此方案中，您要将离线客户数据从[!DNL CRM]引入Audience Manager，并希望根据该数据创建区段。 为此，[!DNL People-Based Destinations]引入了第四个新的配置文件合并规则，称为&#x200B;**[!DNL All Cross-Device Profiles]**。 这是您在分段纯离线数据时需要使用的规则。
