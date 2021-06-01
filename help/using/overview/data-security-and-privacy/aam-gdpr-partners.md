---
description: 本页概述由我们的合作伙伴在发布更新信息之后直接向我们提供的相关信息，以及这些更新对 Audience Manager 实践所造成的影响。合作伙伴之所以进行这些更新，主要是因为 2018 年 5 月 25 日生效的 GDPR（《通用数据保护条例》）和最新采用的 IAB GDPR 透明度与同意框架（简称“IAB 框架”）。
seo-description: 本页概述由我们的合作伙伴在发布更新信息之后直接向我们提供的相关信息，以及这些更新对 Audience Manager 实践所造成的影响。合作伙伴之所以进行这些更新，主要是因为 2018 年 5 月 25 日生效的 GDPR（《通用数据保护条例》）和最新采用的 IAB GDPR 透明度与同意框架（简称“IAB 框架”）。
seo-title: 与目标相关的 GDPR 注意事项
solution: Audience Manager
title: 与目标相关的 GDPR 注意事项
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: 数据管理和隐私
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 96%

---

# 与目标相关的 GDPR 注意事项{#gdpr-considerations-for-destinations}

本页概述由我们的合作伙伴在发布更新信息之后直接向我们提供的相关信息，以及这些更新对 Audience Manager 实践所造成的影响。合作伙伴之所以进行这些更新，主要是因为 2018 年 5 月 25 日生效的 GDPR（《通用数据保护条例》）和最新采用的 IAB GDPR 透明度与同意框架（简称“IAB 框架”）。

Adobe 合作伙伴拥有自己的业务流程，并可能会决定不时地更新与 Audience Manager 的集成需求。为此，我们一直积极与 Audience Manager 合作伙伴生态系统合作，以便让客户了解所发生的变化。

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Audience Manager用户界面更新 — Yahoo/Oath/DataX集成{#ui-update}

除了上述 IAB 框架更新之外，Yahoo/Oath/DataX 还向其分类和受众 API 中添加了两个新参数，即 **gdpr** 和 **gdpr_mode**。这两个参数可告知 Yahoo/Oath/DataX 他们有权作为数据处理者或数据控制者处理特定区段。因此，Audience Manager 客户在将区段发送到 Yahoo/Oath/DataX 目标时，必须根据其与 Oath 的协议指定相应的参数（处理者或控制者）。

请联系您的顾问或客户关怀团队以设置正确的参数。除非收到请求进行此更新的书面信函，否则 Adobe 不能代表客户进行此更新。请联系您的 Yahoo/Oath/DataX 代表，了解这两个参数的完整定义。
