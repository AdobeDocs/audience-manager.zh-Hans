---
title: 为经过哈希处理的电子邮件工作流配置数据源
description: 了解如何创建数据源以存储经过哈希处理的电子邮件工作流的经过哈希处理的电子邮件。
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# 为经过哈希处理的电子邮件工作流配置数据源

经过哈希处理的电子邮件工作流（如基于人员的目标）要求您创建一个数据源来存储经过哈希处理的电子邮件地址。

请按照以下步骤为经过哈希处理的电子邮件创建和配置数据源。

1. 登录到您的Audience Manager帐户并转到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然后单击 **[!UICONTROL Add New]**.
1. 输入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 以获取您的新数据源。
1. 在 **[!UICONTROL ID Type]** 下拉菜单，选择 **[!UICONTROL Cross Device]**.
   ![显示“数据源详细信息”部分的Audience ManagerUI图像。](../features/assets/create-hashed-email-data-source.png)
1. 在 **[!UICONTROL Data Source Settings]** 部分，选择两者 **[!UICONTROL Inbound]** 和 **[!UICONTROL Outbound]** 选项，并启用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 选项。
1. 使用下拉菜单选择 **[!UICONTROL Emails(SHA256, lowercased)]** 此数据源的标签。

   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法经过哈希处理的数据。 Audience Manager在此步骤中不会散列数据。 确保您计划存储在此数据源中的电子邮件地址已使用 [!DNL SHA256] 算法。 否则，您将无法将其用于经过哈希处理的电子邮件工作流。

   ![显示数据源设置部分的Audience ManagerUI图像。](../features/assets/data-source-settings.png)


