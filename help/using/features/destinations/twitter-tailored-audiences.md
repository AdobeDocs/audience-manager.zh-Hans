---
description: 本文介绍如何为新集成和现有集成配置Twitter定制受众。
seo-description: 本文介绍如何为新集成和现有集成配置Twitter定制受众。
seo-title: 将Twitter定制受众配置为基于设备的自助服务目标
solution: Audience Manager
title: 将Twitter定制受众配置为基于设备的自助服务目标
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# 配置 [!DNL Twitter Tailored Audiences] 为基于自助服务设备的目标 {#configure-twitter}

本文介绍如何配置与 [Twitter定制受众的集成](https://business.twitter.com/en/targeting/tailored-audiences.html)。

## 先决条件 {#prerequisites}

在配置目标 [!DNL Twitter Tailored Audiences] 之前，请确保查看您需要满足的以下Twitter先决条件。

1. 您的 [!DNL Twitter Ads] 帐户必须有资格获得广告。 新帐 [!DNL Twitter Ads] 户在创建后的头2周内没有资格获得广告。
2. 您在 [!DNL Twitter] Audience manager中授权访问的用户帐户必须启用“合 [作伙伴Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) ”权限。
3. 在Audience manager实例中创 [!DNL Twitter Tailored Audiences] 建第一个目标时，请联系Adobe Consulting或客户关怀，为您的帐户启用 [!DNL Twitter] ID同步（数据源ID = 1123）。 这是在Audience manager和之间正确同步所必需的 [!DNL Twitter]。

## 添加新目 [!DNL Twitter Tailored Audiences] 标 {#add-new-twitter-destination}

本节介绍在为配置新的基于设备的目标时需要遵循的步骤 [!DNL Twitter Tailored Audiences]。 此方案假定您没有通过Adobe顾问或客 [!DNL Twitter Tailored Audiences] 户关怀配置任何现有目标。

### 步骤 1. 验证方 [!DNL Twitter Tailored Audiences] 式 {#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要先将Audience manager与您的帐户关 [!DNL Twitter Tailored Audiences] 联。 下面介绍如何实现此操作：

1. 登录您的Audience manager帐户并转到 **[!DNL Administration > Integrated Accounts]**。 如果您之前已配置与目标平台的集成，则应在本页中列出该集成。 否则，页面为空。
1. 单击 **[!DNL Add Account]**.
1. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。                     ![集成平台](assets/dbd-integrated-platforms.png)
1. 通过身份验证后，您将被重定向到Audience Manager，您应在该处查看关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!DNL Confirm]**。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

在将Audience manager与您的Audience Manager关联 [!DNL Twitter Tailored Audiences]后，您可以创建新目标。 下面介绍如何实现此操作：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 确保提供有助于正确识别目标的名称。

1. 登录您的Audience manager帐户，转到并 **[!DNL Audience Data > Destinations]**&#x200B;单击 **[!DNL Create Destination]**。
1. 在部 **[!DNL Basic Information]** 分中，输入 **[!DNL Name]** 和 **[!DNL Description]** 作为新目标，然后使用以下设置：设 ![置](assets/dbd-new-basic.png)
1. 单击 **[!DNL Next]**.
1. 选择要 [为此目标设置的](/help/using/features/data-export-controls.md#controls-labels) “数据导出标签”。
1. 单击 **[!DNL Save]**.
1. 在部 **[!DNL Segment Mappings]** 分中，选择要发送到此目标的受众细分。
1. 保存目标。

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## 区段映射注意事项 {#segment-mapping-considerations}

将受众细分映射 [!UICONTROL Twitter]到时，请确保满足以下细分命名要求：

* 提供可读的段映射名称。 我们建议使用您用于Audience manager区段的相同名称。
* 请勿在段和段映射中使用特殊字`,` 符( `%``:``;``@``/``=``?``$`段名称)。 如果您的Audience manager区段名称包含这些字符，请在将区段映射到目标之前删除这 [!UICONTROL Twitter] 些字符。

### 示例

* 正确的区段或映射名称：“美国和欧洲购物者”;
* 区段或映射名称不正确：“美国，欧洲5h0pP3rs”。

>[!IMPORTANT]
>
>您无法更改已映射区段的名称。 Audience manager使用区段名称来正确识别集成中的区段。

## 匹配率注意事项 {#match-rates-considerations}

* 使用时， [!UICONTROL Twitter Tailored Audiences]目标页 [!UICONTROL Segment Addressable Audience] 面中 [!UICONTROL Segment Match Rate] 的和度量将不显示任何值。 这是正常行为，因为受众匹配以及此目标的匹配率由Adobe而不是Adobe处理和 [!UICONTROL Twitter]托管。
* 目前，Audience manager与Audience manager之间的集成不 [!UICONTROL Twitter Tailored Audiences] 支持历史受众回填。 这意味着只有在将区段映射到 *Twitter目标* 之后发生的区段资格才会实 [!UICONTROL Twitter] 时发送到。
