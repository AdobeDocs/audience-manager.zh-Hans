---
description: 在区段测试组中创建互斥的测试区段，以比较和衡量不同目标的有效性。 您可以留出一个控制组，并将区段划分为整体的百分比，以测试效果。
seo-description: 在区段测试组中创建互斥的测试区段，以比较和衡量不同目标的有效性。 您可以留出一个控制组，并将区段划分为整体的百分比，以测试效果。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

在[!UICONTROL Segment Test Groups]中创建互斥的测试区段，以比较和衡量不同目标的有效性。 您可以留出一个控制组，并将区段划分为整体的百分比，以测试效果。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用配 [置文](../../features/profile-merge-rules/merge-rules-overview.md) 件链接来支持跨设备测试。这有助于确保用户符合同一测试区段的条件，并跨设备获得相同的处理。 测试组中的测试区段将继承分配给基本区段的[配置文件合并规则](../../features/profile-merge-rules/merge-rules-dashboard.md)。

[!UICONTROL Audience Lab]默认视图将显示每个测试组的卡片。 单击卡以访问&#x200B;**[!UICONTROL Test Group]**&#x200B;视图。 此视图包括以下信息：

* **[测试组信息](../../features/audience-lab/audience-lab-information-view.md)**
* **[测试组报表](../../features/audience-lab/audience-lab-reporting-view.md)**

您最多可以创建&#x200B;**10个测试组**，每个测试组具有&#x200B;**最多15个测试区段**。

![](assets/test-groups-view.PNG)

## 搜索和筛选测试组{#search-and-filter}

开始创建具有多个测试区段的多个测试组后，使用搜索框查找特定测试组可能会比较容易。 您可以通过以下方式搜索测试组：

* 测试组的名称；
* 测试组中任意测试区段的名称；
* 测试组的描述。

![](assets/search_and_filter_audience_lab.png)

您还可以按状态过滤测试组。 以下[Status](../../features/audience-lab/audience-lab.md#status)部分介绍了所有可用状态。

## [!UICONTROL Status] {#status}

测试组的状态可以是活动、已计划、已暂停、已草稿或已完成。 下表中提供了关于每个规则的更多信息：

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
   <td colname="col2"> <p><i>active</i>测试组表示数据当前正被发送到目标。 在<b><span class="uicontrol">测试组</span></b>卡中按<b><span class="uicontrol">暂停测试</span></b>以暂停向目标发送数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已计划 </span></b> </p> </td> 
   <td colname="col2"> <p><i>scheduled</i>测试组尚未处于活动状态，但无法再编辑。 在<b>创建测试组</b>向导中选择的开始日期，测试组将处于活动状态。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暂停 </span></b> </p> </td> 
   <td colname="col2"> <p><i>已暂停的</i>测试组当前不向目标发送数据。 在<b><span class="uicontrol">测试组</span></b>卡中按<b><span class="uicontrol">使活动</span></b>以恢复发送特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p><i>draft</i>测试组尚未处于活动状态，仍可编辑。 它尚未将数据发送到映射的目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已完成 </span></b> </p> </td> 
   <td colname="col2"> <p><i>已完成的</i>测试组已到达您在<b><span class="uicontrol">创建测试组</span></b>向导中选择的结束日期，并已停止发送报告数据。 </p> </td>
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
   <td colname="col2"> <p><b>仅</b>适用于草稿测试组。 用于恢复<b><span class="uicontrol">新建测试组</span></b>向导。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暂停 </span></b> </p> </td>
   <td colname="col2"> <p>可用于活动测试组。 允许您暂停将测试区段发送到目标。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 激活  </span></b> </p> </td>
   <td colname="col2"> <p>可用于暂停的测试组。 允许您继续将测试区段发送到目标。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 查看 </span></b> </p> </td>
   <td colname="col2"> <p>可用于已完成的测试组。 用于查看测试生成的报告信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 复制 </span></b> </p> </td>
   <td colname="col2"> <p>允许您使用与复制的测试组相同的配置创建新测试组。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 删除 </span></b> </p> </td>
   <td colname="col2"> <p>用于删除测试组。 测试区段将从目标中取消映射，与测试组关联的基准区段和转化特征可完全编辑。 当您删除测试组以保存报表（如果需要）时，系统会发出警告，提示您下载CSV文件。 </p> </td>
  </tr>
 </tbody>
</table>
