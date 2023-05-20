---
description: 返回有关在您的所有首次和第三方特征中共享的独特用户数量的数据。
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: 特征到特征重叠报表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

---

# 特征到特征重叠报表{#trait-to-trait-overlap-report}

返回有关在您的所有首次和第三方特征中共享的独特用户数量的数据。

>[!NOTE]
>
>Audience Manager 中的重叠报表遵循 RBAC 原则。 您只能根據以下專案檢視您有權存取之資料來源的特徵： [rbac使用者群組](/help/using/features/administration/administration-overview.md) 您所屬的。

<!-- 

c_overlap_reports.xml

 -->

## 概述

此 [!UICONTROL Trait-to-Trait Overlap] report會傳回在您所有特徵與第三方特徵之間共用的不重複使用者百分比資料。 作為最佳化工具，此報表可協助您：

* 根據您的需求，建立具有高重疊或低重疊的區段。 重疊程度高的特徵會提供您目標受眾，但獨特訪客較少。 具有低重叠的特征可用于达到更大的独特访客集。
* 验证第三方特征数据：在类似的第一个和第三方特征之间存在强重叠，意味着您的数据合作伙伴中的特性是准确且可靠的。 相反，低重叠可能表示第三方特征实际不包含与您自己的、类似的第一方特征相同的信息。
* 发现特征之间的意外重叠，并使用该信息版本创新的区段。

## 示例报表

下图提供了报表中 [!UICONTROL Trait-to-Trait Overlap] 元素的高层次概述。

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap]报表会在将相同的特征与自身进行比较时返回空字段。

>[!NOTE]
>
>在特徵對特徵重疊報表中，資料夾特徵無法用於比較。 透過使用特定資料夾特徵建立區段，您可以透過 [區段對特徵重疊報表](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 定義的特徵對特徵重疊資料快顯欄位 {#field-definitions}

說明當您按一下個別資料點時，彈出式視窗中顯示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

报表的弹出窗口 [!UICONTROL Trait-to-Trait Overlap] 包含以下量度。 请注意，表格中的独特量度表示您 *的实时用户* 。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 层叠</span></b> </td> 
   <td colname="col2"> 显示比较的特征（重叠独特/特征独特）之间的唯一重叠百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料來源型別</span></b> </td> 
   <td colname="col2">定義特徵所屬的資料來源型別。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/廠商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵ID</span></b> </td> 
   <td colname="col2"> 重叠特征的唯一数值 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠特征名称</span></b> </td> 
   <td colname="col2"> 重叠特征的名称。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征 ID 2</span></b> </td> 
   <td colname="col2"> 基本数据源中特征的唯一数值 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱2</span></b> </td> 
   <td colname="col2"> 基礎資料來源中的特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊不重複專案</span></b> </td> 
   <td colname="col2"> <p>若要取得重疊%，Audience Manager會使用下列公式：</p> <p>重疊唯一性/ （基本唯一性+重疊唯一性 — 重疊唯一性）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵不重複</span></b> </td> 
   <td colname="col2"> 重叠特征中的独特访客数量。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特征独特</span></b> </td> 
   <td colname="col2"> 基本特征中的独特访客数量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [动态报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [說明報表圖示和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

