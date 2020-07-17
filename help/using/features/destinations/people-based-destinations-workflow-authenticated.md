---
description: '本页包含有关如何将离线CRM数据与实时行为数据相结合的分步指导，供经过身份验证的用户创建受众区段，然后将这些受众区段发送到基于人的目标。 '
seo-description: '本页包含有关如何将离线CRM数据与实时行为数据相结合的分步指导，供经过身份验证的用户创建受众区段，然后将这些受众区段发送到基于人的目标。  '
seo-title: 工作流程 C - 基于已验证活动和离线数据的组合进行个性化
solution: Audience Manager
title: 工作流程 C - 基于已验证活动和离线数据的组合进行个性化
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 5%

---


# 工作流程 C - 基于已验证活动和离线数据的组合进行个性化 {#workflow-c}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含如何将离线数据与实时行为数据相结合的分 [!DNL CRM] 步指导，供经过身份验证的用户创建受众区段，然后将这些受众区段发送给 [!DNL People-Based Destinations]用户。

## 第1步——配置数据源设置 {#configure-data-source-settings}

根据您的DPUUID [是小写](../../reference/ids-in-aam.md) 、散列电子邮件地址，您可能需要配置用于存储散列电子邮件地址的数据源。

 

**方案1: 您[的DPUUID](../../reference/ids-in-aam.md)已是小写的散列电子邮件地址。**

在这种情况下，请跳到 [步骤5 —— 配置基于人员的平台身份验证](#configure-authentication)。

 

**方案2: 您[的DPUUID](../../reference/ids-in-aam.md)不是小写的散列电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源来存储散列电子邮件地址。 下面介绍如何实现此操作：

1. 登录您的Audience Manager帐户并转到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**&#x200B;并单击 **[!UICONTROL Add New]**。
1. 为新 **[!UICONTROL Name]** 数 **[!UICONTROL Description]** 据源输入和。
1. 在下 **[!UICONTROL ID Type]** 拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. 在部 **[!UICONTROL Data Source Settings]** 分中，选择和 **[!UICONTROL Inbound]** 选 **[!UICONTROL Outbound]** 项，然后启用选 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 项。
1. 使用下拉菜单选择此 **[!UICONTROL Emails(SHA256, lowercased)]** 数据源的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法散列的数据。 Audience Manager在此步骤中不对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用算法进行散列 [!DNL SHA256] 处理。 否则，您将无法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 有关 [如何将线下数据引入基于](people-based-destinations-prerequisites.md#data-onboarding) 人的目标Audience Manager的常见问题，请参阅数据入门。

观看以下视频，观看有关如何为其创建数据源的视频教程 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 第2步——使用声明的ID通过实时HTTP调用将DPUUID与散列电子邮件地址匹配 {#match-email-addresses}

要使经过身份验证的用户有资格获得基于规则的特征，您需要通过声明的ID发送特 [征资格](../declared-ids.md)。

### 示例

假设您已创建以下两个数据源。

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 哈希电子邮件地址 |

 

然后，您需要为表中的特征限定以下CRM ID。

| DPUUID(CRM ID) | 电子邮件地址 | 哈希电子邮件地址 | 特征 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美国 |

 

您声明的ID应遵循以下语法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上面的示例中，声明的ID调用应当如下：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 第3步——为分段创建用户档案合并规则 {#create-profile-merge-rule-segmentation}

下一步是创建新的合并规则，该规则将帮助您创建要发送到您的受众段 [!DNL People-Based Destinations]。

>[!IMPORTANT]
>
>如果您已经使用或选项定义了 **[!UICONTROL Current Authenticated Profiles]** 规则， **[!UICONTROL Last Authenticated Profiles]** 则可跳到步骤4 - [创建受众段](#create-audience-segments)。

1. 登录您的Audience Manager帐户并转 **[!UICONTROL Audience Data]** 到-> **[!UICONTROL Profile Merge Rules]**。
2. 单击 **[!UICONTROL Add New Rule]**.
3. 输入用户档案合并规 **[!UICONTROL Name]** 则和 **[!UICONTROL Description]**。
4. 在部 **[!UICONTROL Profile Merge Rule Setup]** 分中，从列表 **[!UICONTROL Current Authenticated Profiles]** 中选择 **[!UICONTROL Last Authenticated Profiles]** 或规则 **[!UICONTROL Cross-Device Options]** 。
5. 在列表 **[!UICONTROL Cross-Device Profile Options]** 中，选择要运行分段的数据源。 这些数据源应包含现有DPUUID。
   ![合并规则设置](assets/pbd-pmr-combined.png)

## 第4步——创建受众段 {#create-audience-segments}

要创建新区段，请使用区 [段生成器](../segments/segment-builder.md)。 如果您有要发送到的现有受众段， [!DNL People-Based Destinations]请跳 [到步骤5 —— 配置基于人员的平台身份验证](#configure-authentication)。

## 第5步——配置基于人的平台身份验证 {#configure-authentication}

1. 登录您的Audience Manager帐户并转 **[!UICONTROL Administration]** 到> **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，您应会在本页中看到该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置与集成的平台。
   ![基于人的平台](assets/pbd-add.png)
4. 单 **[!UICONTROL Confirm]** 击可重定向到所选平台的身份验证页面。
5. 通过社交平台帐户身份验证后，您将被重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户并单击 **[!UICONTROL Confirm]**。
6. Audience Manager在页面顶部显示通知，告诉您帐户是否成功添加。 通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>Audience Manager通过身份验证令牌处理与社交平台的集成，该令牌在一定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 第6步——创建基于人员的目标 {#create-destination}

1. 登录您的Audience Manager帐户，转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**&#x200B;并单击 **[!UICONTROL Create Destination]**。
1. 在部 **[!UICONTROL Basic Information]** 分中，输 **[!UICONTROL Name]** 入新 **[!UICONTROL Description]** 数据源的和，并使用以下设置：
   * **[!UICONTROL Category]**: 集成平台；
   * **[!UICONTROL Type]**: 以人为本；
   * **[!UICONTROL Platform]**: 选择要将受众段发送到的基于人员的平台；
   * **[!UICONTROL Account]**: 选择与所选平台关联的所需广告商帐户。
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 选择 **[!UICONTROL Data Export Labels]** 要为此目标设置的。
1. 在部分 **[!UICONTROL Configuration]** 中，选择包含散列数据源的数据源。
1. 在部 **[!UICONTROL Segment Mappings]** 分中，选择要发送到此目标的区段。 这将是您在第4步——创建 [受众区段时创建的区段](#create-audience-segments)。
1. 保存目标。
