---
description: 本文介绍了两项功能，它们为Audience Lab重复项分配模板和区段维持提供了高级功能。
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: Audience Lab高级功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# [!DNL Audience Lab]高级功能 {#audience-lab-advanced-functionality}

本文介绍了为[!DNL Audience Lab]提供高级功能的两项功能： [!DNL Duplicate Allocation Template]和[!DNL Segment Holdout]。

## 复制分配模板 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在[!DNL Audience Lab]中，[!DNL Allocation Template]表示您在创建测试组时所做的各种选择：

* 设备在测试区段之间的分布；
* 测试区段到目标的映射；
* 用于测试组的转化特征；
* 测试组向选定目标发布的日期范围。

通过复制分配模板，您可以在新的测试组中为不同的基础区段重复使用相同分布的测试区段和目标。 分配模板的示例如下所示。 图像是从&#x200B;**创建测试组**&#x200B;工作流的[!UICONTROL Summary & Finalize]步骤中获取的。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重复分配模板

创建初始测试组，然后选择&#x200B;**[!UICONTROL Duplicate Allocation Template]**&#x200B;以在多个测试组中重复使用相同的设置。 例如，如果您要运行测试来确定多个目标对于多个区段的功效，则可以使用此功能。

1. 在Audience Lab主视图中，搜索要在新测试组中重现其分配模板的测试组。 在下拉框中，选择&#x200B;**[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在[!UICONTROL Create Test Group]向导中，您可以根据需要指定基本区段并重命名测试区段。
3. 您&#x200B;*无法*&#x200B;修改：

   * 设备在测试区段之间的分布；
   * 转化特征；
   * 测试区段到目标的映射。 您只能为需要映射键的目标填写映射键。
   * 您的测试组将发布到所选目标的日期范围。

4. 查看您在前面的步骤中添加的信息，然后选择&#x200B;**[!UICONTROL Finalize Group]**。

## 测试区段维持 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout]是一项高级功能，根据客户请求激活。 请联系[!DNL Customer Care]或[!DNL Adobe Consulting]以激活此功能。

使用此功能可阻止将部分受众包含在测试中。 您选择的百分比将排除在测试之外。 这样，您就可以测量并比较来自目标（在目标上激活）和未目标（保留组）受众的转化次数。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用测试区段维持

1. 使用[!UICONTROL Create Test Group]向导创建新的测试组。
1. 在&#x200B;**[!UICONTROL Allocate Test Segment]**&#x200B;步骤中，您可以选择要不进行测试的部分受众。

   ![列表项](assets/test-segment-holdout.png)

1. 使用滑块可调整要禁止测试的设备数量。 请注意，测试区段1和测试区段2现在仅占总设备的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 完成&#x200B;**[!UICONTROL Create Test Group]**&#x200B;工作流程中的其余步骤，并在对选择感到满意时选择&#x200B;**[!UICONTROL Finalize Group]**。 您现在有一个测试组，其中一部分受众不参与测试。
