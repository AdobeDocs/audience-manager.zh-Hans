---
description: '本页包含有关如何配置和管理Audience Manager与基于人员的平台之间的集成的指导。 '
seo-description: '本页包含有关如何配置和管理Audience Manager与基于人员的平台之间的集成的指导。 '
seo-title: 使用基于人员的平台进行身份验证
solution: Audience Manager
title: 使用基于人员的平台进行身份验证
feature: 基于人员的目标
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 使用基于人员的平台进行身份验证 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何配置和管理集成的指南
Audience Manager平台和基于人员的平台之间。

>[!NOTE]
>无论您的实施方案如何，对于基于人员的目标，都是必备步骤。

## 配置基于人员的平台身份验证{#configure-authentication}

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，则应会在此页面中列出该集成。 否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉菜单选择要配置与的集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
4. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;可重定向到所选平台的身份验证页面。
5. 在您的社交平台帐户上进行了身份验证后，系统会将您重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager在页面顶部显示通知，告知您帐户是否已成功添加。 通知还允许您添加联系人电子邮件地址，以在社交平台身份验证即将过期时从Adobe接收通知。

## 身份验证令牌到期和通知管理{#token-expiration-notification}

Audience Manager通过身份验证令牌处理您与社交平台的集成，该令牌会在特定时间后过期。 令牌有效期受每个社交平台集成规则的约束。 一旦身份验证令牌过期，Audience Manager将无法将受众区段发送到您的目标。 为避免出现这种情况，我们建议向您的集成至少添加一个联系人电子邮件地址，以便在身份验证令牌即将过期时立即向您发送通知。 发生这种情况时，您可以重新进行身份验证，以确保目标继续接收您的受众区段。

以下是如何向现有集成添加电子邮件地址：

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 识别要接收令牌到期通知的集成，然后单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标。
1. 输入要接收令牌到期通知的电子邮件地址（以逗号分隔）。
1. 单击 **[!UICONTROL Save]**.

## 身份验证令牌续订{#token-renewal}

当身份验证令牌过期时，Audience Manager与相应社交平台之间的集成会中断，因此Audience Manager无法再将受众区段发送到目标。 [!UICONTROL Integrated Accounts]页面显示[!UICONTROL Expiration]列中每个集成的过期状态，并允许您随时续订身份验证。

以下是如何续订过期或即将过期的身份验证：
1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 确定续订身份验证所需的集成。 过期的身份验证标记为[!UICONTROL Expired]，而即将过期的身份验证显示剩余的已验证天数。
1. 单击[!UICONTROL Expiration]列中相应的&#x200B;**[!UICONTROL Renew]**&#x200B;图标。 这会触发&#x200B;**[!UICONTROL Renew Account]**工作流，该工作流会引导您返回社交平台的身份验证页面。 验证后，令牌将续订为新的过期日期。
   ![pbd-renew](assets/pbd-renew.png)
