---
description: '本页包含有关如何将离线CRM数据与实时行为数据相结合以创建受众细分的分步指导，然后将这些受众细分发送到基于人员的目标。 '
seo-description: '本页包含有关如何将离线CRM数据与实时行为数据相结合以创建受众细分的分步指导，然后将这些受众细分发送到基于人员的目标。  '
seo-title: 工作流C —— 基于实名活动和离线数据的个性化
solution: Audience Manager
title: 工作流C —— 基于实名活动和离线数据的个性化
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# 工作流C —— 基于实名活动和离线数据的个性化 {#workflow-c}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何将离线数据与实时行为数据相结合的分步指导，供经过身份验证的用 [!DNL CRM] 户创建受众细分，然后将这些受众细分发送到 [!DNL People-Based Destinations]。

## 第1步——配置数据源设置 {#configure-data-source-settings}

根据您的 [DPUUID是小写的](../../reference/ids-in-aam.md) 、哈希电子邮件地址，您可能需要配置用于存储哈希电子邮件地址的数据源。

 

**场景1:您的[DPUUID已是小写](../../reference/ids-in-aam.md)，具有哈希值的电子邮件地址。**

在这种情况下，请跳到第5 [步——配置基于人员的平台身份验证](#configure-authentication)。

 

**场景2:您的[DPUUID不是小写](../../reference/ids-in-aam.md)，具有哈希值的电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源，以存储散列化的电子邮件地址。 下面介绍如何实现此操作：

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Audience Data]** 到-&gt; **[!UICONTROL Data Sources]**&#x200B;并单击 **[!UICONTROL Add New]**。
1. 为新数 **[!UICONTROL Name]** 据源 **[!UICONTROL Description]** 输入和。
1. 在下 **[!UICONTROL ID Type]** 拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. 在部 **[!UICONTROL Data Source Settings]** 分中，选择和 **[!UICONTROL Inbound]** 选 **[!UICONTROL Outbound]** 项，然后启用选 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 项。
1. 使用下拉菜单选择此数 **[!UICONTROL Emails(SHA256, lowercased)]** 据源的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法进行哈希处理的数据。 Audience manager不会在此步骤中对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用算法进行哈希 [!DNL SHA256] 处理。 否则，您将无法将其用于 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 有关 [如何将离线数据导入Audience Manager（针对基于人员的目标）的常见问题解答](people-based-destinations-prerequisites.md#data-onboarding) ，请参阅数据入门。

观看以下视频，了解如何为创建数据源的视频教程 [!UICONTROL People-Based Destinations]。

[!VIDEO](https://video.tv.adobe.com/v/29006/?captions=chi_hans)

## 第2步——使用声明的ID通过实时HTTP调用将DPUUID与散列化的电子邮件地址匹配 {#match-email-addresses}

要使经过身份验证的用户有资格获得基于规则的特征，您需要通过声明的ID发送特 [征资格](../declared-ids.md)。

### 示例

假设您创建了以下两个数据源。

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 散列化的电子邮件地址 |

 

然后，您需要为表中的特征限定以下CRM ID。

| DPUUID(CRM ID) | 电子邮件地址 | 哈希电子邮件地址 | 特性 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

您声明的ID应遵循以下语法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上面的示例中，声明的ID调用应当如下：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 第3步——为分段创建配置文件合并规则 {#create-profile-merge-rule-segmentation}

下一步是创建新的合并规则，帮助您创建要发送到您的受众细分 [!DNL People-Based Destinations]。

>[!IMPORTANT]
>
>如果已经使用或选项定义了规 **[!UICONTROL Current Authenticated Profiles]** 则， **[!UICONTROL Last Authenticated Profiles]** 则可跳到第4步- [创建受众细分](#create-audience-segments)。

1. 登录您的Audience manager帐户并转 **[!UICONTROL Audience Data]** 到-&gt; **[!UICONTROL Profile Merge Rules]**。
2. 单击 **[!UICONTROL Add New Rule]**.
3. 输入配置文件合并规 **[!UICONTROL Name]** 则和 **[!UICONTROL Description]**。
4. 在部 **[!UICONTROL Profile Merge Rule Setup]** 分中，从列表 **[!UICONTROL Current Authenticated Profiles]** 中选 **[!UICONTROL Last Authenticated Profiles]** 择或规 **[!UICONTROL Cross-Device Options]** 则。
5. 在列 **[!UICONTROL Cross-Device Profile Options]** 表中，选择要运行分段的数据源。 这些应是包含现有DPUUID的数据源。
   ![合并规则设置](assets/pbd-pmr-combined.png)

## 第4步——创建受众细分 {#create-audience-segments}

要创建新区段，请使用区 [段生成器](../segments/segment-builder.md)。 如果您有要发送到的现有受众细分，请跳 [!DNL People-Based Destinations]到步骤5 [-配置基于人员的平台身份验证](#configure-authentication)。

## 第5步——配置基于人员的平台身份验证 {#configure-authentication}

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Administration]** 到&gt; **[!UICONTROL Integrated Accounts]**。 如果您之前已配置与社交平台的集成，则应在本页中列出该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置其集成的平台。
   ![基于人的平台](assets/pbd-add.png)
4. 单 **[!UICONTROL Confirm]** 击以重定向到所选平台的身份验证页面。
5. 通过社交平台帐户的身份验证后，您将被重定向到Audience Manager，您应在Audience manager中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!UICONTROL Confirm]**。
6. Audience manager在页面顶部显示通知，告诉您帐户是否已成功添加。 通知还允许您添加联系人电子邮件地址，以在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>Audience manager通过身份验证令牌处理与社交平台的集成，这些令牌在一定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 第6步——创建基于人员的目标 {#create-destination}

1. 登录到您的Audience Manager帐户，转到 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**，然后单击 **[!UICONTROL Create Destination]**。
1. 在部 **[!UICONTROL Basic Information]** 分中，输入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 作为新数据源，然后使用以下设置：
   * **[!UICONTROL Category]**:集成平台；
   * **[!UICONTROL Type]**:以人为本；
   * **[!UICONTROL Platform]**:选择要将受众细分发送到的基于人的平台；
   * **[!UICONTROL Account]**:选择与所选平台关联的所需广告商帐户。
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 选择要 **[!UICONTROL Data Export Labels]** 为此目标设置的目标。
1. 在部分 **[!UICONTROL Configuration]** 中，选择包含哈希数据源的数据源。
1. 在部 **[!UICONTROL Segment Mappings]** 分中，选择要发送到此目标的区段。 这将是您在步骤4 —— 创建受 [众区段时创建的区段](#create-audience-segments)。
1. 保存目标。
