---
description: 此过程可指导您完成在Audience Lab中创建、编辑或删除测试组所需的步骤
seo-description: 此过程可指导您完成在Audience Lab中创建、编辑或删除测试组所需的步骤
seo-title: 管理测试组
solution: Audience Manager
title: 管理测试组
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# 管理测试组 {#manage-test-groups}

此过程将指导您完成在[!UICONTROL Audience Lab]中创建、编辑或删除测试组所需的步骤。

## 创建区段测试组{#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* 您需要至少设置一个&#x200B;**转化特征**。 您可以在[特征生成器](../../features/traits/create-onboarded-rule-based-traits.md)中设置转化特征，方法是选择&#x200B;**转化**&#x200B;作为事件类型。 有关什么是转化特征以及如何设置转化特征的更多信息，我们为您准备了[video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html)。

   >[!IMPORTANT]
   >
   >[不](../../features/traits/about-folder-traits.md) 支持 **文** 件夹 [!UICONTROL Audience Lab]特性。将文件夹特征的[事件类型](../../features/traits/create-onboarded-rule-based-traits.md)设置为&#x200B;**conversion**&#x200B;将不会在[!UICONTROL Audience Lab]中为该特定文件夹特征生成任何数据。

* 对于使用[基于角色的访问控制](../../features/administration/administration-overview.md)的公司：将[!UICONTROL Audience Lab] [通配符权限](../../features/administration/administration-overview.md#wild-card-permissions)分配给&#x200B;**[!UICONTROL User Groups]**&#x200B;以提供访问权限。 此权限允许用户创建和查看测试结果。 用户只能使用其具有&#x200B;**read**&#x200B;和&#x200B;**映射到目标**&#x200B;权限的数据源中的区段。 用户只能使用其具有&#x200B;**&quot;read&quot;**&#x200B;权限的数据源中的转化特征。 用户也只能查看他们有权访问的目标。 因此，在向组添加[!DNL Audience Lab]通配符权限之前，请确保该组具有：
   * 有权读取相关转化特征；
   * 读取和映射相关区段以进行测试；
   * 访问相关目标。

要创建新的[!UICONTROL Segment Test Group]，请执行以下操作：

1. 在[!UICONTROL Audience Lab]功能板中选择&#x200B;**[!UICONTROL Create New Test Group]**&#x200B;以启动向导。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填写&#x200B;**[!UICONTROL Test Group Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
   * 选择&#x200B;**[!UICONTROL Base Segment]**，方法是在文件浏览器中导航，或在搜索栏中键入，然后按&#x200B;**[!UICONTROL Choose Segment.]**&#x200B;确认
   * 您可以将测试组另存为草稿，稍后继续处理该测试组。
   * 如果您选择的基本区段已用于其他测试组，则会显示警报。 两次使用基本区段可能会扭曲两个测试的转换结果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您最多可以创建&#x200B;**15个测试区段**&#x200B;并按您希望的方式划分设备百分比。
   * 您可以通过单击测试区段的名称来编辑这些区段的名称。
   * 分配新测试区段后，百分比会自动平均划分为100%。 然后，您可以手动编辑百分比。 编辑百分比后单击复选框，并确保这些百分比加起来最多为100%，否则您将无法继续执行下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要保留区段的特定部分以用作控制组，请选择控制区段。 控制组允许您查看与基准比较您创建的测试区段的影响。
   * 您可以在下拉列表中选择测试区段作为控制区段，也可以选择&#x200B;**[!UICONTROL None]**&#x200B;作为无控制区段。
   * 完成后，单击&#x200B;**[!UICONTROL Next]**。

1. **[!UICONTROL Select Conversion Traits]**

   * 通过在转化特征窗口中键入内容来添加转化特征。 这是一个&#x200B;**必备的**&#x200B;步骤，除非至少添加一个转化特征，否则无法继续下一步。
   * 如果需要，最多可以添加5个转化特征。
   * 如果您选择的转化特征已用于其他测试组，则会显示警报。
   * 请注意，Audience Manager不支持将[文件夹特征](/help/using/features/traits/about-folder-traits.md)用作转化特征。 选择文件夹特征作为转化特征会导致测试中显示0个汇总和趋势报表。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索字段中键入所需目标或使用下拉箭头。 [!UICONTROL Audience Lab] 测试区段可以发送到URL、Cookie或服务器到服务器目标。
   * 将区段拖放到目标。
   * 在目标中放置区段后，在盲中填充&#x200B;**[!UICONTROL Destination Mapping Value]**。
   * 您可以将同一测试区段发送到多个目标，并且可以将多个测试区段添加到单个目标。
   * 如果目标不可用于基于[数据导出控制](../../features/data-export-controls.md)的特定测试区段，则目标将呈灰显状态。
   * 用户将仅根据其所属的[RBAC用户组](../../features/administration/administration-overview.md)查看他们有权访问的目标。
   * 最后，您需要为测试组选择开始日期。 此日期标记将测试组发布到目标的时间段的开始。 选择&#x200B;**无结束日期**&#x200B;以无限期地比较测试区段。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 仅在实时目标中支持使用已验证的用户档案。如果将具有该配置配置文件合并规则的测试区段发送到基于文件的服务器到服务器目标，则受众可能不会填充。

   单击&#x200B;**[!UICONTROL Next]**&#x200B;以查看并完成测试组。

1. **[!UICONTROL Summary & Finalize]**

   * 查看在前面的步骤中添加的信息，然后选择&#x200B;**[!UICONTROL Finalize Group]**。
   * 请记住，完成测试组后，该测试组可以被复制或删除，但不能进行编辑。

   >[!NOTE]
   >* 您可以在创建过程中的任意时刻保存测试组，稍后再返回到向导。 测试组状态将为&#x200B;**[!UICONTROL Draft]**，在您完成区段测试组之前，测试组不会向目标发送任何数据。
   >* 对于草稿测试，您可以返回并编辑测试组，方法是在主视图[!UICONTROL Audience Lab]的测试组卡中单击&#x200B;**[!UICONTROL Edit]**。


## 编辑区段测试组{#edit-test-groups}

在[!UICONTROL Audience Lab]中，您只能编辑草稿测试组。 在[!UICONTROL Create Segment Test Group]向导中，您可以将测试组另存为草稿，然后继续处理该草稿。

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 搜索草稿测试组，并在测试组卡中选择&#x200B;**[!UICONTROL Edit]**&#x200B;控件。
1. 完成后，恢复[创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)向导并选择&#x200B;**[!UICONTROL Finalize Group]**。

## 删除区段测试组{#delete-test-groups}

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 查找要删除的测试组。 您可以:

   * 按测试组卡中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件，或
   * 按测试组卡中的测试组标题可转到[测试组信息](../../features/audience-lab/audience-lab-information-view.md)视图，然后按标题栏中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件。

1. 对于[已完成的测试区段](../../features/audience-lab/audience-lab.md#status)，如果您愿意，系统会发出警报，提示您下载CSV文件以保存报表。
