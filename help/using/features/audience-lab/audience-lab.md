---
description: 在细分测试组中创建互斥的测试细分，以比较和衡量不同目标的有效性。您可以设置一个控制组，并将您的细分分成一部分，以测试效果。
seo-description: 在细分测试组中创建互斥的测试细分，以比较和衡量不同目标的有效性。您可以设置一个控制组，并将您的细分分成一部分，以测试效果。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8 f-2629085d78 e9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. 您可以设置一个控制组，并将您的细分分成一部分，以测试效果。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用 [配置文件链接](../../features/profile-merge-rules/merge-rules-overview.md) 支持跨设备测试。这有助于确保用户符合相同的测试细分条件，并在不同设备之间获得相同的治疗。The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

[!UICONTROL Audience Lab] 默认视图会显示每个测试组的卡。Click a card to access the **[!UICONTROL Test Group]** view. 此视图包括以下信息：

* **[测试组信息](../../features/audience-lab/audience-lab-information-view.md)**
* **[测试组报告](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

开始创建具有多个测试区段的多个测试组后，使用搜索框查找特定测试组可能会更容易。您可以通过以下方式搜索测试组：

* 测试组的名称；
* 测试组中任意测试区段的名称；
* 测试组的说明。

![](assets/search_and_filter_audience_lab.png)

您还可以按状态筛选测试组。All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## 状态 {#status}

测试组的状态可以是活动的、计划好的、暂停的、草稿的或已完成的。如下表所示的更多信息：

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 状态 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Active(活动) </span></b> </p> </td> 
   <td colname="col2"> <p><i>活动</i> 测试组表示数据当前正在发送到目标。Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已安排 </span></b> </p> </td> 
   <td colname="col2"> <p><i>计划</i> 的测试组尚未激活，但无法再进行编辑。It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已暂停 </span></b> </p> </td> 
   <td colname="col2"> <p><i>暂停</i> 的测试组当前不向目标发送数据。Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p><i>草稿</i> 测试组尚未激活，仍然可以编辑。它尚未向映射的目标发送数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已完成 </span></b> </p> </td> 
   <td colname="col2"> <p><i>完成</i> 的测试组已到达您在 <b><span class="uicontrol"> “创建测试组 </span></b> ”向导中选择的结束日期，并且已停止发送报告数据。 </p> </td>
  </tr>
 </tbody>
</table>

## 操作 {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 操作 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 编辑 </span></b> </p> </td>
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暂停 </span></b> </p> </td>
   <td colname="col2"> <p>可用于活动测试组。允许您暂停向目标发送测试区段。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 使活动变为活动状态 </span></b> </p> </td>
   <td colname="col2"> <p>可用于暂停的测试组。允许您恢复向目标发送测试区段。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 查看 </span></b> </p> </td>
   <td colname="col2"> <p>可用于已完成的测试组。允许您查看测试生成的报告信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 复制 </span></b> </p> </td>
   <td colname="col2"> <p>允许您创建一个与正在复制的相同的配置的新测试组。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 删除 </span></b> </p> </td>
   <td colname="col2"> <p>允许您删除测试组。将从目标中取消映射测试区段，与测试组关联的基线区段和转换特征是完全可编辑的。如果您希望删除测试组，警报将提示您在删除测试组时下载CSV文件。 </p> </td>
  </tr>
 </tbody>
</table>