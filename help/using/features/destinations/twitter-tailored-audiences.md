---
description: This article explains how to configure Twitter Tailored Audiences for both new and existing integrations.
seo-description: This article explains how to configure Twitter Tailored Audiences for both new and existing integrations.
seo-title: Configure Twitter Tailored Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configure Twitter Tailored Audiences as a Self-Service Device-Based Destination
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# Configure  as a Self-Service Device-Based Destination [!DNL Twitter Tailored Audiences]{#configure-twitter}

This article explains how to configure Twitter Tailored Audiences for both new and existing integrations.[](https://business.twitter.com/en/targeting/tailored-audiences.html)

## 先决条件 {#prerequisites}

Before you configure your  destination, make sure to review the following Twitter prerequisites that you need to meet.[!DNL Twitter Tailored Audiences]

1. Your  account must be eligible for advertising. [!DNL Twitter Ads]New  accounts are not eligible for advertising in the first 2 weeks after creating them.[!DNL Twitter Ads]
1. Your Twitter user account that you authorized access for in Audience Manager must have the Partner audience manager permission enabled.[](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)
1. If you are updating your existing Twitter integration to self-service administration, your Twitter user account must have the Ad manager permission enabled.[](#update-existing-twitter-integrations)[](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)
1. When creating the first  destination in your Audience Manager instance, please contact Adobe Consulting or Customer Care to enable the  ID synchronization (Data Source ID = 1123) for your account. [!DNL Twitter Tailored Audiences][!DNL Twitter]这是在Audience manager和之间正确同步所必需的 [!DNL Twitter]。

## 添加新目 [!DNL Twitter Tailored Audiences] 标 {#add-new-twitter-destination}

本节介绍在为配置新的基于设备的目标时需要遵循的步骤 [!DNL Twitter Tailored Audiences]。 此方案假定您没有通过Adobe顾问或客 [!DNL Twitter Tailored Audiences] 户关怀配置任何现有目标。

### 步骤 1. Authenticate with  [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要先将Audience manager与您的帐户关 [!DNL Twitter Tailored Audiences] 联。 下面介绍如何实现此操作：

1. 登录您的Audience manager帐户并转到 **[!DNL Administration > Integrated Accounts]**。 如果您之前已配置与目标平台的集成，则应在本页中列出该集成。 否则，页面为空。
2. 单击 **[!DNL Add Account]**.
3. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。                     ![集成平台](assets/dbd-integrated-platforms.png)
4. 通过身份验证后，您将被重定向到Audience Manager，您应在该处查看关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!DNL Confirm]**。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

在将Audience manager与您的目标关联 [!DNL Twitter Tailored Audiences]后，您可以创建新的目标。 下面介绍如何实现此操作：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 确保提供有助于正确识别目标的名称。

1. 登录您的Audience manager帐户，转到并 **[!DNL Audience Data > Destinations]**&#x200B;单击 **[!DNL Create Destination]**。
2. 在部 **[!DNL Basic Information]** 分中，输入 **[!DNL Name]** 和 **[!DNL Description]** 作为新目标，然后使用以下设置：设 ![置](assets/dbd-new-basic.png)
3. 单击 **[!DNL Next]**.
4. 选择要 [为此目标设置的](/help/using/features/data-export-controls.md#controls-labels) “数据导出标签”。
5. 单击 **[!DNL Save]**.
6. 在部 **[!DNL Segment Mappings]** 分中，选择要发送到此目标的受众细分。
7. 保存目标。

## 将现有Twitter集成更新到自助管理 {#update-existing-twitter-integrations}

为了改善用户体验并简化配置过程，我们将集成升级到自助服务模型，您可以在该模型中，通过Audience Manager UI自行执行配置。 [!DNL Twitter Tailored Audiences] This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>以下所述步骤仅在您与Audience manager顾问或客户关怀部门 [!DNL Twitter Tailored Audiences]进行了现有集成时适用。 目标升级到自助服务模式的完整升级过程最长可能需要5个工作日。 同时，您的目标仍处于活动状态，Audience manager会继续向其发送受众。
> See item number 3 in Prerequisites before migrating your  to the self-service model.[](#prerequisites)[!DNL Twitter Tailored Audiences]

Follow the steps below to migrate your existing  destination to the self-service model.[!DNL Twitter Tailored Audiences]

1. Log in to your Audience Manager account and go to .**[!DNL Administration > Integrated Accounts]**
1. 单击 **[!DNL Add Account]**.
1. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。 ![integrated-platforms](assets/dbd-integrated-platforms.png)
1. 使用帐户进行身份验证后， [!DNL Twitter] 您将被重定向到Audience Manager，您应在该处查看关联的广告商帐户。 Select the advertiser account that you want to use and click .**[!DNL Confirm]**
1. Go to  &gt;  and click the Twitter destination that you need to configure.**[!UICONTROL Audience Data]****[!UICONTROL Destinations]**
1. 单击 **[!UICONTROL Edit]**. In the  section, click the  drop-down menu and select the  account that you have authenticated with at Step 4.**[!UICONTROL Basic Information]****[!UICONTROL Integrated Account]**[!DNL Twitter]
1. **[!UICONTROL Save]** 目标。

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing  integrations to self-service administration can take up to 7 days. [!DNL Twitter]Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your  account, with their names prefixed by []. [!DNL Twitter][!DNL Adobe DMP Audience]Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones.

## 区段映射注意事项 {#segment-mapping-considerations}

When mapping audience segments to Twitter, make sure to meet the following segment naming requirements:

* 提供可读的段映射名称。 我们建议使用您用于Audience manager区段的相同名称。
* 请勿在区段和区段映射名称中使用逗号。

### 示例

* 正确的区段或映射名称：“美国和欧洲购物者”;
* 区段或映射名称不正确：“美国，欧洲5h0pP3rs”。

>[!IMPORTANT]
>
>您无法更改已映射区段的名称。 Audience manager使用区段名称来正确识别集成中的区段。

## 匹配率注意事项 {#match-rates-considerations}

使用时， [!UICONTROL Twitter Tailored Audiences]目标页 [!UICONTROL Segment Addressable Audience] 面中 [!UICONTROL Segment Match Rate] 的和度量将不显示任何值。 这是正常行为，因为受众匹配以及此目标的匹配率由Adobe而不是Adobe处理和 [!UICONTROL Twitter]托管。
