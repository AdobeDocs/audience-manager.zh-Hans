---
title: 为经过哈希处理的电子邮件工作流配置数据源
description: 了解如何创建数据源以存储经过哈希处理的电子邮件工作流的经过哈希处理的电子邮件。
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# 为经过哈希处理的电子邮件工作流配置数据源

经过哈希处理的电子邮件工作流（如基于人员的目标）要求您创建一个数据源来存储经过哈希处理的电子邮件地址。

请按照以下步骤为经过哈希处理的电子邮件创建和配置数据源。

1. 登录到您的Audience Manager帐户并转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然后单击&#x200B;**[!UICONTROL Add New]**。
1. 输入新数据源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Cross Device]**。
   ![显示数据源详细信息部分的Audience Manager UI图像。](../features/assets/create-hashed-email-data-source.png)
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分中，选择&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;选项，并启用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;选项。
1. 使用下拉菜单为此数据源选择&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;标签。

   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法经过哈希处理的数据。 Audience Manager不会在此步骤中对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用[!DNL SHA256]算法进行哈希处理。 否则，您将无法将其用于经过哈希处理的电子邮件工作流。

   ![显示数据源设置部分的Audience Manager UI图像。](../features/assets/data-source-settings.png)
