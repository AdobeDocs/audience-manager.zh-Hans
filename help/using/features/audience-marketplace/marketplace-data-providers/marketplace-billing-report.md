---
description: 生成Audience Marketplace账单报告，以便每个订阅者在上个月使用视图数据馈送。 您可以随时创建上个月的报表。 但是，在当月的当天或之后生成报表时，该报表会更加准确。
seo-description: 生成Audience Marketplace账单报告，以便每个订阅者在上个月使用视图数据馈送。 您可以随时创建上个月的报表。 但是，在当月的当天或之后生成报表时，该报表会更加准确。
seo-title: 面向数据信息源提供商的账单
solution: Audience Manager
title: 面向数据信息源提供商的账单
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 6%

---

# 面向数据信息源提供商的账单 {#billing-for-data-feed-providers}

生成[!DNL Audience Marketplace]账单报告，以视图每个订阅者上个月的数据馈送使用情况。 您可以随时创建上个月的报表。 但是，在当月的当天或之后生成报表时，该报表会更加准确。

## 下载帐单报告{#download-billing-report}

要下载报告，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Receivables]**。
1. 单击 **[!UICONTROL Generate Billing Report]**.

## 已定义{#report-fields-defined}的报表字段

帐单报表包含以下信息。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报表字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据提供程序PID</span></b> </p> </td> 
   <td colname="col2"> <p>您的<span class="keyword">Audience Manager</span>数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据提供程序名称</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或组织名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 采购员PID</span></b> </p> </td> 
   <td colname="col2"> <p>购买者（订阅者）ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 采购员姓名</span></b> </p> </td> 
   <td colname="col2"> <p>采购员的公司或组织名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送 ID</span></b> </p> </td> 
   <td colname="col2"> <p>数据馈送的ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送名称</span></b> </p> </td> 
   <td colname="col2"> <p>数据馈送的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 计划使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用案例让销售者能够控制购买者使用数据的方式。 选项包括： </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">区段和重叠 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">建模 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">激活 </li> 
    </ul> <p>请参阅<a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types">数据馈送的计划类型</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 单位</span></b> </p> </td> 
   <td colname="col2"> <p>指示CPM或统一费用计费。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 列表价格</span></b> </p> </td> 
   <td colname="col2"> <p>每个订阅源的数据费。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣价</span></b> </p> </td> 
   <td colname="col2"> <p>折扣数据馈送的订阅费。 请参阅<a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts">数据提供者折扣</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件数</span></b> </p> </td> 
   <td colname="col2"> <p>因馈送价格类型而异： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">统一费用数据馈送：仅返回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM数据馈送：返回CPM数据馈送的实际使用量。 如果用户尚未为CPM源提供印象数据，则“单位”单元为空，“标志”单元设置为1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 总成本</span></b> </p> </td> 
   <td colname="col2"> <p>金额<span class="keyword">Audience Manager</span>向买方开单。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 结算期</span></b> </p> </td> 
   <td colname="col2"> <p> 在报表中，这是上个月的最后一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 登录日期</span></b> </p> </td> 
   <td colname="col2"> <p>采购员输入订阅/使用信息的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 订阅开始日期</span></b> </p> </td> 
   <td colname="col2"> <p>采购员开始其数据馈送订阅的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 订阅结束日期</span></b> </p> </td> 
   <td colname="col2"> <p>买方结束其数据馈送订阅的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 标志</span></b> </p> </td> 
   <td colname="col2"> <p> <i>仅适用于CPM源</i>。标志选项包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0:指示订阅者已向<span class="keyword">Audience Manager</span>报告使用信息。 </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1:指示订阅者未向<span class="keyword">Audience Manager</span>报告使用信息。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM数据馈送的计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [统一费用数据馈送的计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何报告CPM使用情况](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

