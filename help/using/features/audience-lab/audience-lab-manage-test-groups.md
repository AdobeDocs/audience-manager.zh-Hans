---
description: 此过程会指导您完成在Audience lab中创建、编辑或删除测试组所需的步骤
seo-description: 此过程会指导您完成在Audience lab中创建、编辑或删除测试组所需的步骤
seo-title: 管理测试组
solution: Audience Manager
title: 管理测试组
uuid: 2faddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 管理测试组 {#manage-test-groups}

此过程将指导您完成在中创建、编辑或删除测试组所需的步骤 [!UICONTROL Audience Lab]。

## 创建区段测试组 {#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* 您至少需要设置一 **个转换特** 征。 通过选择转换作为事件类型 [，可以在](../../features/traits/create-onboarded-rule-based-traits.md)Trait Builder中设置 **转换特征** 。 有关转换特征以及如何设置这些特征的更多信息，我们为您准备了 [视频](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 。

   >[!IMPORTANT]
   >
   >[不支持](../../features/traits/about-folder-traits.md)**文件夹特征** 。 [!UICONTROL Audience Lab]将文件 [夹特征的“事件类型](../../features/traits/create-onboarded-rule-based-traits.md) ”设置为“转 **换”** ，将不会为该特定文件夹特征 [!UICONTROL Audience Lab] 生成任何数据。

* 对于使用基于角 [色的访问控制的公司](../../features/administration/administration-overview.md):指定通配 [!UICONTROL Audience Lab] 符权限 [，以](../../features/administration/administration-overview.md#wild-card-permissions)**[!UICONTROL User Groups]** 提供访问权限。 此权限允许用户创建和查看测试结果。 用户只能使用其具有读取权限的数据源中的区 **段** , **并映射到目标** 权限。 用户只能使用其具有“读取”权限的数据源的转 **换特征** 。 用户也只能查看他们有权访问的目标。 因此，在将通配符权 [!DNL Audience Lab] 限添加到组之前，请确保该组具有：
   * 获取相关转化特征；
   * 访问读取并映射相关测试细分；
   * 访问相关目标。

要创建新内容，请执行以下操 [!UICONTROL Segment Test Group]作：

1. 在功 **[!UICONTROL Create New Test Group]** 能板中 [!UICONTROL Audience Lab] 选择以启动向导。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填写 **[!UICONTROL Test Group Name]** 和a **[!UICONTROL Description]**。
   * 在文件浏 **[!UICONTROL Base Segment]** 览器中导航或在搜索栏中键入内容，然后按下确认，即可选择 **[!UICONTROL Choose Segment.]**
   * 您可以将测试组另存为草稿，稍后继续处理它。
   * 如果您选择的基本区段已用于其他测试组，则会显示警报。 两次使用基本段可能会扭曲两个测试的转换结果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以创 **建多达15个测试区段** ，并根据需要划分设备百分比。
   * 您可以通过单击测试区段来编辑这些区段的名称。
   * 分配新测试区段时，百分比会自动平均分配为100%。 然后，您可以手动编辑百分比。 编辑百分比后，单击该复选框，并确保百分比加起来最多为100%，否则您将无法继续执行下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要将区段的特定部分预留出来用作控制组，请选择一个控制段。 控制组允许您查看您创建的测试区段与基准测试的影响。
   * 您可以在下拉列表中选择一个测试段作为控制段，也可以选择 **[!UICONTROL None]** 不控制。
   * 完 **[!UICONTROL Next]** 成后单击。

1. **[!UICONTROL Select Conversion Traits]**

   * 通过在转换特征窗口中键入来添加转换特征。 这是必需 **步骤** ，除非您添加至少一个转换特征，否则您无法继续执行下一步。
   * 如果需要，最多可以添加5个转换特征。
   * 当您选择已用于其他测试组的转换特征时，将显示警报。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索字段中键入所需目标或使用下拉箭头。 [!UICONTROL Audience Lab] 测试区段可以发送到URL、cookie或服务器到服务器目标。
   * 将区段拖放到目标。
   * 在将区段放到目标位置后，在盲 **[!UICONTROL Destination Mapping Value]** 中填充。
   * 您可以将同一测试段发送到多个目标，并可将多个测试段添加到单个目标。
   * 如果目标不适用于基于数据导出控件的特定测试区段，则这些目标将 [灰显](../../features/data-export-controls.md)。
   * 用户只能根据自己所属的 [RBAC用户组来查看自己有权访问的目标](../../features/administration/administration-overview.md) 。
   * 最后，您需要为测试组选择开始日期。 此日期标记将测试组发布到目标的时间段的开始。 选择 **“无结束日期** ”可无限期地比较测试段。
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 只有实时目标中支持通过身份验证的配置文件。 如果具有该配置的配置文件合并规则的测试区段被发送到基于文件的服务器到服务器目标，则可能不会填充受众。

   单击 **[!UICONTROL Next]** 以查看并完成测试组。

1. **[!UICONTROL Summary & Finalize]**

   * 查看您在上一步中添加的信息，然后选择 **[!UICONTROL Finalize Group]**。
   * 请记住，完成测试组后，可以复制或删除它，但不能编辑它。
   >[!NOTE]
   >* 您可以在创建过程中的任意点保存测试组，稍后再返回向导。 测试组状态将为， **[!UICONTROL Draft]** 测试组不会向目标发送任何数据，直到您完成区段测试组。
   >* 对于草稿测试，您可以返回并编辑测试组，方法是在主视 **[!UICONTROL Edit]** 图中单击测试组卡 [!UICONTROL Audience Lab] 片。


## 编辑区段测试组 {#edit-test-groups}

在 [!UICONTROL Audience Lab]中，您只能编辑草稿测试组。 在向 [!UICONTROL Create Segment Test Group] 导中，您可以将测试组另存为草稿，稍后继续处理它。

1. 导航到主 [!UICONTROL Audience Lab] 视图。
1. 搜索草稿测试组，并在测试 **[!UICONTROL Edit]** 组卡中选择控件。
1. 继续创 [建区段测试组向导](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，并 **[!UICONTROL Finalize Group]** 在完成后进行选择。

## 删除区段测试组 {#delete-test-groups}

1. 导航到主 [!UICONTROL Audience Lab] 视图。
1. 查找要删除的测试组。 您可以:

   * 按测试 **[!UICONTROL Delete]** 组卡中的控件，或
   * 按测试组卡中的测试组标题以转到“ [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) （测试组信息）”视图，然后按 **[!UICONTROL Delete]** 标题栏中的控件。

1. 对于 [已完成的测试段](../../features/audience-lab/audience-lab.md#status)，如果您愿意，系统会提示您下载CSV文件以保存报告。
