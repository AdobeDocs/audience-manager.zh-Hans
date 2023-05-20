---
description: 使用儀表板可檢視有關您合作夥伴在指定時間範圍內依特徵型別和區段劃分的不重複訪客計數資訊。
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: 报表仪表板
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# 报表仪表板 {#reports-dashboard}

使用控制面板檢視指定時間範圍內按特徵型別和區段劃分的不重複訪客計數相關資訊。

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組許可權擴充至 [!UICONTROL Dashboard]. 使用者只能在控制面板上檢視他們有權檢視的資訊。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可以檢視哪些報告資料。

例如，管理不同廣告商帳戶的機構可以設定使用者群組許可權，這樣管理廣告商A帳戶的團隊就看不到廣告商B的報告資料。 此儀表板可用來疑難排解資料傳送問題。

例如，如果您發現不重複使用者總數出現谷值或峰值，並有獨特使用者型別（規則型與已上線）的劃分，您有一個更好的起點來追蹤潛在的資料傳送問題。 如果您發現不重複使用者總數和已上線的不重複使用者出現下降，您可以前往 [!UICONTROL On-boarding Status] 檢視傳入檔案是否有問題的報告。

**若要存取控制面板：**

1. 在頂端導覽功能表中，按一下 **[!UICONTROL Dashboard]**.
2. *可選* 從下拉式清單中選取上次報告日期的所需時間範圍(7天、14天（預設值）、30天或60天)。

   根據選取的期間，差異會改變 [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] 和 [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] 面板會顯示今天結束的期間與相同長度的上一期間之間，對象中獨特訪客的變化。 例如，如果您選取「7天」，差值會比較今天結束前7天內的不重複訪客與七天前結束前7天內的不重複訪客。

   >[!NOTE]
   >
   >您可以透過執行 [!UICONTROL Trend] 報告。 例如，如果您在過去七天內看到異常大的差異變更，您可以執行 [!UICONTROL Trend] 報告過去14天(2 x 7)的情況，以更清楚瞭解數字。

   視登入使用者的許可權而定，系統會顯示下列面板：

   * [合作夥伴獨特](../reporting/reports-dashboard.md#partner-uniques)
   * [最大特徵/最多變更的特徵](../reporting/reports-dashboard.md#largest-traits)
   * [最大區段/最常變更的區段](../reporting/reports-dashboard.md#most-changed-segments)

3. *可選* 按一下 **[!UICONTROL Normalize]** 位於任何圖表上方，以相同比例顯示所有資料。 您也可以將滑鼠移到任何資料點上，以檢視更多資訊。

## 合作夥伴獨特 {#partner-uniques}

檢視所需的許可權： [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

此面板會顯示指定時段內的不重複訪客數量。 以顏色標示的個別行代表獨特訪客總數，以及使用演演算法、規則型和已上線特徵擷取的不重複訪客數。

>[!NOTE]
>
>不重複訪客的總數代表透過規則型或已上線特徵擷取的訪客。 不過，不重複訪客的總數並不等於使用規則型和已上線特徵擷取的不重複訪客總數。 在這兩種特徵型別中，同一不重複使用者可能會出現。

## 最大特徵/最多變更的特徵 {#largest-traits}

檢視所需的許可權： [!UICONTROL View Traits].

![](assets/largest_traits.png)

此面板會顯示各種特徵所擷取的不重複訪客數量。

使用 **[!UICONTROL Show]** 下拉式清單，顯示不同型別特徵的資訊： [!UICONTROL All Traits]， [!UICONTROL Algorithmic]， [!UICONTROL Onboarded]，或 [!UICONTROL Rule-Based].

此面板包含下列標籤：

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示按數字排序的不重複訪客數目的相關資訊（最高至最低），也會列出指定時間範圍內不重複訪客的差異變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 變更次數最多的特徵</span> </p> </td> 
   <td colname="col2"> <p>顯示依差異變更排序的不重複訪客數目的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最大區段/最常變更的區段 {#most-changed-segments}

檢視所需的許可權： [!UICONTROL View Segments].

![](assets/largest_segments.png)

此面板會顯示不同區段即時擷取的不重複訪客數量。

此面板包含下列標籤：

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 最大區段</span> </p> </td> 
   <td colname="col2"> <p>顯示指定時段內不重複訪客的數目和不重複訪客的差異變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 變更最多的區段</span> </p> </td> 
   <td colname="col2"> <p>顯示依差異變更排序的不重複訪客數目的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>
