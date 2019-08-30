---
description: '本页包含有关如何将离线CRM数据与实时行为数据相结合以供身份验证用户创建受众细分的分步指南，然后将这些受众细分发送到基于人员的目标。 '
seo-description: '本页包含有关如何将离线CRM数据与实时行为数据相结合以供身份验证用户创建受众细分的分步指南，然后将这些受众细分发送到基于人员的目标。  '
seo-title: 工作流程C-基于实名活动和离线数据的个性化
solution: Audience Manager
title: 工作流程C-基于实名活动和离线数据的个性化
translation-type: tm+mt
source-git-commit: d0e343e3fbaf527e9b630dc2dbc851d8f8f4c0b2

---


# 工作流程C-基于实名活动和离线数据的个性化 {#workflow-c}

本页包含有关如何将离线 [!DNL CRM] 数据与实时行为数据相结合以供身份验证用户创建受众细分的分步指南，然后将这些受众细分发送到这些受众细分 [!DNL People-Based Destinations]。

## 步骤-配置数据源设置 {#configure-data-source-settings}

根据 [您的dpuUID](../../reference/ids-in-aam.md) 是否为小写电子邮件地址，您可能需要配置将存储散列电子邮件地址的数据源。

 

**场景1：您[的DpuUID](../../reference/ids-in-aam.md)已经是小写的电子邮件地址。**

在这种情况下，请跳到 [步骤5-配置基于人物的平台身份验证](#configure-authentication)。

 

**场景2：您[的DPuID](../../reference/ids-in-aam.md)不是小写的电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源，它将存储您的散列电子邮件地址。下面是如何执行此操作的方法：

1. 登录Audience Manager帐户并转到 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**，然后单击 **[!UICONTROL Add New]**。
1. 输入和 **[!UICONTROL Name]****[!UICONTROL Description]** 用于新数据源。
1. 在 **[!UICONTROL ID Type]** 下拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. **[!UICONTROL Data Source Settings]** 在部分中，选择和 **[!UICONTROL Inbound]****[!UICONTROL Outbound]** 选项，并启用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 选项。
1. 使用下拉菜单选择此数据源 **[!UICONTROL Emails(SHA256, lowercased)]** 的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标签为包含特定算法散列的数据。Audience Manager不会在此步骤中散列数据。确保您计划在此数据源中存储的电子邮件地址已用 [!DNL SHA256] 算法散列。否则 [!DNL People-Based Destinations]，您将无法使用它。

   ![pdd-数据源设置](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 有关如何将离线数据引入Audience Manager for People Manager的常见问题，请参阅 [数据入门培训](people-based-destinations-prerequisites.md#data-onboarding) 。

## 步骤-使用声明ID将DPuUID与通过实时HTTP调用哈希化的电子邮件地址相匹配 {#match-email-addresses}

要符合基于规则的特征的身份验证用户，您需要通过 [声明的ID](../declared-ids.md)发送特征资格资格。

### 示例

假设您已经创建了以下两个数据源。

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有的DPuUID(CRM ID) |
| 987654 | 散列电子邮件地址 |

 

然后，您要符合以下表格中特征的CRM ID。

| DPUUID(CRM ID) | 电子邮件地址 | 散列电子邮件地址 | 特性 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location= US |

 

您声明的ID应遵循以下语法：

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

 

在上面的示例中，声明的ID调用应当如下：

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## 步骤-为分段创建配置文件合并规则 {#create-profile-merge-rule-segmentation}

下一步是创建新的合并规则，它将帮助您创建受众细分，以发送 [!DNL People-Based Destinations]给您的受众。

>[!IMPORTANT]
>
>如果您已经使用 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]** 选项定义了规则，则可以跳到 [第步-创建受众区段](#create-audience-segments)。

1. 登录Audience Manager帐户并转到 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**。
2. 单击 **[!UICONTROL Add New Rule]**.
3. 输入配置文件合并规则 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**。
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 部分中，从列表中选择 **[!UICONTROL All Cross-Device Profiles]** 规则 **[!UICONTROL Cross-Device Options]** 。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 列表中，选择要在其上运行分段的数据源。这些数据源应该是包含您现有的DPUUID的数据源。
   ![合并规则设置](assets/pbd-pmr-combined.png)

## 步骤-创建受众细分 {#create-audience-segments}

要创建新区段，请使用 [区段生成器](../segments/segment-builder.md)。如果您有要发送到 [!DNL People-Based Destinations]的现有受众细分，请跳到 [步骤5-配置基于人物的平台身份验证](#configure-authentication)。

## 步骤-配置基于人物的平台身份验证 {#configure-authentication}

1. 登录Audience Manager帐户，然后转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。如果您先前已配置与社交平台的集成，则应当在此页面中列出它。否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
4. 单击 **[!UICONTROL Confirm]** 以重定向到所选平台的身份验证页面。
5. 在对社交平台帐户进行身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!UICONTROL Confirm]**&#x200B;的广告商帐户。
6. Audience Manager会在页面顶部显示通知，以便您了解是否成功添加了帐户。此通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>用户经理通过在特定时间段后过期的身份验证令牌处理与社交平台的集成。有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 步骤-创建基于人物的目标 {#create-destination}

1. 登录Audience Manager帐户，转至 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**&#x200B;并单击 **[!UICONTROL Create Destination]**。
1. **[!UICONTROL Basic Information]** 在部分中，输入一个 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新的数据源，然后使用以下设置：
   * **[!UICONTROL Category]**：集成平台；
   * **[!UICONTROL Type]**：基于人员；
   * **[!UICONTROL Platform]**：选择要将受众细分发送到的基于人员的平台；
   * **[!UICONTROL Account]**：选择与选定平台关联的所需广告商帐户。
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 选择要 **[!UICONTROL Data Export Labels]** 为此目标设置的内容。
1. **[!UICONTROL Configuration]** 在部分中，选择包含散列数据源的数据源。
1. 在 **[!UICONTROL Segment Mappings]** 部分中，选择要发送到此目标的区段。这将是您在 [第步-创建受众区段](#create-audience-segments)创建的区段。
1. 保存目标。
