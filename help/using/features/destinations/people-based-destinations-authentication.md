---
description: 本页包含有关如何配置和管理Audience Manager与基于人员的平台之间集成的指导。
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: 使用基于人员的平台进行身份验证
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# 使用基于人员的平台进行身份验证 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何配置和管理集成的指南
Audience Manager和基于人员的平台之间的通信。

>[!NOTE]
>这是基于人员的目标的强制步骤，与您的实施方案无关。

## 配置基于人员的平台身份验证 {#configure-authentication}

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，您应会看到此页面中列出了该集成。 否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**。
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**&#x200B;下拉菜单选择要配置集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
4. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;以重定向到所选平台的身份验证页面。
5. 在验证您的Social Platform帐户后，您将被重定向到Audience Manager，您应该会在其中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager会在页面顶部显示通知，让您知道帐户是否已成功添加。 通知还允许您添加联系人电子邮件地址，以在Social平台身份验证即将过期时从Adobe接收通知。

## 身份验证令牌过期和通知管理 {#token-expiration-notification}

Audience Manager通过在一段时间后过期的身份验证令牌处理您与社交平台的集成。 令牌的有效期取决于每个社交平台的集成规则。 身份验证令牌过期后，Audience Manager无法将您的受众区段发送到您的目标。 为了避免出现这种情况，我们建议向您的集成至少添加一个联系人电子邮件地址，以便在身份验证令牌即将过期时，您会收到通知。 发生这种情况时，您可以重新进行身份验证以确保目标继续接收您的受众区段。

以下是如何将电子邮件地址添加到现有集成：

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 识别要接收令牌过期通知的集成，然后单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标。
1. 输入您要接收令牌过期通知的电子邮件地址，用逗号分隔。
1. 单击 **[!UICONTROL Save]**。

## 身份验证令牌续订 {#token-renewal}

身份验证令牌过期后，Audience Manager与相应社交平台之间的集成会中断，因此Audience Manager无法再将受众区段发送到目标。 [!UICONTROL Integrated Accounts]页显示[!UICONTROL Expiration]列中每个集成的到期状态，并允许您随时续订身份验证。

下面是如何续订已过期或即将过期的身份验证：

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 确定续订身份验证所需的集成。 过期的身份验证将标记为[!UICONTROL Expired]，而即将过期的身份验证会显示剩余的身份验证天数。
1. 单击&#x200B;**[!UICONTROL Renew]**&#x200B;列中相应的[!UICONTROL Expiration]图标。 这会触发&#x200B;**[!UICONTROL Renew Account]**&#x200B;工作流，该工作流将带您回到Social平台的身份验证页面。 进行身份验证后，令牌将续订并带有新的到期日期。

   ![pbd — 续订](assets/pbd-renew.png)
