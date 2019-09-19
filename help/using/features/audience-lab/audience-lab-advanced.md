---
description: 本文介绍了为Audience Lab重复分配模板和区段抑制提供高级功能的两个功能。
seo-description: 本文介绍了为Audience Lab重复分配模板和区段抑制提供高级功能的两个功能。
seo-title: Audience lab高级功能
solution: Audience Manager
title: Audience lab高级功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] 高级功能 {#audience-lab-advanced-functionality}

本文介绍了两种功能，它们为以下对象提供高级功 [!DNL Audience Lab]能： [!DNL Duplicate Allocation Template] 和 [!DNL Segment Holdout]。

## 复制分配模板 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在中， [!DNL Audience Lab]表示 [!DNL Allocation Template] 您在创建测试组时所做的各种选择：

* 设备在测试段之间的分布；
* 将测试段映射到目标；
* 用于测试组的转换特征；
* 测试组发布到所选目标的日期范围。

通过复制分配模板，您可以在新测试组中为不同的基本区段重复使用相同的测试区段和目标分布。 分配模板的示例如下所示。 该图像是从“创建测试组 [!UICONTROL Summary & Finalize] ”工作流中 **的步骤中获取的** 。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重复分配模板

创建初始测试组，然后选择以 **[!UICONTROL Duplicate Allocation Template]** 在多个测试组之间重复使用相同的设置。 例如，如果您正在运行测试，以确定多个区段的多个目标的有效性，则可以使用此功能。

1. 在Audience lab主视图中，搜索要在新测试组中重现其分配模板的测试组。 在下拉框中，选择 **[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在向 [!UICONTROL Create Test Group] 导中，您可以指定基本区段并根据需要重命名测试区段。
3. 您无 *法修* 改：

   * 设备在测试段之间的分布；
   * 转换特征；
   * 测试区段到目标的映射。 对于需要映射密钥的目标，您只能填写映射密钥。
   * 测试组将发布到所选目标的日期范围。

4. 查看您在上一步中添加的信息，然后选择 **[!UICONTROL Finalize Group]**。

## 测试段抑制 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是根据客户请求激活的高级功能。 请联系 [!DNL Customer Care] 或激 [!DNL Adobe Consulting] 活此功能。

使用此功能可阻止部分受众加入测试。 您选择的百分比不在测试范围之内。 这样，您可以衡量和比较来自目标（在目标上激活）和非目标（保持组）受众的转化数。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用测试段抑制

1. 使用向导创建新的测试 [!UICONTROL Create Test Group] 组。
1. 在该步 **[!UICONTROL Allocate Test Segment]** 骤中，您可以选择要从测试中隐藏的受众的一部分。

   ![列表项](assets/test-segment-holdout.png)

1. 使用滑块调整要阻止测试的设备数量。 请注意，测试区段1和测试区段2现在仅占总设备的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 完成工作流中的其余步骤， **[!UICONTROL Create Test Group]** 并在您对 **[!UICONTROL Finalize Group]** 您的选择感到满意时进行选择。 您现在有一个测试组，其中一部分受众拒绝测试。
