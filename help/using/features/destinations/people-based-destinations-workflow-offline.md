---
description: '本页包含如何根据仅线下客户数据构建受众细分并将其发送到基于人员的目标的逐步指导。  '
seo-description: 'This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.  '
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: Workflow B - Personalization Based on Offline-Only Data
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Workflow B - Personalization Based on Offline-Only Data {#workflow-b}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

本页包含如何根据仅线下客户数据构建受众细分并将其发送到基于人员的目标的逐步指导。

## 第1步——板载脱机特征 {#step-1-onboard-traits}

在此方案中，创建受众细分的第一步是将线下客户数据导入Audience Manager。

>[!IMPORTANT]
>
> 在继续操作之前，请确保您即将加入的客户活动已在Audience manager中定义，并具有相应的已加入 [的特征](../traits/trait-qualification-reference.md)。

无论您现有的Audience Manager客户ID([DPUUID](../../reference/ids-in-aam.md))是否为哈希电子邮件，都必须对包含DPUUID的数据源执行特征 [登记](../../reference/ids-in-aam.md)。

### 示例

You want to qualify the customer IDs from the table below for the corresponding onboarded trait IDs. 让我们考虑一下，您 [的DPUUID](../../reference/ids-in-aam.md) （ID为999999）存储在一个数据源中，而您的Audience Manager合作伙伴ID为123。

| Customer ID (DPUUID) | 已载入的特征ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
To qualify the customer IDs in the example above for the corresponding onboarded traits, you must upload an [inbound data file](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) with the following contents:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

The file name would look like this: .
`ftp_dpm_999999_123_TIMESTAMP.sync.gz`See Amazon S3 Name and File Size Requirements for Inbound Data Files for detailed information on the file name structure.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

## Step 2 - Configure Data Source Settings {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**场景1:您的[DPUUID已是小写](../../reference/ids-in-aam.md)，具有哈希值的电子邮件地址。**

在这种情况下，您需要将相应的数据源标记为：

1. 转至 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**。
1. 查找包含DPUUID的数 [据源](../../reference/ids-in-aam.md)，然后单击它。
1. 确保未选中该 **[!UICONTROL Cannot be tied to personally identifiable information]** 选项。
1. 保存数据源设置。

 

**场景2:您的[DPUUID不是小写](../../reference/ids-in-aam.md)，具有哈希值的电子邮件地址。**

在这种情况下，您需要创建一个新的跨设备数据源，以存储散列化的电子邮件地址。 下面介绍如何实现此操作：

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Audience Data]** 到-&gt; **[!UICONTROL Data Sources]**&#x200B;并单击 **[!UICONTROL Add New]**。
1. 为新数 **[!UICONTROL Name]** 据源 **[!UICONTROL Description]** 输入和。
1. 在下 **[!UICONTROL ID Type]** 拉菜单中，选择 **[!UICONTROL Cross Device]**。
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. 使用下拉菜单选择此数 **[!UICONTROL Emails(SHA256, lowercased)]** 据源的标签。
   >[!IMPORTANT]
   >
   >此选项仅将数据源标记为包含使用该特定算法进行哈希处理的数据。 Audience manager不会在此步骤中对数据进行哈希处理。 确保您计划存储在此数据源中的电子邮件地址已使用算法进行哈希 [!DNL SHA256] 处理。 否则，您将无法将其用于 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

Watch the video below for a video tutorial of how to create a data source for .[!UICONTROL People-Based Destinations]

>[!VIDEO](https://video.tv.adobe.com/v/29006/?captions=chi_hans)

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-offline.md#configure-data-source-settings)如果您的现有 [DPUUID](../../reference/ids-in-aam.md) ，电子邮件地址已经过哈希处理，请跳到第 [4步——为分段创建配置文件合并规则](#create-profile-merge-rule)。

Let's say you want to match your existing DPUUIDs from the example at Step 1 to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 2 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](#configure-data-source-settings)

As a reminder, you would now have two data sources:

| 数据源ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 现有DPUUID(CRM ID) |
| 987654 | 散列化的电子邮件地址 |

| DPUUID(CRM ID) | 电子邮件地址 | 哈希电子邮件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我们的示例中，您的 [ID同步文件](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 将包含以下内容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

ID同 [步文件必须遵循](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 以下命名结构：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上面的示例中，文件名如下：
`c2c_id_999999_987654_1560431657.sync`

[在此处下载示例文件](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)。

创建ID同步文件后，您需要将其上传到存储段 [!DNL Amazon S3] 中。 要了解如何上传ID同步文件，请参阅 [将批量数据发送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 第4步——为分段创建配置文件合并规则 {#create-profile-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your .[!DNL People-Based Destinations]

1. 登录您的Audience manager帐户并转 **[!UICONTROL Audience Data]** 到-&gt; **[!UICONTROL Profile Merge Rules]**。
2. 单击 [!UICONTROL Add New Rule].
3. 输入配置文件合并规 **[!UICONTROL Name]** 则和 **[!UICONTROL Description]**。
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. In the  list, select the data source that your traits are onboarded against.**[!UICONTROL Cross-Device Profile Options]**
   ![合并规则设置](assets/pbd-pmr.png)

## 第5步——创建受众细分 {#create-audience-segments}

要根据仅脱机数据创建新区段，请使用 [Segment Builder](../segments/segment-builder.md) ，并确保在创建区段时使用在上一步中创建的新配置文件合并规则。

## 第6步——配置基于人员的平台身份验证 {#configure-authentication}

1. 登录到您的Audience manager帐户，然后转 **[!UICONTROL Administration]** 到&gt; **[!UICONTROL Integrated Accounts]**。 如果您之前已配置与社交平台的集成，则应在本页中列出该集成。 否则，页面为空。
   ![基于人的集成](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜单选择要配置其集成的平台。
   ![基于人的平台](assets/pbd-add.png)
1. 单 **[!UICONTROL Confirm]** 击以重定向到所选平台的身份验证页面。
1. 通过社交平台帐户的身份验证后，您将被重定向到Audience Manager，您应在Audience manager中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!UICONTROL Confirm]**。
1. Audience manager在页面顶部显示通知，告诉您帐户是否已成功添加。 The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>Audience manager通过身份验证令牌处理与社交平台的集成，这些令牌在一定时间后过期。 有关如何续订过期令牌的详细信息，请参阅身份验证令牌续订。

## Step 7 - Create a People-Based Destination {#create-destination}

1. 登录到您的Audience Manager帐户，转到 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**，然后单击 **[!UICONTROL Create Destination]**。
1. 在部 **[!UICONTROL Basic Information]** 分中，输入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 作为新数据源，然后使用以下设置：
   * **[!UICONTROL Category]**: Integrated Platforms;
   * **[!UICONTROL Type]**:以人为本；
   * **[!UICONTROL Platform]**:选择要将受众细分发送到的基于人的平台；
   * **[!UICONTROL Account]**: select the desired advertiser account associated with the selected platform.
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 选择要 **[!UICONTROL Data Export Labels]** 为此目标设置的目标。
1. 在部分 **[!UICONTROL Configuration]** 中，选择包含哈希数据源的数据源。
1. 在部 **[!UICONTROL Segment Mappings]** 分中，选择要发送到此目标的区段。 这将是您在步骤5 —— 创建受 [众区段时创建的区段](people-based-destinations-workflow-offline.md#create-audience-segments)。
1. 保存目标。
