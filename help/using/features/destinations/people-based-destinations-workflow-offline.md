---
description: '本页包含关于如何从仅离线客户数据构建受众细分的循序渐进式指导，并将其发送到基于人员的目标。  '
seo-description: '本页包含关于如何从仅离线客户数据构建受众细分的循序渐进式指导，并将其发送到基于人员的目标。  '
seo-title: 工作流B-基于离线数据的个性化
solution: Audience Manager
title: 工作流B-基于离线数据的个性化
translation-type: tm+mt
source-git-commit: fdb17c46dd66794cfb744b77e8e5c8be9fd65dd5

---


# 工作流B-基于离线数据的个性化 {#workflow-b}

本页包含关于如何从仅离线客户数据构建受众细分的循序渐进式指导，并将其发送到基于人员的目标。

## 步骤-载入脱机特征 {#step-1-onboard-traits}

在此情景中创建受众细分的第一步是将线下客户数据引入Audience Manager。

>[!IMPORTANT]
>
> 继续之前，请确保在Audience Manager中定义的客户活动已在Audience Manager中定义，具有相应的已 [载入特征](../traits/trait-qualification-reference.md)。

无论您现有的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))是否为哈希电子邮件，您都必须根据包含 [您的DPUUID](../../reference/ids-in-aam.md)的数据源执行特征适职。

### 示例

您希望从下表中获得相应的内置特征ID的客户ID。我们考虑将您 [的DPuID](../../reference/ids-in-aam.md) 存储在ID999999的数据源中，Audience Manager合作伙伴ID为123。

| 客户ID(DPUUID) | 载入的特征ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

要在上面的示例中确定相应的已载入特征的客户ID，您必须上传 [包含以下内容的入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ：

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

文件名如下所示： `ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
有关文件名称结构的详细信息，请参阅 [Amazon S名称和入站数据文件](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 的文件大小要求。

## 步骤-配置数据源设置 {#configure-data-source-settings}

根据 [您的dpuUID](../../reference/ids-in-aam.md) 是否为小写电子邮件地址，您可能需要配置将存储散列电子邮件地址的数据源。

**场景1：您[的DpuUID](../../reference/ids-in-aam.md)已经是小写的电子邮件地址。**

在这种情况下，您需要为相应的数据源添加标签：

1. 转到 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**。
1. 找到包含您 [的DpuUID](../../reference/ids-in-aam.md)的数据源，然后单击它。
1. 确保取消 **[!UICONTROL Cannot be tied to personally identifiable information]** 选中此选项。
1. 保存数据源设置。

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

## 步骤-将DPuID与通过基于文件的ID同步的散列电子邮件地址相匹配 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步骤仅适用于上述 [描述的](people-based-destinations-workflow-offline.md#configure-data-source-settings) Scene2。如果现有 [的DPuID](../../reference/ids-in-aam.md) 已散列化电子邮件地址，请跳到 [第步-创建配置文件合并规则以进行分段](#create-profile-merge-rule)。

假设您希望将您的现有 [DPuUID](../../reference/ids-in-aam.md) 从步骤中的示例与下表中哈希化的电子邮件地址相匹配，并将哈希电子邮件地址存储在您在 [第步创建的新数据源中-配置数据源设置](#configure-data-source-settings)。

作为提醒，您现在有两个数据源：

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有的DPuUID(CRM ID) |
| 987654 | 散列电子邮件地址 |

| dpuUID(CRM ID) | 电子邮件地址 | 散列电子邮件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

<br/>

[您的ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 将具有以下内容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

<br/>

[ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 必须遵循以下命名结构：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

<br/>

在上面的示例中，文件名将如下所示： `c2c_id_999999_987654_1560431657.sync`

[在此处下载示例文件](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)。

## 步骤-为分段创建配置文件合并规则 {#create-profile-merge-rule}

下一步是创建新的合并规则，它将帮助您创建受众细分，以发送 [!DNL People-Based Destinations]给您的受众。

1. 登录Audience Manager帐户并转到 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**。
2. 单击 [!UICONTROL Add New Rule].
3. 输入配置文件合并规则 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**。
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 部分中，从列表中选择 **[!UICONTROL All Cross-Device Profiles]** 规则 **[!UICONTROL Cross-Device Options]** 。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 列表中，选择您的特征被载入的数据源。
   ![合并规则设置](assets/pbd-pmr.png)

## 步骤-创建受众细分 {#create-audience-segments}

要从仅脱机数据创建新区段，请使用 [区段生成器](../segments/segment-builder.md) 并确保您使用在创建区段时在上一步中创建的新配置文件合并规则。

## 步骤-配置基于人物的平台身份验证 {#configure-authentication}

1. 登录Audience Manager帐户，然后转到 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。如果您先前已配置与社交平台的集成，则应当在此页面中列出它。否则，页面为空。
   ![基于人员的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置集成的平台。
   ![基于人员的平台](assets/pbd-add.png)
1. 单击 **[!UICONTROL Confirm]** 以重定向到所选平台的身份验证页面。
1. 在对社交平台帐户进行身份验证后，您将重定向到Audience Manager，此时您应该可以看到您的关联广告商帐户。选择要使用并单击 **[!UICONTROL Confirm]**&#x200B;的广告商帐户。
1. Audience Manager会在页面顶部显示通知，以便您了解是否成功添加了帐户。此通知还允许您添加联系人电子邮件地址，以便在社交平台身份验证即将过期时接收通知。

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
1. 在 **[!UICONTROL Segment Mappings]** 部分中，选择要发送到此目标的区段。这将是您在 [第步-创建受众区段](people-based-destinations-workflow-offline.md#create-audience-segments)创建的区段。
1. 保存目标。
