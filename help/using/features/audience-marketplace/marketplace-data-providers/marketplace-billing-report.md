---
description: 生成Audience Marketplace帐单报告以查看每个用户上一个月的数据源使用情况。您可以随时为上一个月创建报告。但是，当您在当月的第10天或之后生成报表时，报表更准确。
seo-description: 生成Audience Marketplace帐单报告以查看每个用户上一个月的数据源使用情况。您可以随时为上一个月创建报告。但是，当您在当月的第10天或之后生成报表时，报表更准确。
seo-title: 数据馈送提供商计费
solution: Audience Manager
title: 数据馈送提供商计费
topic: DIL API
uuid: e11dbd2-91fd-4b59-a66 d-86a92 e0 de655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Billing for Data Feed Providers {#billing-for-data-feed-providers}

Generate an [!DNL Audience Marketplace] billing report to view data feed usage for the previous month for each of your subscribers. 您可以随时为上一个月创建报告。但是，当您在当月的第10天或之后生成报表时，报表更准确。

## Download a Billing Report {#download-billing-report}

要下载报告，请执行以下操作：

1. **[!UICONTROL Audience Marketplace > Receivables]**&#x200B;转至。
1. 单击 **[!UICONTROL Generate Billing Report]**.

## Report Fields Defined {#report-fields-defined}

账单报告包含以下信息。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报告字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据提供者PID</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 数据提供商ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据提供程序名称</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或组织名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 买方PID</span></b> </p> </td> 
   <td colname="col2"> <p>买方(订阅者) ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 买家姓名</span></b> </p> </td> 
   <td colname="col2"> <p>买方的公司或组织名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送 ID</span></b> </p> </td> 
   <td colname="col2"> <p>数据源的ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 馈送名称</span></b> </p> </td> 
   <td colname="col2"> <p>数据源的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 计划使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用案例可让卖家控制购买者使用数据的方式。选项包括： </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">区段和重叠 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">建模 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">激活 </li> 
    </ul> <p>See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plan Types for Data Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 度量单位</span></b> </p> </td> 
   <td colname="col2"> <p>指示CPM或简单费用计费。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 价目表价格</span></b> </p> </td> 
   <td colname="col2"> <p>每个数据源的订阅费用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣价格</span></b> </p> </td> 
   <td colname="col2"> <p>折扣数据馈送的订阅费用。See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Discounts for Data Providers</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件数</span></b> </p> </td> 
   <td colname="col2"> <p>因源价格类型而异： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">付费数据服务：仅返回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM数据源：返回CPM数据源的实际使用使用量。如果订阅者尚未为CPM源提供印象数据，则Units单元格为空，“标志”单元格设置为1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 总成本</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 向买家收取的金额。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 结算期</span></b> </p> </td> 
   <td colname="col2"> <p> 在报告中，这是上一个月的最后一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 登录日期</span></b> </p> </td> 
   <td colname="col2"> <p>买家输入订阅/使用信息的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 订阅开始日期</span></b> </p> </td> 
   <td colname="col2"> <p>买家开始其数据源订阅的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 订阅结束日期</span></b> </p> </td> 
   <td colname="col2"> <p>买家结束其数据源订阅的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 旗标</span></b> </p> </td> 
   <td colname="col2"> <p> <i>仅适用于CPM源</i>。旗标选项包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indicates a subscriber has reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indicates a subscriber has not reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [CPM数据源的结帐和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [付费数据馈送计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何报告CPM使用情况](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

