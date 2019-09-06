---
description: '本页包含有关如何配置和管理Audience Manager与基于人员的平台之间集成的指导。 '
seo-description: '本页包含有关如何配置和管理Audience Manager与基于人员的平台之间集成的指导。 '
seo-title: 使用基于人员的平台进行身份验证
solution: Audience Manager
title: 使用基于人员的平台进行身份验证
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# 使用基于人员的平台进行身份验证 {#authentication-with-people-based-platforms}

本页包含有关如何配置和管理Audience Manager与基于人员的平台之间集成的指导。

>[!NOTE]
>这是基于People的目标的强制性步骤，无论您的实施方案如何。

## 配置基于人物的平台身份验证 {#configure-authentication}

1. 登录Audience Manager帐户，然后转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。如果您先前已配置与社交平台的集成，则应当在此页面中列出它。否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
1. 单击 **[!UICONTROL Confirm]** 以重定向到所选平台的身份验证页面。
1. 在对社交平台帐户进行身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!UICONTROL Confirm]**&#x200B;的广告商帐户。
1. Audience Manager会在页面顶部显示通知，以便您了解是否成功添加了帐户。此通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时接收通知。

## 身份验证令牌过期和通知管理 {#token-expiration-notification}

Audience Manager通过在特定时间段后过期的身份验证令牌与社交平台进行集成。令牌有效性持续时间受每个社交平台的集成规则约束。验证令牌到期后，Audience Manager无法将受众细分发送到您的目标。为避免这种情况，我们建议向您的集成中添加至少一个联系电子邮件地址，以便在身份验证令牌即将过期时通知您。当发生这种情况时，您可以重新进行身份验证，以确保目标继续接收受众细分。

下面介绍如何向现有集成添加电子邮件地址：

1. 登录Audience Manager帐户，然后转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 识别要接收令牌过期通知的集成，然后单击 **[!UICONTROL Edit]** 图标。
1. 输入要接收令牌过期通知的电子邮件地址，以逗号分隔。
1. 单击 **[!UICONTROL Save]**.

## 身份验证令牌续订 {#token-renewal}

身份验证令牌过期后，Audience Manager与相应社交平台之间的集成将中断，因此Audience Manager无法再将受众细分发送到目标。[!UICONTROL Integrated Accounts] 该页面会显示 [!UICONTROL Expiration] 列中每个集成的过期状态，并允许您随时续订身份验证。

下面介绍如何续订过期或即将过期的身份验证：
1. 登录Audience Manager帐户，然后转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 识别您需要续订身份验证所需的集成。过期的身份验证标记为 [!UICONTROL Expired]，即将过期的身份验证将显示剩余的身份验证天数。
1. 单击列中的相应 **[!UICONTROL Renew]** 图标 [!UICONTROL Expiration] 。这会触发 **[!UICONTROL Renew Account]** 工作流，使您返回到社交平台的身份验证页面。验证后，令牌将通过新的过期日期续订。
   ![pdd-renew](assets/pbd-renew.png)
