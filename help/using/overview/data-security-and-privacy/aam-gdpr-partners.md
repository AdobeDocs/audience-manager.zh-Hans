---
description: 本页概述了合作伙伴在信息可用时直接提供的信息，以及与您的Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴来说，关键影响在于2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度与同意框架（IAB框架）。
seo-description: 本页概述了合作伙伴在信息可用时直接提供的信息，以及与您的Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴来说，关键影响在于2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度与同意框架（IAB框架）。
seo-title: 目的地的GDPR考虑事项
solution: Audience Manager
title: 目的地的GDPR考虑事项
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# 目的地的GDPR考虑事项{#gdpr-considerations-for-destinations}

本页概述了合作伙伴在信息可用时直接提供的信息，以及与您的Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴来说，关键影响在于2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度与同意框架（IAB框架）。

Adobe合作伙伴拥有其业务流程，并可能决定不时更新其与Audience Manager的集成要求。 我们积极与Audience Manager伙伴生态系统合作，令客户获悉变化。

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

## Audience Manager用户界面更新- Yahoo/Aoth/DataX集成 {#ui-update}

除了上述对IAB框架的更新，Yahoo/Oath/DataX还为其分类和受众API **添加了****新参数gdpr和** gdpr_mode。 其参数告知Yahoo/Oath/DataX他们有权作为数据处理者或作为数据管理者处理特定段。 因此，将Audience Manager段发送到Yahoo/Oath/DataX目标的客户必须根据他们与Aoth的协议指定相应的参数（处理器或控制器）。

请联系您的顾问或客户服务中心以设置正确的参数。 除非我们收到请求此更新的书面通信，否则Adobe不能代表客户进行此更新。 请联系您的Yahoo/Oath/DataX代表，了解这些参数的完整定义。
