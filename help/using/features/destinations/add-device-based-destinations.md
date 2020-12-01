---
description: 本文介绍如何从Audience Manager用户界面配置基于设备的新目标。
seo-description: 本文介绍如何从Audience Manager用户界面配置基于设备的新目标。
seo-title: 添加新的基于设备的目标
solution: Audience Manager
title: 添加新的基于设备的目标
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 4%

---


# 添加新的基于设备的目标 {#add-new-device-based-destinations}

本文介绍如何从Audience Manager用户界面配置基于设备的新目标。

>[!IMPORTANT]
>
>目前，大多数基于设备的目标都没有资格使用自助服务配置工作流。 如果您需要添加的基于设备的目标未显示在目标列表中，请与Adobe顾问或客户支持联系以获得帮助。

## 概述 {#overview}

添加新的基于设备的目标的过程包括两个主要步骤。 首先，您需要配置Audience Manager与目标合作伙伴之间的集成。 完成此操作后，您可以创建基于设备的新目标。

## 先决条件 {#prerequisites}

在使用集成平台创建第一个基于设备的目标时，请与Adobe咨询或客户关怀部门联系，以在Audience Manager和您的帐户的集成平台之间实现ID同步。 这是Audience Manager与目标平台之间正确同步所必需的。

## 步骤 1. 使用目标平台{#step1}进行身份验证

在创建基于设备的新目标之前，您需要配置Audience Manager与目标平台之间的集成。 下面介绍如何实现此操作：

1. 登录您的Audience Manager帐户并转到&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您之前配置了与目标平台的集成，您应会在本页中看到该集成。 否则，页面为空。
1. 单击 **[!DNL Add Account]**.
1. 选择要进行身份验证的目标平台，然后单击&#x200B;**[!DNL Confirm]**&#x200B;以重定向到所选平台的身份验证页面。

   ![集成平台](assets/dbd-integrated-platforms.png)

1. 通过目标平台帐户身份验证后，您将被重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!DNL Confirm]**。

## 步骤 2. 创建新的基于设备的目标{#step2}

配置目标平台集成后，您可以创建新目标。 下面介绍如何实现此操作：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 请确保提供有助于正确识别目标的名称。

1. 登录您的Audience Manager帐户，转到&#x200B;**[!DNL Audience Data > Destinations]**，然后单击&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;部分，输入新目标的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，然后使用以下列表中的设置：

   ![设置](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:选择要将受众段发送到的目标平台。
   * **[!DNL Account]**:选择与所选平台关联的所需广告商帐户。
1. 单击 **[!DNL Next]**.
1. 选择要为此目标设置的[数据导出标签](/help/using/features/data-export-controls.md#controls-labels)。
1. 单击 **[!DNL Save]**.
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;部分，选择要发送到此目标的受众段。
1. 保存目标。
