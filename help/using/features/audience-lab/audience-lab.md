---
description: 在“细分测试组”中创建互斥的测试区段，以比较和衡量不同目标的有效性。 您可以留出一个控制组，将您的细分分为整体百分比，以测试效果。
seo-description: 在“细分测试组”中创建互斥的测试区段，以比较和衡量不同目标的有效性。 您可以留出一个控制组，将您的细分分为整体百分比，以测试效果。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aee820c-1e78-4fd4-bd8f-2629085d78e9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

创建互斥的测试细分，以 [!UICONTROL Segment Test Groups] 比较和衡量不同目标的有效性。 您可以留出一个控制组，将您的细分分为整体百分比，以测试效果。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用 [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md) （配置文件链接）来支持跨设备测试。 这有助于确保用户有资格获得相同的测试段，并在不同设备上获得相同的处理。 测试组中的测试段将继承基本段 [分配给它的配置文件合并规则](../../features/profile-merge-rules/merge-rules-dashboard.md) 。

默 [!UICONTROL Audience Lab] 认视图显示每个测试组的卡。 单击信息卡以访问视 **[!UICONTROL Test Group]** 图。 此视图包括以下信息：

* **[测试组信息](../../features/audience-lab/audience-lab-information-view.md)**
* **[测试组报告](../../features/audience-lab/audience-lab-reporting-view.md)**

您最多可以创建 **10个测试组**，每个组最 **多包含15个测试段**。

![](assets/test-groups-view.PNG)

## 搜索和筛选测试组 {#search-and-filter}

开始创建包含多个测试段的多个测试组后，使用搜索框查找特定测试组可能会更容易。 您可以通过以下方式搜索测试组：

* 测试组的名称；
* 测试组中任意测试段的名称；
* 测试组的说明。

![](assets/search_and_filter_audience_lab.png)

您还可以按状态筛选测试组。 以下“状态”部分介绍了所 [有可用](../../features/audience-lab/audience-lab.md#status) 状态。

## 状态 {#status}

测试组的状态可以是活动、已计划、已暂停、草稿或已完成。 下表中各项的更多信息：

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
   <td colname="col2"> <p>活动 <i>测试组</i> ，表示数据当前正被发送到目标。 在“测 <b><span class="uicontrol"> 试组” </span></b> 卡中按“暂 <b><span class="uicontrol"> 停测试”可暂 </span></b> 停向目标发送数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已计划 </span></b> </p> </td> 
   <td colname="col2"> <p>计 <i>划的测试组</i> ，尚未激活，但不能再编辑。 它将在您在“创建测试组”向导中选择的开始日期 <b>变为活动</b> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已暂停 </span></b> </p> </td> 
   <td colname="col2"> <p>暂 <i>停的测试组</i> 当前不向目标发送数据。 在“测 <b><span class="uicontrol"> 试组” </span></b> 卡中按 <b><span class="uicontrol"> “设为活动” </span></b> 可继续发送特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p>草 <i>稿测试组</i> 尚未激活，仍可编辑。 它尚未将数据发送到映射的目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已完成 </span></b> </p> </td> 
   <td colname="col2"> <p>已完 <i>成的测试组</i> ，已到达您在“创建测试组”向导中选择的结束日期，并 <b><span class="uicontrol"></span></b> 且已停止发送报告数据。 </p> </td>
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
   <td colname="col2"> <p>仅适用于 <b>草稿测试组</b> 。 允许您恢复“创建 <b><span class="uicontrol"> 新测试组”向 </span></b> 导。 </p> </td>
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
   <td colname="col2"> <p>适用于已完成的测试组。 允许您查看测试生成的报告信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 复制 </span></b> </p> </td>
   <td colname="col2"> <p>允许您使用与复制的测试组相同的配置创建新测试组。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 删除 </span></b> </p> </td>
   <td colname="col2"> <p>允许您删除测试组。 测试区段将从目标取消映射，与测试组关联的基线区段和转换特征将完全可编辑。 在删除测试组以保存报告时，如果您愿意，系统会提示您下载CSV文件。 </p> </td>
  </tr>
 </tbody>
</table>