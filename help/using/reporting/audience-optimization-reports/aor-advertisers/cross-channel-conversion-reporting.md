---
description: 「Audience Optimization」報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: 跨渠道转化
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# 跨渠道转化{#cross-channel-conversion}

「Audience Optimization」報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。

此 [!UICONTROL Cross Channel Conversion] 報告結合來自以下各項的結果： [!DNL Google Campaign Manager] 平台，搭配 [!DNL Audience Manager] 轉換特徵。 這可讓您將離線轉換連結至線上曝光數或點按數。

您可以使用 [!UICONTROL Cross Channel Conversion] 的 [區段績效](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 和 [最佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 報表。

若要檢視 [!UICONTROL Cross Channel Conversion] 報表，選取 **[!UICONTROL AAM + Ad Server Name]** 中的專案 **[!UICONTROL Platform]** 下拉式清單。

下表列出設定時的重要考量 [!UICONTROL Cross Channel Conversion]：

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 注意事项 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>轉換特徵的最小數量 </p> </td> 
   <td colname="col1"> <p>資料來源至少必須指派一個轉換特徵，才能 <span class="wintitle"> 跨管道轉換</span> 要執行的報告。 另請參閱 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 特徵的基本資訊</a> 以取得特徵的詳細資訊。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>歸因視窗 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google行銷活動管理員</span></b> 歸因期間為14天，這表示系統只會考量過去兩週中的轉換特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>使用者在轉換前最後看到的創意是獲得轉換的創意。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點按次數與曝光次數 </p> </td> 
   <td> <p>在判斷歸因是否同時發生時，點按優先於曝光。 例如，在顯示多個創意的頁面上，被點按的創意會獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料時近 </p> </td> 
   <td> <p>系統會一律根據前一天的可用資料計算報表。 </p> </td> 
  </tr> 
 </tbody> 
</table>
