---
description: '本页包含有关如何从仅离线客户数据构建受众区段，并将其发送到基于人员的目标的分步指南。  '
seo-description: '本页包含有关如何从仅离线客户数据构建受众区段，并将其发送到基于人员的目标的分步指南。  '
seo-title: 工作流程 B - 基于仅离线数据进行个性化
solution: Audience Manager
title: 工作流程 B - 基于仅离线数据进行个性化
feature: 基于人员的目标
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 6%

---

# 工作流程 B - 基于仅离线数据进行个性化 {#workflow-b}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何从仅离线客户数据构建受众区段，并将其发送到基于人员的目标的分步指南。

## 步骤1 — 载入离线特征{#step-1-onboard-traits}

在此方案中，创建受众区段的第一步是将离线客户数据引入Audience Manager。

>[!IMPORTANT]
>
> 在继续操作之前，请确保已在Audience Manager中定义要载入的客户活动，且其中具有相应的[已载入特征](../traits/trait-and-segment-qualification-reference.md)。

无论您现有的Audience Manager客户ID([DPUUIDs](../../reference/ids-in-aam.md))是否是经过哈希处理的电子邮件，您都必须对包含[DPUUIDs](../../reference/ids-in-aam.md)的数据源执行特征载入。

### 示例

您需要从下表中为相应的已载入特征ID确定客户ID的资格。 假设您的[DPUUIDs](../../reference/ids-in-aam.md)存储在ID为999999的数据源中，并且您的Audience Manager数据源ID为123。

| 客户ID(DPUUID) | 已载入的特征ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345,23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

要将上述示例中的客户ID限定为对应的已载入特征，您必须上传包含以下内容的[入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md):

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

文件名将如下所示：`ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
有关文件名结构的详细信息，请参阅[Amazon S3入站数据文件的名称和文件大小要求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

## 步骤2 — 配置数据源设置{#configure-data-source-settings}

根据[DPUUIDs](../../reference/ids-in-aam.md)是否为小写且经过哈希处理的电子邮件地址，您可能需要配置将存储经过哈希处理的电子邮件地址的数据源。

 

**场景1:您的 [](../../reference/ids-in-aam.md) DPUUID已经小写，经过哈希处理的电子邮件地址。**

在这种情况下，您需要为相应的数据源添加如下标签：

1. 转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 找到包含[DPUUIDs](../../reference/ids-in-aam.md)的数据源，然后单击该数据源。
1. 确保未选中选项&#x200B;**[!UICONTROL Cannot be tied to personally identifiable information]**。
1. 保存数据源设置。

 

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

## 步骤3 — 通过基于文件的ID同步将DPUUID与经过哈希处理的电子邮件地址进行匹配{#match-ids-emails}

>[!IMPORTANT]
>
> 此步骤仅适用于上述[场景2](people-based-destinations-workflow-offline.md#configure-data-source-settings)。 如果您现有的[DPUUIDs](../../reference/ids-in-aam.md)已经对电子邮件地址进行了哈希处理，请跳转到[步骤4 — 为分段创建配置文件合并规则](#create-profile-merge-rule)。

假设您希望将现有[DPUUID](../../reference/ids-in-aam.md)从步骤1中的示例与下表（右列）中经过哈希处理的电子邮件地址进行匹配，并将经过哈希处理的电子邮件地址存储在您在[步骤2 — 配置数据源设置](#configure-data-source-settings)创建的新数据源中。

请提醒您，现在有两个数据源：

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 经过哈希处理的电子邮件地址 |

| DPUUID(CRM ID) | 电子邮件地址 | 经过哈希处理的电子邮件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在本例中，您的[ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)将包含以下内容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)必须遵循以下命名结构：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在以上示例中，文件名如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在此处下载示例文件](assets/c2c_id_999999_987654_1560431657.sync)。

创建ID同步文件后，您需要将其上传到[!DNL Amazon S3]存储段。 要了解如何上传ID同步文件，请参阅[将批量数据发送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 第4步 — 为分段创建配置文件合并规则{#create-profile-merge-rule}

下一步是创建新的合并规则，以帮助您创建要发送到[!DNL People-Based Destinations]的受众区段。

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 单击 [!UICONTROL Add New Rule].
3. 输入配置文件合并规则&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分中，从&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;列表中选择&#x200B;**[!UICONTROL All Cross-Device Profiles]**&#x200B;规则。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**列表中，选择要载入特征的数据源。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 步骤5 — 创建受众区段{#create-audience-segments}

要从仅离线数据创建新区段，请使用[区段生成器](../segments/segment-builder.md)，并确保使用在创建区段时在上一步中创建的新配置文件合并规则。

## 步骤6 — 配置基于人员的平台身份验证{#configure-authentication}

1. 登录您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，则应会在此页面中列出该集成。 否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉菜单选择要配置与的集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
1. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;可重定向到所选平台的身份验证页面。
1. 在您的社交平台帐户上进行了身份验证后，系统会将您重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
1. Audience Manager在页面顶部显示通知，告知您帐户是否已成功添加。 此通知还允许您添加联系人电子邮件地址，以在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>Audience Manager通过身份验证令牌处理与社交平台的集成，该令牌会在特定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 步骤7 — 创建基于人员的目标{#create-destination}

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
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;部分中，选择要发送到此目标的区段。 这将是您在[步骤5 — 创建受众区段](people-based-destinations-workflow-offline.md#create-audience-segments)中创建的区段。
1. 保存目标。
