---
description: '本页包含有关如何将离线CRM数据与Audience Manager中已有的行为数据相结合以创建新受众区段的分步指导，然后将这些受众区段发送到基于人员的目标。  '
seo-description: '本页包含有关如何将离线CRM数据与Audience Manager中已有的行为数据相结合以创建新受众区段的分步指导，然后将这些受众区段发送到基于人员的目标。   '
seo-title: 工作流程 A - 基于所有在线活动和离线数据的组合进行个性化
solution: Audience Manager
title: 工作流程 A - 基于所有在线活动和离线数据的组合进行个性化
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---


# 工作流程 A - 基于所有在线活动和离线数据的组合进行个性化 {#workflow-a}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含如何将离线数据与Audience Manager中已有的行为数 [!DNL CRM] 据相结合以创建新的受众区段，然后将这些受众区段发送到的分步指导 [!DNL People-Based Destinations]。

## 第1步——配置数据源设置 {#configure-data-source-settings}

根据您的DPUUID [是小写](../../reference/ids-in-aam.md) 、散列电子邮件地址，您可能需要配置用于存储散列电子邮件地址的数据源。

 

**方案1: 您[的DPUUID](../../reference/ids-in-aam.md)已是小写的散列电子邮件地址。**

在这种情况下，您需要将相应的数据源标记为：

1. 转到 [!UICONTROL Audience Data] -> [!UICONTROL Data Sources]。
1. 找到包含DPUUID的数 [据源](../../reference/ids-in-aam.md)，然后单击它。
1. 在下 **[!UICONTROL ID Type]** 拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. 确保选项未 [!UICONTROL Cannot be tied to personally identifiable information] 选中。
1. 在部 **[!UICONTROL Data Source Settings]** 分中，选择和 **[!UICONTROL Inbound]** 选 **[!UICONTROL Outbound]** 项，然后启用选 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 项。
1. 使用下拉菜单选择此 **[!UICONTROL Emails(SHA256, lowercased)]** 数据源的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法散列的数据。 Audience Manager在此步骤中不对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用算法散列 [!DNL SHA256] 处理。 否则，您将无法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 保存数据源设置。

 

**方案2: 您[的DPUUID](../../reference/ids-in-aam.md)不是小写的散列电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源来存储散列电子邮件地址。 下面介绍如何实现此操作：

1. 登录您的Audience Manager帐户，转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**&#x200B;并单击 **[!UICONTROL Add New]**。
1. 为新 [!UICONTROL Name] 数 [!UICONTROL Description] 据源输入和。
1. 在下 **[!UICONTROL ID Type]** 拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. 在部 **[!UICONTROL Data Source Settings]** 分中，选择和 **[!UICONTROL Inbound]** 选 **[!UICONTROL Outbound]** 项，然后启用选 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 项。
1. 使用下拉菜单选择此 **[!UICONTROL Emails(SHA256, lowercased)]** 数据源的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法散列的数据。 Audience Manager在此步骤中不对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用算法进行散列 [!DNL SHA256] 处理。 否则，您将无法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 保存数据源设置。

观看以下视频，观看有关如何为其创建数据源的视频教程 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> 有关 [如何将线下数据引入基于](people-based-destinations-prerequisites.md#data-onboarding) 人的目标Audience Manager的常见问题，请参阅数据入门。

## 第2步——通过基于文件的ID同步将DPUUID与散列电子邮件地址匹配 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步骤仅适用于上 [述方案](people-based-destinations-workflow-combined.md#configure-data-source-settings) 2。 如果您的现 [有DPUUID](../../reference/ids-in-aam.md) 已经有散列电子邮件地址 [，请跳到步骤3 -](people-based-destinations-workflow-combined.md#create-merge-rule)为分段创建用户档案合并规则。

假设您要将现有DPUUID与下表(右 [列](../../reference/ids-in-aam.md) )中的散列电子邮件地址匹配，并将散列电子邮件地址存储在您在步骤1 —— 配置数据源设置中创建的 [新数据源中](people-based-destinations-workflow-combined.md#configure-data-source-settings)。

| DPUUID(CRM ID) | 电子邮件地址 | 哈希电子邮件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

最多可以将10个哈希电子邮件地址链接到一个 [DPUUID](../../reference/ids-in-aam.md)。 为此，请在同步文件中用逗号分隔散列电子邮件地址。

在我们的示例中，您现在有两个数据源。

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 哈希电子邮件地址 |

 

您的 [ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 将包含以下内容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

ID同 [步文件必须](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 遵循以下命名结构：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上面的示例中，文件名如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在此处下载示例文件](assets/c2c_id_999999_987654_1560431657.sync)。

创建ID同步文件后，您需要将其上传到存储桶 [!DNL Amazon S3] 中。 要了解如何上传ID同步文件，请参阅 [将批量数据发送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 第3步——为分段创建用户档案合并规则 {#create-merge-rule}

下一步是创建新的合并规则，该规则将帮助您创建要发送到基于人员的目标的受众段。

>[!IMPORTANT]
>
> 如果您已经使用或选项定义了 [!UICONTROL Current Authenticated Profiles] 规则， [!UICONTROL Last Authenticated Profiles] 则可跳到步骤4 - [创建受众段](people-based-destinations-workflow-combined.md#create-audience-segments)。

1. 登录您的Audience Manager帐户并转 **[!UICONTROL Audience Data]** 到> **[!UICONTROL Profile Merge Rules]**。
1. 单击 **[!UICONTROL Add New Rule]**.
1. 输入用户档案合并规 **[!UICONTROL Name]** 则和 **[!UICONTROL Description]**。
1. 在部 **[!UICONTROL Profile Merge Rule Setup]** 分中，选择 **[!UICONTROL Current Authenticated Profiles]** 或选 **[!UICONTROL Last Authenticated Profiles]** 项。
1. 在列表 **[!UICONTROL Cross-Device Profile Options]** 中，选择要运行分段的数据源。 这些数据源应包含现有 [DPUUID](../../reference/ids-in-aam.md)。

## 第4步——创建受众段 {#create-audience-segments}

要创建新的受众区段，请使用 [区段生成器](../segments/segment-builder.md)。 如果您有要发送到的现有受众段， [!DNL People-Based Destinations]请跳 [到步骤5 —— 配置基于人员的平台身份验证](people-based-destinations-workflow-combined.md#configure-authentication)。

## 第5步——配置基于人的平台身份验证 {#configure-authentication}

1. 登录您的Audience Manager帐户并转 **[!UICONTROL Administration]** 到> **[!UICONTROL Integrated Accounts]**。 如果您之前配置了与社交平台的集成，您应会在本页中看到该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置与集成的平台。
   ![基于人的平台](assets/pbd-add.png)
1. 单 **[!UICONTROL Confirm]** 击可重定向到所选平台的身份验证页面。
1. 通过社交平台帐户身份验证后，您将被重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户并单击 **[!UICONTROL Confirm]**。
1. Audience Manager在页面顶部显示通知，告诉您帐户是否成功添加。 通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时接收通知。

>[!IMPORTANT]
>
>受众管理者通过身份验证令牌处理与社交平台的集成，该令牌在一定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

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
1. 在部 **[!UICONTROL Segment Mappings]** 分中，选择要发送到此目标的区段。 这将是您在第4步——创建 [受众区段时创建的区段](people-based-destinations-workflow-combined.md#create-audience-segments)。
1. 保存目标。
