---
description: '本页介绍如何配置和管理Audience manager与基于人员的平台之间的集成。 '
seo-description: '本页介绍如何配置和管理Audience manager与基于人员的平台之间的集成。 '
seo-title: 使用基于人的平台进行身份验证
solution: Audience Manager
title: 使用基于人的平台进行身份验证
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# 使用基于人的平台进行身份验证 {#authentication-with-people-based-platforms}

本页介绍如何配置和管理Audience manager与基于人员的平台之间的集成。

>[!NOTE]
>无论您的实施方案如何，这是基于人员的目标的必选步骤。

## 配置基于人员的平台身份验证 {#configure-authentication}

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Administration]** 到&gt; **[!UICONTROL Integrated Accounts]**。 如果您之前已配置与社交平台的集成，则应在本页中列出该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置其集成的平台。
   ![基于人的平台](assets/pbd-add.png)
1. 单 **[!UICONTROL Confirm]** 击以重定向到所选平台的身份验证页面。
1. 通过社交平台帐户的身份验证后，您将被重定向到Audience Manager，您应在Audience manager中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!UICONTROL Confirm]**。
1. Audience manager在页面顶部显示通知，告诉您帐户是否已成功添加。 通知还允许您添加联系人电子邮件地址，以在社交平台身份验证即将过期时接收通知。

## 身份验证令牌到期和通知管理 {#token-expiration-notification}

Audience manager通过身份验证令牌处理与社交平台的集成，这些令牌在一定时间后过期。 令牌有效性持续时间取决于每个社交平台的集成规则。 身份验证令牌到期后，Audience manager将无法将受众细分发送到您的目标。 为避免出现此情况，我们建议在您的集成中添加至少一个联系电子邮件地址，以便在身份验证令牌即将过期时立即向您发送通知。 发生这种情况时，您可以重新验证身份，以确保目标继续接收您的受众细分。

下面介绍如何将电子邮件地址添加到现有集成：

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Administration]** 到&gt; **[!UICONTROL Integrated Accounts]**。
1. 确定要接收令牌到期通知的集成，然后单击图 **[!UICONTROL Edit]** 标。
1. 输入要接收令牌到期通知的电子邮件地址，以逗号分隔。
1. 单击 **[!UICONTROL Save]**.

## 身份验证令牌续订 {#token-renewal}

当身份验证令牌过期时，Audience manager与相应社交平台之间的集成将中断，因此Audience manager无法再将受众区段发送到目标。 该页 [!UICONTROL Integrated Accounts] 面在列中显示每个集成的过期状态， [!UICONTROL Expiration] 并允许您随时续订身份验证。

下面介绍如何续订过期或即将过期的身份验证：
1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Administration]** 到&gt; **[!UICONTROL Integrated Accounts]**。
1. 确定续订身份验证所需的集成。 过期的身份验证标 [!UICONTROL Expired]记为，而即将过期的身份验证显示剩余的已验证天数。
1. 单击列中 **[!UICONTROL Renew]** 的相应图 [!UICONTROL Expiration] 标。 这会触发 **[!UICONTROL Renew Account]** 工作流，该工作流会带您重新浏览社交平台的身份验证页面。 在您进行身份验证后，令牌会以新的到期日期续订。
   ![pbd-renew](assets/pbd-renew.png)
