---
description: 本页概述了我们的合作伙伴直接提供的信息，以及与Audience Manager实践相关的任何含义。对作出这些更新的合作伙伴而言，关键的影响是GDPR(一般数据保护规定)的结果，该规定于2018年月25日生效，以及新的IAB GDPR透明度与同意框架(IAB Framework)。
seo-description: 本页概述了我们的合作伙伴直接提供的信息，以及与Audience Manager实践相关的任何含义。对作出这些更新的合作伙伴而言，关键的影响是GDPR(一般数据保护规定)的结果，该规定于2018年月25日生效，以及新的IAB GDPR透明度与同意框架(IAB Framework)。
seo-title: 目标的GDPR注意事项
solution: Audience Manager
title: 目标的GDPR注意事项
uuid: e8a40060-086c-4f03-b48 c-9c903 acb7891
translation-type: tm+mt
source-git-commit: 0ddc86391cbc751dfd4d46946222d555cefbfe38

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

本页概述了我们的合作伙伴直接提供的信息，以及与Audience Manager实践相关的任何含义。对作出这些更新的合作伙伴而言，关键的影响是GDPR(一般数据保护规定)的结果，该规定于2018年月25日生效，以及新的IAB GDPR透明度与同意框架(IAB Framework)。

Adobe合作伙伴拥有他们的业务流程，并且可以随时决定更新与Audience Manager的集成要求。我们积极与Audience Manager合作伙伴生态系统合作，以保持我们的客户精通更改。

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

如下表所列，一些合作伙伴已更改与Audience Manager的集成要求，以纳入基于IAB Framework的支持，以符合GDPR标准。

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>合作伙伴名称 </p> </th> 
   <th colname="col2" class="entry"> <p>期望影响 </p> </th> 
   <th colname="col3" class="entry"> <p>更改的状态 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Os/Datax </p> </td> 
   <td colname="col2"> <p>合作伙伴放弃欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>自2018年月22日起直播 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>贸易台 </p> </td> 
   <td colname="col2"> <p>合作伙伴放弃欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未实时 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>合作伙伴放弃欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未实时 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveMP </p> </td> 
   <td colname="col2"> <p>合作伙伴放弃欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未实时 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. 他们的参数告知Yahoo/Os/Datax，他们有权将特定区段作为数据处理者或数据管理者处理。因此，向Yahoo/Os/Datax目标发送细分的Audience Manager客户必须根据与Oath的协议指定适当的参数(处理器或控制器)。

请联系您的顾问或Client Care以设置正确的参数。除非我们收到书面信函，否则Adobe无法代表客户进行此更新，除非我们收到此更新。请联系Yahoo/Os/Datax代表以了解这些参数的完整定义。

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

为了帮助我们的客户自动执行GDPR请求，Audience Manager向我们的激活合作伙伴发送了取消数据主体请求(或删除区段)信息的通知。

但是，我们的一些激活合作伙伴：

1. 不能支持来自Adobe和/或
1. 30天内不能频繁接收我们的更新。

在这些情况下，您无法通过Audience Manager以自动化方式向激活合作伙伴发送删除请求。Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-March2019.xlsx) to see which Audience Manager activation partners support unsegment.
