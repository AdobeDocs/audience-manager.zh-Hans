---
description: 在“细分测试组”中创建互斥的测试细分，以比较和衡量不同目标的有效性。 您可以搁置对照组，将细分成整体的百分比，以测试效果。
seo-description: 在“细分测试组”中创建互斥的测试细分，以比较和衡量不同目标的有效性。 您可以搁置对照组，将细分成整体的百分比，以测试效果。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# [!UICONTROL Audience Lab] {#audience-lab}

创建互斥的测试细分，以 [!UICONTROL Segment Test Groups] 比较和衡量不同目标的有效性。 您可以搁置对照组，将细分成整体的百分比，以测试效果。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使 [用用户档案链](../../features/profile-merge-rules/merge-rules-overview.md) 接来支持跨设备测试。 这有助于确保用户有资格获得相同的测试段，并在不同设备上获得相同的待遇。 测试组中的测试段将继承基 [本段分配给](../../features/profile-merge-rules/merge-rules-dashboard.md) 它的用户档案合并规则。

默 [!UICONTROL Audience Lab] 认视图显示每个测试组的卡。 单击卡以访问 **[!UICONTROL Test Group]** 视图。 此视图包含以下信息：

* **[测试组信息](../../features/audience-lab/audience-lab-information-view.md)**
* **[测试组报表](../../features/audience-lab/audience-lab-reporting-view.md)**

您最多可以创建 **10个测试组**，每个组 **最多包含15个测试段**。

![](assets/test-groups-view.PNG)

## 搜索和筛选测试组 {#search-and-filter}

开始创建具有多个测试段的多个测试组后，使用搜索框查找特定测试组可能会更简单。 可以通过以下方式搜索测试组：

* 测试组的名称；
* 测试组中任意测试段的名称；
* 测试组的说明。

![](assets/search_and_filter_audience_lab.png)

您还可以按状态筛选测试组。 以下状态部分介绍了所 [有可用](../../features/audience-lab/audience-lab.md#status) 状态。

## [!UICONTROL Status] {#status}

测试组的状态可以是活动、计划、暂停、草稿或完成。 下表中提供了有关每个应用程序的更多信息：

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 状态 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 活动 </span></b> </p> </td> 
   <td colname="col2"> <p>活动 <i>测试</i> 组表示数据当前正被发送到目标。 在“测 <b><span class="uicontrol"> 试组” </span></b> 卡中按“ <b><span class="uicontrol"> 暂停测试”可 </span></b> 暂停向目标发送数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已计划 </span></b> </p> </td> 
   <td colname="col2"> <p>计 <i>划的测试</i> 组尚未处于活动状态，但无法再进行编辑。 它将在您在“创建测试组”向导中选择的开始 <b>日期变为</b> “活动”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暂停 </span></b> </p> </td> 
   <td colname="col2"> <p>暂停 <i>的测试</i> 组当前不向目标发送数据。 在测 <b><span class="uicontrol"> 试组 </span></b> 卡中按 <b><span class="uicontrol"> Make Active以 </span></b> 继续发送特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p>草 <i>稿测试</i> 组尚未激活，仍可进行编辑。 它尚未将数据发送到映射的目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已完成 </span></b> </p> </td> 
   <td colname="col2"> <p>完成 <i>的测试</i> 组已到达您在“创建测试组”向导中选择 <b><span class="uicontrol"> 的结束日期，并 </span></b> 且已停止发送报告数据。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

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
   <td colname="col2"> <p>仅适用于 <b>草稿</b> （测试组）。 允许您恢复“新建 <b><span class="uicontrol"> 测试组” </span></b> 向导。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暂停 </span></b> </p> </td>
   <td colname="col2"> <p>可用于活动测试组。 允许您暂停将测试区段发送到目标。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 激活 </span></b> </p> </td>
   <td colname="col2"> <p>可用于已暂停的测试组。 允许您继续将测试区段发送到目标。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 查看 </span></b> </p> </td>
   <td colname="col2"> <p>可用于已完成的测试组。 允许您视图测试生成的报告信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 复制 </span></b> </p> </td>
   <td colname="col2"> <p>允许您使用与复制的测试组相同的配置创建新测试组。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 删除 </span></b> </p> </td>
   <td colname="col2"> <p>允许您删除测试组。 测试段将从目标中取消映射，与测试组关联的基线段和转换特征将完全可编辑。 在删除测试组时，系统会显示一条警报，提示您下载CSV文件，以便根据需要保存报告。 </p> </td>
  </tr>
 </tbody>
</table>