---
description: 產生Audience Marketplace計費報告，以檢視每個訂閱者的上個月資料摘要使用量。 您可以隨時建立上個月的報表。 不過，如果您在當月10日當天或之後產生報表，報表會更準確。
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: 面向数据信息源提供商的账单
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 5%

---

# 面向数据信息源提供商的账单 {#billing-for-data-feed-providers}

產生 [!DNL Audience Marketplace] 計費報告，以檢視每個訂閱者的上個月資料摘要使用量。 您可以隨時建立上個月的報表。 不過，如果您在當月10日當天或之後產生報表，報表會更準確。

## 下載計費報告 {#download-billing-report}

若要下載報表：

1. 前往 **[!UICONTROL Audience Marketplace > Receivables]**.
1. 单击 **[!UICONTROL Generate Billing Report]**.

## 已定義報表欄位 {#report-fields-defined}

帳單報告包含下列資訊。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告欄位 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供者PID</span></b> </p> </td> 
   <td colname="col2"> <p>您的 <span class="keyword"> Audience Manager</span> 資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購買者PID</span></b> </p> </td> 
   <td colname="col2"> <p>購買者（訂閱者）識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購買者姓名</span></b> </p> </td> 
   <td colname="col2"> <p>採購員的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送 ID</span></b> </p> </td> 
   <td colname="col2"> <p>資料摘要的ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送名称</span></b> </p> </td> 
   <td colname="col2"> <p>資料摘要的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 計畫使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用案例可讓賣家控制買家如何使用資料。 选项包括： </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">區段和重疊 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">模型 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">激活 </li> 
    </ul> <p>另請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> 資料摘要的計畫型別</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 測量單位</span></b> </p> </td> 
   <td colname="col2"> <p>指出CPM或固定費用帳單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 定價</span></b> </p> </td> 
   <td colname="col2"> <p>每個資料摘要的訂閱費用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣價格</span></b> </p> </td> 
   <td colname="col2"> <p>折扣資料摘要的訂閱費用。 另請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> 資料提供者的折扣</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件数</span></b> </p> </td> 
   <td colname="col2"> <p>依摘要價格型別而異： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">固定費用資料摘要：僅傳回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM資料摘要：傳回CPM資料摘要的實際使用量。 如果訂閱者尚未提供CPM饋送的曝光資料，單位儲存格為空白，且旗標儲存格設為1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 總成本</span></b> </p> </td> 
   <td colname="col2"> <p>金額 <span class="keyword"> Audience Manager</span> 為採購員開立帳單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 計費期間</span></b> </p> </td> 
   <td colname="col2"> <p> 在報表中，這是上個月的最後一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 登录日期</span></b> </p> </td> 
   <td colname="col2"> <p>採購員輸入訂閱/使用量資訊的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱開始日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者開始訂閱資料摘要的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱結束日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者結束其資料摘要訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 標幟</span></b> </p> </td> 
   <td colname="col2"> <p> <i>僅適用於CPM摘要</i>. 標幟選項包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0：表示訂閱者已將使用資訊報告給 <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1：表示訂閱者尚未向報告使用資訊 <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM資料摘要的計費和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [固定費用資料摘要的計費和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何報告CPM使用量](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

