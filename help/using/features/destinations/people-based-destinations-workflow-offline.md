---
description: 本页包含有关如何从仅离线客户数据构建受众区段并将它们发送到基于人员的目标的分步指南。
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: 工作流程B — 基于仅离线数据的Personalization
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---

# 工作流程B — 基于仅离线数据的Personalization {#workflow-b}

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含有关如何从仅离线客户数据构建受众区段并将它们发送到基于人员的目标的分步指南。

## 步骤1 — 载入离线特征 {#step-1-onboard-traits}

在此场景中创建受众区段的第一步是将离线客户数据导入Audience Manager。

>[!IMPORTANT]
>
> 在继续之前，请确保已在Audience Manager中定义了您即将载入的客户活动以及相应的[已载入的特征](../traits/trait-and-segment-qualification-reference.md)。

无论您现有的Audience Manager客户ID ([DPUUID](../../reference/ids-in-aam.md))是否为哈希电子邮件，您都必须对包含[DPUUID](../../reference/ids-in-aam.md)的数据源执行特征载入。

### 示例

您希望下表中的客户ID符合相应的已载入特征ID。 假定您的[DPUUID](../../reference/ids-in-aam.md)存储在ID为999999的数据源中，并且您的Audience Manager数据源ID为123。

| 客户ID (DPUUID) | 已载入的特征ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345， 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223， 93342， 27341 |

<br />

要使上述示例中的客户ID符合相应的已载入特征，必须上传包含以下内容的[入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)：

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

文件名应如下所示： `ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
有关文件名结构的详细信息，请参阅入站数据文件的[Amazon S3名称和文件大小要求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

## 步骤2 — 配置数据Source设置 {#configure-data-source-settings}

根据您的[DPUUID](../../reference/ids-in-aam.md)是否为小写、经过哈希处理的电子邮件地址，您可能需要配置用于存储经过哈希处理的电子邮件地址的数据源。

 

**方案1：您的[DPUUID](../../reference/ids-in-aam.md)已经是小写、经过哈希处理的电子邮件地址。**

在这种情况下，您需要将相应的数据源标记为如下：

1. 转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 查找包含您的[DPUUID](../../reference/ids-in-aam.md)的数据源，然后单击该数据源。
1. 确保取消选中选项&#x200B;**[!UICONTROL Cannot be tied to personally identifiable information]**。
1. 保存数据源设置。

 

**方案2：您的[DPUUID](../../reference/ids-in-aam.md)不是小写、经过哈希处理的电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源，用于存储经过哈希处理的电子邮件地址。 以下是操作方法：

1. 登录到您的Audience Manager帐户并转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然后单击&#x200B;**[!UICONTROL Add New]**。
1. 输入新数据源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分中，选择&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;选项，并启用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;选项。
1. 使用下拉菜单为此数据源选择&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;标签。

   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法经过哈希处理的数据。 Audience Manager不会在此步骤中对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用[!DNL SHA256]算法进行哈希处理。 否则，您将无法将其用于[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 有关如何将离线数据导入Audience Manager以实现基于人员的目标的常见问题解答，请参阅[数据载入](people-based-destinations-prerequisites.md#data-onboarding)。

观看以下视频，观看有关如何为[!UICONTROL People-Based Destinations]创建数据源的视频教程。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步骤3 — 通过基于文件的ID同步将DPUUID与经过哈希处理的电子邮件地址进行匹配 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步骤仅适用于上述的[方案2](people-based-destinations-workflow-offline.md#configure-data-source-settings)。 如果您现有的[DPUUID](../../reference/ids-in-aam.md)已经过哈希处理，请跳到[步骤4 — 为分段创建配置文件合并规则](#create-profile-merge-rule)。

假设您要将步骤1示例中的现有[DPUUID](../../reference/ids-in-aam.md)与下表（右列）中的经过哈希处理的电子邮件地址相匹配，并将经过哈希处理的电子邮件地址存储在您于[步骤2 — 配置数据Source设置](#configure-data-source-settings)创建的新数据源中。

提醒一下，您现在拥有两个数据源：

| 数据源Id | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID (CRM ID) |
| 987654 | 经过哈希处理的电子邮件地址 |

| DPUUID (CRM ID) | 电子邮件地址 | 经过哈希处理的电子邮件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我们的示例中，您的[ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)将包含以下内容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)必须遵循此命名结构：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上述示例中，文件名将如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在此下载示例文件](assets/c2c_id_999999_987654_1560431657.sync)。

创建ID同步文件后，您需要将其上传到[!DNL Amazon S3]存储段。 要了解如何上传ID同步文件，请参阅[将批次数据发送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 第4步 — 创建用于区段的配置文件合并规则 {#create-profile-merge-rule}

下一步是创建新合并规则，以帮助您创建要发送到[!DNL People-Based Destinations]的受众区段。

1. 登录到您的Audience Manager帐户并转到&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 单击 [!UICONTROL Add New Rule]。
3. 输入配置文件合并规则&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分中，从&#x200B;**[!UICONTROL All Cross-Device Profiles]**&#x200B;列表中选择&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;规则。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**&#x200B;列表中，选择特征载入的数据源。
   ![合并规则设置](assets/pbd-pmr.png)

## 步骤5 — 创建受众区段 {#create-audience-segments}

若要从仅离线数据创建新区段，请使用[区段生成器](../segments/segment-builder.md)，并确保在创建区段时使用上一步中创建的新配置文件合并规则。

## 步骤6 — 配置基于人员的平台身份验证 {#configure-authentication}

1. 登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，您应会看到此页面中列出了该集成。 否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**。
1. 使用&#x200B;**[!UICONTROL People-Based Platform]**&#x200B;下拉菜单选择要配置集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
1. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;以重定向到所选平台的身份验证页面。
1. 在验证您的Social Platform帐户后，您将被重定向到Audience Manager，您应该会在其中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。
1. Audience Manager会在页面顶部显示通知，让您知道帐户是否已成功添加。 通知还允许您添加联系人电子邮件地址，以在Social平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>Audience Manager通过在一段时间后过期的身份验证令牌处理与社交平台的集成。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## 步骤7 — 创建基于人员的目标 {#create-destination}

1. 登录到您的Audience Manager帐户，转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然后单击&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;部分中，输入新数据源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，并使用以下设置：
   * **[!UICONTROL Category]**：集成平台；
   * **[!UICONTROL Type]**：基于人员；
   * **[!UICONTROL Platform]**：选择要将受众区段发送到的基于人员的平台；
   * **[!UICONTROL Account]**：选择与所选平台关联的所需广告商帐户。
     ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**。
1. 选择要为此目标设置的&#x200B;**[!UICONTROL Data Export Labels]**。
1. 在&#x200B;**[!UICONTROL Configuration]**&#x200B;部分中，选择包含哈希数据源的数据源。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;部分中，选择要发送到此目标的区段。 这就是您在[第5步 — 创建受众区段](people-based-destinations-workflow-offline.md#create-audience-segments)中创建的区段。
1. 保存目标。
