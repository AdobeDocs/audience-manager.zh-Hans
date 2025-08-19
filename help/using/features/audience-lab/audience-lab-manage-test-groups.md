---
description: 此过程将指导您完成在Audience Lab中创建、编辑或删除测试组所需的步骤
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: 管理测试组
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# 管理测试组 {#manage-test-groups}

此过程将指导您完成在[!UICONTROL Audience Lab]中创建、编辑或删除测试组所需的步骤。

## 创建区段测试组 {#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* 您需要设置至少一个&#x200B;**转化特征**。 您可以通过选择[转化](../../features/traits/create-onboarded-rule-based-traits.md)作为事件类型，在&#x200B;**特征生成器**&#x200B;中设置转化特征。 有关转化特征是什么以及如何设置这些特征的更多信息，我们为您准备了[视频](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html)。

  >[!IMPORTANT]
  >
  >[文件夹特征](../../features/traits/about-folder-traits.md)是&#x200B;**不支持的**&#x200B;[!UICONTROL Audience Lab]。 将文件夹特征的[事件类型](../../features/traits/create-onboarded-rule-based-traits.md)设置为&#x200B;**转换**&#x200B;将不会在[!UICONTROL Audience Lab]中为该特定文件夹特征生成任何数据。

* 对于使用[基于角色的访问控制](../../features/administration/administration-overview.md)的公司：将[!UICONTROL Audience Lab] [通配符权限](../../features/administration/administration-overview.md#wild-card-permissions)分配给&#x200B;**[!UICONTROL User Groups]**&#x200B;以提供访问权限。 此权限允许用户创建和查看测试结果。 用户将只能从具有&#x200B;**读取**&#x200B;和&#x200B;**映射到目标**&#x200B;权限的数据源中使用区段。 用户将只能使用他们具有&#x200B;**“读取”**&#x200B;权限的数据源的转化特征。 用户也只能查看他们有权访问的目标。 因此，在将[!DNL Audience Lab]通配符权限添加到组之前，请确保该组具有：
   * 访问相关的转化特征；
   * 访问读取和映射测试的相关区段；
   * 相关目标的访问权限。

要创建新[!UICONTROL Segment Test Group]，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL Create New Test Group]**&#x200B;仪表板中的[!UICONTROL Audience Lab]以启动向导。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填写&#x200B;**[!UICONTROL Test Group Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
   * 通过在文件浏览器中导航或在搜索栏中键入内容来选择&#x200B;**[!UICONTROL Base Segment]**，按&#x200B;**[!UICONTROL Choose Segment.]**&#x200B;进行确认
   * 您可以将测试组另存为草稿，稍后再继续处理。
   * 如果您选择的基本区段已用于其他测试组，则会显示一个警报。 两次使用基础区段可能会扭曲两个测试的转换结果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以创建&#x200B;**最多15个测试区段**，并根据需要划分设备百分比。
   * 您可以通过单击测试区段来编辑其名称。
   * 在分配新的测试区段时，百分比会自动平均分配为100%。 然后，您可以手动编辑百分比。 编辑百分比后单击复选框，并确保它们合计为100%，否则将无法继续执行下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要将某个区段的特定部分用作控制组，请选择控制区段。 通过对照组，可查看与基准比较您创建的测试区段的影响。
   * 您可以在下拉列表中选择一个测试区段作为控制区段，也可以选择&#x200B;**[!UICONTROL None]**&#x200B;作为无控制区段。
   * 完成后，单击&#x200B;**[!UICONTROL Next]**。

1. **[!UICONTROL Select Conversion Traits]**

   * 通过在转化特征窗口中键入内容来添加转化特征。 这是&#x200B;**强制的**&#x200B;步骤，除非添加至少一个转化特征，否则无法继续执行下一步。
   * 您最多可以添加5个转化特征（如果需要）。
   * 如果您选择已用于其他测试组的转化特征，则会显示警报。
   * 请注意，Audience Manager不支持使用[文件夹特征](/help/using/features/traits/about-folder-traits.md)作为转化特征。 将文件夹特征选择为转化特征会导致测试中显示0个汇总报表和趋势报表。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索字段中键入所需的目标或使用下拉箭头。 可以将[!UICONTROL Audience Lab]测试区段发送到URL、Cookie或服务器到服务器目标。
   * 将区段拖放到目标。
   * 将区段放入目标中后，在盲区中填充&#x200B;**[!UICONTROL Destination Mapping Value]**。
   * 您可以将同一测试区段发送到多个目标，也可以将多个测试区段添加到单个目标。
   * 如果目标对于基于[数据导出控制](../../features/data-export-controls.md)的特定测试区段不可用，则它们将显示为灰色。
   * 用户只能根据他们所属的[RBAC用户组](../../features/administration/administration-overview.md)查看他们有权访问的目标。
   * 最后，您需要为测试组选择开始日期。 此日期标记将测试组发布到目标的时段的开始。 选择&#x200B;**无结束日期**&#x200B;对测试区段进行无限期比较。

   >[!NOTE]
   >
   >只有实时目标才支持具有已验证配置文件的[!UICONTROL Profile Merge Rules]。 如果将具有该配置的配置文件合并规则的测试区段发送到基于文件的服务器到服务器目标，则可能无法填充受众。

   单击&#x200B;**[!UICONTROL Next]**&#x200B;以查看并完成测试组。

1. **[!UICONTROL Summary & Finalize]**

   * 查看您在前面的步骤中添加的信息，然后选择&#x200B;**[!UICONTROL Finalize Group]**。
   * 请记住，完成测试组后，可以复制或删除该组，但不能对其进行编辑。

   >[!NOTE]
   >* 您可以在创建过程中的任何时候保存测试组，并稍后返回到向导。 测试组状态将为&#x200B;**[!UICONTROL Draft]**，在您完成区段测试组之前，测试组不会向目标发送任何数据。
   >* 对于草稿测试，您可以通过单击主&#x200B;**[!UICONTROL Edit]**&#x200B;视图中测试组卡片中的[!UICONTROL Audience Lab]返回并编辑测试组。

## 编辑区段测试组 {#edit-test-groups}

在[!UICONTROL Audience Lab]中，您只能编辑草稿测试组。 在[!UICONTROL Create Segment Test Group]向导中，您可以将测试组另存为草稿，稍后再继续处理。

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 搜索您的草稿测试组，然后在测试组卡中选择&#x200B;**[!UICONTROL Edit]**&#x200B;控件。
1. 继续[创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)向导，并在完成后选择&#x200B;**[!UICONTROL Finalize Group]**。

## 删除区段测试组 {#delete-test-groups}

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 查找要删除的测试组。 您可以：

   * 按测试组卡片中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件，或者
   * 按测试组卡片中的测试组标题以转到[测试组信息](../../features/audience-lab/audience-lab-information-view.md)视图，然后按标题栏中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件。

1. 对于[已完成的测试区段](../../features/audience-lab/audience-lab.md#status)，如果您愿意，警报将提示您下载CSV文件以保存报表。
