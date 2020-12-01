---
description: 此过程将指导您完成在受众实验室中创建、编辑或删除测试组所需的步骤
seo-description: 此过程将指导您完成在受众实验室中创建、编辑或删除测试组所需的步骤
seo-title: 管理测试组
solution: Audience Manager
title: 管理测试组
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 1%

---


# 管理测试组 {#manage-test-groups}

此过程将指导您完成在[!UICONTROL Audience Lab]中创建、编辑或删除测试组所需的步骤。

## 创建段测试组{#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* 您至少需要设置一个&#x200B;**转换特征**。 可以在[特征生成器](../../features/traits/create-onboarded-rule-based-traits.md)中设置转换特征，方法是选择&#x200B;**转换**&#x200B;作为事件类型。 有关转换特征的详细信息以及如何设置它们，我们为您准备了[视频](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html)。

   >[!IMPORTANT]
   >
   >[不支](../../features/traits/about-folder-traits.md) 持文 **件** 夹跟踪 [!UICONTROL Audience Lab]。将文件夹特征的[事件类型](../../features/traits/create-onboarded-rule-based-traits.md)设置为&#x200B;**转换**&#x200B;不会在[!UICONTROL Audience Lab]中为该特定文件夹特征生成任何数据。

* 对于使用[基于角色的公司](../../features/administration/administration-overview.md)的访问控制:将[!UICONTROL Audience Lab] [通配符权限](../../features/administration/administration-overview.md#wild-card-permissions)分配给&#x200B;**[!UICONTROL User Groups]**&#x200B;以提供访问权限。 此权限允许用户创建和视图测试结果。 用户只能使用其具有&#x200B;**读取**&#x200B;和&#x200B;**映射到目标**&#x200B;权限的数据源中的段。 用户只能使用来自其具有&#x200B;**&quot;read&quot;**&#x200B;权限的数据源的转换特征。 用户也只能查看他们有权访问的目标。 因此，在向组添加[!DNL Audience Lab]通配符权限之前，请确保该组具有：
   * 获取相关转化特征；
   * 访问读取并映射相关测试段；
   * 访问相关目标。

创建新[!UICONTROL Segment Test Group]:

1. 在[!UICONTROL Audience Lab]仪表板中选择&#x200B;**[!UICONTROL Create New Test Group]**&#x200B;以开始向导。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填写&#x200B;**[!UICONTROL Test Group Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
   * 选择&#x200B;**[!UICONTROL Base Segment]**，方法是在文件浏览器中导航，或在搜索栏中键入，然后按&#x200B;**[!UICONTROL Choose Segment.]**&#x200B;进行确认
   * 可以将测试组另存为草稿，稍后继续处理它。
   * 如果您选择的基本区段已用于其他测试组，则将显示警报。 两次使用基线段可能会扭曲两个测试的转换结果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以创建&#x200B;**最多15个测试段**&#x200B;并根据需要划分设备百分比。
   * 您可以通过单击测试区段来编辑其名称。
   * 分配新测试区段时，百分比会自动平均分配为100%。 然后，您可以手动编辑百分比。 编辑百分比后，单击该复选框，确保百分比加起来达到100%，否则您将无法继续执行下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要保留区段的特定部分以用作对照组，请选择控制区段。 对照组允许您查看您创建的测试区段与基准测试的影响。
   * 您可以在下拉列表中选择测试段作为控制段，也可以选择&#x200B;**[!UICONTROL None]**&#x200B;作为无控件。
   * 完成后，单击&#x200B;**[!UICONTROL Next]**。

1. **[!UICONTROL Select Conversion Traits]**

   * 通过在转换特征窗口中键入来添加转换特征。 这是&#x200B;**mandatory**&#x200B;步骤，除非您添加至少一个转换特征，否则您无法继续执行下一步。
   * 如果需要，最多可以添加5个转换特征。
   * 如果您选择已用于其他测试组的转换特征，则会显示警报。
   * 请注意，Audience Manager不支持将[文件夹traits](/help/using/features/traits/about-folder-traits.md)用作转换特征。 选择文件夹特征作为转换特征会导致测试中显示0个聚合和趋势报告。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索字段中键入所需目标或使用下拉箭头。 [!UICONTROL Audience Lab] 测试区段可以发送到URL、cookie或服务器到服务器的目标。
   * 将区段拖放到目标。
   * 将段放到目标后，在盲中填入&#x200B;**[!UICONTROL Destination Mapping Value]**。
   * 您可以将同一测试段发送到多个目标，并可以将多个测试段添加到单个目标。
   * 如果目标在[数据导出控件](../../features/data-export-controls.md)的某个测试段中不可用，则它们将灰显。
   * 用户只能根据他们所属的[RBAC用户组](../../features/administration/administration-overview.md)来查看他们有权访问的目标。
   * 最后，您需要为测试组选择开始日期。 此日期标记将测试组发布到目标的开始。 选择&#x200B;**无结束日期**&#x200B;以不定期比较测试段。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 只有实时目标支持通过身份验证的用户档案。如果具有该配置的用户档案合并规则的测试区段被发送到基于文件的服务器到服务器目标，则受众可能不会填充。

   单击&#x200B;**[!UICONTROL Next]**&#x200B;以查看并完成测试组。

1. **[!UICONTROL Summary & Finalize]**

   * 查看您在前面的步骤中添加的信息，然后选择&#x200B;**[!UICONTROL Finalize Group]**。
   * 请记住，完成测试组后，它可以被复制或删除，但不能进行编辑。

   >[!NOTE]
   >* 您可以在创建过程中的任意点保存测试组，稍后返回向导。 测试组状态将为&#x200B;**[!UICONTROL Draft]**，测试组不会向目标发送任何数据，直到您完成段测试组。
   >* 对于草稿测试，可以通过单击主[!UICONTROL Audience Lab]视图中测试组卡中的&#x200B;**[!UICONTROL Edit]**，返回并编辑测试组。


## 编辑段测试组{#edit-test-groups}

在[!UICONTROL Audience Lab]中，您只能编辑草稿测试组。 在[!UICONTROL Create Segment Test Group]向导中，可以将测试组另存为草稿，稍后继续处理它。

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 搜索草稿测试组，并选择测试组卡中的&#x200B;**[!UICONTROL Edit]**&#x200B;控件。
1. 完成后，恢复[创建段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)向导并选择&#x200B;**[!UICONTROL Finalize Group]**。

## 删除段测试组{#delete-test-groups}

1. 导航到[!UICONTROL Audience Lab]主视图。
1. 查找要删除的测试组。 您可以:

   * 按测试组卡中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件，或
   * 按测试组卡中的测试组标题以转到[测试组信息](../../features/audience-lab/audience-lab-information-view.md)视图，然后按标题栏中的&#x200B;**[!UICONTROL Delete]**&#x200B;控件。

1. 对于[已完成的测试区段](../../features/audience-lab/audience-lab.md#status)，系统会显示一条警报，提示您下载CSV文件以保存报告（如果愿意）。
