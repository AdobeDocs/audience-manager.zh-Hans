---
description: 本文介绍了两种功能，它们为受众实验室重复分配模板和细分抑制提供了高级功能。
seo-description: 本文介绍了两种功能，它们为受众实验室重复分配模板和细分抑制提供了高级功能。
seo-title: Audience Lab 高级功能
solution: Audience Manager
title: Audience Lab 高级功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---


# [!DNL Audience Lab] 高级功能  {#audience-lab-advanced-functionality}

本文介绍为[!DNL Audience Lab]提供高级功能的两个功能：[!DNL Duplicate Allocation Template]和[!DNL Segment Holdout]。

## 重复分配模板{#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在[!DNL Audience Lab]中，[!DNL Allocation Template]表示创建测试组时所做的各种选择：

* 设备在测试段之间的分布；
* 测试段到目标的映射；
* 用于测试组的转换特征；
* 测试组发布到所选目标的日期范围。

通过复制分配模板，您可以在新测试组中，将测试段和目标的相同分布重新用于不同的基本段。 分配模板的示例如下所示。 该图像是从&#x200B;**创建测试组**&#x200B;工作流中的[!UICONTROL Summary & Finalize]步骤获取的。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重复分配模板

创建初始测试组，然后选择&#x200B;**[!UICONTROL Duplicate Allocation Template]**&#x200B;以在多个测试组之间重复使用相同的设置。 例如，如果要运行测试，以确定多个区段的多个目标的有效性，则可以使用此功能。

1. 在受众实验室主视图中，搜索要在新测试组中重现其分配模板的测试组。 在下拉框中，选择&#x200B;**[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在[!UICONTROL Create Test Group]向导中，您可以指定基本段，并根据需要重命名测试段。
3. *不能*&#x200B;修改：

   * 设备在测试段之间的分布；
   * 转换特征；
   * 测试区段到目标的映射。 对于需要映射密钥的目标，只能填写映射密钥。
   * 测试组将发布到所选目标的日期范围。

4. 查看您在前面的步骤中添加的信息，然后选择&#x200B;**[!UICONTROL Finalize Group]**。

## 测试段保持{#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是一项高级功能，可根据客户请求激活。请联系[!DNL Customer Care]或[!DNL Adobe Consulting]以激活此功能。

使用此功能可阻止测试中包含部分受众。 您选择的百分比将不在测试中。 这样，您可以衡量和比较目标（在目标上激活）和非目标（保持组）受众的转化数。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用测试段抑制

1. 使用[!UICONTROL Create Test Group]向导新建一个测试组。
1. 在&#x200B;**[!UICONTROL Allocate Test Segment]**&#x200B;步骤中，可以选择要从测试中隐藏的受众的一部分。

   ![列表项](assets/test-segment-holdout.png)

1. 使用滑块调整要阻止测试的设备数量。 注意测试段1和测试段2现在仅占总设备的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 完成&#x200B;**[!UICONTROL Create Test Group]**&#x200B;工作流中的其余步骤，并在您对您的选择感到满意时选择&#x200B;**[!UICONTROL Finalize Group]**。 您现在有一个测试组，其中部分受众未通过测试。
