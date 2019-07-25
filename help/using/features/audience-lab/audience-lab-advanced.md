---
description: 本文描述了为Audience Lab重复分配模板和区段剔除提供高级功能的两个功能。
seo-description: 本文描述了为Audience Lab重复分配模板和区段剔除提供高级功能的两个功能。
seo-title: Audience Lab高级功能
solution: Audience Manager
title: Audience Lab高级功能
uuid: 0f57d634-ca0-40da-81a2-c23 fbd299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] 高级功能 {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* 设备在测试段之间的分布；
* 测试区段到目标的映射；
* 用于测试组的转换特征；
* 测试组publishes到选定目标的日期范围。

通过复制分配模板，您可以在新的测试组中重用不同基础区段的测试区段和目标的相同分发。分配模板示例如下所示。The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重复分配模板

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. 例如，如果正在运行一个要确定多个区段的目标效力的测试，则可以使用此功能。

1. 在Audience Lab主视图中，搜索要在新测试组中重现其分配模板的测试组。In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. [!UICONTROL Create Test Group] 在向导中，可以根据需要指定基本区段并重命名测试区段。
3. You *cannot* modify:

   * 设备在测试段之间的分布；
   * 转换特征；
   * 测试区段到目标的映射。只能填写映射密钥，对于需要的目标。
   * 测试组将发布到选定目标的日期范围。

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是在客户请求上激活的高级功能。Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

使用此功能可阻止受众部分加入测试。您选择的百分比将离开测试。这样，您就可以衡量和比较来自目标(已激活在目的地)和未定位(全能组)受众的转化率。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用测试区段Holdout

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![列表项](assets/test-segment-holdout.png)

1. 使用滑块调整您要从测试中保持多少设备。请注意，Test Segment和Test Segment现在只占总设备的70%。

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you're satisfied with your selection. 您现在有一个测试组，其中受众的一部分不受测试的影响。
