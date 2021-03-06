---
description: '本页包含有关如何将离线CRM数据与经过身份验证的用户的实时行为数据相结合，以创建受众区段，然后将这些受众区段发送到基于人员的目标的分步指南。 '
seo-description: '本页包含有关如何将离线CRM数据与经过身份验证的用户的实时行为数据相结合，以创建受众区段，然后将这些受众区段发送到基于人员的目标的分步指南。  '
seo-title: 工作流程 C - 基于已验证活动和离线数据的组合进行个性化
solution: Audience Manager
title: 工作流程 C - 基于已验证活动和离线数据的组合进行个性化
feature: 基于人员的目标
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# 工作流程 C - 基于已验证活动和离线数据的组合进行个性化 {#workflow-c}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何将离线[!DNL CRM]数据与经过身份验证的用户的实时行为数据合并以创建受众区段，然后将这些受众区段发送到[!DNL People-Based Destinations]的分步指南。

## 步骤1 — 配置数据源设置{#configure-data-source-settings}

根据[DPUUIDs](../../reference/ids-in-aam.md)是否为小写且经过哈希处理的电子邮件地址，您可能需要配置将存储经过哈希处理的电子邮件地址的数据源。

 

**场景1:您的 [](../../reference/ids-in-aam.md) DPUUID已经小写，经过哈希处理的电子邮件地址。**

在这种情况下，请跳转至[步骤5 — 配置基于人员的平台身份验证](#configure-authentication)。

 

**场景2:您的 [](../../reference/ids-in-aam.md) DPUUID不是小写的、经过哈希处理的电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源，以存储经过哈希处理的电子邮件地址。 下面是如何执行此操作：

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然后单击&#x200B;**[!UICONTROL Add New]**。
1. 为新数据源输入&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜单中，选择&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分中，选择&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;选项，然后启用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;选项。
1. 使用下拉菜单为此数据源选择&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法进行哈希处理的数据。 Audience Manager在此步骤中不会对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用[!DNL SHA256]算法进行哈希处理。 否则，将无法将其用于[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 有关如何将离线数据引入Audience Manager以实现基于人员的目标的常见问题，请参阅[数据载入](people-based-destinations-prerequisites.md#data-onboarding)。

请观看以下视频教程，了解如何为[!UICONTROL People-Based Destinations]创建数据源。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步骤2 — 使用声明的ID通过实时HTTP调用将DPUUID与经过哈希处理的电子邮件地址进行匹配{#match-email-addresses}

要使经过身份验证的用户符合基于规则的特征的资格条件，您需要通过[声明的ID](../declared-ids.md)发送特征资格条件。

### 示例

假设您已创建了以下两个数据源。

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 经过哈希处理的电子邮件地址 |

 

然后，您需要将下面的CRM ID用于表中的特征。

| DPUUID(CRM ID) | 电子邮件地址 | 经过哈希处理的电子邮件地址 | 特征 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美国 |

 

您声明的ID应遵循以下语法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在以上示例中，声明的ID调用应当如下所示：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 第3步 — 为分段创建配置文件合并规则{#create-profile-merge-rule-segmentation}

下一步是创建新的合并规则，以帮助您创建要发送到[!DNL People-Based Destinations]的受众区段。

>[!IMPORTANT]
>
>如果已使用&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;选项定义了规则，则可以跳到[步骤4 — 创建受众区段](#create-audience-segments)。

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 单击 **[!UICONTROL Add New Rule]**.
3. 输入配置文件合并规则&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分中，从&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;列表中选择&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;规则。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**列表中，选择要对其运行分段的数据源。 这些应是包含现有DPUUID的数据源。
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 步骤4 — 创建受众区段{#create-audience-segments}

要创建新区段，请使用[区段生成器](../segments/segment-builder.md)。 如果您有要发送到[!DNL People-Based Destinations]的现有受众区段，请跳转至[步骤5 — 配置基于人员的平台身份验证](#configure-authentication)。

## 步骤5 — 配置基于人员的平台身份验证{#configure-authentication}

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，则应会在此页面中列出该集成。 否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉菜单选择要配置与的集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
4. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;可重定向到所选平台的身份验证页面。
5. 在您的社交平台帐户上进行了身份验证后，系统会将您重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager在页面顶部显示通知，告知您帐户是否已成功添加。 此通知还允许您添加联系人电子邮件地址，以在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>Audience Manager通过身份验证令牌处理与社交平台的集成，该令牌会在特定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 步骤6 — 创建基于人员的目标{#create-destination}

1. 登录Audience Manager帐户，转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然后单击&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;部分中，为新数据源输入&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，然后使用以下设置：
   * **[!UICONTROL Category]**:集成平台；
   * **[!UICONTROL Type]**:以人为本；
   * **[!UICONTROL Platform]**:选择要将受众区段发送到的基于人员的平台；
   * **[!UICONTROL Account]**:选择与所选平台关联的所需广告商帐户。
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 选择要为此目标设置的&#x200B;**[!UICONTROL Data Export Labels]**。
1. 在&#x200B;**[!UICONTROL Configuration]**&#x200B;部分中，选择包含您的哈希数据源的数据源。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;部分中，选择要发送到此目标的区段。 这将是您在[步骤4 — 创建受众区段](#create-audience-segments)中创建的区段。
1. 保存目标。
