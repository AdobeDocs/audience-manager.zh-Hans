---
description: 本文介绍如何为新的和现有集成配置Twitter定制受众。
seo-description: 本文介绍如何为新的和现有集成配置Twitter定制受众。
seo-title: 将Twitter定制的受众配置为基于自助服务设备的目标
solution: Audience Manager
title: 将Twitter定制的受众配置为基于自助服务设备的目标
translation-type: tm+mt
source-git-commit: 96717384ebb82056f330312b0f99fb97086a2e05

---


# 配置 [!DNL Twitter Tailored Audiences] 为基于自助服务设备的目标 {#configure-twitter}

本文介绍如何为新的和现有集成配置 [Twitter定制受众](https://business.twitter.com/en/targeting/tailored-audiences.html) 。

## 先决条件 {#prerequisites}

配置 [!DNL Twitter Tailored Audiences] 目标之前，请确保查看需要满足的Twitterprerequi站点。

1. [!DNL Twitter Ads] 您的帐户必须具有广告资格。在创建广告后的前两周，新 [!DNL Twitter Ads] 帐户没有资格获得广告。
2. 您在Audience Manager中授权访问的Twitter用户帐户必须启用 [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 权限。
3. 如果 [您正在将现有Twitter集成更新到自助服务管理](#update-existing-twitter-integrations)，则您的Twitter用户帐户必须启用 [广告管理器](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 权限。



## 添加新 [!DNL Twitter Tailored Audiences] 目标 {#add-new-twitter-destination}

本节介绍配置基于设备的新目标时需要遵循的步骤 [!DNL Twitter Tailored Audiences]。此方案假定您没有通过Adobe顾问或客户关怀配置的现有 [!DNL Twitter Tailored Audiences] 目标。

### 步骤 1. 身份验证 [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要链接Audience Manager和 [!DNL Twitter Tailored Audiences] 您的帐户。下面是如何执行此操作的方法：

1. 登录Audience Manager帐户 **[!DNL Administration > Integrated Accounts]**，然后转到。如果您先前已配置与目标平台的集成，则应当在此页面中列出它。否则，页面为空。
2. 单击 **[!DNL Add Account]**.
3. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。![集成平台](assets/dbd-integrated-platforms.png)
4. 经过身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!DNL Confirm]**&#x200B;的广告商帐户。

### 步骤 2. 创建基于设备的新目标 {#step2-create-new-destination}

在您与Audience [!DNL Twitter Tailored Audiences]Manager关联之后，您可以创建新目标。下面是如何执行此操作的方法：

>[!NOTE]
>
>您无法更改现有设备的目标名称。确保提供可帮助您正确识别目标位置的名称。

1. 登录Audience Manager帐户，转至 **[!DNL Audience Data > Destinations]**&#x200B;并单击 **[!DNL Create Destination]**。
2. 在 **[!DNL Basic Information]** 部分中，输入一个 **[!DNL Name]****[!DNL Description]** 新目标并使用下面的设置： ![setup](assets/dbd-new-basic.png)
3. 单击 **[!DNL Next]**.
4. 选择要为此目标设置 [的数据导出标签](/help/using/features/data-export-controls.md#controls-labels) 。
5. 单击 **[!DNL Save]**.
6. 在 **[!DNL Segment Mappings]** 部分中，选择要发送到此目标的受众细分。
7. 保存目标。

## 将现有Twitter集成更新到自助服务管理 {#update-existing-twitter-integrations}

为了改进用户体验并简化配置过程，我们将 [!DNL Twitter Tailored Audiences] 从Audience Manager UI升级到自助服务模型，您可以从中自己执行配置。本节介绍更新现有Twitter集成所需采取的步骤。

>[!IMPORTANT]
>
>仅当您与Audience [!DNL Twitter Tailored Audiences]Manager顾问或客户关怀部门进行了现有集成时，下述步骤才适用。您的目标到自助服务模型的完整升级过程最长可能需要个工作日。同时，您的目标仍处于活动状态，Audience Manager将继续向受众发送受众。
> 请在 [迁移](#prerequisites)[!DNL Twitter Tailored Audiences] 到自助服务模型之前查看先决条件中的项目号3。

请按照以下步骤将现有 [!DNL Twitter Tailored Audiences] 目标迁移到自助服务模型。

1. 登录Audience Manager帐户 **[!DNL Administration > Integrated Accounts]**，然后转到。
2. 单击 **[!DNL Add Account]**.
3. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。![集成平台](assets/dbd-integrated-platforms.png)
4. 通过Twitter帐户进行身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!DNL Confirm]**&#x200B;的广告商帐户。

## 区段映射注意事项 {#segment-mapping-considerations}

将受众区段映射到Twitter时，请确保满足以下区段命名要求：

* 提供可读的区段映射名称。我们建议使用您用于Audience Manager区段的相同名称。
* 请勿在区段和区段映射名称中使用逗号。

**示例**

* 正确的区段或映射名称：“美国和欧洲购物者”；
* 区段或映射名称不正确：“US，European h0Pp3rs”.

>[!IMPORTANT]
>
>您无法更改已映射区段的名称。Audience Manager使用细分名称正确识别集成中的区段。