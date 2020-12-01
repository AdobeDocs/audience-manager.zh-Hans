---
description: '本页介绍如何配置和管理Audience Manager平台与基于人的平台之间的集成。 '
seo-description: '本页介绍如何配置和管理Audience Manager平台与基于人的平台之间的集成。 '
seo-title: 使用基于人员的平台进行身份验证
solution: Audience Manager
title: 使用基于人员的平台进行身份验证
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---


# 使用基于人员的平台进行身份验证 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何配置和管理集成的指导
在Audience Manager和基于人的平台之间。

>[!NOTE]
>对于基于人员的目标，这是必需步骤，无论您的实施方案如何。

## 配置基于人员的平台身份验证{#configure-authentication}

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，您应会在本页中看到该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉菜单选择要配置其集成的平台。
   ![基于人的平台](assets/pbd-add.png)
4. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;以重定向到所选平台的身份验证页面。
5. 通过社交平台帐户身份验证后，您将被重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager在页面顶部显示通知，告诉您帐户是否成功添加。 通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时从Adobe接收通知。

## 身份验证令牌过期和通知管理{#token-expiration-notification}

Audience Manager通过身份验证令牌处理您与社交平台的集成，该令牌在特定时间后过期。 令牌有效期受每个社交平台的集成规则约束。 一旦身份验证令牌过期，Audience Manager将无法将受众区段发送到目标。 为避免出现这种情况，我们建议在您的集成中至少添加一个联系人电子邮件地址，以便在身份验证令牌即将过期时立即向您发送通知。 发生这种情况时，您可以重新进行身份验证，以确保目标继续接收您的受众段。

下面介绍如何向现有集成添加电子邮件地址：

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 确定要接收令牌到期通知的集成，然后单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标。
1. 输入要接收令牌到期通知的电子邮件地址，以逗号分隔。
1. 单击 **[!UICONTROL Save]**.

## 身份验证令牌续订{#token-renewal}

当身份验证令牌过期时，Audience Manager与相应社交平台之间的集成会中断，因此Audience Manager无法再将受众段发送到目标。 [!UICONTROL Integrated Accounts]页面在[!UICONTROL Expiration]列中显示每个集成的过期状态，并允许您随时续订身份验证。

下面介绍如何续订过期或即将过期的身份验证：
1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 确定续订身份验证所需的集成。 过期的身份验证标记为[!UICONTROL Expired]，而即将过期的身份验证显示剩余的已验证天数。
1. 单击[!UICONTROL Expiration]列中相应的&#x200B;**[!UICONTROL Renew]**&#x200B;图标。 这会触发&#x200B;**[!UICONTROL Renew Account]**工作流，该工作流会带您返回社交平台的身份验证页面。 验证后，令牌将随新的过期日期续订。
   ![pbd-renew](assets/pbd-renew.png)
