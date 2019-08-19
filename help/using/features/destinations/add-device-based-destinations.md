---
description: 本文介绍如何从Audience Manager UI配置基于设备的新目标。
seo-description: 本文介绍如何从Audience Manager UI配置基于设备的新目标。
seo-title: 添加基于设备的新目标
solution: Audience Manager
title: 添加基于设备的新目标
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# 添加基于设备的新目标 {#add-new-device-based-destinations}

本文介绍如何从Audience Manager UI配置基于设备的新目标。

## 概述 {#overview}

添加基于设备的新目标的过程包括两个主要步骤。首先，您需要配置Audience Manager与目标合作伙伴之间的集成。完成此操作后，可创建基于设备的新目标。

>[!IMPORTANT]
>
>并非所有基于设备的目标都有资格获得自助服务配置工作流。如果您需要添加的基于设备的目标未显示在目标列表中，请与Adobe顾问或客户支持联系以获取帮助。

## 步骤 1. 使用目标平台进行身份验证 {#step1}

在创建新的基于设备的目标之前，您需要配置Audience Manager与目标平台之间的集成。下面是如何执行此操作的方法：

1. 登录Audience Manager帐户 **[!DNL Administration > Integrated Accounts]**，然后转到。如果您先前已配置与目标平台的集成，则应当在此页面中列出它。否则，页面为空。
2. 单击 **[!DNL Add Account]**.
3. 选择要通过身份验证的目标平台，然后单击 **[!DNL Confirm]** 以重定向到所选平台的身份验证页面。![集成平台](assets/dbd-integrated-platforms.png)
4. 在您对目标平台帐户进行身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!DNL Confirm]**&#x200B;的广告商帐户。

## 步骤 2. 创建基于设备的新目标 {#step2}

配置目标平台集成后，您可以创建新目标。下面是如何执行此操作的方法：

>[!NOTE]
>
>您无法更改现有设备的目标名称。确保提供可帮助您正确识别目标位置的名称。

1. 登录Audience Manager帐户，转至 **[!DNL Audience Data > Destinations]**&#x200B;并单击 **[!DNL Create Destination]**。
2. 在 **[!DNL Basic Information]** 该部分中，输入一个 **[!DNL Name]****[!DNL Description]** 新目标，然后使用以下列表中的设置： ![setup](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**：选择要将受众区段发送到的目标平台。
   * **[!DNL Account]**：选择与选定平台关联的所需广告商帐户。
3. 单击 **[!DNL Next]**.
4. 选择要为此目标设置 [的数据导出标签](/help/using/features/data-export-controls.md#controls-labels) 。
5. 单击 **[!DNL Save]**.
6. 在 **[!DNL Segment Mappings]** 部分中，选择要发送到此目标的受众细分。
7. 保存目标。

