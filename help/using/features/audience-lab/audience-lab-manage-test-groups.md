---
description: 此过程指导您完成在Audience Lab中创建、编辑或删除测试组所需的步骤
seo-description: 此过程指导您完成在Audience Lab中创建、编辑或删除测试组所需的步骤
seo-title: 管理测试组
solution: Audience Manager
title: 管理测试组
uuid: fadddeb-7574-4853-8c52-c5845682 c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[不支持](../../features/traits/about-folder-traits.md)**** 文件夹特征 [!UICONTROL Audience Lab]。Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. 此权限允许用户创建和查看测试结果。A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. 用户只能查看他们也有权访问的目标。So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * 访问了解相关转化特征；
   * 访问对测试的相关区段进行读取和映射；
   * 访问相关目标。

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * 您可以将测试组另存为草稿，稍后继续处理它。
   * 如果您选择的基本区段已经在其他测试组中使用，则会显示警报。使用基本区段两次可能会扭曲两次测试的转换结果。

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * 您可以通过单击来编辑测试区段的名称。
   * 在分配新的测试区段时，百分比会自动自动细分为100%。然后，您可以手动编辑百分比。编辑百分比后单击复选框，确保它们最多可添加100%，否则您将无法继续执行下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要设置要用作控制组的区段的特定部分，请选择控制区段。控制组允许您查看与基准相比创建的测试区段的影响。
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you're done.

1. **[!UICONTROL Select Conversion Traits]**

   * 通过在转化特征窗口中键入内容来添加转换特性。This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * 您可以根据需要添加最多个转换特征。
   * 如果您选择了用于其他测试组的转化特征，则会显示警报。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索字段中键入所需的目标，或使用下拉箭头。[!UICONTROL Audience Lab] 可将测试区段发送到URL、cookie或服务器到服务器目标。
   * 将区段拖放到目标。
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * 您可以向多个目标发送相同的测试区段，并且可以将多个测试区段添加到单个目标。
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * 最后，您必须为测试组选择一个开始日期。此日期标志着测试组将发布到目标的开始时间。Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 具有身份验证的配置文件仅在实时目标中受支持。如果具有该配置的配置文件合并规则的测试区段被发送到基于文件的服务器到服务器目标，则受众可能无法填充。

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * 请记住，一旦对测试组进行了优化，该组便会重复或删除，但不会进行编辑。
   >[!NOTE]
   >* 您可以在创建过程中的任意点保存测试组，并在以后返回向导。The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. [!UICONTROL Create Segment Test Group] 在向导中，您可以将测试组另存为草稿，稍后继续处理它。

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. 查找要删除的测试组。您可以:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
